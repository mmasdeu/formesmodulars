.. _day1:

***************************
Primer dia!
***************************

..
   Links to lectures
   =================

   Videos of Keith Conrad: https://www.youtube.com/watch?v=LolxzYwN1TQ
   Keith Conrad: https://ctnt-summer.math.uconn.edu/wp-content/uploads/sites/1632/2016/02/CTNTmodularforms.pdf
   Ram Murty: https://www.youtube.com/watch?v=LhCMD7N_fMc

Definicions bàsiques
====================


Considerem el semiplà superior de Poincaré,
$$
\HH = \{z\in \CC : \Im(z) >0\}
$$
i el grup $\operatorname{SL}_2(\mathbb{R})$, definit com
$$
\SL_2(\RR) = \left\{ \smtx abcd \in M_2(\RR) : ad-bc = 1\right\}.
$$

Aquest grup actua en els complexos (de fet, a $\mathbb{C} \cup \{\infty\}$)
mitjançant les anomenades *transformacions lineals fraccionàries*:
$$g\cdot z =\smtx{a}{b}{c}{d}\cdot z = \frac{az+b}{cz+d}.$$

Es té una fórmula  senzilla per la part imaginària d'aquesta quantitat:
$$
\Im(gz) = \frac{\Im(z)}{ | cz+d | ^2}.
$$

Per tant, veiem que $\operatorname{SL}_2(\mathbb{R})$ actua a $\mathbb{H}$. També veiem que $-1$ actua trivialment, i per tant de fet tenim un grup del quocient $\PSL_2(\RR) = \SL_2(\RR)/\{\pm 1\}$, que de fet és *fidel*.

**Remarca:** De fet, el grup $\PSL_2(\RR)$ és el grup d'automorfismes analítics d'$\HH$.

**Definició:** El grup $G = \SL_2(\RR)/\{\pm 1\}$ s'anomena el *grup modular*. Sovint confondrem una matriu $g = \smtx abcd$ amb la seva imatge a $G$.

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
Considerem ara el conjunt $D\subseteq \HH$ definit com
$$
D = \{ z \in \HH : \Re(z)\leq 1/2, | z | \geq 1 \}.
$$
Es té el següent teorema:

**Teorema:**

1. Per cada $z\in \HH$, hi ha algun $g\in G$ tal que $g\cdot z \in D$.
#. Siguin $z, z'\in D$ congruents mòdul $G$. Aleshores o bé $\Re(z)=\pm 1/2$ i $z=z'\pm 1$, o bé $\abs{z} = 1$ i $z'=-1/z$.
#. Sigui $z\in D$, i considerem $G_z=\{g \in G: g\cdot z = z\}$. Aleshores $G_z=1$ excepte si:

   a. $z=i$, i aleshores $G_i = \{1, S\}$.
   #. $z = \rho=e^{2\pi i/3}$, i aleshores $G_\rho=\{1, ST, (ST)^2\}$.
   #. $z = -\bar\rho=e^{\pi i /3}$, i aleshores $G_{-\bar\rho}=\{1, (TS), (TS)^2\}$.

