---
layout: page
title: Mehrdimensionales Ableiten
nav: true
permalink: /mehrdimensionales-ableiten/
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


Was eine Ableitung ist, wissen wir bereits aus der Schule: Steigungsdreieck und so weiter. Wir haben auch schon Ableitungsregeln kennen gelernt, mit deren Hilfe wir für eine Funktion f(x) die Ableitung f'(x) bestimmen können. f'(x) gibt uns dann für jeden x-Wert die Steigung in diesem Punkt.

Das ganze wollen wir jetzt auf Funktionen in mehreren Dimensionen übertragen, nämlich für Funktionen der Form

$$ f : \mathbb{R}^2 \rightarrow \mathbb{R} $$

Das ganze lässt sich dann sofort auch Funktionen in noch mehr Dimensionen übertragen, also

$$ f : \mathbb{R}^n \rightarrow \mathbb{R}, n > 2 $$

aber wir bleiben der Anschaulichkeit halber bei zwei Eingangsvariablen x und y.
<h2>Mehrdimensionales Ableiten - Erklärung an einem Beispiel</h2>
Wir betrachten die Funktion

$$ f(x,y) = 5x^2 + 2xy^2 + 2y + 3 $$

welche in folgender interaktiver Graphik dargestellt ist (klicken und ziehen für andere Perspektive, Maus über Gitterpunkt für Infos, mit zwei Fingern hoch bzw. runter zum Zoomen):

<div id="mygraph" style="width:600px;height:500px;"></div>

<script src="https://cdn.plot.ly/plotly-2.30.0.min.js"></script>

<script>
function f(x,y){
  return 5*x*x + 2*x*y*y + 2*y + 3;
}

var step = 0.25;

var x = [];
var y = [];
var z = [];

for (var xi = -6; xi <= 6; xi += step) x.push(xi);
for (var yi = -6; yi <= 6; yi += step) y.push(yi);

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




var layout = {
  width: 600,
  height: 500,
  scene: {
    xaxis: {title:"x", showspikes:false},
    yaxis: {title:"y", showspikes:false},
    zaxis: {title:"z", showspikes:false}
  }
};

Plotly.newPlot("mygraph", [surface], layout, {
  displayModeBar: false
});
</script>


<h2>Von f' zur Richtungsableitung</h2>
Im eindimensionalen war alles einfach, wir hatten unser f' und konnten die Steigung in jedem Punkt ausrechnen, es gab nur eine Richtung, nämlich die x-Richtung. War $f'(x)$ an einer Stelle positiv, hieß es, an dieser Stelle geht es in x-Richtung bergauf, war $f'(x)$ an einer Stelle negativ, so hieß es, dass es an dieser Stelle in x-Richtung bergab ging.

Nun aber haben wir nicht nur eine x-Richtung, sondern auch noch die y-Richtung und unendlich viele Kombinationen davon! In welche Richtung sollen wir jetzt das Steigungsdreieck anlegen? Die Richtung muss vorgegeben sein! Daher kommt anstelle einer einfachen Ableitung nun zunächst die Richtungsableitung an der Stelle $p=(x,y)$ in Richtung des Vektors $v$:

$$ D_vf(p) = \lim_{h\rightarrow 0} \frac{f(p+h\cdot v) - f(p)}{h} $$

Das sollte euch gleich bekannt vorkommen, denn es ist nichts anderes als die normale Formel für die Ableitung, bloß mit einem Richtungsvektor $v$! Denn wie gesagt, haben wir nun mehrere Richtungen, in die wir ableiten können.
<h3>Beispiel für die Berechnung einer Richtungsableitung</h3>
Nehmen wir zum Beispiel den Punkt $ p=(0,1) $ und die Richtung $ v = (1,1) $. Wie steil geht es von $ p $ in Richtung $ v $?

$$ \begin{align*}
D_{(1,1)}f(0,1) &= \lim_{h\rightarrow0}\frac{f((0,1)+h\cdot(1,1))-f(0,1)}{h} = \lim_{h\rightarrow0}\frac{f((h,1+h))-f(0,1)}{h} \\&= \lim_{h\rightarrow0}\frac{\left[5h^2+2h(1+h)^2+2(1+h)+3\right]-\left[5\cdot0^2+2\cdot0\cdot1^2+2\cdot1+3\right]}{h} \\
&= \lim_{h\rightarrow0}\frac{2h^3+9h^2+4h}{h} = \lim_{h\rightarrow0}\frac{h(2h^2+9h+4)}{h} = \lim_{h\rightarrow0}2h^2+9h+4 = 4
\end{align*} $$

Die Steigung in Punkt p in Richtung v beträgt also 4. Wenn ihr mal in der Graphik oben die Maus auf den Punkt (0,1) setzt, seht ihr, dass dort der Funktionswert 5 beträgt. Wenn wir einen Schritt in Richtung v gehen, kommen wir an die Stelle (1,2), wo der Funktionswert 20 beträgt. Dies scheint zunächst ein bisschen hoch, man würde dort vielleicht eher einen Wert erwarten, der in der Nähe von 5+4=9 liegt. Allerdings haben wir ja die Richtungsableitung genau im Punkt (0,1) berechnet, und man sieht, dass die Funktion dort noch vergleichsweise flach ist und dann aber bald stärker ansteigt. (Wir erinnern uns daran, dass die Ableitung immer etwas lineares ist - Stichwort Tangente - unsere Funktion allerding quadratisch ansteigt)
<h2>Von der Richtungsableitung zur partiellen Ableitung</h2>
Von besonderem Interesse sind nun die Richtungsableitungen in x- und y-Richtung, sprich die Richtungsableitungen in Richtung $ v = (1,0) $ oder $ v=(0,1) $, auch <strong>partielle Ableitungen</strong> genannt und bekommen eine eigene Schreibweise, so schreibt man für die partielle Ableitung in x-Richtung $\frac{\partial f}{\partial x}f(x,y)$. Schauen wir uns das mal beispielhaft für die x-Richtung in einem beliebigen Punkt (x,y) an:

