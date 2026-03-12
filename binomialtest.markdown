---
layout: page
title: Binomialtest
nav: true
permalink: /binomialtest/
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


In diesem Artikel soll es um den Binomialtest gehen, wie er funktioniert und wann er angewendet wird. Dazu machen wir zunächst nochmal einen kleinen Rückblick auf die Binomialverteilung.
<h3>Zur Erinnerung: Binomialverteilung</h3>
Wenn man $n$ Bernoulli-Experimente (Experimente mit zwei Ausgangsmöglichkeiten, "Treffer" und "Nicht-Treffer", und einer konstanten Trefferwahrscheinlichkeit $p$) hintereinander ausführt, so ist die Wahrscheinlichkeit, dass man genau $k$ Treffer bekommt:

$$ \mathbb{P}(X=k) = \begin{pmatrix} n \\ k \end{pmatrix} p^k (1-p)^{n-k} $$

In dieser Formel steht: genau $k$ Treffer ($p^k$), genau $n-k$ Nichttreffer, ($(1-p)^{n-k}$) und die Summe über alle möglichen Kombinationen davon($\begin{pmatrix} n \\ k \end{pmatrix}$). Schließlich kann man zunächst $k$ Treffer hintereinander machen und dann nur noch Nichttreffer landen, oder erst einen Treffer, dann keinen Treffer, dann wieder einen Treffer, oder oder oder. Schlicht, es gibt viele Möglichkeiten, genau $k$ Treffer zu landen. Der Faktor $\begin{pmatrix} n \\ k \end{pmatrix}$ enthält diese Möglichkeiten.

Die Binomialverteilung für $n=20$ sieht so aus:


<img src="{{ site.baseurl }}/assets/binomialverteilung.png" alt="Plot der Binomialverteilung, der Grundlage für den Binomialtest">


Ähnlich wie die Normalverteilung, im Gegensatz zu der geht es bei der Binomialverteilung nur um ganze, natürliche Zahlen.
<h3>Was ist ein Binomialtest und wann verwendet man ihn?</h3>
Mit einem Binomialtest kann man prüfen, ob eine Zufallsvariable $X$ auch wirklich binomialverteilt ist.
<h3>Wie funktioniert der Binomialtest - ein Beispiel</h3>
Wir fangen hier mit einem ganz leichten Beispiel für einen Binomialtest an: Jemand gibt uns eine Münze und behauptet, dies sei eine absolut faire Münze, d.h. die Wahrscheinlichkeit, dass bei einem Wurf "Zahl" oben liegt, ist genau $p=0,5$. Nun möchte dieser Jemand mit uns ein Spiel um Geld mit dieser Münze machen. Hier stellt sich die Frage: Ist diese Münze auch wirklich fair? Oder werden wir vielleicht über's Ohr gehauen? Mit einem Binomialtest können wir das prüfen.

Wie in jedem statistischen Test formulieren wir zunächst die Nullhypothese. Die Nullhypothese ist immer der "Regelfall", und wir wollen mit einer Stichprobe prüfen, ob diese Stichprobe sehr stark von diesem Regelfall abweicht. Das würde dann bedeuten, dass wir die Nullhypothese verwerfen.

In diesem Fall wäre die Nullhypothese also, dass die Wahrscheinlichkeit, "Zahl" (=Treffer) zu werfen, genau $p=0,5$ beträgt. Damit ist die Zufallsvariable, die zählt, wieviele Treffer in $n$ Würfen auftreten, gerade binomialverteilt. Die Wahrscheinlichkeit für $k$ Treffer in $n$ Würfen wäre also

$$ \mathbb{P}(X=k) = \begin{pmatrix} n \\ k \end{pmatrix} (0,5)^k (1-0,5)^{n-k} $$

Zum Beispiel ist die Wahrscheinlichkeit, bei 10 Würfen genau 5-mal "Zahl" zu bekommen

$$ \mathbb{P}(X=5) = \begin{pmatrix} 10 \\ 5 \end{pmatrix} (0,5)^5 (0,5)^{10-5} \approx 0,246  $$

