# Algorithm



## KMP



### next数组

1. next[] 的含义：x[i-next[i]...i-1]=x[0...next[i]-1]

2. next[i] 为满足 x[i-z...i-1]=x[0...z-1] 的最大 z 值（就是 x 的自身匹配）

```c++
void kmp_pre(char x[], int m, int next[]) {
	int i, j;
	j = next[0] = -1;
	i = 0;
	while(i < m) {
		while(-1! = j && x[i] != x[j]){
			j = next[j];
		}
		next[++i] = ++j;
	}
}
```



3. 对称不是中心对称，而是中心字符块对称，比如不是abccba，而是abcabc这种对称





### 红黑树

1.节点是红色或黑色。

2.根节点是黑色。

3.每个叶子节点都是黑色的空节点（NIL节点）。

4 每个红色节点的两个子节点都是黑色。(从每个叶子到根的所有路径上不能有两个连续的红色节点)

5.从任一节点到其每个叶子的所有路径都包含相同数目的黑色节点。