$$ \begin{align*} \frac{\partial f}{\partial x}(x,y) &=  D_{(1,0)}f(x,y) = \lim_{h\rightarrow0}\frac{f((x,y)+h(1,0))-f(x,y)}{h} \\ &= \lim_{h\rightarrow0}\frac{f(x+h,y)-f(x,y)}{h} = \cdots \end{align*} $$

Die Ableitung hängt gar nicht von y ab, nur der in der x-Koordinate hängt das h mit drin. Wenn wir das jetzt mal weiterrechnen, merken wir, dass viele Summanden wegfallen:

$$ \begin{align*} \cdots &= \lim_{h\rightarrow0}\frac{\left[ 5(x+h)^2 + 2(x+h)y^2 +2y +3 \right] - \left[5x^2 +2xy^2 +2y +3\right]}{h} \\ &= \lim_{h\rightarrow0}\frac{10xh +5h^2 +2y^2h}{h} = \lim_{h\rightarrow0}10x +5h +2y^2 = 10x +2y^2 \end{align*} $$

Wenn wir diese allgemeine Richtungsableitung jetzt mit der Ausgangsfunktion vergleichen, sollte etwas auffallen! Die Richtungsableitung in x-Richtung entspricht genau dem was wir bekommen, wenn wir die Funktion f ganz normal nach x ableiten und das y einfach als Konstante sehen! Dies ist einer der zentralen Punkte beim Ableiten in mehreren Dimensionen: <strong>Die partiellen Ableitungen entsprechen gerade der ganz normalen Ableitung nach der entsprechenden Variable, wobei die anderen Variablen als Konstanten aufgefasst werden.</strong> Ist ja auch irgendwie verständlich: Die partielle Ableitung in x-Richtung hat ja eben überhaupt nichts mit der y-Richtung zu tun. Es ist wie wenn wir in der Graphik oben die Funktion nur entlang eines "Gitterstrangs" betrachten, wo der y-Wert immer gleich ist, das ist einfach wie eine ganz normale eindimensionale Funktion.

Dementsprechend können wir die partielle Ableitung nach y bilden:

$$ \frac{\partial f}{\partial y}(x,y) = 4xy +2 $$
<h2>Der Gradient</h2>
Der Gradient von $f$, geschrieben $\nabla f$, ist einfach der Spaltenvektor der partiellen Ableitungen:

$$ \nabla f(x,y) = \begin{pmatrix}  \frac{\partial f}{\partial x}(x,y)  \\  \frac{\partial f}{\partial y}(x,y) \end{pmatrix} $$

Im letzten Beispiel also:

$$ \nabla f(x,y) = \begin{pmatrix} 10x +2y^2 \\ 4xy +2 \end{pmatrix} $$
<h2>Das totale Differential</h2>
Das totale Differential von f, bezeichnet mit $df$ ist nun eine Funktion, die uns im Prinzip alle Informationen zur Ableitung von f zusammenfasst. Zugegeben, es sieht etwas komisch aus, aber wenn man genau darüber nachdenkt, was es bedeutet, ist es gar nicht so schwer. Schauen wir uns zunächst die Definition an:

$$ df(x,y) = \frac{\partial f}{\partial x}(x,y)dx + \frac{\partial f}{\partial y}(x,y)dy $$

Häh? Und was soll das heißen? Naja, die partiellen Ableitungen kennen wir ja schon und haben wir schon ausgerechnet. Die können wir ja mal einsetzen und schauen, was rauskommt:

$$ df(x,y) = (10x+2y^2)dx + (4xy +2)dy $$

Irgendwie immernoch komisch. Was bedeutet überhaupt das $dx$ und $dy$? Naja, $dx$ steht einfach für "Größe des Schritts in x-Richtung" und $dy$ entsprechend für "Größe des Schrittes in y-Richtung". Will heißen: Wenn ich einen Punkt p=(x,y) habe sowie eine Richtung (dx, dy) in die ich gehen will, dann sagt mir das totale Differential, wie steil es an dieser Stelle in genau diese Richtung ist. Naja, und drei Mal dürft ihr raten, was rauskommt, wenn wir wie vorhin p=(0,1) und (dx, dy) = (1,1) nehmen! Das totale Differential in (0,1) lautet

$$ df(0,1) = 2dx + 2dy $$

und für dx=1 und dy=1 erhalten wir genau 4, was wir vorher schon bei der Richtungsableitung berechnet haben.

Wir können uns also das bestimmen von Richtungsableitungen sparen, indem wir einfach nur die partiellen Ableitungen bestimmen und mittels des totalen Differentials die Richtungsableitungen in bestimmte Richtungen ablesen können.

Um da Beispiel abzuschließen, könnt ihr die letzte Aussage nochmal überprüfen, in dem ihr die Richtungsableitung in $p=(2,1)$ in Richtung $v=(-1,1)$ bestimmt und es mit dem totalen Differential vergleicht. Ihr solltet erhalten:

$$ \begin{align*} D_{(-1,1)}(2,1) &= -12 \\ df(2,1) &= 22dx+10dx \end{align*} $$

und das wenn wir für (dx,dy) dieselbe Richtung nehmen, kommt dort auch wieder -12 raus!