*Prova:* El primer pas és considerar $G'=\langle S, T\rangle$ i $z\in\HH$, i veure que hi ha un $g'\in G'$ tal que $g'\cdot z \in D$. Hi un nombre finit de parelles $(c,d)$ tals que $ \abs{c z + d} $ és menor que un nombre fixat. Per tant, hi ha algun $g\in G'$ tal que $\Im(g\cdot z)$ és màxim. També hi ha un enter $n$ tal que $z'=T^ng z$ té part real entre $-1/2$ i $1/2$. Veurem ara que $\abs{z'}\geq 1$ i que, per tant, pertany a $D$: si no fos així, aleshores $\abs{z'}<1$ faria que $\Im(-1/z') = \Im(z')/\abs{z'}^2 > \Im(z')$, contradient la maximalitat de $\Im(z')$.

Per demostrar el segon punt, suposem que $z$ i $gz$ pertanyen a $D$. Per simetria, podem assumir que $\Im(gz)\geq \Im(z)$, és a dir,
$$
\abs{cz+d}^2=(cx+d)^2 + (cy)^2\leq 1, \quad z=x+iy.
$$
Com que $y>1/2$, això implica que $\abs{c}\leq 1$. Analitzant els diferents casos $c=0$, $c=1$ i $c=-1$ obtenim el que quedava per demostrar, excepte el fet que $G=G'$.

Sigui ara $g\in G$ un element arbitrari, i prenem $z_0$ a l'interior de $D$. Considerem $z=gz_0$, i trobarem $g'\in G'$ tal que $g'z$ pertanyi a $D$. Pel què hem vist $g'z=z_0$ i d'aquí obtenim $g'g=1$, i per tant $g$ pertany a $G'$.


**Corol·lari:** L'aplicació de pas al quocient $D \to \HH/G$ és exhaustiva, i la seva restricció a l'interior de $D$ és injectiva.

**Teorema:** El grup $G$ està generat per $S$ i $T$. De fet, es té $G=\langle S, T | S^2=(ST)^3=1 \rangle$.

Formes modulars
====================

Definicions
-----------

**Definició:** Diem que una funció $f$ meromorfa a $\HH$ és *dèbilment modular* de pes $k\in\Z$ si
$$f(g\cdot z) = (cz+d)^k f(z),\forall g=\smtx abcd \in\SL_2(\Z).$$

És convenient introduir aquí la notació "slash": definim $f | g$ com la funció (que depèn de $k$, encara que no ho posem a la notació)
$$(f | g)(z) = (cz+d)^{-k} f(z).$$
Aleshores veiem que $f$ és dèbilment modular si, i només si, $f| g=f$ per a tot $g\in \SL_2(\Z)$.

Com que $G$ està generat pels elements $S$ i $T$, aquesta condició és equivalent a demanar que, per a tot $z\in \HH$,
$$f(z+1)=f(z),\quad f(-1/z) = z^{k}f(z).$$

**Remarca:** Aplicant la definició a $-1\in \SL_2(\Z)$ obtenim que $f(z)=(-1)^k f(z)$. Per tant, si $k$ és senar només la funció $0$ és dèbilment modular. Demanarem doncs, d'aquí en endavant, que $k$ sigui parell.

Fixem-nos que, si $f(z+1)=f(z)$ per a tot $z\in \HH$, aleshores podem composar amb el canvi $q=e^{2\pi i z}$ i obtenir una funció $\tilde f(z)$ definida a $\tilde\HH=\{q\in \CC : 0 < | q | < 1 \}$. Aleshores, $\tilde f$ tindrà una sèrie de Laurent al voltant de $q=0$:
$$\tilde f(q) = \sum_{n=-\infty}^\infty a_nq^n.$$
Direm aleshores que $f$ és *meromorfa a l'infinit* si $\tilde f$ és meromorfa a $q=0$ ($a_n=0$ per $n<<0$). També direm que $f$ és *holomorfa a l'infinit* si $a_n=0$ per $n < 0$, i $f$ s'anul·la a l'infinit si $a_n=0$ per $n\leq 0$.

**Definició:** Una *forma modular* de pes $k$ és una funció dèbilment modular que és holomorfa a tot arreu, incloent l'infinit. Si aquesta s'anula a l'infinit, l'anomenarem una *forma cuspidal*.

Resumint, una forma modular de pes $k$ ve donada per una sèrie
$$
f(z) = \sum_{n=0}^\infty a_n q^n = \sum_{n=0}^\infty a_ne^{2\pi i z},
$$
que convergeix per a tot $z\in \HH$, i que satisfà $f(-1/z) = z^kf(z)$.

**Remarca:** Si multipliquem una forma modular $f$ de pes $k$ amb una $f'$ de pes $k'$ obtindrem una forma $ff'$ de pes $k+k'$.

.. TODO
   Interpretació via reticles
   --------------------------

Sèries d'Eisenstein
-------------------
Per ara els únics exemples que tenim de formes modulars són les constants, que són formes modulars de pes zero (de fet, són les úniques formes modulars de pes zero). Si considerem una funció holomorfa $h$ qualsevol, aleshores una manera de construir una funció modular és "simetritzar-la", és a dir, considerrar $\sum_{g\in G} h|_k g$. El problema és que en general aquesta suma no té per què convergir. Una segona idea seria considerar una funció que ja sigui invariant per algun subgrup de $H\leq G$, i aleshores només simetritzar per $G/H$. La versió més senzilla d'aquest principi és considerar la funció constant $1$. Si $H=\{ \pm \smtx{1}{t}{0}{1}\}$, veiem que $1|_k h=1$ per a tot $h\in H$. Per tant, podem considerar
$$
G_k(z) = \sum_{\gamma \in H\backslash \SL_2(\Z)} 1|_k \gamma= \sum_{\smtx abcd \in H \backslash \SL_2(\Z)} (cz+d)^{-k}.
$$
Fixem-nos que, donada una matriu $\smtx abcd\in \SL_2(\Z)$, la classe lateral$H\smtx abcd$ està formada per totes les matrius de la forma $\smtx{a'}{b'}{c}{d}\in\SL_2(\Z)$. Per tant, podem reescriure
$$
G_k(z) = \sum_{(c,d)\neq (0,0)} \frac{1}{(cz+d)^k},
$$

**Proposició:** Si $k>2$, la funció $G_k(z)$ és una forma modular de pes $k$. El seu valor a l'infinit és $2\zeta(k)$, on $\zeta$ és la funció zeta de Riemann.

*Prova:* Ens cal primer veure la convergència de la sèrie per tot $z$. Considerem primer $z\in D$ fixat, i podem veure fàcilment que $\abs{c z + d}^2 \geq \abs{c\rho - d}^2$. Com que
$$
\#\{ (c,d)\neq (0,0) : N \leq \abs{c\rho + d}< N+1\} = O(N)
$$
i $\sum_n n^{1-k}$ convergeix per $k>2$, ja estem. Com que $D$ és compacte, la sèrie $G_k(z)$ convergeix normalment a $D$ i, com que podem traslladar $D$ per recobrir tot $\HH$ amb elements de $\SL_2(\Z)$, en deduïm que $G_k(z)$ també convergeix a tot $\HH$ a una funció holomorfa.

Per calcular $G_k(\infty)$, prenem el límit quan $\Im(z)\to\infty$, i això ho podem fer mantenint $z$ a $D$. En aquest cas, gràcies a la convergència uniforme de la sèrie podem prendre el límit terme a terme. Els termes que tenen $c\neq 0$ tots van a $0$, i només ens queda
$$
\lim G_k(z) = \sum_{n\neq 0} n^{-k} = 2 \zeta(k).
$$

Podem normalitzar $G_k$ per tal que prengui el valor $1$ a l'infinit, i obtenim $E_k(z)=\frac{1}{2\zeta(k)} G_k(z)$. Aleshores podem fer combinacions de sèries d'Eisenstein per obtenir altres formes modulars. Per exemple,
$$
\Delta(z) = \frac{E_4^3 - E_6^2}{1728}
$$
és una forma cuspidal de pes $12$, anomenada la funció discriminant.

**Remarca:** Definim, per $\tau\in\HH$ i $w\in\CC$, la funció $\wp$ de Weierstrass, com
$$
\wp_\tau(w)=\frac{1}{w^2}+\sum_{(c,d)\neq (0,0)} \left(\frac{1}{(w-c\tau-d)^2}-\frac{1}{(c\tau+d)^2}\right).
$$
Aleshores la sèrie de Laurent de $\wp_\tau$ és fàcil de calcular, i resulta que les sèries d'Eisenstein apareixen com a coeficients d'aquesta sèrie:
\[
\wp_\tau(w) = \frac{1}{w^2} + \sum_{k=2}^\infty (2k-1)G_{2k}(\tau)w^{2k-2}.
\]
De fet, si definim $x=\wp_\tau(w)$ i $y=\wp_\tau'(w)$ (la derivada respecte $w$), tenim
\[
y^2=4x^3-60G_2(\tau)x-140G_3(\tau),
\]
que és una corba el·líptica amb discriminant justament $16\Delta(\tau)$, que per tant és diferent de zero.

L'espai de les formes modulars
==============================

Zeros i pols d'una funció modular
---------------------------------
Sigui $f\neq 0$ una funció meromorfa a $\HH$, i sigui $\tau\in\HH$. Escrivim $v_{\tau}(f)$ com l'enter tal que $(z-\tau)^{- v_{\tau}(f)} f(z)$ és holomorfa i diferent de zero a $z=\tau$ (l'ordre de $f$ a $\tau$).

