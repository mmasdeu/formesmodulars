.. _day1:

***************************
Primer dia
***************************

Links to lectures
=================

Videos of Keith Conrad: https://www.youtube.com/watch?v=LolxzYwN1TQ
Keith Conrad: https://ctnt-summer.math.uconn.edu/wp-content/uploads/sites/1632/2016/02/CTNTmodularforms.pdf

Definicions bàsiques
====================


Considerem el semiplà superior de Poincaré,
$$
\H = \{z\in \C : \Im(z) >0\}
$$
i el grup $\operatorname{SL}_2(\mathbb{R})$, definit com
$$
\SL_2(\R) = \left\{ \smtx abcd \in M_2(\R) : ad-bc = 1\right\}.
$$

Aquest grup actua en els complexos (de fet, a $\mathbb{C} \cup \{\infty\}$)
mitjançant les anomenades *transformacions lineals fraccionàries*:
$$g\cdot z =\smtx{a}{b}{c}{d}\cdot z = \frac{az+b}{cz+d}.$$

Es té una fórmula  senzilla per la part imaginària d'aquesta quantitat:
$$
\Im(gz) = \frac{\Im(z)}{ | cz+d | ^2}.
$$

Per tant, veiem que $\operatorname{SL}_2(\mathbb{R})$ actua a $\mathbb{H}$. També veiem que $-1$ actua trivialment, i per tant de fet tenim un grup del quocient $\PSL_2(\R) = \SL_2(\R)/\{\pm 1\}$, que de fet és *fidel*.

**Remarca:** De fet, el grup $\PSL_2(\R)$ és el grup d'automorfismes analítics d'$\H$.

**Definició:** El grup $G = \SL_2(\R)/\{\pm 1\}$ s'anomena el *grup modular*. Sovint confondrem una matriu $g = \smtx abcd$ amb la seva imatge a $G$.

El domini fonamental
====================

Considerem dos elements a $G$ que jugaran un paper important:
$$
S = \smtx{0}{-1}{1}{0},\quad T = \smtx 1101.
$$
Actuen enviant $z$ a $S\cdot z=-1/z$ i $T\cdot z = z+1$. A més, satisfan les relacions (a $G$)
$$
S^2=1,\quad (ST)^3=1.
$$
Considerem ara el conjunt $D\subseteq \H$ definit com
$$
D = \{ z \in \H : \Re(z)\leq 1/2, | z | \geq 1 \}.
$$
Es té el següent teorema:

**Teorema:**

1. Per cada $z\in \H$, hi ha algun $g\in G$ tal que $g\cdot z \in D$.
#. Siguin $z, z'\in D$ congruents mòdul $G$. Aleshores o bé $\Re(z)=\pm 1/2$ i $z=z'\pm 1$, o bé $| z | = 1$ i $z'=-1/z$.
#. Sigui $z\in D$, i considerem $G_z=\{g \in G: g\cdot z = z\}$. Aleshores $G_z=1$ excepte si:

   a. $z=i$, i aleshores $G_i = \{1, S\}$.
   #. $z = \rho=e^{2\pi i/3}$, i aleshores $G_\rho=\{1, ST, (ST)^2\}$.
   #. $z = -\bar\rho=e^{\pi i /3}$, i aleshores $G_{-\bar\rho}=\{1, (TS), (TS)^2\}$.

*Prova:* El primer pas és considerar $G'=\langle S, T\rangle$ i $z\in\H$, i veure que hi ha un $g'\in G'$ tal que $g'\cdot z \in D$. Hi un nombre finit de parelles $(c,d)$ tals que $ | c z + d | $ és menor que un nombre fixat. Per tant, hi ha algun $g\in G'$ tal que $\Im(g\cdot z)$ és màxim. També hi ha un enter $n$ tal que $z'=T^ng z$ té part real entre $-1/2$ i $1/2$. Aleshores es veu que $z'$ pertany a $D$...

..  TODO: acabar-la.


**Corol·lari:** L'aplicació de pas al quocient $D \to \H/G$ és exhaustiva, i la seva restricció a l'interior de $D$ és injectiva.

