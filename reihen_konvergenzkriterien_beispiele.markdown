---
layout: page
title: Reihen (Konvergenzkriterien und Beispiele)
nav: true
permalink: /reihen-konvergenzkriterien-beispiele/
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


Im Artikel [Grundlagen von Reihen]({{ "/reihen-grundlagen/" | relative_url }}) haben wir bereits einiges über Konvergenz und Divergenz von Reihen gelernt. Nun soll es um die Kriterien gehen, anhand derer man Reihen auf Konvergenz oder Divergenz prüfen kann. Ich will sie euch im folgenden vorstellen.
<h2>Nullfolgenkriterium</h2>
Das Nullfolgenkriterium ist das grundlegendste Kriterium. Es besagt:
<blockquote>Eine Reihe $\sum a_n$ kann nur dann konvergieren, wenn $(a_n)$ eine Nullfolge ist.</blockquote>
Das sollte auch klar sein, denn nur, wenn die Summanden immer kleiner werden, haben wir überhaupt eine Chance, dass die Summe einen endlichen Wert hat.

Das Nullfolgenkriterium ist aber auch nur ein notwendiges Kriterium, kein hinreichendes Kriterium! Bestes Beispiel dafür ist die sogenannte <strong>harmonische Reihe</strong>

$$ \sum_{n=1}^\infty \frac{1}{n} $$

Die Folge $(\frac{1}{n})$ ist zwar eine Nullfolge, die Summe ist allerdings bestimmt divergent. Wie zeigt man denn aber, dass diese harmonische Reihe divergiert? Im Artikel [Grundlagen von Reihen]({{ "/reihen-grundlagen/" | relative_url }}) haben wir in einer Grafik gesehen, dass die Reihe immer weiter wächst, aber mit welchem Kriterium können wir wirklich die Divergenz zeigen? Das geht mit dem folgenden Kriterium:

<hr />

<h2>Integralkriterium</h2>
Beim Integralkriterium vergleicht man die Reihe mit dem dazugehörigen Integral: Wir betrachten eine Reihe $ \sum_{k=p}^\infty a_k $, wobei $p$ irgendeine natürliche Zahl ist und $a_k$ monoton fallend sein muss(das ist wichtig). Jetzt fassen wir $a_k$ als kontinuierliche Funktion auf, und bestimmen das Integral $\int_{p}^\infty a(x) dx$. Also zum Beispiel vergleichen wir $ \sum_{k=1}^\infty \frac{1}{k} $ mit dem Integral $\int_{1}^\infty \frac{1}{x} dx$. Das Integralkriterium sagt uns dann, wenn $a_k$ tatsächlich monoton fallend ist:
<blockquote>Eine Reihe $ \sum_{k=p}^\infty a_k $ konvergiert genau dann, wenn das Integral $\int_{p}^\infty a(x) dx$ einen endlichen Wert hat.</blockquote>
Warum macht das Sinn? Naja, das Integral ist ja nichts anderes als, die Fläche unter dem Graphen von $f$ und vielleicht erinnert ihr euch daran, wie man das hergeleitet hat: Mit der Obersumme und Untersumme, wie hier:

<img class="wp-image-859 aligncenter" src="http://matheistkeinarschloch.de/wp-content/uploads/2016/11/reihe_integral-300x270.png" alt="reihe_integral" width="400" height="360" />

