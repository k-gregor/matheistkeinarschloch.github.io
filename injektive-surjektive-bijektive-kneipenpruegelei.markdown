---
layout: page
title: Die injektive, surjektive, bijektive Kneipenprügelei
nav: true
permalink: /die-injektive-surjektive-bijektive-kneipenpruegelei/
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


<!-- wp:paragraph -->
<p>Die drei Eigenschaften Injektivität, Surjektivität und Bijektivität beziehen sich auf Abbildungen (Funktionen) zwischen zwei Mengen und führen oft zu Verwirrung. Ich möchte diese Eigenschaften hier an dem naheliegenden Beispiel einer Prügelei erklären, um diese Verwirrung hoffentlich beseitigen zu können. Schauen wir uns zunächst aber einmal die mathematischen Definitionen an.</p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>Eine Funktion $f:X\rightarrow Y$</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>heißt <strong>injektiv</strong>, wenn gilt: $f(x_1)=f(x_2) \Rightarrow x_1=x_2$, will heißen: für jedes $y\in Y$ gibt es entweder nur ein $x\in X$, für das $f(x)=y$ gilt, oder gar keins. Aber niemals mehrere $x$, die den gleichen Funktionswert haben.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>heißt <strong>surjektiv</strong>, wenn gilt: Für alle $y\in Y$ existiert mindestens ein $x\in X$, sodass $f(x)=y$ gilt. Heißt also, dass jedes $y$ von mindestens einem $x$ erreicht wird, möglicherweise auch von mehreren.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>heißt <strong>bijektiv</strong>, wenn sie surjektiv und bijektiv zugleich ist. Das heißt also dass jedes $x$ genau auf ein $y$ abbildet, kein $y$ doppelt getroffen wird und kein $y$ ausgelassen wird.</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list --></blockquote>
<!-- /wp:quote -->

<!-- wp:heading -->
<h2>Die injektive/surjektive/bijektive Kneipenprügelei</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Stellen wir uns nun eine Kneipe vor, in dem sich einige Herren (wir erinnern uns, die Herren der Schöpfung haben im Gegensatz zu den Damen ein $Y$-Chromosom!) feucht-fröhlich amüsieren. Es kommt eine Gruppe weiblicher Amazonen (mit $X$-Chromosomen) daher, die ziemlich auf Krawall gebürstet ist. Nach einigen frechen Sprüchen seitens der Herren eskaliert die Situation, und die Amazonen verprügeln die Männer.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Wat hat dat denn mit Mathe zu tun? Naja, die Amazonen sind unsere Menge X, die Kerle die Menge Y. Und wann immer eine Amazone x einem Kerl y eine reinhaut, haben wir eine Funktion von X nach Y. Damit das ganze auch wirklich eine Funktion ist (wir erinnern uns, <strong>bei einer Funktion wird einem x höchstens ein y zugewiesen</strong>), nehmen wir an, dass jede Amazone jeweils maximal einem Mann eine reinhaut.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Es gibt nun drei Möglichkeiten, wie es ablaufen könnte:</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3>Injektiv</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Injektiv heißt anschaulich: Jedem y-Wert wird maximal ein x-Wert zugeordnet! Bei unserer Prügelei heißt das, dass niemals zwei Amazonen auf einen Mann gehen würden. Dann gäbe es nämlich zwei x-Werte, die auf einen y-Wert abbilden. Das wäre nicht injektiv! Das heißt aber <strong>nicht</strong>, dass auch alle Männer etwas abkriegen. Helmut zum Beispiel hat direkt Angst bekommen und sich hinter der Theke versteckt, er kriegt keine rein, es gibt also kein x, welches auf den speziellen y-Wert "Helmut" abgebildet wird. Ist aber egal, trotzdem injektiv!</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3><strong>Surjektiv</strong></h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Surjektiv ist die Schlägerei, wenn wirklich jeder Mann eine reinkriegt. Das heißt nämlich, dass für jeden y-Wert mindestens ein x da ist, um auf diesen y-Wert abzubilden. Wenn wie vorher tatsächlich Helmut hinter der Bar versteckt bleibt, ist unsere Schlägerei <strong>nicht</strong> surjektiv, denn dann wäre Helmut genau der y-Wert, der von gar keinem x erreicht wird. Hier lässt sich auch eine spezielle Sache der Surjektivität erklären: Angenommen, Helmut wäre gar nicht da, unsere $Y$-Menge also um 1 kleiner, ansonsten aber keinerlei Änderung beim Kampf: Dann wäre die Schlägerei surjektiv, denn außer Helmut kriegen alle etwas ab. Das heißt: <strong>Surjektivität hängt ganz besonders von der Y-Menge ab:</strong> Wir können die Funktion gleich lassen (an der Schlägerei an sich ändert sich nichts), machen unsere Menge Y aber etwas kleiner und alle y-Werte werden getroffen: Die Funktion, die vorher nicht surjektiv war, ist es nun.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3>Bijektiv</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Bijektiv ist die Rauferei, wenn wirklich jede Amazone genau einen Mann verkloppt und auch kein Mann seinem Schicksal entgeht, also jeder etwas abbekommt. Es gibt also eine 1-zu-1-Beziehung, wiklich jede Amazone haut genau einen Mann und niemand bleibt übrig. Die Abbildung ist damit <strong>injektiv</strong> (jeder Mann bekommt von maximal einer Amazone etwas ab) <strong>und surjektiv</strong> (ohne Ausnahme bekommt jeder Mann etwas ab). Das heißt insbesondere: <strong>Die Funktion ist umkehrbar! </strong>Die Männer, die nun ordentlich eingesteckt haben, drehen den Spieß um, und verprügeln die Amazonen, und zwar ein jeder genau die, von der er eine abbekommen hat! Y bildet nun auf X ab und natürlich wieder 1-zu-1.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Nachdem die Kerle nun also die Frauen zurückgehauen haben, einigte man sich darauf, dass das ganze mit dem Prügeln doch irgendwie Schwachsinn ist und entschloss sich, lieber ein paar Biere zu trinken. Danach ging man gemeinsam nach Hause um Liebe zu machen. Ob das immernoch bijektiv war, oder vielleicht doch mehrere x auf ein y kamen, weiß ich nicht mehr. ;-)</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>Zurück zur Mathematik: Beispiele!</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Jetzt wollen wir noch ein paar mathematische Beispiele durchgehen! Danach könnt ihr auch gerne in die Kneipe gehen.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3>Beispiel 1</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>$$ f : \mathbb{R} \rightarrow \mathbb{R},~~ f(x) = x^2 $$</p>
<!-- /wp:paragraph -->


