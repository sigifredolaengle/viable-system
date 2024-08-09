
## preliminaries
---
In all the article we consider $\mathcal{H}$ an Euclidean space with inner product $\langle\cdot |\cdot\rangle$ and induced norm $\|\cdot\|$. Let $T\in\mathbb{R}_{++}$, define the set-valued mapping as $\varphi:\mathcal{H}\rightarrow 2^{\mathcal{H}}$,  we say that the function $x:[0,T]\rightarrow\mathcal{H}$ is a solution of the differential inclusion $\dot{x}\in\varphi x$ if $x$ is absolutely continuous and $\dot{x}\in\varphi x$. Let $\epsilon>0$, $\overline{B}_{\epsilon}(0)$ denotes the closed ball in $\mathcal{H}$ with centre $0$ and radius $\epsilon$. We say that a set-valued mapping is *upper-semi continuous* (usc) if
$$(\forall u\in\mathcal{H})(\forall\epsilon>0)(\exists\delta>0)(\forall v\in \overline{B}_{\delta}(0))~\varphi v\subset\varphi u+\overline{B}_{\epsilon}(0).$$
 >[!definition] viable system
> We say that the pair $(C, \varphi)$ is a *viable system* if for any $u\in C$ there exists a solution $x$ on $[0,T]$ of  $\dot{x}\in\varphi x$ such that $x(0)=u$ and $x(t)\in C$ for almost all $t\in[0,T]$. The following theorem, the viability theorem, characterizes the viable systems: 