Man hat die Flächen von Rechtecken zusammenaddiert, deren Höhe jeweils der Funktionswert an der Stelle war. Und die Breite der Rechtecke (hier 1) hat man immer kleiner werden lassen, und im Grenzwert hat man das Integral erhalten. Das heißt, im Wesentlichen ist das Integral auch einfach eine Art Reihe. Im Beispiel hier sehen wir die Folge $a_k = \frac{1}{k}$. die Reihe $\sum a_k$ ist gerade die Summe der Flächeninhalte der Rechtecke, denn der Flächeninhalt ist gerade $1\cdot a_k$ für jedes $k$. Dazu sehen wir die Funktion $f(x) = \frac{1}{x}$. Man sieht, dass die Fläche unterhalb der Funktion in etwa der Summe der Flächen der Rechtecke entspricht. Wenn das eine also endlich ist, so muss es das andere auch sein und umgekehrt. Schauen wir das uns einmal an konkreten Beispielen an.
<h3>Beispiele für das Integralkriterium</h3>
Wir wollen zeigen, dass die harmonische Reihe divergent ist. Die dazugehörige Folge  $\frac{1}{n}$ und damit auch die entsprechende Funktion $\frac{1}{x}$ sind monoton fallend. Wir können das Integralkriterium also anwenden. Um nun zu zeigen dass $ \sum_{k=1}^\infty \frac{1}{k} $ konvergiert, betrachten wir das Integral $\int_1^\infty \frac{1}{x} dx $. Also mal wieder die Integrations-Skills ausgepackt:

$$ \int_1^\infty \frac{1}{x} dx  = \lim_{c \rightarrow \infty} \int_1^c \frac{1}{x} dx = \lim_{c \rightarrow \infty} \left[ \ln(x) \right]_1^c = \lim_{c \rightarrow \infty} \ln(c) - \ln(1) = \infty $$

Damit haben wir gezeigt, dass die harmonische Reihe divergiert.

Im Gegensatz dazu können wir uns die Reihe $\sum_{n=1}^\infty \frac{1}{n^2} $ anschauen. Wir bilden wieder das dazugehörige Integral:

$$ \int_1^\infty \frac{1}{x^2} dx  = \lim_{c \rightarrow \infty} \int_1^c \frac{1}{x^2} dx = \lim_{c \rightarrow \infty} \left[ -\frac{1}{x} \right]_1^c = \lim_{c \rightarrow \infty} -\frac{1}{c} - (-1) = 1 $$

Die Reihe $\sum_{n=1}^\infty \frac{1}{n^2} $ konvergiert also.

<hr />

<h2>Minorantenkriterium</h2>
Mit dem Minorantenkriterium kann man keine Konvergenz beweisen, sondern nur Divergenz! Wir können die Divergenz einer Reihe $\sum a_n$ zeigen, indem wir eine andere, Reihe finden (die sogenannte <strong>Minorante</strong>), welche "kleiner" ist als unsere Reihe und divergiert. Da unsere Reihe noch größer ist, muss diese also auch divergieren. Genau gesagt lautet das Kriterium:
<blockquote>Wenn eine Reihe (die "Minorante") $\sum b_n$ divergiert und $0 \leq b_n \leq a_n$ für alle $n$ gilt, so divergiert auch die Reihe $\sum a_n$.</blockquote>
<h3>Beispiel für das Minorantenkriterium</h3>
Die klassiche Minorante ist die harmonische Reihe $\sum \frac{1}{n}$, welche divergiert. Mit ihrer Hilfe können wir z.B. zeigen, dass die Reihe $\sum \frac{1}{\sqrt{n}}$ divergiert, denn offenbar ist $\frac{1}{n} \leq \frac{1}{\sqrt{n}}$. Jeder Summand ist also größer als der entsprechende Summand der harmonischen Reihe, also muss die Reihe mit der Folge $\frac{1}{\sqrt(n)}$ divergieren
<h4>Klassische Minoranten:</h4>
<ul>
 	<li>$\sum \frac{1}{n} = \infty$</li>
 	<li>$\sum \frac{1}{\sqrt{n}} = \infty $ (Diese Aussage lässt sich selbst mit dem Minorantenkriterium zeigen!)</li>
 	<li>$\sum \frac{1}{\ln(n)} = \infty $ (Diese Aussage lässt sich selbst mit dem Minorantenkriterium zeigen!)</li>
</ul>

<hr />

