**(1 page)**
[[_jean luc structure#^need| need]]

> [!summary section]
> En esta sección desarrollamos los notación matemática preliminar, planteamos el teorema de viabilidad y describimos el algoritmo de viabilidad fundamental. 

> [!mathematical preliminars]
[[_l24 mathematical preliminars]] In all the article we consider $\mathcal{H}$ an Euclidean space with inner product $\langle\cdot |\cdot\rangle$ and induced norm $\|\cdot\|$. Let $T\in\mathbb{R}_{++}$, define the set-valued mapping as $\varphi:\mathcal{H}\rightarrow 2^{\mathcal{H}}$,  we say that the function $x:[0,T]\rightarrow\mathcal{H}$ is a solution of the differential inclusion $\dot{u}\in\varphi u$ if $x$ is absolutely continuous and $\dot{u}\in\varphi u$. Let $\epsilon>0$, $\overline{B}_{\epsilon}(0)$ denotes the closed ball in $\mathcal{H}$ with centre $0$ and radius $\epsilon$. We say that a set-valued mapping is *upper-semi continuous* (usc) if
$$(\forall x\in\mathcal{H})(\forall\epsilon>0)(\exists\delta>0)(\forall y\in \overline{B}_{\delta}(0))~\varphi y\subset\varphi x+\overline{B}_{\epsilon}(0).$$
 
> [!definition of viable system]
> In addition, we say that the pair $(C, \varphi)$ is a *viable system* if for any $x_0\in C$ there exists a solution $x$ on $[0,T]$ of  $\dot{u}\in\varphi u$ such that $x(0)=x_0$ and $x(t)\in C$ for almost all $t\in[0,T]$. The following theorem, the viability theorem, characterizes the viable systems: 

> [!viability Theorem]
> (See i.e., [Deimling 92, p. 53](https://app.readcube.com/library/93459b1e-6692-4206-aac2-638bc86c8329/item/ed3d4b60-e4e0-4c9c-bd4a-c135f27a6ae0) or [Clarke 95, p.193](https://app.readcube.com/library/93459b1e-6692-4206-aac2-638bc86c8329/item/9b382bf0-d900-4643-9aa0-6ce680ca456d)) Let $C$ be a nonempty closed subset of $\mathcal{H}$, $\varphi:C\rightarrow 2^{\mathcal{H}}$ an usc set valued mapping with nonempty compact convex values. The following assertions are equivalent:
> (i) The system $(C, \varphi)$ is viable.
> (ii) For any $x\in C$ there exists $y\in C$ such that $y-x\in\varphi y$.

> [!comments of the viability algorithm]
>The important equivalence of viability is a tangential condition, which we did not present here. However, it is not difficult to see that viability (i) is equivalent to a local viability (ii), what we used here (see for example [Clarke 95, p 194](https://app.readcube.com/library/93459b1e-6692-4206-aac2-638bc86c8329/item/9b382bf0-d900-4643-9aa0-6ce680ca456d), which we posed in its implicit version).

> [!definition of viability kernel]
In case that the system $(C, \varphi)$ were not a viable itself, we try to find the greatest subset of $C$, say $\text{Viab}_{\varphi}(C)$, such that the system $(\text{Viab}_{\varphi}(C), \varphi)$ is viable. We call $\text{Viab}_{\varphi}(C)$ the *viability kernel* of the set $C$ under $\varphi$. Thus, given a system $(C, \varphi)$, the viability kernel can be computed according to the following proposition (see [Laengle 24](https://app.readcube.com/library/93459b1e-6692-4206-aac2-638bc86c8329/item/d737323f-1403-4f8c-b64c-d0932c791711) for the proof, which is the version implicit of the Proposition 2.1 of [Saint-Pierre 94](https://app.readcube.com/library/93459b1e-6692-4206-aac2-638bc86c8329/item/d737323f-1403-4f8c-b64c-d0932c791711)):

 > [!Viability algorithm]
> Let $C$ be a nonempty closed subset of $\mathcal{H}$, $\varphi$ an usc set-valued mapping with nonempty compact convex values. We define recursively the family of sets $\{C_n\}_{n\in\mathbb{N}}$ as 
> $$(\forall n\in\mathbb{N})~C_{n+1}\doteq(\text{Id}-\varphi)(C_n)\cap C_n\text{ and }C_0\doteq C,$$ then $\text{Viab}_{\varphi}(C)=\cap_{n\in\mathbb{N}}C_n$.



[[_jean luc structure#^task| task]]

> [!operations needed for the viability algorithm]
> The above proposition shows the operations between sets that we need for computing the viability kernel. Operation by the operator $\text{Id}-\varphi$ and the set intersections are obviously necessary. More operations can be deduced from the operator $\text{Id}-\varphi$, which in any case is defined by $(\text{Id}-\varphi)(C)\doteq\cup_{x\in C}(\text{Id}-\varphi)(x)$ for any nonempty subset $C$. It is clear that, depending on the definition of the set-valued operator $\varphi$, we will additionally need the union and Minkoswki sum of sets.

> [!set representations]
> An analysis quite exhaustive of sets representation was recently presented in [Althoff 2023, p. 280](https://app.readcube.com/library/93459b1e-6692-4206-aac2-638bc86c8329/item/459c045b-6e1c-4dd1-a4d9-38a13c4997e1). The representations are grouped in two main categories: convex an nonconvex. Between the convex representations we have ([polytope-wiki](https://en.wikipedia.org/wiki/Polytope)) (convex) polytopes, ellipsoids, support functions, and zonotopes. Support functions are generalization of polytopes and ellipsoids. Special types of polytopes are the zonotopes and intervals. The group of nonconvex representations consists on polynomial and constrained polynomial zonotopes (both generalizations of zonotopes) and level sets, which can represent any nonconvex set.

> [!level set representation]
> We adopt the level set representation, which, as we said previously, can represent any set, however most likely at the cost of data storage volume, processing time, and error propagation. In the next section we will solve a simple problem to understand this problem.