> [!theorem] Viability Theorem
> (See i.e., [Deimling 92, p. 53](https://app.readcube.com/library/93459b1e-6692-4206-aac2-638bc86c8329/item/ed3d4b60-e4e0-4c9c-bd4a-c135f27a6ae0) or [Clarke 95, p.193](https://app.readcube.com/library/93459b1e-6692-4206-aac2-638bc86c8329/item/9b382bf0-d900-4643-9aa0-6ce680ca456d)) Let $C$ be a nonempty closed subset of $\mathcal{H}$, $\varphi:C\rightarrow 2^{\mathcal{H}}$ an usc set valued mapping with nonempty compact convex values. The following assertions are equivalent:
> (i) The system $(C, \varphi)$ is viable.
> (ii) For any $u\in C$ there exists $v\in C$ such that $v-u\in\varphi v$.

The important equivalence of viability is a tangential condition, which we did not present here. However, it is not difficult to see that viability (i) is equivalent to a local viability (ii). We will use here the local viability characterisation (see for example [Clarke 95, p 194](https://app.readcube.com/library/93459b1e-6692-4206-aac2-638bc86c8329/item/9b382bf0-d900-4643-9aa0-6ce680ca456d), which we posed in its implicit version).

> [!definition] Viability kernel
In case that the system $(C, \varphi)$ were not a viable itself, we try to find the greatest subset of $C$, say $\text{Viab}_{\varphi}(C)$, such that the system $(\text{Viab}_{\varphi}(C), \varphi)$ is viable. We call $\text{Viab}_{\varphi}(C)$ the *viability kernel* of the set $C$ under $\varphi$. Thus, given a system $(C, \varphi)$, the viability kernel can be computed according to the following proposition (see [Laengle 24](https://app.readcube.com/library/93459b1e-6692-4206-aac2-638bc86c8329/item/d737323f-1403-4f8c-b64c-d0932c791711) for the proof, which is the version implicit of the Proposition 2.1 of [Saint-Pierre 94](https://app.readcube.com/library/93459b1e-6692-4206-aac2-638bc86c8329/item/d737323f-1403-4f8c-b64c-d0932c791711)):

## algorithm theory
---
In the following we present an adaptation of the paper [bonneuil, 2006](https://app.readcube.com/library/93459b1e-6692-4206-aac2-638bc86c8329/item/0f76012e-5cae-4340-96af-472d585f0191):

Bonneuil, N. Computing the viability kernel in large state dimension. _J Math Anal Appl_ **323**, 1444–1454 (2006).
	
Fix $T\in\mathbb{R}_{++}$ a time space value. Let $u\in C$, and the set-valued mapping 
$$\mathcal{S}_{\varphi}:C\rightarrow W^{1,1}([0,T];\mathcal{H}):u\mapsto \left\{x\in W^{1,1}([0,T]):\dot{x}\in\varphi x~\text{and}~x(0)\doteq u\right\},$$
i.e., given $u\in C$, $\mathcal{S}_{\varphi}(u)$ is the set of solutions of the differential inclusion $\dot{x}\in\varphi x$ such that $x(0)\doteq u$. If $u\in\mathcal{H}\setminus C$, then $\mathcal{S}_{\varphi}(u)\doteq\emptyset$. Let $\xi\in\mathbb{R}$, let us represent the set $C$ by the lower level set of a function $h:\mathcal{H}\rightarrow]-\infty,\infty]$, such that
$$C=\{u\in\mathcal{H}:h(u)\leq\xi\}.$$
Finally, define the following *cost function* 
$$c_T:\mathcal{H}\rightarrow]-\infty,\infty]:u\mapsto\inf_{x\in\mathcal{S}_{\varphi}(u)}\sup_{t\in[0,T]}h(x(t)).$$

>[!lemma]
>Let $(C,\varphi)$ a viable system, where $C$ is represented by the lower set of a function $h$. Let us define the cost function $c_T:\mathcal{H}\rightarrow]-\infty,\infty]:u\mapsto\inf_{x\in\mathcal{S}_{\varphi}(u)}\sup_{t\in[0,T]}h(x(t))$. Let $u\in\mathcal{H}$. Then 
>$$u\in\text{Viab}_{\varphi}(C)~\leftrightarrow~ c_T(u)\leq 0.$$

>[!theorem] Bonneuil, 2006, p. 1447
>Let $C$ be a nonempty subset of $\mathcal{H}$ represented by the lower set of a function $h$. Assume that $\varphi:\mathcal{H}\rightarrow 2^{\mathcal{H}}$ is $\lambda-$Lipschitz continuous on $\mathcal{H}$ and $h$ is $l-$Lipschitz continuous on $\mathcal{H}$. Then
>$$(\forall u\in\mathcal{H})(\forall v\in\mathcal{H})~c_T(u)\leq c_T(v)+l e^{\lambda T}\|u-v\|.$$

>[!corollary]
>Let $C$ be a nonempty closed subset of $\mathcal{H}$ represented by the $0$-lower set of a function $h$. Assume that $\varphi:\mathcal{H}\rightarrow 2^{\mathcal{H}}$ is a set-valued mapping with nonempty closed convex values. Additionally, $\varphi$ is $\lambda-$Lipschitz continuous on $\mathcal{H}$ and $h$ is $l-$Lipschitz continuous on $\mathcal{H}$. Then
>**(i)** Given $u\in \text{Viab}_{\varphi}(C)$, determine states close to $u$ that are viable:
>$$(\forall u\in\text{Viab}_{\varphi}(C))~\{v\in C:le^{\lambda T}\|v-u\|\leq-c_T(u)\}\subset\text{Viab}_{\varphi}(C).$$
>**(ii)** Given $u\in \text{Viab}_{\varphi}(C)$ and $v\in C$, determine a bound for $c_T(v)$, i.e.,
>$$(\forall u\in\text{Viab}_{\varphi}(C))(\forall v\in C)~c_T(v)\leq le^{\lambda T}\|v-u\|.$$
>**(iii)** The closer a state $v\in C$ to the viability kernel, the smaller $c_T(v)$, i.e.,
>$$(\forall v\in C)~c_T(v)\leq le^{\lambda T}d(v,\text{Viab}_{\varphi}(C)).$$

The theorem of semi-permeability says that having located a state  u “close enough” to the viability boundary, the part of the evolution located in the interior of $C$ (from $u$ to the first encounter of the solution  with $\text{bdry}~C$) travels close to the viability boundary, without entering into the viability kernel. Formally,

>[!theorem] Semi-permeability property
>Let $C$ be a nonempty closed subset of , $\varphi:C\rightarrow 2~^\mathcal{H}$ an usc set valued mapping with nonempty compact convex values. Then for all $u\in\text{bdry}~\text{Viab}_{\varphi}(C)\setminus\text{bdry}~C$ there exist a solution $x\in\mathcal{S}_{\varphi}(u)$ and $\tau>0$ such that
>**(i)** $(\forall t\in[0,\tau])~x(t)\in\text{bdry}~\text{Viab}_{\varphi}(C)$, and
>**(ii)** $x(\tau)\in\text{Viab}_{\varphi}(C)\cap\text{bdry~C}$.


```image-layout
---
layout: carousel
carouselShowThumbnails: true
---
![[DFOG method.jpeg]]
![[DFOG method 2.jpeg]]
![[Bonneuil, 2006.jpeg]]
![[Bonneuil, 2007.jpeg]]
```

The algorithm at high level is the following. 

Let $C$ be a nonempty subset of $\mathcal{H}$ represented by the lower set of a function $h$. Assume that $\varphi:\mathcal{H}\rightarrow 2^{\mathcal{H}}$ is $\lambda-$Lipschitz continuous on $\mathcal{H}$ and $h$ is $l-$Lipschitz continuous on $\mathcal{H}$.  Let $u\in C$ and define 
$$D_u\doteq\{v\in C:le^{\lambda T}\|v-u\|\leq-c_T(u)\}.$$
Let us observe that, according to Corollary 1.6, if $u\in\text{Viab}_{\varphi}(C)$ then $D_u\subset\text{Viab}_{\varphi}(C)$. Thus, the algorithm is designed with the following steps:

1. Find $u\in\text{Viab}_{\varphi}(C)$ 
2. Assign $V\doteq\{u\}$.
3. For all $t\in[0,T]$
	1. Compute $D_{x(t)}$, where $x$ is the solution of the optimization problem $c_T(u)=\inf_{x\in\mathcal{S}_{\varphi}(u)}\sup_{t\in[0,T]}~h(x(t))$ and assign $V\doteq V\cup D_{x(t)}$.
	2. For all $v\in D_{x(t)}$ go to 2. with $u\doteq v$.
4. Return $\text{Viab}_{\varphi}(C)=V$.