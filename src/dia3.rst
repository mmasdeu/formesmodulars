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