<h2>Majorantenkriterium</h2>
Das Majorantenkriterium ist genau das Gegenstück zum Minorantenkriterium. Hier zeigen wir, dass unsere Reihe kleiner ist als eine andere, konvergente Reihe. Da unsere Reihe kleiner ist, muss auch der Wert der Reihe kleiner sein als derjenige der Majorante, und damit muss unsere Reihe auch konvergent sein. Genau formuliert lautet das Kriterium:
<blockquote>Wenn $b_n$ eine nichtnegative, reelle Folge ist, und $|a_n| \leq b_n$ für alle $n$ gilt, und $\sum b_n$ konvergiert, dann konvergiert auch $\sum a_n$ (sogar absolut) und es ist $|\sum a_n| \leq \sum b_n$.</blockquote>
<h3>Beispiel für das Majorantenkriterium</h3>
Eine klassische Majorante ist die Reihe $\sum \frac{1}{n^2}$. Mit dieser Majorante können wir zum Beispiel zeigen, dass auch

$$ \sum \frac{1}{n^3} $$

absolut konvergent ist. Schließlich gilt $\frac{1}{n^2} \geq \frac{1}{n^3}$. Jeder Summand der Majorante ist also größer, aber trotzdem konvergiert die Majorante. Damit muss $\sum \frac{1}{n^3}$ auch konvergieren.
<h4>Klassische Majoranten</h4>
Siehe [Grundlagen von Reihen]({{ "/reihen-grundlagen/" | relative_url }}) für Beispiele von konvergenten Reihen. Jede davon könnte potentiell eine Majorante sein. Man muss nur eine passende finden, sodass man möglichst gut die Abschätzung der gegebenen Reihe zu der Majorante machen kann.

<hr />

<h2>Quotientenkriterium</h2>
Das Quotientenkriterium setzt aufeinanderfolgende Folgeglieder zueinander in Relation und schaut sich den Quotienten an: $\frac{a_{n+1}}{a_n}$. Wenn dieser deutlich kleiner ist als $1$, bedeutet das, dass die Folgeglieder mit jedem Schritt auch deutlich kleiner werden. Schauen wir uns das einmal an, zunächst die genaue Definition:
<blockquote>Eine Reihe ist konvergent, wenn es ein $q<1$ gibt, sodass $\left| \frac{a_{n+1}}{a_n}\right| \leq q < 1$ ab einem gewissen $n$.</blockquote>
Warum dort dieses $q$ wichtig ist, werden wir gleich noch sehen, aber im Wesentlichen heißt $\frac{a_{n+1}}{a_n} \leq q$ dass $a_{n+1} \leq q \cdot a_n$, also die Folgenglieder werden immer um einen Faktor kleiner. Das ist also ein sehr starkes Schrumpfen von Folgeglieder, und dann erhalten wir Konvergenz. Schauen wir uns ein Beispiel an.
<h3>Beispiel für das Quotientenkriterium</h3>
Die Reihe $\sum \frac{2^n}{n!}$ konvergiert, denn:

$$ \left| \frac{a_{n+1}}{a_n} \right| =  \left| \frac{\frac{2^{n+1}}{(n+1)!}}{\frac{2^n}{n!}} \right| = \frac{2^{n+1} n!}{2^n (n+1)!}   = \frac{2 n!}{(n+1)!} = \frac{2}{n+1}$$

