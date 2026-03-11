---
layout: page
title: Stetigkeit von Funktionen
nav: true
permalink: /stetigkeit-von-funktionen/
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


<p>Stetigkeit ist ein zentrales Konzept in der Analysis. Über stetige Funktionen kann man enorm viele Aussagen treffen.</p>


<p>Aber was bedeutet aber Stetigkeit eigentlich?</p>


<p>Ganz einfach und anschaulich gesprochen: eine Funktion ist stetig, wenn sie mit einem Stift ohne abzusetzen zu zeichnen ist. Die Funktion hat also keine Sprünge oder so etwas (es gibt noch ein paar komplexere Sachen, die auftreten können, dazu weiter unten mehr). Hier seht ihr Beispiele für eine stetige und eine unstetige Funktion:</p>
<!-- /wp:paragraph -->

<img src="{{ site.baseurl }}/assets/stetige_funktionen.jpg" alt="Beispiele für nicht-stetige Funktion und stetige Funktion"/>

<!-- wp:paragraph -->
<p>So weit so einfach. Deutlich komplizierter wird es, wenn man sich die tatsächliche mathematische Definition dieser Aussage anschaut. Wenn man darüber nachdenkt, sollte klar sein, dass sich die Aussage mit dem Stift nicht so einfach in eine Formel übertragen lässt. Tatsächlich tut die folgende Formel - auch wenn sie sehr kompliziert aussieht - genau das! Die Idee ist im Prinzip folgende: Wenn eine Funktion ohne Abzusetzen zeichenbar ist, bedeutet das, wenn ich mit dem Stift die Funktion zeichnen will, und nur ein kleines Stück in x-Richtung gehe, dann sollte ich auch nur ein verhältnismäßig kleines Stück in y-Richtung gehen müssen. Dann ist die Funktion stetig. Bei unstetigen Funktionen, wo die Funktion zum Beispiel einen Sprung nach unten macht, wie z.B. die rote aus dem Bild oben, gibt es nun aber Stellen, wo ich nur ein kleines Stück in x-Richtung gehe, aber auf einmal eben einen ganz schönen Sprung in y-Richtung machen muss. Das ist dann nicht mehr stetig.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Schauen wir uns nun also die Definition an, aber nicht erschrecken! Später gibt es noch ein metaphorisches Beispiel, was das eigentlich ganz anschaulich macht.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3>Definition: Stetigkeit (auch: Epsilon-Delta-Kriterium)</h3>
<!-- /wp:heading -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>Eine Funktion $f : D \rightarrow \mathbb{R}$ ist stetig im Punkt p, wenn dort gilt: Zu jedem $\varepsilon > 0$ existiert ein $\delta>0$ sodass für alle $x$ mit $\left| x-p \right|<\delta $ folgt, dass $ \left| f(x) - f(p) \right| < \varepsilon$ gilt. Wenn $f$ in jedem Punkt $p \in D$ stetig ist, so ist eben die ganze Funktion $f$ stetig.</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<p>Sieht erstmal ziemlich komisch aus, oder? Brechen wir diese Definition einmal herunter: Zu <strong>jedem </strong>Epsilon, also zu jeder Änderung in y-Richtung existiert (mindestens!) ein Delta, also eine Änderung in x-Richtung, sodass bei jeder Veränderung von p um weniger als Delta, die Funktion nicht weiter als Epsilon vom Wert f(p) abhaut. Folgende Darstellung veranschaulicht dies ein bisschen, zu der Epsilon-Umgebung um f(p) finden wir eine Delta-Umgebung von p.</p>


<img src="{{ site.baseurl }}/assets/stetig2.jpg" alt="Beispiele für nicht-stetige Funktion und stetige Funktion"/>


