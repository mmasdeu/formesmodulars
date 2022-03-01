.. _day3:

***************************
Tercer dia
***************************

Operadors de Hecke
==================================

Definició
-----------

.. TODO
   Fer una definició en termes de reticles

Sigui $f$ una forma dèbilment modular de pes $k$ (és a dir, meromorfa i satisfà la simetria corresponent per $\SL_2(\ZZ)$). Per cada $n\geq 1$ i cada $d\mid n$, definim
$$
(T_nf)(z) = n^{k-1} \sum_{e\geq 1, ed=n}\sum_{0\leq b < d} d^{-k} f\left(\frac{ez+b}{d}\right).
$$

En particular, si $n=p$ és un primer, tenim
$$
(T_pf)(z) = p^{-1} \left(\sum_{b=0}^{p-1} f(\frac{z+b}{p}) + f(pz)\right).
$$

**Proposició:** La funció $T_nf$ és dèbilment modular de pes $k$. Si $f$ és holomorfa, també ho és $T_nf$. A més:

1. $T_m T_n = T_n T_m = T_{nm}$ si $(m,n)=1$.
#. $T_{p^{r+1}} = T_p T_{p^r} - p^{k-1} T_{p^{r-1}}$ si $p$ és primer i $n\geq 1$.

Podem calcular l'efecte d'aquests operadors en les $q$-expansions, obtenint:

**Proposició:** Si $f(z)=\sum_{m\in \ZZ} a_m(f)q^m$ és meromorfa l'infinit, aleshores $T_nf(z)=\sum_{m\in\ZZ} a_m(T_nf)q^m$ també ho és, i
$$
a_m(T_nf) = \sum_{d \mid (m,n)} d^{k-1} a_{mn/d^2}(f).
$$

En particular, $a_0(T_nf) = \sigma_{k-1}(n) a_0(f)$, $a_1(T_nf) = a_n(f)$ i, si $n=p$ és un primer,
$$
a_m(T_pf) = a_{pm}(f) + p^{k-1} a_{m/p}(f),
$$
on entenem que $a_{m/p}(f)=0$ si $p$ no divideix $m$. Veiem també que $T_n$ actua a $M_k$ i $S_k$, i commuten entre si.

Formes pròpies
----------------

Suposem ara que $f=\sum_{n\geq 0} a_n(f)q^n$ és una forma modular de pes $k>0$, que és pròpia per tots els $T_n$. És a dir, per cada $n\geq 1$ tenim $T_nf=\lambda_nf$, per algun $\lambda_n\in\CC$.


**Teorema:**  $a_1(f)\neq 0$. Si $f$ està normalitzada de manera que $a_1(f)=1$, aleshores $a_n(f) = \lambda_n$.

*Prova:* Hem vist que $a_1(T_nf) = a_n(f)$. Com que $f$ és pròpia, $a_1(T_nf) = \lambda_n a_1(f)$. Per tant, $a_n(f) = \lambda_n a_1(f)$. Si suposem que $a_1(f)=0$, aleshores tindríem $a_n(f)=0$ per a tot $n\geq 1$, i per tant $f$ seria una constant. Però $k>0$, i per tant arribem a contradicció. $\qed$

**Corol·lari:** Si $f$ i $g$ són formes pròpies per tot $T_n$ amb els mateixos valors propis, aleshores són proporcionals.

**Corol·lari:** Si $f$ està normalitzada, aleshores
$$
a_m(f)a_n(f)=a_{mn}(f),\text{ i}
$$
$$
a_{p^{r+1}}(f) = a_p(f)a_{p^r}(f) - p^{k-1} a_{r-1}(f).
$$

La funció L associada a una forma modular
=========================================

Podem empaquetar tota la informació que hem trobat de manera analítica, mitjançant la funció-L. Sigui
$$
L(f,s) = \sum_{n=1}^\infty a_n(f)n^{-s},\quad \Re(s)>k.
$$
Observem que convergeix per a tot $\Re(s)>k$ gràcies a que controlem el creixement dels $a_n(f)$. Si $f$ és cuspidal,
aleshores sabem que la sèrie convergeix a $\Re(s)>k/2+1$.

El producte d'Euler i l'equació funcional
-----------------------------------------