Und das ist $<\frac{2}{3} <1$ ab $n=2$.
<h3>Warum brauchen wir das q beim Quotientenkriterium?</h3>
Nehmen wir die Reihe $\sum \frac{1}{n}$ (ihr seht schon, ich hab's irgendwie mit der Reihe. Aber es ist tatsächlich einfach die, mit der man die meisten Sachen gut zeigen kann). Wir wissen ja nun (siehe oben), dass die Reihe divergiert. Was passiert wenn wir das Quotientenkriterium auf die harmonische Reihe anwenden?

$$ \left| \frac{a_{n+1}}{a_n}\right| = \left| \frac{\frac{1}{n+1}}{\frac{1}{n}}\right| = \left| \frac{n}{n+1}\right| = \frac{n}{n+1} $$

Nun, das ist zwar immer $<1$ aber wir finden niemals ein $q<1$ sodass $\left| \frac{a_{n+1}}{a_n}\right| \leq q < 1$ gilt! Das Quotientenkriterium greift hier also nicht! Und das ist wichtig, schließlich konvergiert die Reihe ja auch nicht. Dieses $q$ gibt uns also immer einen "Sicherheitsabstand" zur $1$. Nur wenn dieses $q$ existiert, werden die Folgeglieder klein genug, sodass die Reihe konvergiert. Dass der Quotient immer kleiner ist als $1$ reicht nicht aus!

<hr />

<h2>Wurzelkriterium</h2>
Das Wurzelkriterium entsteht aus der geometrischen Reihe (über die ein Artikel bereits in Arbeit ist). Es lautet:
<blockquote>Eine Reihe $\sum a_k$ ist absolut konvergent, wenn es ein $q<1$ gibt, sodass $\sqrt[k]{|a_k|} \leq q < 1$ ab einem gewissen $n$.</blockquote>
Meistens wird dieses Kriterium auch so geschrieben:
<blockquote>Eine Reihe $\sum a_k$ konvergiert absolut, wenn für den Limes Superior gilt: $\limsup_{k\rightarrow \infty} \sqrt[k]{|a_k|} < 1$</blockquote>
Zu dieser Beschreibung unten noch etwas mehr. Zunächst mal ein einfaches Beispiel:
<h3>Beispiel für das Wurzelkriterium</h3>
$\sum_{n=0}^\infty \frac{3^n}{2^{2n}} $ konvergiert, denn

$$ \sqrt[n]{\frac{3^n}{2^{2n}}} = \frac{3}{4} < 1 $$
<h3>Warum braucht man beim Wurzelkriterium den Limes Superior?</h3>
Schauen wir uns kurz die zweite Beschreibung des Kriteriums mit dem Limes Superior $\limsup$ an. Der Limes Superior beschreibt den größten Häufungspunkt (siehe Artikel zu <a href="http://matheistkeinarschloch.de/folgen-und-grenzwerte/">Folgen und Grenzwerten</a>) einer Folge. Also zum Beispiel ist $\limsup_{n\rightarrow \infty} (-1)^n = 1$. Die Folge hat die zwei Häufungspunkte $1$ und $-1$, und der größte davon ist offensichtlich $1$.

Was bringt uns das hier? Naja, schauen wir uns die Folge

$$ a_n = \begin{cases} (\frac{1}{4})^n & \mbox{n gerade} \\  (\frac{1}{2})^n & \mbox{n ungerade} \end{cases} $$

und die dazugehörige Reihe $\sum a_n$ an. Ist die Reihe konvergent? Das können wir mit dem Wurzelkriterium zeigen (mit beiden Arten, aber hier exemplarisch mit dem Limes Superior). Also, die Folge $\sqrt[n]{|a_n|}$ ist einfach:

$$ \sqrt[n]{|a_n|} = \begin{cases} \frac{1}{4} & \mbox{n gerade} \\  \frac{1}{2} & \mbox{n ungerade} \end{cases} $$

und sie hat offenbar zwei Häufungspunkte, nämlich $\frac{1}{4}$ und $\frac{1}{2}$. Also:

$$ \limsup_{n\rightarrow \infty} \sqrt[n]{|a_n|} = \limsup_{n\rightarrow \infty} \begin{cases} \frac{1}{4} \\ \frac{1}{2} \end{cases} = \frac{1}{2} < 1 $$

Die dazugehörige Reihe ist also konvergent.
<h3>Ein Beispiel, wo das Wurzelkriterium Divergenz zeigt</h3>
Die Reihe $\sum \frac{n^n}{2^n}$ ist divergent, denn $\sqrt[n]{ \frac{n^n}{2^n}} = \frac{n}{2}$ und das ist $\geq 1$ ab $n=2$

<hr />

<h2>Leibnizkriterium</h2>
Zu guter Letzt gibt uns das Leibnizkriterium eine schöne Aussage über alternierende Reihen. Nämlich
<blockquote>Wenn $a_n$ eine monoton fallende Nullfolge ist, so konvergiert die alternierende Reihe $\sum (-1)^n~a_n$.</blockquote>
<h3>Beispiel für das Leibnizkriterium</h3>
Die Reihe $\sum (-1)^n~\frac{1}{n}$ konvergiert, denn $a_n$ ist eine monoton fallende Nullfolge.
<h3>Die monotone Konvergenz beim Leibnizkriterium ist wichtig!</h3>
Schauen wir uns nun aber folgende Reihe an:

$$ \sum (-1)^n a_n $$

mit $ a_n = \begin{cases} \frac{1}{n} & n~ \mbox{ungerade} \\ \frac{2}{n} & n~ \mbox{gerade}  \end{cases} $

Das Leibnizkriterium zieht hier nicht, denn die Folge $a_n$ ist nicht monoton fallend! Sie konvergiert zwar gegen Null, hüpft aber immer wieder ein bisschen hoch und runter

<img class="size-full wp-image-831 aligncenter" src="http://matheistkeinarschloch.de/wp-content/uploads/2016/11/folge_nicht_monoton_fallend_konvergent.png" alt="folge_nicht_monoton_fallend_konvergent" width="530" height="403" />

Diese Reihe konvergiert tatsächlich nicht, denn:

$$ \begin{align} \sum (-1)^k a_k &= \sum_{k=1}^\infty (-1)^{2k} a_{2k} + \sum_{k=0}^\infty (-1)^{2k+1} a_{2k+1} \\ &= \sum_{k=1}^\infty 1\cdot \frac{2}{2k} +  \sum_{k=0}^\infty (-1)\frac{1}{2k+1} \\ &=  \sum_{k=1}^\infty \frac{1}{k} -  \sum_{k=0}^\infty \frac{1}{2k+1} \\ &= (1 + \frac{1}{2} + \frac{1}{3} + \frac{1}{4} + \cdots) - (1 + \frac{1}{3} + \frac{1}{5} + \cdots)  \\ &= (\frac{1}{2} + \frac{1}{4} + \frac{1}{6} + \cdots) \\ &= \sum_{k=1}^\infty \frac{1}{2k} \\ &= \frac{1}{2} \sum_{k=1}^\infty \frac{1}{k} = \infty \end{align} $$
<h2></h2>

<hr />

<h2></h2>
<h2>Wann benutzt man welches Konvergenzkriterium?</h2>
Es gibt offenbar einige Kriterien, die wir zur Überprüfung von Konvergenz herannehmen können, dabei ist nicht immer sofort klar, welches das einfachste ist. Bei alternierenden Reihen nehmen wir in der Regel das Leibnizkriterium.

Ansonsten schaut man, ob man durch das Wurzelziehen oder Quotientenbilden die Arbeit leichter machen kann, wobei man das Wurzelkriterium eigentlich nur dann benutzt, wenn alle Teile der Summanden einen Exponenten haben, wie z.b. $\frac{2^n}{n^n}$. Dann hilft uns das Wurzelziehen. Bei Summanden wir $\frac{x^n}{n!}$ ist das Quotientenkriterium nützlich, weil man dann schön kürzen kann.

Reihen, deren Summanden $\frac{1}{n}$ oder so etwas wie $\frac{1}{\sqrt{n(n+1)}}$ ähneln, schreien quasi schon nach Minoranten- oder Majorantenkriterien.