Si $f$ és una funció modular de pes $k$, aleshores $v_\tau(f)=v_{g\tau}(f)$, perquè $cz+d$ és holomorfa i diferent de zero a tot $\HH$. També podem definir $v_\infty(f)=n_0$ si $\tilde f(q)=\sum_{n\geq n_0} a_nq^n$ amb $a_{n_0}\neq 0$.

**Teorema (fórmula de la valència):** Si $f\neq 0$ és una funció modular de pes $k$, es té
$$v_{\infty}(f) + \frac{1}{2} v_{i}(f) +\frac{1}{3}v_{\rho}(f) +\sum_{\tau\in G\backslash \HH} v_{\tau}(f) = \frac{k}{12},
$$
on la suma recorre les òrbites de punts d'$\HH$ diferents de $i$ i $\rho$.

**Remarca:** la suma només conté un nombre finit de termes no nuls. En efecte, com que $f$ és meromorfa tenim que $\tilde f$ no té cap zero ni pol al disc $0<\abs{q}<r$ per algun $r >0$. Per tant, $f$ no té zeros ni pols a la regió $\Im(z)>\frac{\log(1/r)}{2\pi}$ i, llavors $f$ té tots els zeros i pols de $D$ a la regió compacta $D\cap \Im(z)< \frac{\log(1/r)}{2\pi}$, on només n'hi pot haver un nombre finit.