<img src="{{ site.baseurl }}/assets/xquadrat.png" alt="Plot der Funktion X zum Quadrat"/>


<!-- wp:paragraph -->
<p>ist als solches weder injektiv noch surjektiv! Denn alle y-Werte außer Null werden von zwei x-Werten erreicht (also nicht injektiv) und manche y-Werte werden gar nicht erreicht, alle negativen Zahlen nämlich (also nicht surjektiv). Letzteres können wir aber ändern, indem wir den tatsächlichen minimalen Wertebereich von f nehmen (nennt man auch Bild(f)):</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>$$ f : \mathbb{R} \rightarrow \mathbb{R}_{\geq 0},~~ f(x) = x^2 $$</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Jetzt ist die Funktion surjektiv (jedes $y \in \mathbb{R}_{\geq 0}$ wird erreicht), obwohl wir <em>eigentlich</em> gar nichts geändert haben: wenn wir die Funktion zeichnen würden, würde sie immernoch genauso aussehen wie vorher!</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Damit die Funktion injektiv wäre, müssten wir ihren Definitionsbereich einschränken, zum Beispiel nur alle x-Werte zulassen, die größer oder gleich Null sind. Beachtet, dass wir dann eine wirkliche Änderung an der Funktion machen, die sieht nämlich dann nur noch so aus:</p>
<!-- /wp:paragraph -->



<img src="{{ site.baseurl }}/assets/xquadrateingeschr.png" alt="Plot der Funktion X zum Quadrat mit eingeschraenktem Definitionsbereich"/>


<!-- wp:paragraph -->
<p>Die Funktion</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>$$ f : \mathbb{R}_{\geq 0} \rightarrow \mathbb{R}_{\geq 0},~~ f(x) = x^2 $$</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>ist also sowohl injektiv, als auch surjektiv, also bijektiv. Die Umkehrfunktion kennen wir alle, sie lautet:</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>$$ f^{-1} : \mathbb{R}_{\geq 0} \rightarrow \mathbb{R}_{\geq 0},~~ f^{-1}(x) = \sqrt{x} $$</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Wir sehen: <strong>Der Definitionsbereich von $f$ wird zum Wertebereich von $f^{-1}$ und umgekehrt!</strong></p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3>Beispiel 2</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>$$ f : \mathbb{R} \rightarrow \mathbb{R},~~ f(x) = e^x $$</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>ist als solche injektiv, aber nicht surjektiv. Wenn wir allerdings den Wertebereich auf $\mathbb{R}_{> 0}$ ändern, welches absolut nichts ändert, ist die Funktion bijektiv mit Umkehrfunktion</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>$$ f^{-1} : \mathbb{R}_{>0} \rightarrow \mathbb{R},~~ f^{-1}(x) = \ln(x) $$</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>wieder ist der Definitionsbereich von $f$ der Wertebereich von $f^{-1}$, und der (eingeschränkte) Wertebereich von $f$ ider der Definitionsbereich von $f^{-1}$.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3>Beispiel 3</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>$$ f : \mathbb{R} \rightarrow \mathbb{R},~~ f(x) = 5 $$</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>ist weder surjektiv noch injektiv.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3>Beispiel 4</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>$$ f : \mathbb{R} \rightarrow \mathbb{R},~~ f(x) = \sin(x) $$</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>ist weder surjektiv noch injektiv, das kann man sich am Graphen veranschaulichen:</p>
<!-- /wp:paragraph -->



<img src="{{ site.baseurl }}/assets/sin.png" alt="Plot der Sinusfunktion."/>

<!-- wp:paragraph -->
<p> Der Sinus kann aber surjektiv gemacht werden indem wir (keine Änderung an der Funktion, sähe immernoch genauso aus) den Wertebereich einschränken:</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>$$ f : \mathbb{R} \rightarrow [-1; 1],~~ f(x) = \sin(x) $$</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Für Bijektivität müssten wir die Funktion tatsächlich verkleinern, z.B. ist:</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>$$ f : [-\frac{\pi}{2};&nbsp;\frac{\pi}{2}] \rightarrow [-1; 1],~~ f(x) = \sin(x) $$</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>bijektiv:</p>
<!-- /wp:paragraph -->

<img src="{{ site.baseurl }}/assets/sineingeschr.png" alt="Plot der Sinusfunktion mit eingeschraenktem Definitionsbereich"/>

<!-- wp:heading {"level":3} -->
<h3>Hinweise</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Die Einschränkung des Definitionsbereich ist wie oben beschrieben und an x² gezeigt, wirklich eine Veränderung der Funktion. Deshalb schreibt man dies auch oft explizit hin, z.B. so:</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>$$ f|_{ [-\frac{\pi}{2};&nbsp;\frac{\pi}{2}]} $$</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Damit klar ist, dass es um die Einschränkung geht.</p>
<!-- /wp:paragraph -->
