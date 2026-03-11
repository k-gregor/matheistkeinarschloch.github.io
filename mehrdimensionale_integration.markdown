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



<div id="mygraph" style="width:600px;height:500px;"></div>

<script src="https://cdn.plot.ly/plotly-2.30.0.min.js"></script>

<script>
function f(x,y){
  return 6*x + 4*x*y + 2*y*y + 2;
}

var step = 0.25;

var x = [];
var y = [];
var z = [];

for (var xi = 0; xi <= 2; xi += step) x.push(xi);
for (var yi = 0; yi <= 3.5; yi += step) y.push(yi);

for (var i = 0; i < y.length; i++){
  var row = [];
  for (var j = 0; j < x.length; j++){
    row.push(f(x[j], y[i]));
  }
  z.push(row);
}

var surface = {
  type: "surface",
  x: x,
  y: y,
  z: z,
  hovertemplate: "x=%{x}<br>y=%{y}<br>z=%{z}<extra></extra>"
};



// shaded rectangle
var rect_x = [0,1];
var rect_y = [0,3];
var rect_z = [
  [0,0],
  [0,0]
];

var rectangle = {
  type: "surface",
  x: rect_x,
  y: rect_y,
  z: rect_z,
  opacity:0.75,
  showscale: false,
  colorscale: [[0,"gray"],[1,"gray"]],
  hoverinfo: "skip"
};

var layout = {
  width: 600,
  height: 500,
  scene: {
    xaxis: {title:"x", showspikes:false},
    yaxis: {title:"y", showspikes:false},
    zaxis: {title:"z", showspikes:false}
  }
};

Plotly.newPlot("mygraph", [surface, rectangle], layout, {
  displayModeBar: false
});
</script>

Wir können mal versuchen, das Volumen zwischen $f$ und der Fläche auf der x-y-Ebene abzuschätzen: Die Eckpunkte der Funktion über der Fläche sind (0,0,2), (0,3,20), (1,0,8) und (1,3,38). Die Grundfläche beträgt offensichtlich $3\cdot1 = 3$ und die Funktion ist über dieser Fläche gaaanz grob im Mittel so bei 15 würde ich sagen. Mal deutlich niedriger und mal deutlich höher, aber so ungefähr in diesem Bereich. Das Volumen unter $f$ müsste also in der Nähe von 45 liegen. (wie gesagt, das ist nur ganz grob. Wenn wir jetzt aber das Integral berechnen und 500 rauskommt, oder 2, dann wissen wir, dass da etwas nicht stimmen kann.

## Berechnung von mehrdimensionalen Integralen

Die Berechnung von mehrdimensionalen Integralen ist kaum schwieriger als von normalen Integralen. Man macht es einfach Schritt für Schritt: erst nach x integrieren, und dann nach y. Später werden wir sehen, dass es in der Regel keine Rolle spielt, welche Richtung wir zu erst nehmen. In diesem Beispiel beginnen wir mit der x-Richtung. Dabei behandeln wir y einfach wie eine Konstante und integrieren ganz normal nach x. D.h. zum Beispiel aus $xy$ wird nach x integriert $\frac{1}{2}x^2y$. Rechnen wir unser Beispiel einmal durch:

$$
\begin{align*}
\int_0^3 \int_0^1 6x + 4xy + 2y^2 +2 dx~ dy &= \int_0^3 ( \int_0^1 6x + 4xy + 2y^2 +2 dx ) ~dy \\ &= \int_0^3 [ 3x^2 + 2x^2y + 2xy^2 + 2x ]_{x=0}^1 ~dy \\ &= \int_0^3 3 + 2y + 2y^2 + 2 ~dy \\ &= [5y + y^2 + \frac{2}{3}y^3]_{y=0}^3 = 42
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

wir können also die Integrationsreihenfolge vertauschen. Falls $f$ über der Integrationsfläche nichtnegativ ist, können wir übrigens immer die Integrationsreihenfolge vertauschen! Denn entweder es greift der Satz von Fubini, oder das Integral ist eben unendlich! (Im Falle einer Funktion, die auch mal negativ sein kann, geht es nicht! Siehe Beispiel ["Gegenbeispiel zum Satz von Fubini"]({{ "/mehrdimensionale-integrale-gegembeispiel-zum-satz-von-fubini/" | relative_url }}))


<h4>Wann kann man also die Integrationsreihenfolge vertauschen?</h4>
<ul>
 	<li>Wenn $f$ über der Integrationsfläche nicht-negativ ist</li>
 	<li>Wenn $f$ eine "unkomplizierte Funktion" ist, also z.B. Polynome, Sinus, Cosinus, Exponentialfunktion etc.</li>
</ul>
<h4>Wann kann man die Integrationsreihenfolge nicht vertauschen?</h4>
<ul>
 	<li>Bei Funktionen, die im Integrationsbereich komplizierte Stellen haben, z.B. "durch Null teilen"</li>
 	<li>siehe Blog-Eintrag ["Gegenbeispiel zum Satz von Fubini"]({{ "/mehrdimensionale-integrale-gegembeispiel-zum-satz-von-fubini/" | relative_url }}))</li>
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

