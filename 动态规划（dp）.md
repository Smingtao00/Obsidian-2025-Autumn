能用动态规划解决的问题，要满足三个条件：最优子结构，后无效性，子问题重叠。

最长不下降子序列

> [!question] 最长不下降子序列问题  
> 给定一个长度为 $n$ 的序列 $a (n \leq 5000)$，求出一个最长的 $a$ 的子序列，满足该子序列的后一个元素不小于前一个元素。

维护数组 $d$，其中第 $x$ 位表示长度为 $x$ 的不下降子序列末尾元素的最小值。

```c++
int n, a[MAXN], d[MAXN], di[MAXN], pre[MAXN], res[MAXN];

int dp() {
	int ans = 0;
	for(int i = 1; i <= n; i++) {
		int tmp = std::upper_bound(d, d + ans, a[i]) - d;
		pre[i] = tmp ? di[tmp - 1] : -1;
		d[tmp] = a[i];
		di[tmp] = i;
		if (tmp == ans) ++ans;	
	}
	
	for(int k = ans, i = di[ans - 1]; k; --k) {
		res[k] = a[i];
		i = pre[i];	
	}
	return ans;
}
```