<p>Das dies wirklich zeigt, dass eine Funktion stetig ist, sollte das folgende metaphorische Beispiel klar machen:</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3>Die unstetige Dusche</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Es geht um unsere morgendliche Dusche! Und zwar so: die x-Werte beschreiben die Position des Wärme-Reglers, die y-Werte die Temperatur des Duschwassers. Wenn wir die Temperatur stetig verändern können, bedeutet das folgendes: Zu jeder (auch noch so kleinen) Änderung Epsilon der Temperatur (Änderung in y-Richtung) gibt es eine Veränderung Delta der Position des Wärme-Reglers (in x-Richtung), sodass eine Veränderung des Reglers um maximal Delta auch nur eine Veränderung der Temperatur um maximal Epsilon bewirkt.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Wenn unsere Dusche jetzt nicht stetig wäre, sagen wir, sie springt von 20° auf 40° (kennt jeder, unglaublich nervig), finden wir zu bestimmten Epsilons eben kein passendes Delta:<br>Sagen wir, unser Regler hat gerade die Position p und die Dusche ist 20° warm. Das bedeutet nun, wir finden <strong>absolut kein</strong> Delta, sodass wir den Regler um dieses Delta drehen, damit die Temperatur auf 30° steigt! Zu einer Änderung um diese 10° in y-Richtung gibt es einfach kein Delta, sodass eine Veränderung in x-Richtung die y-Werte nur um 10° verändern lässt. Mathematisch ausgedrückt: Für $\varepsilon = 10$ existiert an der Stelle p kein $\delta>0$ sodass aus $\left| x-p \right|<\delta$ die Aussage $\left| f(x) - f(p) \right|<10$ folgt. Egal wie sanft wir den Regler bewegen: kaaalt, kaalt, kaaalt, kaaalt, HEISS HEISS HEISS!! Es gibt nichts dazwischen. Die Funktion ist nicht stetig. Wir geben auf und duschen kalt. Ist eh besser für die Umwelt und macht uns wach um jetzt Stetigkeit anhand von Beispielen zu bestimmen!</p>
<!-- /wp:paragraph -->

<h3>Epsilon-Delta-Kriterium für Stetigkeit anhand einiger Beispiele</h3>



Lasst uns das Epsilon-Delta-Kriterium einmal an ein paar Beispielen durchrechnen!


## Beispiel 1: Stetige Funktion

Beginnen wir mit der Funktion $x^2$.


<img src="{{ site.baseurl }}/assets/xquadrat.png" alt="Plot der Funktion X zum Quadrat"/>

Schauen wir mal, ob diese Funktion in p=0 stetig ist. Es ist also folgendes zu zeigen:<br>Für alle $\varepsilon>0$ müssen wir immer mindestens ein $\delta>0$ finden, sodass gilt:

$$
\left| x-0 \right| < \delta \Rightarrow \left| f(x) - f(0) \right| < \varepsilon $$

<!-- wp:paragraph -->
<p>Das funktioniert folgendermaßen: Man beginnt mit dem Term $ \left| f(x) - f(p) \right|$ und versucht ihn so umzubiegen, dass dort irgendetwas mit $\left| x-p \right|$ steht. Dann kann herausfinden, wie das <b>Delta in Abhängigkeit von Epsilon, x und p</b> gewählt werden kann, um die Stetigkeit zu beweisen. Beim Umbiegen muss man aber immer größer werden oder gleich bleiben, also es dürfen nur Gleichheitszeichen oder "Kleiner als" auftreten, denn: Am Ende wollen wir folgenden Zusammenhang herstellen:
<br/><br/>

Aus $\left| x-p \right|<\delta$ folgt, dass <b>irgendwas </b> $ < \varepsilon$. Und weil dieses <b>irgendwas</b> $ \geq \left| f(x) - f(p) \right|$ ist,  gilt insgesamt auch $\left| f(x) - f(p) \right| < \varepsilon$.

<br/>

<br>Hier ist also:<br>$\left| f(x) - f(0) \right| = \left| x^2 - 0 \right| = \left| (x-0)(x-0) \right| = \left| x-0 \right|^2 $.<br>Das soll nun kleiner als $\varepsilon$ sein. Naja, und wenn das $< \varepsilon$ sein soll, dann muss offenbar $\left| x-0 \right|$ kleiner als $\sqrt{\varepsilon}$ sein.<br>Damit haben wir also zu JEDEM $\varepsilon$ ein $\delta$ gefunden, nämlich $\delta = \sqrt{\varepsilon}$, sodass gilt:<br/>