El teorema es demostra aplicant el teorema del residu a un contorn adequat, i no el farem en aquestes notes.

L'àlgebra de formes modulars
----------------------------

Escrivim $M_k$ com el $\CC$-espai vectorial format per les formes modulars de pes $k$, i $S_k$ com el subespai format per les formes cuspidals. Com que $S_k=\ker( f\mapsto f(\infty))$, tenim $\dim M_k/S_k\leq 1$. A més, quan $k\geq 4$ les sèries d'Eisenstein són de M_k\setminus S_k$ i, per tant
$$
M_k = \CC G_k \oplus S_k.
$$

Aplicarem la fórmula de la valència a alguns casos senzills. Per exemple, si $f$ és una funció holomorfa, aleshores tots els termes que apareixen a l'esquerra són positius o zero, i per tant $M_k=0$ per $k<0$. Per $k=2$, veiem que no hi ha manera d'obtenir $1/6$ sumant múltiples de $1$, $1/2$ i $1/3$, i per tant $M_2=0$.

Ara, apliquem la fórmula a $G_4$. Podem escriure 1/3 = 0 + 1/2\cdot 0 + 1/3\cdot 1+0$ (i només d'aquesta manera), i per tant $G_4(\rho)=0$ (amb ordre $1$), i no s'anul·la enlloc més. De forma semblant, $v_{i}(G_6) = 1$ i aquest és l'únic punt on s'anul·la $G_6$. Observem llavors que $\Delta(i)\neq 0$ i que, per tant $\Delta\neq 0$. A més, per construcció $v_{\infty}(\Delta)\geq 1$. Per tant, la fórmula de la valència ens diu que $\Delta$ no s'anul·la a $\HH$, i té un zero simple a l'infinit.

Finalment, sigui $f$ un element de $S_k$, i definim $g=f/\Delta$. Aleshores $g$ té pes $k-12$, i $v_{\tau}(g)\geq 0$ per a tot $\tau$. Per tant $g\in M_{k-12}$.

Podem acabar calculant per $k\leq 10$ els espais $M_k$. En aquest cas, $k-12 < 0$ i $S_k=0$. Per tant, $\dim M_k\leq 1$. Com que $1, G_4, G_6, G_8, G_10$ són elements de $M_k$ per $k=0, 4,6,8,10$, formen una base de l'espai corresponent.

Resumim el què hem demostrat:

**Teorema:**

1. $M_k=0$ per $k<0$ i $k=2$.
2. $M_0=\CC\cdot 1$, $M_4=\CC\cdot G_4$, $M_6=\CC\cdot G_6$, $M_8=\CC\cdot G_8$ i $M_{10} = \CC\cdot G_{10}$. En aquests casos, $S_k=0$.
3. La multiplicació per $\Delta$ indueix un isomorfisme $M_{k-12}\cong S_k$.

En particular, $\dim M_k=\lfloor k/12\rfloor$ si $k\equiv 2 \pmod{12}$, i $\dim M_k=\lfloor k/12\rfloor +1$ si $k\neq 2\pmod{12}$.

**Corol·lari:** L'espai $M_k$ té com a base el conjunt de monomis $G_4^iG_6^j$, on $i,j\geq 0$ són enters amb $4i+6j=k$.

*Prova:* Veiem primer que generen, cosa que és clara per $k\leq 6$. Per $k\geq 8$, fem inducció en $k$. Triem enters positius $i,j$ tals que $4i+6j=k$, i considerem $g =G_4^iG_6^j$, que no s'anula a l'infinit. Si $f\in M_k$, aleshores $f-\lambda g\in S_k$ per algun $\lambda\in\CC$. Per aquest $\lambda$, tenim $f-\lambda g = \Delta h$ amb $h\in M_{k-12}$. Apliquem ara la hipòtesi d'inducció a $h$, i ja estem.
Si aquests monomis no fossin linealment independents, la funció $G_4^3/G_6^2$ satisfaria un polinomi amb coeficients a $\CC$ i, per tant, seria constant. Però això no pot ser, perquè $G_4$ s'anula a $\rho$ i $G_6$ no, per exemple.

**Remarca:** Es pot resumir l'anterior dient que $M=\bigoplus_{k\in\Z} M_k \cong \CC[G_4,G_6]$.

La funció j de Klein
--------------------
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

**Remarca:** Aviat veurem les $q$-expansions de les sèries d'Eisenstein, i podrem deduir-ne la de $j$, que de fet és
$$
j(z)=\frac{1}{q} + 744 + 196884q + 21493760q^2+\cdots
$$
Els coeficients són tots enters, que a més satisfan $n\equiv 0\pmod{p^i}\implies c(n) \equiv 0 \pmod{p^i}$ per $p=2,3,5,7,11$ (per $p=2,3,5$ la divisilitat de $c(n)$ és per $2^{3i+8}$, $3^{2i+3}$ i $5^{i+1}$, respectivament).

Càlcul de les q-expansions
==========================

Els nombres de Bernoulli
------------------------

Es defineixen com els coeficients de la sèrie de Taylor de
$$
\frac{t}{e^t-1} = \sum_{k=0}^\infty B_k \frac{t^k}{k!}.
$$

Es poden calcular de manera recursiva, calculant el terme de grau $n$ de l'expansió
$$
t = \sum_{k=0}^\infty B_k \frac{t^k}{k!} \sum_{\ell=1}^\infty \frac{t^\ell}{\ell!}.
$$
De fet, veiem que $B_0=1$, $B_1=-1/2$, i $B_k=0$ per a tot $k\geq 3$ senar. També podem calcular $B_2=1/6$, $B_4=-1/30$,...

L'interès en els nombres de Bernoulli prové del fet que són la "part racional" dels valors de la funció zeta de Riemann en els enters parells (per exemple, $\zeta(2)=\pi^2/6$, $\zeta(4)=\pi^4/90$,...

**Proposició:** si $n\geq 2$ és un enter parell,
$$
\zeta(n) = \frac {2^{n-1}\pi^{n} \abs{B_{n}}} {n!}
$$

*Prova:* Substituint $t=2iz$ a la definició dels nombres de Bernoulli obtenim la fórmula
$$
z\cot z = \sum_{k=0}^\infty \abs{B_{2k}}\frac{2^{2k}z^{2k}}{(2k)!}.
$$
D'altra banda, de la famosa fórmula
$$
\sin(z) = z\prod_{n=1}^\infty \left(1-\frac{z^2}{n^2\pi^2}\right)
$$
n'obtenim, fent la derivada logarítmica,
$$
z\cot z = 1+2\sum_{n=1}^\infty \frac{z^2}{z^2-n^2\pi^2}=1-2\sum_{n=1}^\infty\sum_{k=1}^\infty \frac{z^{2k}}{n^{2k}{\pi^{2k}}}.
$$
Arribem al resultat comparant el terme de $z^{2k}$ de cada equació.$\qed$

Expansions de les sèries d'Eisenstein
-------------------------------------

Observem que, de la igualtat
$$
z\cot z = 1+2\sum_{n=1}^\infty \frac{z^2}{z^2-n^2\pi^2}
$$
en podem deduir
$$
\pi\cot (\pi z)=\frac{1}{z} + \sum_{m=1}^\infty \left(\frac{1}{z+m}-\frac{1}{z-m}\right).
$$
D'altra banda,
$$
\pi\cot(\pi z) = \pi \frac{\cos(\pi z)}{\sin(\pi z)} = i\pi\frac{q+1}{q-1} = i\pi - \frac{2i\pi}{1-q} = i\pi -2\pi i \sum_{n=0}^\infty q^n.
$$
Comparant les dues expressions, obtenim la igualtat bàsica
$$
\frac{1}{z} + \sum_{m=1}^\infty \left(\frac{1}{z+m}-\frac{1}{z-m}\right) =  i\pi -2\pi i \sum_{n=0}^\infty q^n.
$$
Derivant-la successivament, obtenim el que es coneix com la **fórmula de Lipschitz**:
$$
\sum_{m\in\Z} \frac{1}{(m+z)^k} = \frac{(-1)^k (2\pi i)^k}{(k-1)!}\sum_{n=1}^\infty n^{k-1}q^n, \quad k\geq 2.
$$

**Proposició:** Per cada $k\geq 4$ parell, tenim
$$
G_k(z) = 2\zeta(k) + 2\frac{(2\pi i)^{k}}{(k-1)!} \sum_{n=1}^\infty \sigma_{k-1}(n)q^n.
$$

*Prova:* Expandim $G_k(z)$ com
$$
G_k(z)=\sum_{(c,d)\neq (0,0)} \frac{1}{(cz+d)^k} =2\zeta(k) + 2\sum_{n=1}^\infty\sum_{m\in\Z} \frac{1}{(cz+d)^k}.
$$
Aplicant la igualtat bàsica anterior amb $cz$ en comptes de $z$, tenim
$$
G_k(z) = 2\zeta(k) +2\frac{(-1)^k (2\pi i)^k}{(k-1)!} \sum_{d=1}^\infty \sum_{a=1}^\infty d^{k-1} q^{ad} = 2\zeta(k) + \frac{2(2\pi i)^k}{(k-1)!}\sum_{n=1}^\infty \sigma_{k-1}(n)q^n.
$$

**Corol·lari:** Tenim $G_k(z)=2\zeta(k)E_k(z)$, amb
$$
E_k(z) = 1-\frac{2k}{B_k}\sum_{n=1}^\infty \sigma_{k-1}(n)q^n.
$$

Per exemple,
$$
E_4=1+240\sum_{n\geq 1} \sigma_3(n)q^n,\quad E_6=1-504\sum_{n\geq 1} \sigma_5(n)q^n.
$$

Una primera aplicació
---------------------
Ja hem vist que $M_8$ i $M_{10}$ tenen dimensió $1$. Per tant, $E_4^2=E_8$ i $E_4E_6=E_{10}$. Comparant coeficients de les corresponents expansions, obtenim les identitats
$$
\sigma_7(n)=\sigma_3(n)+120\sum_{m=1}^{n-1} \sigma_3(m)\sigma_3(n-m),
$$

$$
11\sigma_9(n)=21\sigma_5(n)-10\sigma_3(n)+5040\sum_{m=1}^{n-1} \sigma_3(m)\sigma_5(n-m).
$$