**Proposició:** $f$ és una forma pròpia normalitzada si i només si la funció $L(f,s)$ té un producte d'Euler:
$$
L(f,s) = \prod_{p} \frac{1}{1-a_p(f)p^{-s} + p^{k-1-2s}},
$$
on el producte és sobre els primers $p$.
*Prova*: Com que els coeficients $a_{n}(f)$ formen una successió multiplicativa, tenim
$$
L(f,s) = \prod_p \sum_{r=0}^\infty a_{p^r}(f)p^{-rs}.
$$
Per tant, si escrivim $T=p^{-s}$, aleshores hem de demostrar
$$
\sum_{r=0}^\infty a_{p^r}(f)T^r = \left(1-a_p(f)T + p^{k-1}T^2\right)^{-1}.
$$
Equivalentment, podem demostrar
$$
\left(1-a_p(f)T + p^{k-1}T^2\right)\sum_{r=0}^\infty a_{p^r}(f)T^r = 1.
$$
El coeficient de $T$ és $a_p(f)-a_p(f)=0$. El de $T^{r+1}$ és, per a tot $r\geq 1$,
$$
a_{p^{r+1}} - a_pa_{p^{r}} + p^{k-1}a_{p^{r-1}},
$$
que ja sabem que és $0$. $\qed$

Escrivim $\Lambda(f,s) = (2\pi)^{-s} \Gamma(s) L(f,s)$, on
$$
\Gamma(s) = \int_0^{\infty} t^{s}e^{-t}\frac{dt}{t}.
$$

**Proposició:**
$$
\Lambda(f,s) = \int_0^\infty (f(it) - a_0)t^s\frac{dt}{t}.
$$
*Prova:*
Calculem:
$$
\Lambda(f,s) = (2\pi)^{-s} \int_0^\infty t^s e^{-t}\frac{dt}{t} \sum_{n=1}^\infty a_nn^{-s} = \sum_{n=1}^\infty a_n \int_0^\infty \left(\frac{t}{2\pi n}\right)^s e^{-t}\frac{dt}{t}.
$$
Si fem el canvi de variables $t\mapsto t/(2\pi n)$ al terme $n$-èssim, obtenim
$$
\sum_{n=1}^\infty a_n\int_0^\infty t^s e^{-2\pi n t} \frac{dt}{t} = \int_0^\infty \left(\sum_{n=1}^\infty a_ne^{-2\pi nt}\right) t^s\frac{dt}{t}.\quad \qed
$$


Volem extendre $\Lambda(f,s)$ a tot el pla complex, però la integral tal i com la tenim té problemes de convergència prop de $t=0$. Suposem, per simplicar, que $a_0=0$. El que fem és observar que
$$
\int_0^\infty f(it)t^{s}\frac{dt}{t} = \int_0^1(\cdots)+\int_1^\infty(\cdots)
$$
i, fent servir que $f(i/t) = i^kt^kf(it)= (-1)^{k/2}$ trobem, fent el canvi $t\mapsto 1/t$,
$$
\int_0^1  f(it)t^{s}\frac{dt}{t} = (-1)^{k/2} \int_1^\infty f(it)t^{k-s}\frac{dt}{t}.
$$
Per tant,
$$
\Lambda(f,s) = \int_1^\infty f(it) (t^s + (-1)^{k/2} t^{k-s})\frac{dt}{t}.
$$
Aquesta expressió convergeix per tot $s\in\CC$. A més a més, obtenim l'equació funcional, que relaciona $s$ amb $k-s$:
$$
\Lambda(f,k-s) = (-1)^{k/2} \Lambda(f,s).
$$

**Remarca:** Si $f\in M_k$ no és cuspidal, aleshores $\Lambda(f,s)$ no té una continuació holomorfa (només meromorfa), però l'equació funcional es segueix satisfent.

Hi ha un teorema recíproc, que no demostrarem.

**Teorema (Weil):** Sigui $L(\{a_n\},s) = \sum_{n=1}^\infty a_n n^{-s}$ una sèrie de Dirichlet associada a una successió $\{a_n\}_{n\geq 1}$ tal que $\abs{a_n}=O(n^K)$ per $K$ suficientment gran. Suposem que la funció $\Lambda(\{a_n\},s)$ associada tingui continuació analítica a tot $s\in\CC$, fitada en conjunts $\{\sigma_1\leq \Re(s)\leq \sigma_2\}$ i que tingui una equació funcional com l'anterior. Aleshores la funció $f(z)=\sum_{n=1}^\infty a_ne^{2\pi inz}$ pertany a $S_k$.

Funció-L de les sèries d'Eisenstein
-----------------------------------

Sigui $k\geq 4$ un enter, i considerem la sèrie d'Eisenstein $E_k = 1 - \frac{2k}{B_k}\sum_{n=1}^\infty \sigma_{k-1}(n)q^n$.