Wenn nun also wirklich ein Typ zu uns kommt und uns ein solches Spiel vorschlägt, da sollten wir erst einmal testen, ob diese Münze denn auch wirklich fair ist! Wir werfen die Münze also mehrere Male und schreiben auf, wieviel mal sie mit "Zahl" oben landet. Wenn wir 20-Mal werfen, würden wir bei einer fairen Münze ja gerade den Erwartungswert erwarten, also 10 mal. Natürlich kann es aber auch ein bisschen abweichen, 9 oder 11 mal wäre natürlich auch sehr wahrscheinlich. 8 oder 12 auch noch. Aber was ist mit 7 und weniger oder 13 und mehr Treffern? Ab wann wird es ungewöhnlich? Das bestimmen wir mit diesem Test.
<h3>Der Test</h3>
Gegeben sei uns wie immer bei statistischen Tests ein Signifikanzniveau $\alpha$, in der Regel $\alpha = 0,05$. Zur Erinnerung, diese Zahl sagt: die Wahrscheinlichkeit, versehentlich die Nullhypothese zu verwerfen, obwohl sie wahr ist, darf höchstens 5% betragen. Mit höchstens 5% Wahrscheinlichkeit wollen wir also eine faire Münze fälschlicherweise als "unfair" bezeichnen. Unsere Stichprobe soll $n=20$ Würfe sein.

In unserem Fall haben wir offensichtlich einen zweiseitigen Test, schließlich würden wir sowohl zuviele "Zahl"-Würfe, als auch zu wenige als unglaubwürdig einschätzen. Die tatsächliche Zahl sollte nahe bei 10 sein, also der Hälfte der Würfe in unserem Test. Ist sie das nicht, verwerfen wir die Nullhypothese und sagen: "Diese Münze ist nicht fair".
<h3>Bestimmen des kritischen Werts</h3>
Wir bestimmen nun die Wahrscheinlichkeit, dass wir unter der Nullhypothese (also mit einer fairen Münze) genau $c_1$ oder weniger Treffer, oder $c_2$ Treffer oder mehr bekommen. Das ist gerade die Summe der einzelnen möglichen Ausgänge:

$$ \mathbb{P}(X \leq  c_1) + \mathbb{P}(X \geq c_2) = \sum_{k=0}^{c_1} \begin{pmatrix} 20 \\ k \end{pmatrix} 0,5^k 0,5^{20-k} + \sum_{k=c_2}^{20} \begin{pmatrix} 20 \\ k \end{pmatrix} 0,5^k 0,5^{20-k} $$

Beide Summanden müssen kleiner sein als $\alpha/2$. Denn wir erlauben nur kleine Ausreißer nach oben und unten. Damit können wir $c_1$ und $c_2$ bestimmen:
<h4>Bestimmen von $c_1$</h4>
$$ \mathbb{P}(X \leq  c_1)  = \sum_{k=0}^{c_1}\begin{pmatrix} 20 \\ k \end{pmatrix} 0,5^k 0,5^{20-k} = binom(0,5; c_1; 20) \leq 0,025 $$

Aus einer Tabelle der <em>kumulierten Binomialverteilung </em><a href="http://www.mathematik-oberstufe.de/stochastik/download/binomialverteilung-tabellen-n10-20-50.pdf" target="_blank">(siehe z.B. hier)</a> können wir nun den Wert von c_1 ablesen. Wir suchen die Tabelle für $n=20$ heraus und schauen nach dem Eintrag in der Spalte für $p=0,5$, wann die 0,025 gerade noch nicht überschritten werden. Beachtet, dass in der Tabelle nur die Nachkommastellen angegeben sind, die "0," hat man sich gespart. Wir erhalten $binom(0,5;5;20) = 0,0207 < 0,025$. D.h. für den ersten kritischen Wert gilt $c_1=5$
<h4>Bestimmen von $c_2$</h4>
Für $c_2$ müssen wir einen kleinen "Trick" anwenden: Die Tabelle können wir nämlich nur für Wahrscheinlichkeiten der Art $\mathbb{P}(X \leq k)$ anwenden, nicht $\mathbb{P}(X \geq k)$. Aber wir können die <em>Gegenwahrscheinlichkeit</em> benutzen:

$$ \mathbb{P}(X \geq c_2) = 1 - \mathbb{P}(X \leq c_2-1) \leq 0,025 \Leftrightarrow \mathbb{P}(X \leq c_2-1) \geq 0,975$$

