### The hide-and-seek algorithm
---
Throughout the text, let $\mathcal{H}$ be an Euclidean space.

Let $f:\mathcal{H}\rightarrow\mathbb{R}$ be a continuous real function and $C$ be a compact subset of $\mathcal{H}$. The problem consists in to find a [[11.2 minimizers|minimizer]] of $f$ on $C$. If we assume that $f$ is lower semicontinuous, then according to the [[1.10 lower semicontinuity|Weierstrass Theorem]], $f$ attains its minimum over $C$.

Let $g:\mathcal{H}\rightarrow\mathbb{R}_+$ a Lebesgue density defined by (see Lemma 12.1.11 [[schmidt, 2011]]):
$$g_T(x)\doteq\frac{\exp(f(x)/T)}{\int_C\exp(f(z)/T)~d\mathbf{\lambda}(z)},$$
where $\lambda$ is the Lebesgue measure defined on $\mathcal{B}(\mathcal{H})$.

>[!proposition]
>Let $Q_T:\mathcal{B}(\mathcal{H})\rightarrow[0,1]$ be the corresponding distribution of the Lebesgue density $g_T$. Let $\epsilon>0$ and $C_{\epsilon}\doteq~\text{lev}_{\epsilon\leq 0}~(f-\min f(C))$. Then $Q_T(C_{\epsilon})\rightarrow 1$ as $T\rightarrow 0$ for all $\epsilon>0$.

 For any set $C\subset\mathcal{H}$ with positive Lebesgue measure we define a (multivariate) uniform cumulate distribution function (cdf) on $C$ denoted by $\textbf{U}(C)$. Let $x\in\mathcal{H}$ be a value of a random variable $\tilde{x}:\mathcal{H}\rightarrow\mathbb{R}$ with cdf $\textbf{U}(C)$. When the value $u$ is chosen randomly from the variable $\tilde{x}$ with cdf $\textbf{U}(C)$, we simply write $x\sim \textbf{U}(C)$.
 
 Let $F_{a,b}$ be the distribution function over the set $\Lambda\doteq\{\lambda\in\mathbb{R}:a+\lambda(b-a)/|b-a|\in C\}$, where $a,b\in\mathcal{H}$ and $a\neq b$. Let $T>0$ be the classically called *temperature parameter*.  Let $\beta:\mathcal{H}\times\mathcal{H}\rightarrow [0,1]:(x,y)\mapsto\min\{1,\exp~(f(y)-f(x))/T\}$ be the *acceptance probability function*. 
 
 The algorithm schema is the following:

1. Choose $x\in C$
2. Obtain a sequence $\{u_n\}_{n\in\mathbb{N}}$  of vectors of $\mathcal{H}$ from iid (independently identically distributed) random vectors $u_n\sim \textbf{U}(\text{bdry}~B_1)$. 
3. Obtain a sequence $\{\alpha_n\}_{n\in\mathbb{N}}$  of real numbers from iid (independently identically distributed) random variables $\alpha_n\sim \textbf{U}([0,1])$.
4. Obtain a sequence $\{\alpha_n'\}_{n\in\mathbb{N}}$  of real numbers from iid (independently identically distributed) random variables $\alpha_n'\sim \textbf{U}([0,1])$.
5. Obtain the sequence $\{\lambda_n\}_{n\in\mathbb{N}}$ of real numbers such that $\lambda_n\doteq F^{-1}_{x_n,x_n+u_n}(\alpha_n)$.
6. Compute $y_n\doteq x_n+\lambda_n u_n$ and  set $$(\forall n\in\mathbb{N})~x_{n+1}\doteq\begin{cases}y_n, & \text{if}~ \alpha'_n\in~[0,\beta_T(x_n,y_n)]\\x_n, & \text{if}~\alpha'_n\in~]\beta_T(x_n,y_n),1]\end{cases}~~~\text{and}~x_0\doteq x.$$
 
### The pseudocode
---