<img src="{{ site.baseurl }}/assets/memes/meme_fubini.jpg" alt="Good Guy Fubini lässt dich die Integrationsreihenfolge vertauschen" width="400" height="400">

## Integrale mit nicht-rechteckigen Grundflächen

### Integrale mit dreieckigen Grundflächen

In den meisten Fällen berechnen wir ein Volumenintegral über einer rechteckigen Grundfläche. Was aber, wenn wir Integrale über Dreiecken oder Trapezen berechnen wollen? Nehmen wir zum Beispiel folgendes Beispiel, selbe Funktion, aber Dreieck als Grundfläche:



<div id="plot" style="width:800px;height:600px;"></div>

<script>


const n = 60;
const xs = [];
const ys = [];
const zs = [];

for (let i=0;i<=n;i++){
  xs.push(i/n);
  ys.push(i/n);
}

for (let i=0;i<=n;i++){
  const row=[];
  for (let j=0;j<=n;j++){
    row.push(f(xs[j],ys[i]));
  }
  zs.push(row);
}

const surface2 = {
  type:'surface',
  x:xs,
  y:ys,
  z:zs,
  colorscale:'Viridis',
  opacity:0.75,
  hoverinfo:'x+y+z'
};

const triangle2 = {
  type:'mesh3d',
  x:[0,1,0],
  y:[0,0,1],
  z:[0,0,0],
  i:[0],
  j:[1],
  k:[2],
  color:'gray',
  opacity:0.75,
  hoverinfo:'skip'
};


Plotly.newPlot('plot',[surface2,triangle2],layout);

</script>





Wie können wir diese Grundfläche beschreiben und darüber integrieren? Die Idee ist, eine Variable "normal laufen zu lassen", und die andere Variable anhand der ersten zu beschreiben. Wie sieht das hier aus? Wir lassen zum Beispiel y ganz normal von 0 bis 1 laufen. Wie muss sich dann x verhalten? Naja, wir sehen, wenn wir das Dreieck von oben betrachten, dass die Hypothenuse einfach eine lineare Funktion ist, und zwar: y=1-x! Wenn wir das nach x umformen haben wir also x = 1-y. Während y also von 0 bis 1 geht, geht x von 0 bis 1-y. (Probiert anhand einiger Punkte in der x-y-Ebene aus, dass das stimmt!). Diese Werte setzen wir also als Integralsgrenzen und rechnen das Integral "ganz normal" aus, wobei diesmal tatsächlich auch die Grenze von einer Variable abhängt. Das darf einen aber nicht verwirren, man setzt (1-y) dann ganz einfach als obere Grenze ein (Schritt (*) ) und rechnet weiter. Wir erhalten dann:

$$ \begin{align*}
\int_0^1 \int_0^{1-y} 6x+4xy+2y^2+2~dx~dy &= \int_0^1 [3x^2 + 2x^2y + 2xy^2+2x]_{x=0}^{(1-y)}~dy \\ &\stackrel{(*)}{=} \int_0^1 [3(1-y)^2 + 2(1-y)^2y + 2(1-y)y^2+2(1-y)]~dy \\ &= \int_0^1 5-6y+y^2 dy \\ &= [5y - 3y^2 + \frac{1}{3}y^3]_{y=0}^1 = 2,\overline{3}
\end{align*}$$


## Übungsaufgabe 1: Integral über einem anderen Dreieck

Als Übung könnt ihr das Integral über dem "Nachbardreieck" zwischen den drei Punkten (1,0), (0,1), (1,1) bestimmen. Die Lösung lautet:

$$ \int_0^1 \int_{1-y}^1 6x+4xy+2y^2+2~dx~dy = 4,\overline{3} $$

## Übungsaufgabe 2: Integral mit Trapez-Grundflächen

Versucht einmal, das Integral über folgender Grundfläche zu bestimmen:




<div id="plottrapezoid" style="width:800px;height:600px;"></div>

<script src="https://cdn.plot.ly/plotly-latest.min.js"></script>
<script>


const region3 = {
  type:'mesh3d',

  // vertices in boundary order
  x:[0,0,1,1],
  y:[0,3,2,0],
  z:[0,0,0,0],

  // triangles
  i:[0,0],
  j:[1,2],
  k:[2,3],

  color:'gray',
  opacity:0.6,
  hoverinfo:'skip'
};


Plotly.newPlot('plottrapezoid',[surface,region3],layout);

</script>





Herauskommen sollte $28,\overline{3}$.

### Lösung

Erster Schritt: Aufteilen des Trapez in ein Dreieck und ein Rechteck
Zweiter Schritt: Rechteck-Integral: Integral über [0,1]x[0,2] ergibt $19,\overline{3}$.
Dritter Schritt: Aufstellen des Dreiecksintegrals: Die Grenzen sind: y geht von 2 bis 3, während x von 0 bis 3-y geht. Das Integral über dem Dreieck hat Volumen 9.
Vierter Schritt: Zusammengerechnet also $19,\overline{3} + 9 = 28,\overline{3}$

