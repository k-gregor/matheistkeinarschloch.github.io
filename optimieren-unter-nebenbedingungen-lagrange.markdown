---
layout: page
title: Optimieren unter Nebenbedingungen (Lagrange)
nav: true
permalink: /optimieren-unter-nebenbedingungen-lagrange/
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

<h2>Wozu das ganze?</h2>
Optimieren unter Nebenbedingungen hat große Relevanz für schier unendlich viele wissenschaftliche Gebiete. Gut erklären lässt es sich im Wirtschaftsbereich, weil es dort sehr anschaulich ist: Wir haben eine Funktion, die von einigen Variablen abhängt, beispielsweise vom Geld und von der Arbeitszeit. Diese Funktion spuckt uns dann zum Beispiel in Abhängigkeit von diesen beiden Variablen unseren Gewinn aus. Wir wollen nun unseren maximalen Gewinn ausrechnen, haben aber feste Bedingungen an unsere Variablen: Wir haben schlicht und ergreifend nur eine begrenzte Menge an Geld, und auch unendlich viel arbeiten können wir nicht.
<h2>Erklärung an einem Beispiel</h2>
Wie können wir nun eine Funktion optimieren während wir Nebenbedingungen beachten? Schauen wir uns das ganze an einem Beispiel an:

$$ \begin{align*} \mbox{maximiere} ~ f(x,y) = -2x^2 +12x -y^2 +8y -4 \\ \mbox{unter der Nebenbedingung} ~ x+y=2 \end{align*} $$

Wir schauen uns die Funktion mal in einer Visualisierung zusammen mit der Nebenbedingung an. Die Nebenbedingung stellt nur Anforderungen an x und y und ist in x-y-Ebene gezeichnet (schwarz). Uns interessieren nun alle Punkte $(x,y,f(x,y))$, die direkt über der Nebenbedingungslinie liegen und suchen denjenigen Punkt, wo der z-Wert am höchsten ist. Wir schieben also gedanklich die Nebenbedingungslinie nach oben und betrachten die Schnittpunkte mit f. Was man sieht, ist dass der höchste Schnittpunkt genau dort, ist, wo die verschobene Nebenbedingungslinie gerade eine Tangente zu f ist (graue Linie). Höher geht es nicht, denn darüber findet man keinen Schnittpunkt von f und der Nebenbedingung! Der Tangentialpunkt ist also genau der, den wir suchen. (In der Graphik: Klicken, halten und ziehen zum verschieben in alle Richtungen, Maus über Gitterpunkt für Funktionswerte).
Wenn ihr über den Berührungspunkt geht, solltet ihr erkennen, dass der irgendwo in der Nähe von (1.5, 0.5, 13.25) liegt.


<div id="mygraph" style="width:600px;height:500px;"></div>

<script src="https://cdn.plot.ly/plotly-2.30.0.min.js"></script>