**Proposició:** $T_p(E_k) = (1+p^{k-1})E_k$.
*Prova:* Ho comprovem coeficient a coeficient. Si $p\nmid n$, hem de comprovar que
$$
\sigma_{k-1}(pn) = (1+p^{k-1})\sigma_{k-1}(n).
$$
Per altra banda, si $n = p^em$ amb $p\nmid m$ i $e\geq 1$, hem de veure que
$$
\sigma_{k-1}(p^{e+1}m) + p^{k-1} \sigma_{k-1}(p^{e-1}m) = (1+p^{k-1})\sigma_{k-1}(p^em).
$$
La primera equació es comprova fàcilment, i la segona es fa per inducció en $e$. $\qed$

Podem ara calcular ara la seva sèrie de Dirichlet:
$$
\sum_{n=1}^\infty \sigma_{k-1}(n)n^{-s} = \sum_{a,d\geq 1} \frac{a^{k-1}}{a^sd^s} = \left(\sum_{d\geq 1} d^{-s}\right)\left(\sum_{a\geq 1} a^{k-s-1}\right) = \zeta(s)\zeta(s-k+1).
$$

De manera alternativa, podem veure que l'invers del terme $p$-èssim del producte d'Euler és
$$
1-\sigma_{k-1}(p)p^{-s} + p^{k-1-2s} = 1- p^{-s} - p^{k-1-s} + p^{k-1-2s} = (1-p^{-s})(1-p^{k-1-s}),
$$
que coincideix amb el producte dels inversos dels factors d'Euler de $\zeta(s)\zeta(s-k+1)$.

Funció-L de la Delta de Ramanujan
---------------------------------

Recordem $\Delta(q)=q\prod_{n\geq 1} (1-q^n)^{24}$. Com ja hem vist, $S_{12}=\CC\Delta$ i per tant $\Delta$ és trivialment una forma pròpia per tots els operadors de Hecke, que a més ja està normalitzada. Per tant:

**Corol·lari:** Tenim:
$$
\tau(nm)=\tau(n)\tau(m),\quad (n,m)=1,
$$
i
$$
\tau(p)\tau(p^n) = \tau(p^{n+1})+p^{11}\tau(p^{n-1}),\quad \forall p\text{ primer}, n\geq 1.
$$

Es tenen resultats anàlegs per tots els espais $S_k$ de dimensió $1$, que són exactament $k=12,16,18,20,22,26$. Els generador és, en cada cas, $\Delta E_{k-12}$.

El producte de Petersson
========================

Per estudiar més a fons els espais $S_k$, els hem de dotar de més estructura que la d'espai vectorial complex. Podem definir un producte escalar hermític, de la següent manera: donades $f,g\in S_k$, considerem
$$
\phi_{f,g} = = f(z)\overline{g(z)} y^{k}.
$$

Si $\gamma\in\SL_2(\ZZ)$, podem veure fàcilment que $\phi_{f,g}(\gamma z) = \phi_{f,g}(z)$. Per tant, és una funció ben definida a $\SL_2(\ZZ)\backslash\HH$. Podem doncs considerar la integral
$$
\langle f,g\rangle = \frac{3}{\pi}\int_{\SL_2(\ZZ)\backslash\HH} f(z)\overline{g(z)} y^{k-2}dxdy,
$$
ja que $\frac{dxdy}{y^2}$ és una mesura $\SL_2(\ZZ)$-invariant a $\HH$. Respecte aquesta mesura, el domini fonamental de $\SL_2(\ZZ)$ té volum $\frac{\pi}{3}$, i per això escollim la normalització anterior.

**Proposició:** El producte $\langle\cdot,\cdot\rangle$ és hermític i definit positiu. És a dir:
1. $\langle a_1f_1+a_2f_2,g\rangle = a_1\langle f_1,g\rangle + a_2\langle f_2,g\rangle$,
#. $\langle g,f\rangle = \overline{\langle f,g\rangle}$, i
#. $\langle f,f\rangle\geq 0$, amb igualtat només si $f=0$.

**Proposició:** Per a tot $n\geq 1$, tenim $\langle T_n f, g\rangle=\langle f, T_ng\rangle$.

Com a conclusió, els operadors de Hecke $T_n$ formen una família d'operadors normals respecte el producte de Petersson. Per tant, $S_k$ conté una base ortogonal de formes pròpies per **tots** els operadors de Hecke simultàniament. Es diu que $S_k$ satisfà "multiplicitat-1": donat una col·lecció de valors propis $\{\lambda_n\}_{n\geq 1}$, hi ha com a molt una forma cuspidal pròpia $f\in S_k$ tal que $T_n(f)=\lambda_n f$. A més, pel teorema de Cayley-Hamilton tenim que els valors propis dels operadors de Hecke són nombres algebraics reals!


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

