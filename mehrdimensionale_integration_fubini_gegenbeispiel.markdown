---
layout: page
title: Gegenbeispiel zum Satz von Fubini
nav: true
permalink: /mehrdimensionale-integrale-gegenbeispiel-zum-satz-von-fubini/
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

Wir kennen ja den Satz von Fubini (siehe [Mehrdimensionale Integration]({{ "/mehrdimensionale-integration/" | relative_url }})), der uns sagt, dass man für integrierbare Funktionen die Integrationsreihenfolge vertauschen kann. Hier wollen wir uns mal ein Beispiel anschauen, wo man es nicht vertauschen kann!

Gegeben sei folgendes Integral:

$$ \int_0^1 \int_0^1 \frac{x-y}{(x+y)^3} dx dy$$

Wir wollen dieses Integral ausrechnen, einmal indem wir zuerst nach x und dann nach y integrieren, und einmal anders herum.
<h3>Erst dx, dann dy</h3>
$$ \begin{align*} \int_0^1 \int_0^1 \frac{x-y}{(x+y)^3} dx dy &\stackrel{(1)}{=} \int_0^1 \int_y^{1+y} \frac{x-2y}{x^3} dx dy = \int_0^1 \left( \int_y^{1+y} \frac{1}{x^2} - \frac{2y}{x^3} dx \right) dy \\ &= \int_0^1 \left[ -\frac{1}{x} + \frac{y}{x^2} \right]_{x=y}^{1+y} dy =  \int_0^1 \left[ -\frac{1}{1+y} + \frac{y}{(1+y)^2} + \frac{1}{y} - \frac{y}{y^2} \right] dy  \\ &= \int_0^1 - \frac{1}{(1+y)^2} dy =  \left[ \frac{1}{1+y} \right]_{y=0}^1 = -\frac{1}{2} \end{align*} $$

Bei Gleichheitszeichen (1) ist hierbei die Transformation $u(x) = x+y$ eingegangen, sodass sich die Integralgrenzen des innteren Integrals um $ +y$ verschoben haben und $x$ durch $x-y$ ersetzt wurde. Da die Ableitung von diesem $u$ einfach nur $1$ ist, muss nichts mehr ranmultipliziert werden.
<h3>Erst dy, dann dx</h3>
Nun machen wir das ganze anders herum:

$$ \begin{align*} \int_0^1 \int_0^1 \frac{x-y}{(x+y)^3} dy dx &\stackrel{(1)}{=} \int_0^1 \int_x^{1+x} \frac{2x-y}{x^3} dy dx = \int_0^1 \left( \int_x^{1+x} \frac{2x}{y^3} - \frac{1}{y^2} dy \right) dx \\ &= \int_0^1 \left[ -\frac{x}{y^2} + \frac{1}{y} \right]_{y=x}^{1+x} dx =  \int_0^1 \frac{1}{(1+x)^2} dx  \\ &=  \left[ -\frac{1}{1+x} \right]_{x=0}^1 = \frac{1}{2} \end{align*} $$

Bei (1) haben wir wieder den Transformationssatz mit $u(y) = x+y$ benutzt. Der Schritt wird besonders klar, wenn man sich den Zähler mal als $x-y = 2x- (x+y)$ schreibt.

Insgesamt bekommen wir also bei unterschiedlicher Reihenfolge der Integration unterschiedliche Ergebnisse!
<h2>Ein Widerspruch zu Fubini?</h2>
Ist das nun ein Widerspruch zum Satz von Fubini? Nein, natürlich nicht. Aber warum geht das schief? Nun, unsere Funktion $f$ ist auf $[0,1]^2$ gar nicht integrierbar und damit ist die Voraussetzung für Fubini nicht erfüllt. Wie können wir zeigen, dass die Funktion nicht integrierbar ist?

Nun, dadurch, dass Fubini nicht aufgegangen ist, bedeutet schonmal, dass $f$ nicht integrierbar gewesen sein kann. Aber wie können wir es ohne Fubini zeigen? Eine Funktion $f$ ist integrierbar, wenn

$$ \iint_V |f| dxdy < \infty $$

Wie können wir zeigen, dass das für unser $f$ nicht der Fall ist? Das geht am besten, indem wir sie in einen Positiv- und einen Negativteil aufteilen, also den Bereich, wo $f \geq 0$ ist und den, wo $f \leq 0$ und die Integrale getrennt berechnen. Das Integral von $|f|$ ist dann die Summe der Beträge der beiden Integrale.

Probieren wir das einmal aus. Positiv- und Negativteile sind in unserem Beispiel also genau dort, wo $x \geq y $ oder umgekeht. Wir können nun also das gesamte Integral aufteilen in das Integral über den Negativteil plus dem Integral über den Positivteil:

$$ \int_0^1 \int_0^1 |f(x,y)|~ dx dy = \int_0^1 \int_y^1 f(x,y)~ dx dy ~ - \int_0^1 \int_0^y f(x,y)~ dx dy $$

(das Minus steht da, weil das Integral über den Negativteil natürlich negativ ist, und wir ja das Integral von $|f|$ haben wollen, also den negativen Teil als positiv zählen wollen.)

Bevor ihr weiterlest, macht euch klar, dass im zweiten Summanden x immer kleiner gleich y ist: Im Doppelintegral geht für y in äußeren Integral das x im inneren Integral genau von 0 bis y und nicht weiter! Die Grundfläche dieses Intgrals ist also ein Dreieck in der x-y-Ebene: Das Dreieck mit den Endpunkten (0,0), (0,1), (1,1). In jedem Punkt dieses Dreiecks gilt $x\leq y$ und damit also auch $f \leq 0$ ! Analog für das andere Integral, dort ist immer $f \geq 0$.

Rechnen wir diese beiden Integrale nun mal aus!
<h3>Negativteil</h3>
$$ \begin{align*} \int_0^1 \int_0^y \frac{x-y}{(x+y)^3} dx dy &\stackrel{(1)}{=} \int_0^1 \int_y^{2y} \frac{1-2y}{x^3} dx dy = \int_0^1 \left( \int_y^{2y} \frac{1}{x^2} - \frac{2y}{x^3} dx \right) dy \\ &= \int_0^1 \left[ -\frac{1}{x} + \frac{y}{x^2} \right]_{x=y}^{2y} dy =  \int_0^1 - \frac{1}{4y} dy  \\ &= [-\frac{1}{4} ln(y)]_{y=0}^1 \rightarrow - \infty \end{align*} $$

Hierbei ist in Gleichung (1) wieder die Transformation wie oben eingegangen.
<h3>Positivteil</h3>
$$ \begin{align*} \int_0^1 \int_y^1 \frac{x-y}{(x+y)^3} dx dy &= \int_0^1 \left[ -\frac{1}{x} + \frac{y}{x^2} \right]_{x=2y}^{1+y} dy =  \int_0^1 - \frac{1}{(1+y)^2} + \frac{1}{4y} dy  \\ &= [\frac{1}{1+y}+\frac{1}{4} ln(y)]_{y=0}^1  \rightarrow  \infty \end{align*} $$

Insgesamt ergibt sich also

$$ \iint_V |f| dxdy =  \infty - (-\infty) = \infty $$

$f$ ist also nicht integrierbar und Fubini damit nicht anwendbar. Kein Wunder also, dass wir am Anfang unterschiedliche Ergebnisse bekommen haben, wenn wir die Integrationsreihenfolge vertauscht haben.


# Weitere Artikel

[Mehrdimensionale Integration]({{ "/mehrdimensionale-integration/" | relative_url }})