$\left| x-p \right|<\delta \Rightarrow \left| f(x) - f(p) \right|<\varepsilon$, denn aus $ \left| x-0 \right| < \delta$ folgt $ \left| x-0 \right| < \sqrt{\varepsilon}$ folgt $\left| f(x) - f(0) \right| < \varepsilon$</p>

<!-- /wp:paragraph -->

## Beispiel 2: Stetige Funktion

<!-- wp:paragraph -->
<p>Gleiche Funktion, diesmal p=1.<br>Wir fangen wieder mit $|f(x) - f(p)|$ an und versuchen, etwas mit $|x-p|$ daraus zu machen:<br>$$ \left| f(x) - f(1) \right| = \left| x^2 - 1 \right| = \left| (x-1)(x+1) \right| = \left| x-1 \right| ~ \left| x+1 \right| $$<br>Wenn also $\left| f(x) - f(1) \right| < \varepsilon$ sein soll, dann ist also $\left| x-1 \right| ~ \left| x+1 \right| < \varepsilon$ und damit können wir $\delta = \frac{\varepsilon}{\left| x+1 \right|}$ wählen.<br>Denn: $\left| x-1 \right| < \frac{\varepsilon}{\left| x+1 \right|} \Rightarrow \left| f(x) - f(1) \right| = \left| x-1 \right| ~ \left| x+1 \right| < \frac{\varepsilon}{\left| x+1 \right|}\left| x+1 \right| = \varepsilon$ und die Stetigkeit ist gezeigt.</p>
<!-- /wp:paragraph -->

### Nochmal mit Ungleichungen

Oder um auch mal eine Ungleichheit in die Umformungen zu bringen, kann man es auch so machen, wobei hier eingeht, dass p in der Nähe von 1 ist, also können wir einfach nur Punkte betrachten die zwischen 0 und 2 liegen (denn es geht uns ja um die Stetigkeit bei 1 und nicht sonstwo).

$$
\left| f(x) - f(1) \right| = \left| x^2 - 1 \right| = \left| (x-1)(x+1) \right| = \left| x-1 \right| ~ \left| x+1 \right| < 3  \left| x-1 \right|
$$

Wenn wir jetzt $\delta = \frac{\varepsilon}{3}$ wählen, können wir die Ungleichungen zusammenpacken und bekommen:

Gegeben irgendein $\varepsilon$, und $\delta = \frac{\varepsilon}{3}$ folgt:

$$
\left| x-1 \right| < \delta \Rightarrow \left| x-1 \right| < \frac{\varepsilon}{3}
$$

Nun ist aber von oben

$$
\left| f(x) - f(1) \right|  < 3  \left| x-1 \right|
$$

Also auch

$$
 3  \left| x-1 \right| < \varepsilon
$$

Und deshalb auch

$$
\left| f(x) - f(1) \right|  < 3  \left| x-1 \right|  < \varepsilon
$$

Insgesamt also, für alle $\left\| x-1 \right\| < \delta$ gilt $\left\| f(x) - f(1) \right\|  < \varepsilon$. Tada.

## Beispiel 3: Unstetigkeit durch "Lücke"
<!-- /wp:heading -->

<p>$$f(x) = \begin{cases} \frac{x^2-1}{x-1} & x \neq 1 \\ 1 & x=1 \end{cases} $$</p>



<img src="{{ site.baseurl }}/assets/discontinuous.png" alt="Beispiel einer nicht-stetigen Funktion mit Sprungstelle"/>

