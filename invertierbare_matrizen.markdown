---
layout: page
title: Invertierbare Matrizen und ihre Eigenschaften
nav: true
permalink: /invertierbare-matrizen-und-ihre-eigenschaften/
---



<script type="text/javascript" id="MathJax-script" async
  src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js">
</script>
<script>
  MathJax = {
    tex: {
      inlineMath: [['$', '$'], ['$`', '`$'], ['\\(', '\\)']],
      displayMath: [['```math', '```'], ['$$', '$$'], ['\\[', '\\]']]
    }
  };
</script>

Dieser Artikel soll die Zusammenhänge zwischen Invertierbarkeit und anderen Eigenschaften von Matrizen darstellen. Was kann man folgern, wenn eine Matrix $A$ invertierbar ist? Und was kann man vielleicht auch nicht folgern? Schauen wir uns das ganze mal an!
<h3>Eigenwerte</h3>
Eine Matrix $A$ ist invertierbar, genau dann, wenn $\lambda = 0$ <strong>kein</strong> Eigenwert ist. Warum ist das so? Nehmen wir mal an, dass $\lambda = 0 $ ein Eigenwert von $A$ ist. Dann gilt nach der Definition von Eigenwerten

$$Av = 0v = 0$$

für einen Eigenvektor $v \neq 0$. Wenn aber $A$ auch invertierbar wäre, könnten wir an diese Gleichung von links mit $A^{-1}$ multiplizieren und erhalten:

$$ A^{-1} \cdot Av = A^{-1}\cdot 0 $$

also: $ v = 0 $, was im Widerspruch zur Definition von Eigenvektoren steht. Eigenwert Null und Invervierbarkeit passt also nicht zusammen.



<h3>Diagonalisierbarkeit</h3>
Wie im [Beitrag über Diagonalisierbarkeit]({% link diagonalisierbarkeit_matrix.markdown %}) bereits gesehen, kann man aus Invertierbarkeit weder Diagonalisierbarkeit folgern noch umgekehrt. Die Beispiele aus jenem Beitrag sollte man immer im Hinterkopf behalten.




<h3>Gleichungssysteme</h3>
Wenn $A$ invertierbar ist, ist jedes Gleichungssystem

$$ Ax=b $$

<strong>eindeutig </strong>lösbar, d.h. es gibt genau <strong>einen </strong>Vektor x, sodass die Gleichung erfüllt ist. Dieser Vektor ist natürlich genau

$$ x = A^{-1}b $$

Insbesondere bedeutet dies, dass das Gleichungssystem

$$ Ax = 0 $$

genau die Lösung $x = 0$ hat. Daraus können wir direkt folgendes erkennen:
<h3><strong>Lineare Unabhängigkeit</strong></h3>
Wir wissen, dass aus $Ax=0$ folgt, dass $x$ der Nullvektor ist. Wenn wir diese Gleichung einmal ausschreiben und die Spalten von $A$ als Vektoren $a_i$ schreiben, bekommen wir:

$$ Ax = \begin{pmatrix} a_1 | a_2 | \cdots | a_n \end{pmatrix}\cdot x = a_1x_1 + a_2x_2 + \ldots + a_nx_n $$

Die Gleichung $Ax=0$ ist damit also äquivalent zur Gleichung

$$ a_1x_1 + a_2x_2 + \ldots + a_nx_n $$

und wir wissen aus dem vorigen Abschnitt, dass die <strong>einzige</strong> Lösung $x=0$, also $x_1 = x_2 = \cdots = x_n = 0 $ ist. Das heißt, dass die Spaltenvektoren $a_i$ alle linear unabhängig sind!
<h3>Determinante</h3>
Eine Matrix $A$ ist genau dann invertierbar, wenn gilt dass $det(A) \neq 0$. Warum? Naja, nehmen wir mal an, dass $det(A) = 0$. Nehmen wir uns jetzt einen Vektor $v\neq 0$ können wir daraus basteln:

$$ \begin{align} det(A - 0\mathbb{I}v) = 0 \end{align} $$

denn $0\mathbb{I}v = 0$, wir haben also nur eine Null subtrahiert und die Gleichung geht immernoch auf.

Die obige Gleichung sollte euch aber bekannt vorkommen! Wir erinnern uns an die Definition von Eigenwerten, sie sind die Nullstellen des charakteristischen Polynoms:

$$ det(A - \lambda\mathbb{I}v) = 0 $$

Die obige Gleichung sagt also, dass $0$ eine Nullstelle des charakteristischen Polynoms von $A$ ist und damit also auch ein Eigenwert von $A$. Das hatten wir ja aber im ersten Abschnitt bereits ausgeschlossen. Aus $det(A) = 0$ folgt also sofort, dass $\lambda=0$ ein Eigenwert von $A$ ist, und das bedeutet, dass $A$ nicht invertierbar sein kann.