Wir suchen also den Wert in der Tabelle (wieder in der Spalte $p=0,5$ natürlich), an dem wir die 0,975 überschreiten, das ist bei $14$ der Fall. Das heißt also, $c_2=15$ (Ja, 15. Nicht 14!).
<h3>Ergebnis:</h3>
Wenn wir 20 Würfe mit der angeblich fairen Münze machen, und wir erhalten zwischen 6 und 14 mal "Zahl", dann verwerfen wir die Nullhypothese nicht und sagen: Okay, die Münze scheint fair zu sein. Bei 5 und weniger, bzw 15 und mehr "Zahl"-Würfen verwerfen wir die Nullhypothese und sagen, die Münze ist nicht fair, denn es ist sehr unwahrscheinlich, dass eine faire Münze eine solche Trefferzahl hervorbringt.
<h3>Eine kleine Probe</h3>
Um noch einmal kurz zu zeigen, dass unsere Berechnung tatsächlich sinnvoll war, möchte ich noch einmal kurz folgendes ausrechnen: Die Wahrscheinlichkeiten aller Trefferzahlen, bei denen wir ablehnen würden, also genau die Formel von oben, $ \mathbb{P}(X \leq  c_1) + \mathbb{P}(X \geq c_2) $. Wenn wir all diese zusammenrechnen, müssen wir bei einem Wert unter 0,05 rauskommen, denn das war ja unser Ziel: Einen Ablehnungsbereich aufstellen, deren Ergebnisse insgesamt höchstens 5% wahrscheinlich sind. Also:
<ul>
	<li>$\mathbb{P}(X = 0) = \begin{pmatrix} 20 \\ 0 \end{pmatrix} (0,5)^0 (0,5)^{20} \approx 0,0000\ldots $</li>
	<li>$\mathbb{P}(X = 1) = \begin{pmatrix} 20 \\ 1 \end{pmatrix} (0,5)^1 (0,5)^{19} \approx 0,0000\ldots $</li>
	<li>$\mathbb{P}(X = 2) = \begin{pmatrix} 20 \\ 2 \end{pmatrix} (0,5)^2 (0,5)^{18} \approx 0,0002 $</li>
	<li>$\mathbb{P}(X = 3) = \begin{pmatrix} 20 \\ 3 \end{pmatrix} (0,5)^3 (0,5)^{17} \approx 0,0011 $</li>
	<li>$\mathbb{P}(X = 4) = \begin{pmatrix} 20 \\ 4 \end{pmatrix} (0,5)^4 (0,5)^{16}\approx 0,0046 $</li>
	<li>$\mathbb{P}(X = 5) = \begin{pmatrix} 20 \\ 5 \end{pmatrix} (0,5)^5 (0,5)^{15} \approx 0,0148 $</li>
</ul>
Das bedeutet schon einmal: 5 oder weniger Treffer zu bekommen, ist insgesamt nur etwa 0,0207, also 2,07% wahrscheinlich! Wenn wir noch den sechsten Treffer zum Ablehnungsbereich dazunähmen, kämen wir aber auf:
<ul>
	<li>$\mathbb{P}(X = 6) = \begin{pmatrix} 20 \\ 6 \end{pmatrix} (0,5)^6 (0,5)^{14} \approx 0,0370 $</li>
</ul>
Das heißt, diesen Wert dürfen wir tatsächlich nicht in unseren Ablehnungsbereich mit hineinnehmen, da wir sonst die 0,025% für die linke Seite überschreiten würden.

Da die Binomialverteilung symmetrisch ist, würden wir dieselben Ergebnisse für die rechte Seite bekommen: Die Wahrscheinlichkeit für 15 oder mehr treffer, beträgt auch 2,07%.

Insgesamt haben wir also tatsächlich ein Ablehnungkriterium besitmmt, was in weniger als 5% der Fälle fälschlicherweise eine faire Münze als unfair bezeichnen würde.
<h2>Übungsaufgabe zum Binomialtest</h2>
Ihr stellt eine Matheklausur mit 20 Multiple-Choice-Fragen mit jeweils 4 Antworten mit nur einer richtigen Antwort pro Frage. Bei einem Signifikanzniveau von 5%, ab welcher Punktzahl würdet ihr behaupten, dass jemand, der diese Klausur schreibt, wirklich gelernt hat und nicht nur zufällig angekreuzt hat?