<!-- wp:paragraph -->
<p>Ist diese Funktion stetig in p=1?. Anhand des Bildes habt ihr sicher schon eine Vermutung.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Wir beginnen wie immer und wenden beim zweiten Gleichheitszeichen die binomische Formel an: <br>$$\left| f(x) - f(1) \right| = \left| \frac{x^2-1}{x-1} - 1 \right| = \left| \frac{(x-1)(x+1)}{x-1} - 1 \right| = \left| (x+1) - 1 \right| = \left| x \right|$$<br>Das soll $<\varepsilon$ sein. Wir müssen also $\delta$ finden, sodass für jedes $\epsilon>0$ gilt: $|x-1|<\delta \Rightarrow |x|<\varepsilon$.<br>Aber geht das überhaupt?<br>Wenn zum Beispiel $\varepsilon = 1,5$, dann geht das: Für jedes $\delta < 0.5$ wäre dann tatsächlich $|x| < 1,5$.<br>Aber das muss für jedes $\varepsilon$ gelten!<br>Wenn $\varepsilon = 0,2$, dann finden wir absolut kein $\delta$, sodass für alle x mit $|x-1|<\delta$ folgt, dass $|x|<0,5$.<br>Zu diesem Epsilon gibt es also schlicht und ergreifend kein passendes Delta! Bei jedem Delta werden einige x-Werte die Bedingung nicht erfüllen! Die Funktion ist nicht stetig.<br>In der folgenden Graphik ist sind nochmal die beiden Epsilons eingezeichnet: Für $\varepsilon = 1,5$ finden wir ein Delta, sodass alle x die im grünen Bereich liegen ($|x|<\delta$) auch in $|x-1|<\varepsilon$ liegen. Dort gilt also $|x-1|<\delta \Rightarrow \left| f(x)-f(1) \right|<1,5$. Es muss aber für jedes Epsilon gelten. und egal wie wir unser Delta wählen, für $\epsilon_2$ werden immer einige x-Werte außerhalb der Epsilon-Umgebung (rot) liegen.</p>
<!-- /wp:paragraph -->

<img src="{{ site.baseurl }}/assets/epsilons.png" alt="Epsilon-Delta Kriterium für Stetigkeit">


## Beispiel 4: Stetigkeit durch "gestopfte Lücke"

Ihr seht ja im vorigen Beispiel, dass die Funktion eigentlich stetig sein könnte (eigentlich ist diese Funktion ja einfach nur $x+1$!), nur der Punkt in der Lücke an der falschen Stelle ist. Wenn wir den Punkt nun an die richtige Stelle setzen, ist die Funktion stetig. Zeigt das mal mit dem Kriterium! Weiter unten findet ihr die Lösung :)

$$f(x) = \begin{cases} \frac{x^2-1}{x-1} & x \neq 1 \\ 2 & x=1 \end{cases} $$




# Beispiel 5: Unstetigkeit wegen Polstelle

Eben haben wir ein Beispiel mit einer Lücke gesehen. Es gibt aber auch Polstellen. Klassisches Beispiel ist hier

$$f(x) = \begin{cases} \frac{1}{x} & x \neq 0 \\ 0 & x=0 \end{cases} $$

<img src="{{ site.baseurl }}/assets/discontinuous2.png" alt="Beispiele einer nicht-stetigen Funktion mit Polstelle"/>

Die Funktion ist offensichtlich nicht stetig in $x=0$. Aber lasst uns das am Kriterium zeigen. Wir fangen wieder an, mit $\|f(x)-f(0)\|$ herumzuspielen:

$$
|f(x) - f(0)| = |f(x)| = |\frac{1}{x}| = \frac{1}{|x|}
$$


Und das soll kleiner als $\varepsilon$ sein. Können wir jetzt für jedes $\varepsilon$ ein $\delta$ finden, sodass für alle  $\|x-0\| = \|x\| < \delta$ gilt dass $\frac{1}{\|x\|} < \varepsilon$? Nein, das geht nicht! Warum? Denn wenn $\|x\| < \delta$ ist, also x sehr klein ist, dann ist natürlich $\frac{1}{\|x\|}$ immer sehr groß! Das passt also überhaupt nicht zusammen. Beispiel: Wenn $\varepsilon = 0.1$, dann gilt ja für alle x mit $\|x\| < 10


# Beispiel 6: Stetigkeit der Polstellenfunktion, an anderer Stelle

