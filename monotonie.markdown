---
layout: page
title: Monotonie von Funktionen
nav: true
permalink: /monotonie/
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

Monotonie ist die Eigenschaft von Funktionen, die beschreibt, ob eine Funktion (auf ganz $\mathbb{R}$, dem Definitionsbereich von $f$, oder einem definierten Intervall) steigt oder fällt.
Dabei wird unterschieden zwischen <strong>Monotonie</strong> und <strong>strenger Monotonie</strong>: Bei Monotonie kann die Funktion auch (ganz oder teilweise) konstant sein, bei strenger Monotonie muss sie wirklich an jedem Punkt echt steigen bzw. fallen.

Die genaue Definition lautet:
<blockquote>Eine Funktion $f : D \Rightarrow \mathbb{R}$ ist monoton steigend wenn $x \leq y \Rightarrow f(x) \leq f(y)$ und streng monoton steigend wenn $x < y \Rightarrow f(x) < f(y)$. Bei der strengen Monotonie muss mit jedem noch so kleinen Schritt von x nach rechts auch der Funktionswert steigen, bei Monotonie ist auch Gleichheit erlaubt.
Analog dazu definiert man (streng) monoton fallend.</blockquote>
Zunächst einige Beispiele zur Anschauung ohne Herleitung:


<img src="{{ site.baseurl }}/assets/monotonie3.png" alt="Streng monoton steigende Funktion">

$f(x) = e^x$ ist streng monoton steigend auf $\mathbb{R}$

<img src="{{ site.baseurl }}/assets/monotonie2.png" alt="Streng monoton steigende Funktion">

$f(x) = ln(x)$ ist streng monoton steigend auf $\mathbb{R}$


<img src="{{ site.baseurl }}/assets/monotonie1.png" alt="Verschiedene Funktionen">

$f(x) = x+3$ ist streng monoton steigend auf $\mathbb{R}$

$f(x) = x^2$ ist streng monoton steigend auf $[0, \infty)$

$f(x) = x^2$ ist streng monoton fallend auf $(-\infty, 0]$

$f(x) = x^2$ ist nicht monoton auf $\mathbb{R}$

$f(x)=5$ ist gleichzeitig monoton steigend <strong>und</strong> monoton fallend auf $\mathbb{R}$, aber nicht streng monoton!


<h3>Wie zeigt man, dass eine Funktion (streng) monton ist?</h3>
Man kann Monotonie zeigen, indem man die Definition der Monotonie für die gegebene Funktion durchrechnet. Man nimmt also ein x und ein y > x und zeigt dann den Zusammenhang zwischen f(x) und f(y). Viel einfacher geht es jedoch mit folgendem Kriterium:
<h4>Hinreichendes Kriterium: die erste Ableitung</h4>
Am leichtesten kann man die Monotonie mittels der ersten Ableitung überprüfen: Wenn $f'(x) > 0$, so kann man folgern, dass f streng monoton steigend ist.
Wenn $f'(x) >= 0$, so kann man folgern, dass $f$ monoton steigend ist. (Es könnte dann aber sogar noch sein, dass $f$ auch streng monoton steigend ist, siehe unten!)
Für monoton fallende Funktionen kann muss man einfach die Ungleichung umkehren, also $f'(x) \leq 0$ bzw. $f'(x) < 0$ für monotonie und strenge Monotonie.

Beispiele
$f(x) = e^x \Rightarrow f'(x) = e^x >0 \Rightarrow f$ ist auf dem gesamten Definitionsbereich ($\mathbb{R}$) streng monoton steigend
$f(x) = ln(x) \Rightarrow f'(x) = 1/x > 0 \Rightarrow f$ ist auf dem gesamten Definitionsbereich $(0,\infty)$ streng monoton steigend
$f(x) = 5 \Rightarrow f'(x) = 0 \Rightarrow f$ ist auf ganz $\mathbb{R}$ monoton steigend und überall monoton fallend
$f(x) = x^2 \Rightarrow f'(x) > 0 ~\mbox{für}~ x > 0 \Rightarrow f$ ist streng monoton steigend auf $(0, \infty)$
$f(x) = x^2 \Rightarrow f'(x) < 0 ~\mbox{für}~ x < 0 \Rightarrow f$ ist streng monoton steigend auf $(\infty, 0)$

Tatsächlich ist $x^2$ auch auf dem Intervall $[0, \infty)$ (also inklusive $x=0$) streng monoton steigend, obwohl $f'(0) = 0$ ist. Näheres zu diesen Spezialfällen im folgenden Abschnitt:
<h3>"Gegenbeispiel": $f'(x) > 0$ ist nur hinreichendes Kriterium</h3>
$f'(x)>0$ ist ein hinreichendes Kriterium, aber kein notwendiges Kriterium! Aus $f'(x)>0$ können wir also folgern dass die Funktion in x streng monoton steigend ist, $f'(x)=0$ bedeutet aber nicht automatisch, dass die Funktion nicht streng monoton steigend ist.
"Gegenbeispiel":
Die Funktion $f(x) = x^3$ ist auf ganz $\mathbb{R}$ streng monoton steigend. Warum? Nun, offensichtlich ist $f'(x) = 3x^2 > 0$ für alle $x \neq 0$, $f$ ist also schon einmal überall außer bei $x=0$ streng monoton steigend. Wie sieht es allerdings im Punkt $x=0$ aus? Wir haben $f'(0) = 0$, man könnte also denken, die Funktion ist nur monoton steigend, aber nicht streng monoton steigend. Das stimmt aber nicht, denn:
Sei $\varepsilon > 0$ beliebig.
Dann ist offensichtlich $\varepsilon^3 > 0^3$, anders ausgedrückt: $f(\varepsilon) > f(0)$.
Genau so ist damit $-\varepsilon < 0$ und $(-\varepsilon)^3 < 0^3$, also $f(-\varepsilon) < f(0)$.

