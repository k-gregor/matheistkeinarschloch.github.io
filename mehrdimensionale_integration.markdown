---
layout: page
title: Mehrdimensionale Integration
nav: true
permalink: /mehrdimensionale-integration/
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


Aus der Schule wissen wir, was das Integral einer Funktion $f$ ist: Die Fläche zwischen $f$ und der x-Achse. Dieses Konzept können wir auf mehrere Dimensionen übertragen, zum Beispiel auf eine Funktion $f: \mathbb{R}^2 \rightarrow \mathbb{R}$ und dort nicht die Fläche, sondern das Volumen zwischen $f$ und der x-y-Ebene berechnen. Für den Einstieg fangen wir gleich mit einem einfachen Beispiel an!

## Erklärung anhand eines Beispiels

Wir wollen das Volumen der Funktion $f(x,y) = 6x + 4xy + 2y^2 +2 $ im Bereich $[0; 1] \times [0;3]$ bestimmen, also über dem Rechteck mit $x\in[0;1]$ und $y\in[0;3]$.

Die folgende Grafik zeigt die Funktion und die Fläche über die wir integrieren wollen (falls ihr nichts seht, bitte Javascript aktivieren, oder Blocker deaktivieren!). Durch klicken und ziehen könnt ihr die Funktion aus verschiedenen Winkeln betrachten und durch Halten der Maus auf einen Gitterpunkt könnt ihr den Funktionswert an dieser Stelle angezeigt bekommen.


<link href="https://cdnjs.cloudflare.com/ajax/libs/vis/4.21.0/vis.min.css" rel="stylesheet" type="text/css" />
<script src="https://cdnjs.cloudflare.com/ajax/libs/vis/4.21.0/vis.min.js"></script>


<div id="mygraph"></div>

<script>
  function customFunction(x, y) {
    return (6*x + 4*x*y + 2*y*y + 2);
  }

  // Surface data (full grid)
  var surfaceData = [];
  var axisMin = 0;
  var axisMax = 3.5;
  var axisStep = 0.25;

  for (var x = axisMin; x < 2; x += axisStep) {
    for (var y = axisMin; y < axisMax; y += axisStep) {
      surfaceData.push({x: x, y: y, z: customFunction(x, y)});
    }
  }

  var surfaceDataset = new vis.DataSet(surfaceData);


  // Graph options
  var options = {
    width: '500px',
    height: '500px',
    style: 'surface',      // for surface dataset
    showPerspective: false,
    showGrid: true,
    keepAspectRatio: true,
    verticalRatio: 0.5,
    tooltip: true,
    xStep: 0.5
  };

  // Draw surface
  var graph = new vis.Graph3d(document.getElementById('mygraph'), surfaceDataset, options);


</script>