Die Funktion $\frac{1}{x}$ ist aber, wenn man sich von der Polstelle wegbewegt, stetig. Schauen wir uns den Punkt $p=1$ an. 
Wir fangen wieder mit $|f(x) - f(p)|$ an und versuchen, etwas mit $|x-p|$ daraus zu machen:

$$
|f(x) - f(1)| = |\frac{1}{x} - 1| = |\frac{1}{x} - \frac{x}{x}| = |\frac{1-x}{x}| = \frac{|x-1|}{|x|}
$$

Das soll also $<\varepsilon$ sein. Naja, dann können wir $\delta = \varepsilon \|x\|$ wählen, denn dann gilt: Wenn uns ein $\varepsilon$ gegeben wird, dann gilt mit dieser Wahl für $\delta$: Für alle x mit $\|x-1\| < \delta =  \varepsilon \|x\|$ ist dann $\frac{\|x-1\|}{\|x\|} < \frac{\delta}{\|x\|} = \frac{\varepsilon \|x\|}{\|x\|} = \varepsilon  $, also insgesamt $\|f(x) - f(1)\| < \varepsilon$. Wunderbar.


# Beispiel 7: Unstetigkeit an einer Sprungstelle

Gegeben sei die folgende Funktion mit der kritischen Stelle $p=1$:

$$
f(x) = \begin{cases} x+2 & x > 1 \\ x+1 & x\leq 1 \end{cases}
$$


<img src="{{ site.baseurl }}/assets/discontinuous_jump.png" alt="Beispiele für eine nicht-stetige Funktion mit Sprungstelle"/>

Probieren wir es aus. Hier müssen wir unterscheiden, ob wir von rechts oder von links an p rangehen, da die Funktion ja je nachdem unterschiedlich definiert ist. Ich mache hier mal nur von rechts, ihr könnt es dann von links selbst probieren.

$$
|f(x) - f(1)| = |(x+2) - (1+1)| = |x|
$$

Das soll $<\varepsilon$ sein. Finden wir für jedes $\varepsilon$ ein $\delta$, sodass $\|x-1\|<\delta$ zur Folge hat dass $\|x\| < \varepsilon$?
Nein. Angenommen, $\varepsilon = 0.1$. Wir müssten ja für alle x-Werte, die nah an 1 sind (denn das heißt ja $\|x-1\|<\delta$), dass sie kleiner als $\varepsilon$ sind. Das geht natürlich nicht. Die Situation mit den $\varepsilon$ und $\delta$ sieht wieder so aus wie in Beispiel 3.

# Weitere Arten von nicht-stetigen Funktionen

Bis hier haben wir nur Sprungstellen und Polstellen betrachtet. Es gibt aber noch andere Formen von nicht-stetigen Funktionen. Das ist zum Beispiel $f(x) = \sin(1/x)$. Diese Funktion spring bei x=0 so stark hin und her, dass auch dort das Epsilon-Delta-Kriterium nicht erfüllt werden kann.


<img src="{{ site.baseurl }}/assets/oscillation.png" alt="Beispiele für eine nicht-stetige Funktion mit unendlicher Oszillation"/>

<p><br>Das war es erst einmal zum Epsilon-Delta Kriterium der Stetigkeit! Es gibt auch noch weitere Kriterien der Stetigkeit, die ich euch auch bald zeigen werde. Also schaut regelmäßig vorbei!</p>


## Lösung der Übungsaufgabe (Beispiel 4)

Also, wie im Beispiel 3 $\|f(x) - f(p)\|$ starten und umformen bis was mit $\|x-p\|$ rauskommt. Hier hilft auch wieder die binomische Formel.

$$
\left| f(x) - f(1) \right| = \left| \frac{x^2-1}{x-1} - 2 \right| = \left| \frac{(x-1)(x+1)}{x-1} - 2 \right| = |x-1|
$$

Na und das ist natürlich ganz simpel. Wenn das $<\varepsilon$ sein soll, dann müssen wir $\delta \leq \varepsilon$ wählen, denn dann gilt: Für alle $x$ mit $\|x-1\|<\delta$ ist dann natürlich auch $\|x-1\|<\varepsilon$.
Diese Funktion ist also stetig!
