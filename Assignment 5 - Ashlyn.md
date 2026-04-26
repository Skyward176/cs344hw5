## Q2
Graph $G$:
$$\begin{align}
s: a (-1), t(0) \\
a: b(-1) \\
b: t(1)
\end{align}$$
Graph $G'$:
$$\begin{align}
s': a'(0), t'(1) \\
a': b'(0) \\
b': t(2)
\end{align}$$
Dijkstra's Algorithm on $G'$:
$sa, ab, st, bt$

| Vertex | Weight (Previous) |
| ------ | ----------------- |
| $s'$   | $0$               |
| $a'$   | $0 (s')$          |
| $b'$   | $0(a')$           |
| $t'$   | $1(s')$           |
The algorithm then checks $bt$, which gives a worse path ($2$) than the existing path.

The actual shortest distance from $s$ to $t$ in $G$ is $s,a,b,t$, with a weight of $-1$. The algorithm returns $st$, which has a weight of $0$ in $G$. This fails, because by adding $1$ to every edge, the algorithm is adding $l$ to each path, where $l$ is the length of the path. This causes a bias for shorter paths, which might not be the fastest.