Wir können mal versuchen, das Volumen zwischen $f$ und der Fläche auf der x-y-Ebene abzuschätzen: Die Eckpunkte der Funktion über der Fläche sind (0,0,2), (0,3,20), (1,0,8) und (1,3,38). Die Grundfläche beträgt offensichtlich $3\cdot1 = 3$ und die Funktion ist über dieser Fläche gaaanz grob im Mittel so bei 15 würde ich sagen. Mal deutlich niedriger und mal deutlich höher, aber so ungefähr in diesem Bereich. Das Volumen unter $f$ müsste also in der Nähe von 45 liegen. (wie gesagt, das ist nur ganz grob. Wenn wir jetzt aber das Integral berechnen und 500 rauskommt, oder 2, dann wissen wir, dass da etwas nicht stimmen kann.

## Berechnung von mehrdimensionalen Integralen

Die Berechnung von mehrdimensionalen Integralen ist kaum schwieriger als von normalen Integralen. Man macht es einfach Schritt für Schritt: erst nach x integrieren, und dann nach y. Später werden wir sehen, dass es in der Regel keine Rolle spielt, welche Richtung wir zu erst nehmen. In diesem Beispiel beginnen wir mit der x-Richtung. Dabei behandeln wir y einfach wie eine Konstante und integrieren ganz normal nach x. D.h. zum Beispiel aus $xy$ wird nach x integriert $\frac{1}{2}x^2y$. Rechnen wir unser Beispiel einmal durch:

$$
\begin{align*}
\int_0^3 \int_0^1 6x + 4xy + 2y^2 +2 dx~ dy &amp;= \int_0^3 ( \int_0^1 6x + 4xy + 2y^2 +2 dx ) ~dy \\ &amp;= \int_0^3 [ 3x^2 + 2x^2y + 2xy^2 + 2x ]_{x=0}^1 ~dy \\ &amp;= \int_0^3 3 + 2y + 2y^2 + 2 ~dy \\ &amp;= [5y + y^2 + \frac{2}{3}y^3]_{y=0}^3 = 42
\end{align*}
$$

Passt also ganz gut zu unser obigen Schätzung.Vorhin habe ich kurz erwähnt, dass "in der Regel" egal ist, in welcher Reihenfolge wir das Integral berechnen. Was bedeutet "in der Regel"? Das sagt uns der Satz von Fubini:

## Der Satz von Fubini

Der Satz von Fubini sagt uns, wenn eines der beiden Integrale

$$
\int_a^b \int_c^d |f(x,y)| ~dx ~dy  \int_c^d \int_a^b |f(x,y)| ~dy ~dx
$$

existiert und endlich ist, dann existiert auch das jeweils andere, und es gilt:

$$
\int_a^b \int_c^d f(x,y) ~dx ~dy = \int_c^d \int_a^b f(x,y) ~dy ~dx
$$

wir können also die Integrationsreihenfolge vertauschen. Falls $f$ über der Integrationsfläche nichtnegativ ist, können wir übrigens immer die Integrationsreihenfolge vertauschen! Denn entweder es greift der Satz von Fubini, oder das Integral ist eben unendlich! (Im Falle einer Funktion, die auch mal negativ sein kann, geht es nicht! Siehe Beispiel <a href="http://matheistkeinarschloch.de/?page_id=385">"Gegenbeispiel zum Satz von Fubini"</a>)
<h4>Wann kann man also die Integrationsreihenfolge vertauschen?</h4>
<ul>
 	<li>Wenn $f$ über der Integrationsfläche nicht-negativ ist</li>
 	<li>Wenn $f$ eine "unkomplizierte Funktion" ist, also z.B. Polynome, Sinus, Cosinus, Exponentialfunktion etc.</li>
</ul>
<h4>Wann kann man die Integrationsreihenfolge nicht vertauschen?</h4>
<ul>
 	<li>Bei Funktionen, die im Integrationsbereich komplizierte Stellen haben, z.B. "durch Null teilen"</li>
 	<li>siehe Blog-Eintrag <a href="http://matheistkeinarschloch.de/?page_id=385">"Gegenbeispiel zum Satz von Fubini"</a></li>
</ul>
Für andere Arten von Funktionen, die nicht in diese Klassen fallen, muss man eben im Einzelfall die Voraussetzungen des Satzes von Fubini nachprüfen. Das wird einem aber eher selten aufkommen.

In unserem Fall liegt natürlich ein Polynom vor, es geht also problemlos und es kommt dasselbe heraus:

&nbsp;

$$
\begin{align*}
\int_0^1 \int_0^3 6x + 4xy + 2y^2 +2 dy~ dx &= \int_0^1 ( \int_0^3 6x + 4xy + 2y^2 +2 dy ) ~dx \\ &= \int_0^1 [ 6xy + 2xy^2 + \frac{2}{3}xy^3 + 2y ]_{y=0}^3 ~dx \\ &= \int_0^1 18x + 18x + 18 + 6 ~dx \\ &= [18x^2 + 24x ]_{x=0}^1 = 42
\end{align*}
$$

&nbsp;

<img class="aligncenter wp-image-788" src="{{ site.baseurl }}/assets/memes/meme_fubini.jpg" alt="Good Guy Fubini lässt dich die Integrationsreihenfolge vertauschen" width="400" height="400">

## Integrale mit nicht-rechteckigen Grundflächen

### Integrale mit dreieckigen Grundflächen

In den meisten Fällen berechnen wir ein Volumenintegral über einer rechteckigen Grundfläche. Was aber, wenn wir Integrale über Dreiecken oder Trapezen berechnen wollen? Nehmen wir zum Beispiel folgendes Beispiel, selbe Funktion, aber Dreieck als Grundfläche:

<div id="mygraph2" style="text-align: center;"><b>Wenn ihr hier nichts seht, Javascript aktivieren oder Blocker deaktivieren.</b></div>


Wie können wir diese Grundfläche beschreiben und darüber integrieren? Die Idee ist, eine Variable "normal laufen zu lassen", und die andere Variable anhand der ersten zu beschreiben. Wie sieht das hier aus? Wir lassen zum Beispiel y ganz normal von 0 bis 1 laufen. Wie muss sich dann x verhalten? Naja, wir sehen, wenn wir das Dreieck von oben betrachten, dass die Hypothenuse einfach eine lineare Funktion ist, und zwar: y=1-x! Wenn wir das nach x umformen haben wir also x = 1-y. Während y also von 0 bis 1 geht, geht x von 0 bis 1-y. (Probiert anhand einiger Punkte in der x-y-Ebene aus, dass das stimmt!). Diese Werte setzen wir also als Integralsgrenzen und rechnen das Integral "ganz normal" aus, wobei diesmal tatsächlich auch die Grenze von einer Variable abhängt. Das darf einen aber nicht verwirren, man setzt (1-y) dann ganz einfach als obere Grenze ein (Schritt (*) ) und rechnet weiter. Wir erhalten dann:

$$ \begin{align*}
\int_0^1 \int_0^{1-y} 6x+4xy+2y^2+2~dx~dy &= \int_0^1 [3x^2 + 2x^2y + 2xy^2+2x]_{x=0}^{(1-y)}~dy \\ &\stackrel{(*)}{=} \int_0^1 [3(1-y)^2 + 2(1-y)^2y + 2(1-y)y^2+2(1-y)]~dy \\ &= \int_0^1 5-6y+y^2 dy \\ &= [5y - 3y^2 + \frac{1}{3}y^3]_{y=0}^1 = 2,\overline{3}
\end{align*}$$

Als Übung könnt ihr das Integral über dem "Nachbardreieck" zwischen den drei Punkten (1,0), (0,1), (1,1) bestimmen. Die Lösung lautet:

$$ \int_0^1 \int_{1-y}^1 6x+4xy+2y^2+2~dx~dy = 4,\overline{3} $$

## Übungsaufgabe: Integral mit Trapez-Grundflächen

Versucht einmal, das Integral über folgender Grundfläche zu bestimmen:

<div id="mygraph3" style="text-align: center;"><b>Wenn ihr hier nichts seht, Javascript aktivieren oder Blocker deaktivieren.</b></div>

Herauskommen sollte $28,\overline{3}$.

### Lösung

Erster Schritt: Aufteilen des Trapez in ein Dreieck und ein Rechteck
Zweiter Schritt: Rechteck-Integral: Integral über [0,1]x[0,2] ergibt $19,\overline{3}$.
Dritter Schritt: Aufstellen des Dreiecksintegrals: Die Grenzen sind: y geht von 2 bis 3, während x von 0 bis 3-y geht. Das Integral über dem Dreieck hat Volumen 9.
Vierter Schritt: Zusammengerechnet also $19,\overline{3} + 9 = 28,\overline{3}$