**Teorema:** El grup $G$ està generat per $S$ i $T$. De fet, es té $G=\langle S, T | S^2=(ST)^3=1 \rangle$.

Formes modulars
====================

Definicions
-----------

**Definició:** Diem que una funció $f$ meromorfa a $\H$ és *dèbilment modular* de pes $k\in\Z$ si
$$f(g\cdot z) = (cz+d)^k f(z),\forall g=\smtx abcd \in\SL_2(\Z).$$

És convenient introduir aquí la notació "slash": definim $f | g$ com la funció (que depèn de $k$, encara que no ho posem a la notació)
$$(f | g)(z) = (cz+d)^{-k} f(z).$$
Aleshores veiem que $f$ és dèbilment modular si, i només si, $f| g=f$ per a tot $g\in \SL_2(\Z)$.

Com que $G$ està generat pels elements $S$ i $T$, aquesta condició és equivalent a demanar que, per a tot $z\in \H$,
$$f(z+1)=f(z),\quad f(-1/z) = z^{k}f(z).$$

**Remarca:** Aplicant la definició a $-1\in \SL_2(\Z)$ obtenim que $f(z)=(-1)^k f(z)$. Per tant, si $k$ és senar només la funció $0$ és dèbilment modular. Demanarem doncs, d'aquí en endavant, que $k$ sigui parell.

Fixem-nos que, si $f(z+1)=f(z)$ per a tot $z\in \H$, aleshores podem composar amb el canvi $q=e^{2\pi i z}$ i obtenir una funció $\tilde f(z)$ definida a $\tilde\H=\{q\in \C : 0 < | q | < 1 \}$. Aleshores, $\tilde f$ tindrà una sèrie de Laurent al voltant de $q=0$:
$$ \tilde f(q) = \sum_{n=-\infty}^\infty a_nq^n.$$
Direm aleshores que $f$ és *meromorfa a l'infinit* si $\tilde f$ és meromorfa a $q=0$ ($a_n=0$ per $n<<0$). També direm que $f$ és *holomorfa a l'infinit* si $a_n=0$ per $n < 0$, i $f$ s'anul·la a l'infinit si $a_n=0$ per $n\leq 0$.

**Definició:** Una *forma modular de pes $k$* és una funció dèbilment modular que és holomorfa a tot arreu, incloent l'infinit. Si aquesta s'anula a l'infinit, l'anomenarem una *forma cuspidal*.

Resumint, una forma modular de pes $k$ ve donada per una sèrie
$$
f(z) = \sum_{n=0}^\infty a_n q^n = \sum_{n=0}^\infty a_ne^{2\pi i z},
$$
que convergeix per a tot $z\in \H$, i que satisfà $f(-1/z) = z^kf(z)$.

**Remarca:** Si multipliquem una forma modular $f$ de pes $k$ amb una $f'$ de pes $k'$ obtindrem una forma $ff'$ de pes $k+k'$.

.. TODO
   Interpretació via reticles
   --------------------------

Sèries d'Eisenstein
-------------------
Per ara els únics exemples que tenim de formes modulars són les constants, que són formes modulars de pes zero (de fet, són les úniques formes modulars de pes zero). Si considerem una funció holomorfa $h$ qualsevol, aleshores una manera de construir una funció modular és "simetritzar-la", és a dir, considerrar $\sum_{g\in G} h|_k g$. El problema és que en general aquesta suma no té per què convergir. Una segona idea seria considerar una funció que ja sigui invariant per algun subgrup de $H\leq G$, i aleshores només simetritzar per $G/H$. La versió més senzilla d'aquest principi és considerar la funció constant $1$. Si $H=\{ \pm \smtx{1}{t}{0}{1}\}$, veiem que $1|_k h=1$ per a tot $h\in H$. Per tant, podem considerar
$$
G_k(z) = \sum_{\gamma \in H\backslash \SL_2(\Z)} 1|_k \gamma.
$$
Fixem-nos que, donada una matriu $\smtx abcd\in \SL_2(\Z)$, la classe lateral$H\smtx abcd$ està formada per totes les matrius $\smtx{a'}{b'}{c}{d}\in\SL_2(\Z)$.

