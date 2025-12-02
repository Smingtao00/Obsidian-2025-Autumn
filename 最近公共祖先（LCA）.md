#LCA

## 定义

最近公共祖先简称 LCA（Lowest Common Ancestor）。两个节点的最近公共祖先，就是这两个点的公共祖先里面，离根最远的那个。为了方便，我们记某点集 $S = \{v_1, v_2, \dots, v_n\}$ 的最近公共祖先为 $LCA(v_1, v_2, \dots, v_n)$ 或 $LCA(S)$。

## 性质

1. $LCA(\{u\}) = u$
2. $u$ 是 $v$ 的祖先，当且仅当 $LCA(u,v) = u$
3. 如果 $u$ 不为 $v$ 祖先并且 $v$ 不为 $u$ 的祖先，那么 $u,v$ 分别处于 $LCA(u, v)$ 的两颗不同子树中
4. 前序遍历中，$LCA(S)$ 出现在所有 $S$ 中元素之前，后序遍历中 $LCA(S)$ 则出现在所有 $S$ 中元素之后
5. 两点集并的最近公共祖先为两点集分别的最近公共祖先的最近公共祖先，即 $LCA(A \cup B) = LCA(LCA(A), LCA(B))$
6. 两点的最近公共祖先必定处在树上两点间的最短路上
7. $d(u, v) = h(u) + h(v) - 2h(LCA(u, v))$，其中 $d$ 是树上两点间的距离， $h$ 代表某点到树根的距离

## 求法

### 朴素算法

#### 过程
可以每次找深度比较大的那个点，让它向上跳。显然在树上，这两个点最后一定会相遇，相遇的位置就是想要求的 LCA。或者先向上调整深度较大的点，令他们深度相同，然后再共同向上跳转，最后也一定会相遇。

#### 性质
朴素算法预处理时需要 dfs 整棵树，时间复杂度为 $O(n)$，单词查询时间复杂度为 $\Theta(n)$。如果树满足随机性质，则时间复杂度于这种随机树的期望高度有关。

### 倍增算法

#### 过程
倍增算法是最经典的 LCA 求法，是朴素算法的改进算法。通过预处理 $fa_{x,i}$ 数组，游标可以快速移动，大幅减少了游标的跳转次数。$fa_{x,i}$ 表示点 $x$ 的第 $2^i$ 个祖先。$fa_{x,i}$ 数组可以通过 dfs 预处理出来。

现在我们看看如何优化这些跳转： 在调整游标的第一阶段中，我们要将 $u,v$ 两点跳转到同一深度。我们可以计算出 $u,v$ 两点的深度之差，设为 $y$。通过将 $y$ 进行二进制拆分，我们将 $y$ 次跳转优化为 **y 的二进制表示中 `1`  的个数** 次跳转。在第二阶段中，我们从最大的 $i$ 开始循环尝试，一直尝试到 0（包括 0 ），如果 $fa_{u, i} \neq fa_{v, i}$，则 $u \leftarrow fa_{u, i}, v \leftarrow fa_{v, i}$，那么最后的 LCA 为 $fa_{u, 0}$ 。

#### 性质
倍增算法的预处理时间复杂度为 $O(n logn)$，单次查询时间复杂度为 $O(logn)$。另外倍增算法可以通过交换 `fa` 数组的两维使较小维放在前面，这样可以减少 cache miss 次数，提高程序效率。

#### 实现
1. 存储一棵树
2. 获取树各结点的深度（DFS）
3. 获取2次幂祖先的结点，用 `fa[][]` 数组存储
4. 用倍增法查询LCA

```c++ {.line-numbers}
#include <bits/stdc++.h>
using namespace std;

const int N = 5e6 + 10;
const int MAX_LEVEL = 20;
struct node {
	int to, nex;
}e[N<<1];
int dep[N], fa[22][N], head[N], cnt;

void add(int a, int b) {
	e[++cnt].to = b;
	e[cnt].nex = head[a];
	head[a] = cnt;
}

//dfs 初始化fa和dep
void dfs(int cur, int father) {
	dep[cur] = dep[father] + 1;
	fa[0][cur] = father;
	for (int i = 1; (1 << i) <= dep[cur]; i++) {
		fa[i][cur] = fa[i - 1][fa[i - 1][cur]];
	}
	for (int i = head[cur]; i; i = e[i].nex) {
		int v = e[i].to;
		if (v == father) continue;
		dfs(v, cur);
	}
}

int lca(int u, int v) {
	if (dep[u] < dep[v]) swap(u, v);
	for (int k = MAX_LEVEL; k >= 0; --k) {
		if (dep[u] - (1 << k) >= dep[v]) {
			u = fa[k][u];
		}
	}
	if (u == v) return u;
	for (int k = MAX_LEVEL - 1; k >= 0; --k) {
		if (dep[fa[k][u]] <= 0) continue;
		if (fa[k][u] == fa[k][v]) continue;
		u = fa[k][u], v = fa[k][v];
	}
	return fa[0][u];
}

void solve() {
	int n, m, s;
	cin >> n >> m >> s;
	for (int i = 0; i < n; i++) {
		int a, b;
		cin >> a >> b;
		add(a, b);
		add(b, a);
	}
	dfs(s, 0);
	while(m--) {
		int u, v;
		cin >> u >> v;
		cout << lca(u, v) << endl;
	}
}

int main()
{
	ios::sync_with_stdio(false);
	cin.tie(0);
	int _;
	cin >> _;
	while(_--) solve();
	return 0;
}
```


### Tarjan 算法

Tarjan 算法是一种 **离线算法**，需要使用 [[并查集]] 记录某个结点的祖先结点。做法如下：
1. 首先接受输入边（邻接链表）、查询边（存储在另一个邻接链表内）。查询边其实是虚拟加上去的边，为了方便，每次输入查询边的时候，将这个边及其反向边都加入到 `queryEdge` 数组里。
2. 然后对其进行一次 DFS 遍历，同时使用 `visited` 数组进行记录某个结点是否被访问过，`parent` 记录当前结点的父亲结点。
3. 其中涉及到了 **回溯思想**，我们每次遍历到某个结点的时候，认为这个结点的根结点就是它本身。让以这个结点为根结点的 DFS 全部遍历完毕以后，再将这个结点的根节点设置为这个结点的父一级结点。
4. 回溯的时候，如果以该结点为起点，`queryEdge` 查询边的另一个结点也恰好访问过了，则直接更新查询边的 LCA 结果。
5. 最后输出结果。

#### 性质
Tarjan 算法需要初始化并查集，所以预处理时间复杂度为 $O(n)$。
朴素的 Tarjan 算法处理所有 $m$ 次询问的时间复杂度为 $O(m\alpha(m + n, n) + n)$，但是 Tarjan 算法的常熟比倍增算法大。存在 $O(m + n)$ 的实现。

### 用欧拉序列转化为 RMQ 问题
[[RMQ问题]]
[[欧拉序列]]

### 树链剖分

[[树链剖分]]
LCA 为两个游标跳转到同一条重链上时深度较小的那个游标所指向的点。

树链剖分的预处理时间复杂度为 $O(n)$，单词查询的时间复杂度为 $O(logn)$，并且常数较小。