Da $\varepsilon$ ein beliebiger Wert war, ist jeder Funktionswert rechts von $x=0$ echt größer als $f(0) = 0$, und jeder Funktionswert links von $x=0$ echt kleiner als $f(0)$. Damit ist $f$ also doch streng monoton steigend auf ganz $\mathbb{R}$! Obwohl die Ableitung $f'(0)=0$ ist.

Zum Glück gibt es aber folgendes Resultat, was uns die Arbeit in diesen Fällen abnimmt:

<h3>Monotonieeigenschaften lassen sich bei stetigen Funktionen auf abgeschlossene Intervalle erweitern</h3>

Das heißt: Wenn wir gezeigt haben, dass $f$ auf dem offenen Intervall $(a,b)$ monoton ist, und $f$ ist [stetig]({{ "/stetigkeit/" | relative_url }}) auf $[a,b]$, so gilt die gezeigte Aussage auch für das abgeschlossene Intervall $[a,b]$!

Also: Weil wir gezeigt haben, dass $f(x) = x^3$ auf $(0, \infty)$ streng monoton steigend ist, $f$ aber auf $[0, \infty)$ stetig ist ($f$ ist natürlich sogar auf ganz $\mathbb{R}$ stetig), gilt die Aussage auch für das Intervall $[0, \infty)$. Außerdem haben wir gezeigt, dass $x^3$ auf $(-\infty, 0)$ streng monoton steigend ist, wegen der Stetigkeit ist die Funktion also auch auf $(-\infty, 0]$ streng monoton steigend. Zusammengefasst können wir also sagen, dass $f(x) = x^3$ auf ganz $\mathbb{R}$ streng monoton steigend ist.

Für $f(x) = x^2$ hatten wir gezeigt, dass $f$ auf $(0, \infty)$ streng monoton steigend ist, wegen der [Stetigkeit]({{ "/stetigkeit/" | relative_url }}) folgt also, dass $x^2$ auf $[0, \infty)$ streng monoton wächst. Genauso können wir argumentieren, dass $x^2$ auf $(-\infty, 0]$ streng monoton fällt.
<h3>Zusammenhang zur Bijektivität</h3>
Zu guter letzt noch ein kleiner Anwendungsfall der Monotonie. Wir erinnern uns an die Eigenschaften der Surjektivität, Injektivität und Bijektivität (siehe [Kneipenprügelei]({{ "/die-injektive-surjektive-bijektive-kneipenpruegelei/" | relative_url }})).
Injektivität hieß ja, dass aus f(x)=f(y) auch sofort x=y folgt. Dies ist gleichbedeutend damit, dass f streng monoton ist!
Das heißt, eine streng monotone Funktion ist immer injektiv. Und weil wir Surjektivität durch Angabe des Wertebereichts erzwingen können, ist eine streng monotone Funktion also bijektiv und damit umkehrbar! Das ist hilfreich, weil sich strenge Monotonie in der Regel sehr leicht zeigen lässt, und man die Injektivität einfach mittels der Monotonie statt der Definition von Injektivität zeigen kann.
<h3>Übungen:</h3>
<ol>
 	<li>Angenommen, wir haben für eine Funktion $f$ gezeigt, dass sie auf $(-\infty, 0]$ und $(0, \infty)$ streng monoton fallend ist. Können wir daraus schließen, dass sie auf ganz $\mathbb{R}$ streng monoton fallend ist?</li>
 	<li>Zeigt mittels der Definition (also ohne Ableitung!) dass $e^x$ streng monoton wachsend ist!</li>
 	<li>Prüft mittels der Ableitung die Monotonie-Eigenschaften von $f(x) = 3x^2 -12x  + 8$</li>
</ol>
<h3>Lösungen:</h3>
1. Nein, nicht wenn die Funktion nicht [stetig]({{ "/stetigkeit/" | relative_url }}) ist! Die Funktion könnte auf $(-\infty, 0]$ streng monoton fallend sein, an der Stelle $x=0$ einen Sprung nach oben machen, und dann wieder fallen!
2. Wir nehmen ein beliebiges $x$ und ein $y > x$. Weil es einfacher ist, bezeichnen wir $y=x+h$ mit $h>0$. Jetzt schauen wir uns den Zusammenhang von $f(x)$ und $f(y)$ an:
$$
f(y) - f(x) = f(x+h) - f(x) = e^{x+h} - e^x = e^x(e^h - 1)
$$
Und weil $h>0$, ist $e^h > e^0 = 1$, damit ist die Klammer also >0 und $e^x$ ist sowieso >0. Wir haben also $f(y) - f(x) > 0 \Rightarrow f(x) < f(y)$.
3. $f'(x) = 6x -12$. Für $x>2$ also $f'(x) > 0$ und für $x<2$ umgekehrt. Wegen der Stetigkeit von $f$ erhalten wir : Streng monoton steigend auf $[2, \infty)$ und streng monoton fallend auf $(-\infty, 2]$.
