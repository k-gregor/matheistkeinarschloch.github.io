---
layout: page
title: t-Test (zwei Stichproben)
nav: true
permalink: /zwei-stichproben-t-test/
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



Der t-test gehört neben dem [Chi-Quadrat-Test]({{ "/chi-quadrat-test/" | relative_url }}) zu den wichtigsten statistischen Tests. Hier werde ich den Zweistichproben-t-Test anhand eines Beispiel erklären.

<h3>Worum geht's?</h3>

Gegeben seien zwei normalverteilte Stichproben einer bestimmten Beobachtung. Uns interessiert, ob die Mittelwerte verschieden sind. Klassisches Beispiel sind zwei Gruppen A und B von Patienten, wobei der Gruppe A ein Medikament verabreicht wurde und der zweiten Gruppe B nur ein Placebo. Man misst dann z.B. den Blutdruck (oder irgendetwas anderes) und will schauen, ob der Blutdruck von Gruppe A im Durchschnitt geringer ist, als der von Gruppe B. Natürlich können wir einfach bei jedem den Blutdruck messen und dann die beiden Durchschnitte pro Gruppe vergleichen, aber wir wollen das natürlich auf statistisch fundierter Art und Weise machen. Es reicht nicht aus, einfach nur die ausgerechneten Durchschnitte zu berechnen, wir müssen auch sagen können, ob ein eventueller Unterschied auch wirklich statistisch signifikant ist, oder nur zufällig Zustande gekommen ist.
<h2>Erklärung an einem Beispiel: Zwei-Stichproben t-Test für unabhängige, normalverteilte Stichproben</h2>

<h3>Von der Stichprobe zur Hypothese</h3>

Folgendes Szenario: Wir wollen testen, ob Kollegah-Fans im Durchschnitt schlauer sind als Helene-Fischer-Fans (<b>Notiz</b>: Ich habe den Artikel geschrieben bevor Kollegah ein Schwurbler und wurde). Die beiden Stichproben seien <strong>unabhängig</strong>, das heißt, dass unsere Probanden entweder Kollegah- oder Helene-Fan sind, nicht beides. (An dieser Stelle sei erwähnt, dass ich ein Duett der beiden ziemlich geil fände, aber das ist eine andere Geschichte). Außerdem sind die Stichproben <strong>normalverteilt</strong>, denn der IQ ist normalverteilt. Unsere Messung hat nun folgendes ergeben, wobei K die Gruppe der Kolle-Fans (n Stück) ist und H die der Helene-Fans (m Stück).


K = (104, 111, 116, 103, 97, 99, 109, 112, 94)

H = (103, 110, 115, 102, 96, 98, 108, 111, 93, 104)

Ihr seht, dass die Helene-Fans immer ein klein bisschen schlechter abgeschnitten haben. Jetzt berechnen wir einmal die Durchschnitte:

$$ \bar{K} = 105, \bar{H} =  104 $$

Beide Gruppen sind schon einmal recht schlau (der Durchschnitts-IQ liegt normalerweise bei 100), aber die Kollegah-Fans scheinen noch ein bisschen mehr im Köpfchen zu haben. Aber reicht das aus um pauschal sagen zu können, dass Kollegah-Hörer intelligenter sind als Helene-Hörer? Wir vermuten, nein! Das lässt sich mit dem t-Test prüfen! Unsere Hypothese lautet:

$$ H_0: \mu_K = \mu_H $$
<h3>Die Teststatistik</h3>
Klar, in unserer Stichprobe sieht es so aus, also seien die Kolle-Fans schlauer. Aber wie können wir das statistisch fundiert nachprüfen? Nun, wie immer haben clevere Leute dafür eine Teststatistik gefunden, die in diesem Falle ein gewichteter Abstand der beiden Mittelwerte ist:

$$ T = \frac{\bar{K} - \bar{H}}{S \sqrt{\frac{1}{n} + \frac{1}{m}}} $$.

Im Zähler steht der Abstand der Mittelwerte, der aber noch durch einen komischen Term geteilt wird. Dieser Term enthält auch noch ein $S$, welches so definiert ist:

$$ S = \sqrt{ \frac{(n-1)S_K^2 + (m-1)S_H^2} {n+m-2} } $$

wobei $S_K$ und $S_H$ die Stichprobenvarianzen für Kollegah bzw. Helene sind:

$$ S_K = \sqrt{ \frac{1}{n-1} \sum_{i=1}^n (K_i - \bar{K})} $$

