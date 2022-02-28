.. _day3:

***************************
Tercer dia
***************************


Funcions theta
==============

Sigui $V$ un espai vectorial real de dimensió $n$, amb una mesura invariant $\mu$, i sigui $V'$ l'espai dual. Si $f$ és una funció "bona" (diferenciable, amb decreixement ràpid) aleshores té una transformada de Fourier
$$
\hat f (y) = \int_V e^{-2\pi i\langle x,y\rangle} f(x)d\mu(x),
$$
que és una funció a $V'$ també bona.

Sigui $\Gamma$ un reticle a $V$, i sigui $\Gamma'$ el seu reticle dual:
$$
\Gamma' = \left\{y\in V': \forall x\in\Gamma, \langle x,y\rangle\in \ZZ\right\}.
$$

**Proposició:** Sigui $V=\mu(V/\Gamma)$ el covolum de $\Gamma$. Aleshores
$$
\sum_{x\in \Gamma} f(x) = \frac{1}{V} \sum_{y\in\Gamma'} \hat f(y).
$$

.. TODO: finish this!


La funció j de Klein
====================
Definim la següent funció modular de pes $0$:
$$
j = E_2^3 / \Delta.
$$
Veiem que $j$ té un holomorfa a tot $\HH$, perquè $\Delta$ no s'anula. A més, té un pol simple a l'infinit, provinent del zero simple de $\Delta$.

**Proposició:** L'aplicació $z\mapsto j(z)$ identifica $G\backslash \HH$ amb $\CC$.

*Prova:* com que $j$ és invariant per $G$, obtenim una funció ben definida $G\backslash \HH\to \CC$. Hem de veure que, per a tot $\lambda\CC$, existeix un únic $z\in G\backslash\HH$ tal que $j(z)=\lambda$ o, el què és el mateix, que la funció $f_\lambda(z)=E_2(z)^3 - \lambda\Delta(z)$ té un únic zero mòdul $G$. Aplicant la fórmula de la valència a $f_\lambda$ (que té pes $12$) veiem que hem de descomposar $1$ de la forma $a + b/2 + c/3$ amb $a,b,c\geq 0$. Les úniques possibilitats són $(1,0,0)$, $(0,2,0)$, $(0,0,3)$, i per tant hi ha un únic zero de $f_\lambda$ a $G\backslash\HH$. $\qed$

De fet, d'alguna manera la funció $j$ dona lloc a totes les funcions modulars de pes zero:

**Proposició:** Tota funció modular de pes zero és una funció racional en $j$.

*Prova:* Sigui $f$ una funció modular. Multiplicant-la per un polinomi en $j$, posem suposar que és holomorfa a $\HH$. D'altra banda, com que $\Delta$ té un zero simple a l'infinit, podem multiplicar $f$ per $\Delta^n$ de manera que $g=\Delta^nf$ sigui holomorfa també a l'infinit. Aleshores $g$ és una forma modular de pes $12n$, que podem escriure com un polinomi (4,6)-homogeni en $E_4$ i $E_6$, de grau $12n$. Per linealitat, n'hi ha prou amb veure que $f=E_4^iE_6^j/\Delta^n$ és una funció racional en $j$. Observem però que, com que $4i+6j=12n$, tant $p=i/3$ com $q=j/2$ són enters i, per tant, $f=E_4^{3p}E_6^{2q}/\Delta^{p+q}=(\frac{E_4^3}{\Delta})^p(\frac{E_6^2}{\Delta})^q$. Però tant $E_4^3/\Delta$ com $E_6^2/\Delta$ són funcions racionals en $j$, i ja estem. $\qed$

**Remarca:** A partir de les  $q$-expansions de les sèries d'Eisenstein podem obtenir la de $j$:
$$
j(z)=\frac{1}{q} + 744 + 196884q + 21493760q^2+\cdots
$$
Els coeficients són tots enters, que a més satisfan $n\equiv 0\pmod{p^i}\implies c(n) \equiv 0 \pmod{p^i}$ per $p=2,3,5,7,11$ (per $p=2,3,5$ la divisilitat de $c(n)$ és per $2^{3i+8}$, $3^{2i+3}$ i $5^{i+1}$, respectivament).

