.. _day2:

***************************
Segon dia
***************************

Creixement dels coeficients
===========================

Més endavant ens interessarà tenir fites per l'ordre de creixement dels
coeficients de Fourier de les formes modulars.

**Proposició:** Si $f=E_k$, aleshores $a_n\approx n^{k-1}$. És a dir, que hi ha constants $A, B>0$ tals que
$$
An^{k-1}\leq \abs{a_n}\leq Bn^{k-1}.
$$

*Prova:* Tenim $\abs{a_n} = A \sigma_{k-1}(n)\geq An^{k-1}$. D'altra banda,
$$
\frac{\abs{a_n}}{n^{k-1}} = A \sum_{d\mid n} \frac{1}{d^{k-1}} \leq A\sum_{d=1}^\infty \frac{d^{k-1}} = A\zeta(k-1) < \infty.\quad\qed
$$

El creixement de les formes cuspidals és més lent:

**Teorema (Hecke):** Si $f$ és una forma cuspidal de pes $k$, llavors $a_n=O(n^{k/2})$.

*Prova:*
Primer de tot, com que $a_0=0$, podem escriure $f(z)=q\sum_{n\geq 1}a_nq^{n-1}$ i, per tant,
$$
\abs{f(z)} = O(q)=O(e^{-2\pi \Im(z)}),\quad q\to 0.
$$

Escrivim $z=x+iy$, i definim $\phi(z)=\abs{f(z)}y^{k/2}$. La modularitat de $f$ fa que la funció $C^\infty$ (no-holomorfa) $\phi$ sigui invariant per $\SL_2(\Z)$, i $\phi(z)\to 0$ quan $\Im(z)\to\infty$. Per tant, $\phi$ és fitada: hi ha alguna constant $M$ tal que
$$
\abs{f(z)}\leq My^{-k/2},\quad z\in \HH.
$$
Per com es calculen els coeficients de Fourier, tenim
$$
a_n =  \int_0^1 f(x+iy)e^{-2\pi i n(x+iy)}dx,
$$
i per tant
$$
\abs{a_n} \leq Me^{2\pi n y}\int_0^1 y^{-k/2} e^{-2\pi inx}dx = My^{-k/2}e^{2\pi i n y}.
$$
Aquesta igualtat és vàlida per tot $y>0$. En particular, per $y=1/n$ dona
$$
\abs{a_n}\leq e^{2\pi} M n^{k/2}.\qed
$$

**Corol·lari:** Si $f$ no és cuspidal, aleshores $a_n\approx n^{k-1}$.

*Prova:* Escrivim $f=\lambda E_k + h$ amb $\lambda\neq 0$ i $h$ cuspidal, i apliquem els resultats anteriors. Com que els coeficients d'$E_k$ creixen
molt més ràpid que els de $h$, el creixement de $f$ és igual que el d'$E_k$. $\qed$

La sèrie d'Eisenstein de pes 2
================================

Considerem la funció
$$
G_2(z) = \sum_{m=-\infty}^\infty \sum_{n=-\infty}^\infty \frac{1}{(mz+n)^2},
$$
on si $m=0$ hem d'ometre el terme $n=0$ (a partir d'ara això no ho direm). Podem separar el terme $m=0$ i obtenir:
$$
G_2(z) = 2\zeta(2) + 2\sum_{m\neq 0}\sum_{n\in\Z} \frac{1}{(mz+n)^2}.
$$
Igual que hem fet amb les series d'Eisenstein de pes $k\geq 4$, podem calcular els coeficients de Fourier de $G_2$, i obtenim
$$
G_2(z)= 2\zeta(2)  - 8\pi^2\sum_{n=1}^\infty \sigma_1(n)q^n.
$$
És clar, doncs, que $G_2(z+1)=G_2(z)$. Ara bé, si intentem calcular $G_2(-1/z)$ trobarem un comportament curiós:
$$
G_2(-1/z) = \sum_{m=-\infty}^\infty\sum_{n=-\infty}^\infty \frac{z^2}{(nz+m)^2} = z^2\sum_{n=-\infty}^\infty\sum_{m=-\infty}^\infty \frac{1}{(mz+n)^2}.
$$
Fixem-nos que l'ordre dels sumatoris està canviat! Per relacionar-ho altra vegada amb $G(z)$, ens cal primer poder-la escriure com la suma d'una sèrie absolutament convergent.

**Lema:** Es pot escriure
$$
G_2(z) = 2\zeta(2) + \sum_{m\neq 0,n\in\Z}\frac{1}{(mz+n)^2(mz+n+1)},
$$
on la sèrie és absolutament convergent.

*Prova:* Només cal calcular
$$
\sum_{m\neq 0}\sum_{n\in\Z} \frac{1}{(mz+n)(mz+n+1)} = \sum_{m\neq 0}\sum_{n\in\Z} \left(\frac{1}{mz+n}-\frac{1}{mz+n+1}\right) = \sum_{m\neq 0} 0 = 0.
$$

Per tant, podem restar el terme general de sobre de la sèrie que defineix $G_2(z)$, per obtenir
$$
G_2(z) = 2\zeta(2) + \sum_{m\neq 0}\sum_{n\in\Z} \left(\frac{1}{(mz+n)^2}-\frac{1}{(mz+n)(mz+n+1)}\right)\\=2\zeta(2)+\sum_{m\neq 0
}\sum_{n\in\Z}\frac{1}{(mz+n)^2(mz+n+1)}.\quad\qed
$$