Uff. Ganz schön kompliziert. Aber bevor wir das ausrechnen überlegen wir einmal, was das eigentlich ganz grob bedeutet: Die Testgröße $T$ ist einfach nur der Abstand der Stichprobenmittelwerte, geteilt durch so etwas wie die Varianz beider Stichproben. Das sollte so halbwegs einleuchten: Wenn die Varianzen der beiden Stichproben extrem groß ist, dann sollte die Testgröße etwas kleiner werden, weil eine hohe Varianz auch einen zufällig sehr großen Abstand der Stichprobenmittelwerte hervorrufen kann und das unsere Statistik stark verfälschen könnte. Eine kleine Varianz hingegen weist darauf hin, dass die Stichprobe wahrscheinlich gar nicht so untypisch ist. Der Abstand der Mittelwerte sollte also nicht ganz so stark herunterkorrigiert werden.

Rechnen wir es nun mal an unserem Beispiel aus. Ich komme auf:

$$ S_K \approx 7,48, S_H \approx 7,06, S \approx 7,26 $$

Unsere Testgröße $T$ ist also:

$$ T \approx 0,3 $$
<h3>Warum diese Teststatistik?</h3>
Wozu diese komische Berechnung von $T$? Klar, es ist sinnvoll, den Abstand der Mittelwerte ein wenig durch die Varianz zu teilen, wie oben beschrieben, aber warum so komisch? Nun, es stellt sich nämlich heraus, dass, wenn man es so macht, unser $T$ unter der Nullhypothese gerade $t$-verteilt ist mit $m+n-2$ Freiheitsgraden! Die t-Verteilung sieht in diesem Fall (mit 17 Freiheitsgraden) so aus:


<img src="{{ site.baseurl }}/assets/tverteilung.png" alt="Plot der t-Verteilung, der Grundlage für den t-Test">

Relativ ähnlich wie eine Normalverteilung, je höher der Freiheitsgrad, desto ähnlicher. Wir sehen anhand dieses Graphen, welche Werte von $T$ unter der Nullhypothese eher wahrscheinlich sind, und welche Werte eher unwahrscheinlich sind (die ganz an den Rändern).

Nun, unter unserer Nullhypothese, dass $\mu_K = \mu_H$, dürfte unsere Teststatistik $T$ nicht zu weit weg von $0$ liegen, denn: Wenn $\mu_K = \mu_H$, dann sollte auch $ \bar{K} $ ungefähr so groß sein wie $ \bar{H} $ sein und damit $ \bar{K} - \bar{H} $ nicht zu weit von $0$ weg sein, also auch $ T $ ungefähr $0$ sein.
<h3>Aussage der Teststatistik</h3>
Aber wie weit weg ist zu weit weg von $0$?

In der Statistik nehmen wir natürlich immer ein Signifikanzniveau $\alpha$, z.B. $\alpha = 0,05$. Wie groß muss unser $T$ dann sein, damit es zu weit weg von Null ist? Naja, entweder so weit rechts, dass nur ein solches T nur noch weniger als 2,5% wahrscheinlich ist, oder so weit links, dass es nur noch weniger als 2,5% wahrscheinlich ist. Wir haben hier also einen zweiseitigen Test, sowohl zu weit links als auch zu weit rechts sind schlecht. Die 5% Signifikanzniveau teilen sich deshalb auf. Mathematisch formuliert verwerfen wir die Nullhypothese also genau dann, wenn

$$ T > t(1-\frac{1}{2} \alpha, n+m-2),  ~ \mbox{oder} T < -t(1-\frac{1}{2} \alpha, n+m-2) $$

wobei $t(x, df) $ aus einer Tabelle der $t$-Verteilung abgelesen werden kann. Bei uns wäre dieser Wert gerade $t (0,975, 17) \approx 2,11 $.
In unserem Beispiel hatten wir ja $ T = 0,3 $. Das ist zwar größer als Null (weil ja eben in unserer Stichprobe auch die Kolle-Fans schlauer waren), aber lange nicht stark genug, dass das ein statistisch signifikantes Resultat wäre.

