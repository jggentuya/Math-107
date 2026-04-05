---
subject: Math 107
BookTitle:
  - Chartrand, G., et al. (201i8). Mathematical proofs (4th ed.). Pearson Education.
BookSection:
  - (Math 107 CHA4e 11) Cardinalities of Sets
page: 287
AlsoSolvedBy:
  - JGG_2026
category: instructor
statementType: exercise
Source:
AnswerBook:
SolvedOn: 2026-04-01T15:51:00
DateEncoded: 2026-04-01T15:51:00
LastModified: 2026-04-02T07:55:00
aliases:
status: DONE
---
# CHA 11.03

Prove that if $A$ and $B$ are disjoint denumerable sets, then $A\cup B$ is denumerable.

---

## Idea

Since $A$ and $B$ are both denumerable, we can express them as
$$
\begin{align*}
A & = \{a_1, a_2, a_3, \ldots\}, \\
B & = \{b_1, b_2, b_3, \ldots\}.
\end{align*}
$$

Since $A$ and $B$ are disjoint, we can list the elements of $A \cup B$ by alternating the elements of $A$ and $B$ as follows:
$$
A \cup B = \{a_1, b_1, a_2, b_2, a_3, b_3, \ldots\}
$$

The function $h:\mathbb{N}\to A\cup B$ defined by
$$
h(n) := \begin{cases}
a_{\frac{n+1}{2}} & \text{if $n$ is odd}, \\
b_{\frac{n}{2}} & \text{if $n$ is even}
\end{cases}
$$

is bijective by construction, and thus $A \cup B$ is denumerable. $\blacktriangle$

---

## Proof

Let $A$ and $B$ be disjoint denumerable sets. Then, there exist bijections $f:\mathbb{N}\to A$ and $g:\mathbb{N}\to B$. Define a function $h:\mathbb{N}\to A\cup B$ by
$$
h(n) := \begin{cases}
f\left(\frac{n+1}{2}\right) & \text{if $n$ is odd}, \\
g\left(\frac{n}{2}\right) & \text{if $n$ is even}.
\end{cases}
$$

It is enough to show that $h$ is a bijection.

(One-to-one) Assume $h(n)=h(m)$ for some $n,m\in\mathbb{N}$. We claim that $n$ and $m$ have the same parity.

Indeed, suppose $n$ and $m$ have different parity. WLOG, we may assume that $n$ is odd and $m$ is even. (The case where $n$ is even and $m$ is odd can be handled similarly.) Then,
$$
f\left(\frac{n+1}{2}\right)=h(n)=h(m)=g\left(\frac{m}{2}\right)
$$

Since $f$ and $g$ are onto, it follows that $\text{im}(f)=A$ and $\text{im}(g)=B$, and so $f\left(\frac{n+1}{2}\right)\in A$ and $g\left(\frac{m}{2}\right)\in B$. But $A$ and $B$ are disjoint, so $f\left(\frac{n+1}{2}\right)$ and $g\left(\frac{m}{2}\right)$ cannot be equal, which is absurd. This proves the claim that $n$ and $m$ have the same parity.

Now we have two cases:

**Case 1:** Both $n$ and $m$ are odd. Then $f\left(\frac{n+1}{2}\right)=f\left(\frac{m+1}{2}\right)$. Since $f$ is injective, $\frac{n+1}{2}=\frac{m+1}{2}$, so $n=m$.

**Case 2:** Both $n$ and $m$ are even. Then $g\left(\frac{n}{2}\right)=g\left(\frac{m}{2}\right)$. Since $g$ is injective, $\frac{n}{2}=\frac{m}{2}$, so $n=m$.

Thus, each of the cases leads to having $n=m$, and so $h$ is injective.

(Onto) Let $\omega\in A\cup B$.Then $\omega\in A$ or $\omega\in B$.  We need to show that there exists $p\in\mathbb{N}$ such that $h(p)=\omega$. We have two cases:

**Case 1:** $\omega\in A$. Then there exists $k\in\mathbb{N}$ such that $f(k)=\omega$ since $f$ is surjective. We choose $p:=2k-1$ and observe that
    $$
    h(p)=f\left(\frac{p+1}{2}\right)=f(k)=\omega.
    $$

**Case 2:** $\omega\in B$. Then there exists $k\in\mathbb{N}$ such that $g(k)=\omega$ since $g$ is surjective. We choose $p:=2k$ and observe that
    $$
    h(p)=g\left(\frac{p}{2}\right)=g(k)=\omega.
    $$

Thus, each of the cases leads to the existence of $p\in\mathbb{N}$ such that $h(p)=\omega$, and so $h$ is surjective.

---

Therefore, $h$ is bijective, which implies $A\cup B$ is denumerable. $\blacksquare$