Ara podem veure com es transforma $G_2$:
$$
z^{-2}G_2(-1/z)-G_2(z)= \sum_{n\in \Z}\sum_{m\neq 0}\left(\frac{1}{(mz+n)^2} - \frac{1}{(mz+n)^2(mz+n+1)}\right)\\= \sum_{n\in\Z}\sum_{m\neq 0} \frac{1}{(mz+n)(mz+n+1)} = \sum_{n\in\Z}\sum_{m\neq 0}\left(\frac{1}{mz+n}-\frac{1}{mz+n+1}\right)
$$
Aquesta última suma la podem calcular explícitament:
$$
\sum_{n=-N}^{N-1}\sum_{m\neq 0} \left(\frac{1}{mz+n}-\frac{1}{mz+n+1}\right) =  \sum_{m\neq 0}\sum_{n=-N}^{N-1} \left(\frac{1}{mz+n}-\frac{1}{mz+n+1}\right)\\= \sum_{m\neq 0} \left(\frac{1}{mz-N}-\frac{1}{mz+N}\right) = \frac{-2\pi}{z}\cot(\pi N/z).
$$
Per poder calcular el límit, observem que
$$
\cot(\pi N/z) = i(1-2\sum_{m=0}^\infty e^{2\pi mN/z})\substack{\to\\{\tiny N\rightarrow\infty}} i.
$$

Resumint, hem trobat:

**Teorema:** La funció $G_2$ satisfà, per a tot $z\in \HH$,
$$
G_2(z+1) = G_2(z),\quad z^{-2}G_2(-1/z)-G_2(z) = \frac{-2\pi i}{z}.
$$
De fet, per a tot $\gamma=\smtx abcd\in\SL_2(\Z)$,
$$
G_2(\gamma z) = (cz+d)^2G_2(z) - 2\pi i c(cz+d).
$$

A més, $G_2$ té la $q$ expansió
$$
G_2(z) = 2\zeta(2) - 8\pi^2\sum_{n=1}^\infty \sigma_1(n)q^n = \frac{\pi^2}{3}\left(1-24\sum_{n=1}^\infty \sigma-1(n)q^n\right).
$$

L'expansió de la funció discriminant
=====================================

Volem donar una fórmula per $\Delta(z)=\frac{E_4(z)^3-E_6(z)^2}{1728}$. Per això, considerem $\tilde\Delta=q\prod_{n=1}^\infty(1-q^n)^{24}$. Veurem que aquestes dues funcions coincideixen ($q=e^{2\pi i z})$. Prenent la derivada logarítmica, obtenim (fixem-nos que $\dlog q = 2\pi i$)
$$
\dlog \tilde\Delta = 2\pi i + 24\sum_{n=1}^\infty \frac{-2\pi i n q^n}{1-q^n} = 2\pi i\left(1-24\sum_{n=1}^\infty\frac{nq^n}{1-q^n}\right).
$$
Observem que
$$
\sum_{n=1}^\infty \frac{nq^n}{1-q^n}=\sum_{n=1}^\infty n\sum_{m=1}^\infty q^{nm} = \sum_{n\geq 1}\sigma_1(n)q^n.
$$
Resumint,
$$
\dlog\tilde\Delta = 2\pi i E_2.
$$
Això vol dir que per a tot $z\in\HH$,
$$
\dlog \left(z^{-12}\tilde\Delta(-1/z)\right) = \frac{-12}{z} + \dlog\tilde\Delta(-1/z) =  2\pi i E_2(z)=\dlog\tilde\Delta(z).
$$
Per tant, $z^{-12}\tilde\Delta(-1/z) = C \tilde\Delta(z)$. Evaluant a $z=i$ podem veure que $C=1$ (ja que $\Delta(i)\neq 0$) i que, per tant $\tilde\Delta$ és una forma modular de pes $12$. Per tant, és un múltiple de $\Delta(z)$, que ha de ser $1$ perquè les sèries de Fourier comencen ambdues per $q+O(q^2)$.


La funció tau de Ramanujan
=============================

Recordem la funció $\tilde\Delta=q\prod_{n=1}^\infty(1-q^n)^{24}$. Calculant els primers termes del producte, de seguida veiem que
$$
\tilde\Delta = \sum_{n\geq 1} \tau(n)q^n = q - 24 q^{2} + 252 q^{3} - 1472 q^{4} + 4830 q^{5} - 6048 q^{6} - 16744 q^{7} + O(q^{8}).
$$
Ramanujan va ser el primer a estudiar la funció $\tau(n)$ funció el 1916, i va conjecturar que:

1. $\tau(n)\tau(m)=\tau(nm)$ si $(n,m)=1$.
2. $\tau(p^{k+1}) = \tau(p)\tau(p^k) - p^{11}\tau(p^{k-1})$, per a tot primer $p$ i $k\geq 1$; i
3. $\abs{\tau(p)} \leq 2p^{11/2}$ per a tot primer $p$.

També va observar (sense demostrar-les) tot de congruències que satisfà:

1. $\tau(n)\equiv n^2\sigma_7(n)\pmod{27}$
2. $\tau(n)\equiv n\sigma_3(n)\pmod{7}$
3. $\tau(n)\equiv \sigma_{11}(n)\pmod{691}$.

A més, Ramanujan va relacionar $\tau(n)$ amb si $r_{24}(n)$, el nombre de maneres d'escriure $n$ com a suma de $24$ quadrats (!)

Tot això, vist un segle després, és relativament fàcil de demostrar amb la teoria de les formes modulars. El teorema de Hecke que hem vist abans implica ja que $\abs{\tau(p)} =O(p^6)$, però per veure la fita més fina conjecturada per Ramanujan hauríem de fer servir resultats molt més profunds de P.Deligne (1974).