Wir verwerfen die Nullhypothese also <strong>nicht</strong>. Unser Test konnte keinen signifikanten Unterschied der Intelligenz von Helene Fischer- bzw. Kollegah-Fans erkennen.
<h3>Einseitiger t-Test</h3>
Beim t-Test können wir auch eine einseitige Hypothese aufstellen, also z.B. $ \mu_K \geq \mu_H $. Der t-Test läuft dann ganz genauso ab, nur dass die Teststatistik $T$ etwas anders interpretiert werden muss. Schließlich haben wir jetzt einen einseitigen Test: Wenn $T$ ganz weit rechts ist, passt das ja immernoch zur Nullhypothese, denn dann ist $ \mu_K $ einfach viel größer als $\mu_H$. Abgelehnt wird die Nullhypothese nur, wenn $T$ extrem weit links liegt, nämlich genau ab dort, wo die Wahrscheinlichkeit für einen solchen oder noch kleineren Wert kleiner als 5% ist (wir teilen das Signifikanzniveau also nicht auf links und rechts auf, denn nur links ist "schlecht"). Denn dann scheint $\mu_K$ in Wirklichkeit deutlich kleiner zu sein als $\mu_H$. Die Nullhypothese $ \mu_K \geq \mu_H $ wird also verworfen, wenn

$$ T < -t(1-\alpha, n+m-2) $$

Wie sieht es im obigen Beispiel aus? Es ist $ -t(0,95, 17) \approx -1,74 $. Nunja, unser $T$ ist ja immernoch dasselbe, nämlich $T \approx 0,3$, das heißt, auch hier verwerfen wir die Nullhypothese nicht. Das scheint erst einmal komisch zu sein, ist aber völlig ok, denn die Hypothese $ \mu_K \geq \mu_H $ ist ja auch erfüllt, wenn tatsächlich $ \mu_K = \mu_H $ gilt.

Auch die andere Seite können wir testen, also die Nullhypothese $ \mu_K \leq \mu_H $. Diese wird verworfen, wenn

$$ T > t(1-\alpha, n+m-2) $$

und auch diese Nullhypothese können wir mit unseren Stichproben nicht verwerfen. Könnt ihr ja mal nachprüfen. Insgesamt kann man sagen, dass Helene- und Kolle-Fans mehr oder weniger gleich schlau sind und zumindest diese Stichprobe nichts gegenteiliges zeigen konnte.
<h3>t-Test mit Abstand der Mittelwerte</h3>
Auch Abstände von Mittelwerten können mit dem t-Test geprüft werden. Man könnte zum Beispiel sagen: Kollegah-Fans haben im Schnitt einen um $C$ größeren IQ als Helene-Fans. Der Test läuft dann haargenauso ab, nur die Testgröße enthält noch ein $C$:

$$ T = \frac{\bar{K} - \bar{H} - C}{S \sqrt{\frac{1}{n} + \frac{1}{m}}} $$.
<h3>Einfluss von Varianz auf das Testergebnis</h3>
Die Varianz der Stichproben spielt eine entscheidende Rolle bei diesem Test, wie vorher bereits angekündigt. Angenommen, unsere Stichproben hätten so ausgesehen:

K = c(106, 106, 105, 105, 105, 105, 105, 104, 104)

H = c(105, 105, 104, 104, 104, 104, 104, 103, 103, 104)

Auch hier ist wieder $ \bar{K} = 105, \bar{H} =  104 $, aber die Stichprobenvarianzen sind viel geringer. Wenn wir diese ausrechnen und unsere Prüfgröße $T$ berechnen, kommen wir auf

$$ T \approx 3,17 $$

Das heißt, in diesem Falle würden wir die Nullhypothese $ \mu_K = \mu_H $ verwerfen! Unser Test hätte also gezeigt, dass Kollegah-Fans bei einem Signifikanzniveau von 95% im Schnitt schlauer sind, als Helene-Fans. Wenn wir nochmal die Graphik der t-Verteilung anschauen erkennen wir auch, dass ein solcher Wert unter der Nullhypothese auch einfach extrem unwahrscheinlich ist.

Als Übung könnt ihr euch anhand dieses Beispiels nochmal die einseitigen Tests sowie den Test auf Abstand der Mittelwerte anschauen.

<h3>Letzte Bemerkung</h3>
Der t-Test kann nur ausgeführt werden, wenn die Varianzen der Grundgesamtheiten gleich sind. Da man diese in der Regel nicht weiß, schaut man sich die Stichprobenvarianzen an. wenn diese ähnlich sind, dann ist das in Ordnung. Wenn sie aber stark verschieden sind, können wir nicht davon ausgehen, dass die Varianzen der Grundgesamtheiten gleich sind. Dann müssen wir statt dem t-Test den Welch-Test benutzen.