<script>
function f(x,y){
  return -2 * (x - 3) * (x - 3) - (y - 4) * (y - 4) + 30;
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


const constraint = {
  type: 'scatter3d',
  mode: 'lines',
  x: [-8, 10],
  y: [10, -8],
  z: [-250, -250],
  line: {
    color: 'black',
    width: 6
  },
  hoverinfo: 'skip',
  showlegend: false
};



const constraint_shifted = {
  type: 'scatter3d',
  mode: 'lines',
  x: [-8, 10],
  y: [10, -8],
  z: [13.3333, 13.33333],
  line: {
    color: 'black',
    width: 6
  },
  opacity: 0.5,
  hoverinfo: 'skip',
  showlegend: false
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

Plotly.newPlot("mygraph", [surface, constraint, constraint_shifted], layout, {
  displayModeBar: false
});
</script>



<h2>Von der Vorüberlegung zur Lagrange-Funktion</h2>
Wie können wir nun diesen Punkt finden, an dem die Nebenbedingung tangential zur Funktion verläuft? Schauen wir uns die Höhenlinien der Funktion an, die in folgendem Bild dargestellt sind. Alternativ kann man sich in der interaktiven Visualisierung die Funktion von ganz oben ansehen, dann sieht man quasi auch die Höhenlinien durch die verschiedenen Farbschattierungen.


<img src="{{ site.baseurl }}/assets/finalContour.png" alt="Höhenlinien">


Wenn wir uns die Nebenbedingung als Funktion denken, also quasi g(x,y) = x+y, dann suchen wir genau den Punkt, in welchem der Gradient von f ein vielfaches vom Gradienten von g ist, also $ \nabla f(x,y) = \lambda \nabla g(x,y) $, wie im Bild. Das reicht aber noch nicht aus, denn es gibt viele Punkte, an denen dies gilt. Wir wollen natürlich nur denjenigen finden, der gleichzeitig auch auf der Nebenbedinungslinie liegt, also $ g(x,y) = c $ (im Beispiel ist c=2) muss natürlich weiterhin erfüllt sein. Und genau das macht ja auch eine Tangente im Punkt p aus: der Tangente und Funktion müssen in p denselben Funktionswert haben, und die Steigung muss auch stimmen. Unsere Bedingungen sind also zusammengefasst:

$$ \begin{align*} \nabla f(x,y) &= \lambda \nabla g(x,y) \\ g(x,y) = c \end{align*} $$

Diese Bedingungen kann man sehr schön zusammenfassen, wenn man die so genannte Lagrange-Funktion aufschreibt, welche lautet:

$$ \mathscr{L}(x,y,\lambda) = f(x,y) - \lambda(g(x,y) - c) $$

Denn: wenn wir diese Funktion ableiten und gleich Null setzen, bekommen wir:

$$ \nabla\mathscr{L}(x,y,\lambda) = \begin{pmatrix} \nabla_x \mathscr{L}(x,y,\lambda) \\ \nabla_y \mathscr{L}(x,y,\lambda) \\ \nabla_\lambda \mathscr{L}(x,y,\lambda) \end{pmatrix} = \begin{pmatrix} \nabla f(x,y) - \lambda \nabla g(x,y) \\ -g(x,y)+c \end{pmatrix} = \begin{pmatrix}0 \\ 0 \\ 0 \end{pmatrix} $$

<strong>Bitte beachtet, </strong>dass $\nabla f(x,y)$ und $\nabla g(x,y)$ zweidimensional sind, wir leiten ja nach x und y ab. Deswegen stehen im letzten Vektor auch drei Nullen.

Euch sollte jetzt auffallen, dass die letzte Gleichung genau unseren beiden Anforderungen von oben entspricht.
<h2>Jetzt mal am Beispiel ausprobieren!</h2>
So, wir haben jetzt genug Grundlagen gemacht, um das Beispiel nun tatsächlich auch durchzurechnen. Wenn wir uns die Visualisierung von oben noch einmal ansehen, sehen wir, dass der optimale Punkt in der Nähe von (1,1,13) liegen müsste, etwa dort liegt die Nebenbedinungsgerade als Tangente an f. (Der exakte Punkt ist durch das Gitter nicht ablesbar).

Hier also nochmal das Optimierungsproblem:

$$ \begin{align*} \mbox{maximiere} ~ f(x,y) = -2x^2 +12x -y^2 +8y -4 \\ \mbox{unter der Nebenbedingung} ~ x+y=2 \end{align*} $$
<h3>Schritt 1: Lagrange-Funktion aufstellen</h3>
Wir bringen die Nebenbedinung $ g(x,y) = c $ auf eine Seite, sodass sie die Form $c-g(x,y)=0$ hat, multiplizieren sie mit $\lambda$ und ziehen sie von f ab. <strong>Bitte beachten: </strong>Es ist mathematisch völlig egal, wierum wir nach 0 auflösen, wir könnten auch $g(x,y)-c=0$ schreiben, wir könnten den $\lambda$-Term auch zu f dazuaddieren. Es spielt keine Rolle, denn im optimalen Punkt gilt ja eh $g(x,y)=c$ und dadurch gilt in diesem Punkt auch $ \mathscr{L} = f$, weil der Lagrange-Term einfach Null ist.

Die Lagrange-Funktion lautet also:

$$ \mathscr{L}(x,y,\lambda) = -2x^2 +12x -y^2 +8y - 4 -\lambda(x+y-2) $$
<h3>Schritt 2: Gradienten der Lagrange-Funktion bilden (partiell ableiten)</h3>
Wir bilden den Gradienten von $\mathscr{L}$, indem wir nach $x$, $y$ und $\lambda$ ableiten:

$$ \nabla \mathscr{L}(x,y,\lambda) = \begin{pmatrix} -4x +12 -\lambda \\ -2y +8 -\lambda \\ x+y-2  \end{pmatrix} $$
<h3>Schritt 3: Gradienten gleich Null setzen und auflösen</h3>
Wir setzen den Gradienten Null und erhalten drei Gleichungen, die wir auflösen können:

$$ \begin{align*} -4x +12 -\lambda &= 0 \\ -2y +8 -\lambda &= 0\\ x+y-2 &= 0 \end{align*} $$

Dies kann man jetzt zu Fuß oder mittels Gauß-Algorithmus lösen und kommt schließlich auf die Lösung:

$$ x = \frac{4}{3},~ y  = \frac{2}{3},~ \lambda = \frac{20}{3} $$

Nun können wir noch den zugehörigen Funktionswert von f ausrechnen und bekommen so das Maximum:

$$ (x*,y*, f(x*,y*) ) = (\frac{4}{3}, \frac{2}{3}, 13.\overline{33}) $$

Oben hatten wir ja anhand der Visualisierung schonmal grob abgeschätzt, wo das Optimum liegt und kamen auf einen sehr ähnlichen Wert. Scheint also, als hätten wir richtig gerechnet =)

<h3>Hinweis</h3>
Das Thema ist natürlich noch viel größer als das, was hier gezeigt wurde. Zwei wichtige Fragen, die ich in naher Zukunft hier beanworten will sind zum Beispiel:
<ul>
 	<li>Wie zeigt man, ob man ein Maximum oder ein Minimum gefunden hat?</li>
 	<li>Was passiert, wenn unsere Nebenbedingung keine Gleicheit, sondern eine Ungleichheit ist?</li>
</ul>


# Weitere Artikel

[Mehrdimensionales Ableiten]({{ "/mehrdimensionales-ableiten/" | relative_url }})
