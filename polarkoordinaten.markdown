---
layout: page
title: Polarkoordinaten
nav: true
permalink: /polarkoordinaten/
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


<h3>Was sind Polarkoordinaten?</h3>
Polarkoordinaten sind eine andere Möglichkeit, Punkte in der Ebene zu beschreiben. Wir alle kennen das kartesische Koordinatensystem, mit dem wir in Mathe immer arbeiten. Ein Punkt ist dann einfach die Kombination (x,y) aus dem Abstand zur y-Achse und dem Abstand zur x-Achse.

Bei Polarkoordinaten beschreiben wir den Punkt etwas anders: mittels dem Abstand zum Ursprung und einem  Winkel. Schauen wir uns ein Beispiel an:


<img src="{{ site.baseurl }}/assets/polarkoordinaten_punkt.png" alt="Ein Punkt in kartesichen Koordinaten und Polarkoordinaten">


Der Punkt, den wir ganz normal im kartesischen Koordinatensystem als $p=(1,2)$ beschreiben würden, wird in Polarkoordinaten als $p=(2,24; 63,4)$ beschrieben. Das ist einmal der Abstand zum Ursprung, nämlich $r=2,24$ und der Winkel $\varphi = 63,4$, welcher hierbei gegen den Uhrzeigersinn ausgehend von der x-Achse gemessen wird.

Es gibt auch noch Kugel-Koordinaten, das sind quasi Polarkoordinaten in 3D, mit zwei Winkeln und einem Radius.
<h3>Wozu sind Polarkoordinaten gut?</h3>
Unser kartesisches Koordinatensystem ist doch super, warum brauchen wir ein neues? Nunja manche Dinge lassen sich in der Praxis leichter in Polarkoordinaten behandeln, als im kartesischen System. Ein Kompass zum Beispiel zeigt natürlich einen Winkel an, in den man geht, und nicht einen Richtungsvektor. Auch Punkte auf der Erdoberfläche werden in Polarkoordinaten (Kugelkoordinaten) angegeben, das habt ihr sicher schon einmal gesehen. Google Maps zum Beispiel gibt die Position von wo aus ihr auf die Erde schaut auch damit an: (Winkel zum Äquator, Winkel zum Nullmeridian, Abstand zum Erdmittelpunkt bzw. zur Erdoberfläche). Zum Beispiel:

<a href="https://www.google.de/maps/@49.4068567,8.7044139,4349m/data=!3m1!1e3">https://www.google.de/maps/@49.4068567,8.7044139,4349m/data=!3m1!1e3</a>

In der Mathematik sind die Polarkoordinaten immer dann wichtig, wenn Dinge auf Kreisen, Kugeln, oder Zylindern geschehen. Beispielsweise wenn man eine mehrdimensionale Funktion über einen Kreis integriert, was vor allem bei komplexen Zahlen etwas sehr wichtiges ist.
Umrechnen von kartesischen Koordinaten in Polarkoordinaten

Schauen wir uns das folgende Bild an, auf dem der Punkt $p=(x,y)$ in kartesischen Koordinaten eingetragen ist. Wie kommen wir nun auf die Polarkoordinaten $(r, \varphi)$ desselben Punktes? Dazu muss man einfach nur ein bisschen Geometrie machen.

<img src="{{ site.baseurl }}/assets/polarkoordinaten.png" alt="Ein Punkt in kartesichen Koordinaten und Polarkoordinaten">

<h3>Der Radius r</h3>
Man sieht leicht, dass $r$ einfach die Hypothenuse eines rechtwinkligen Dreiecks ist, mit den Seitenlängen $x$ und $y$ als Katheten. Mit dem Satz des Pythagoras kommen wir also auf $r^2 = x^2 + y^2$, also

$$ r = \sqrt{x^2 + y^2} $$
<h3>Der Winkel $\varphi$</h3>
Zunächst ein Wort der Warnung: Ich erkläre hier genau, wie man auf die Formel für $\varphi$ kommt. Wen das nicht interessiert, kann sich einfach die Formel am Ende des Abschnitts merken. Ich würde euch aber trotzdem raten, wenigstens einmal durchdacht zu haben, warum das so berechnet werden kann.

Für den Winkel gibt es mehrere Möglichkeiten, auch diese erhält man einfach durch Anwenden von Geometrie. Beginnen wir zunächst mit einem Punkt $p=(x,y)$ im ersten Quadranten, das heißt mit $x>0$ und $y>0$. Dann ergibt sich offensichtlich ein rechtwinkliges Dreieck, wie eben im Bild oben.

Erinnert ihr euch noch an die Winkelfunktionen im Dreieck? Wie waren nochmal Sinus, Kosinus und Tangens definiert? Denkt mal kurz nach, bevor ihr weiterlest!

$$ \begin{align} \sin(\varphi) &= \frac{\mbox{Gegenkathete}}{\mbox{Hypothenuse}} \\ \cos(\varphi) &= \frac{\mbox{Ankathete}}{\mbox{Hypothenuse}} \\ \tan(\varphi) &= \frac{\mbox{Gegenkathete}}{\mbox{Ankathete}}\end{align} $$

Aus jedem der Gleichungen kann man nun eine Formel für $\varphi$ herleiten: Die Ankathete von $\varphi$ ist x, die Gegenkathete ist y und die Hypothenuse ist r. Dann müssen wir nur noch die Umkehrfunktion machen, also für Kosinus z.B:

$$ \begin{align} \cos(\varphi) &= \frac{x}{r} \\ \Rightarrow \varphi &= \arccos(\frac{x}{r}) \end{align} $$

Ich würde es immer mit Sinus oder Kosinus machen, denn beim Tangens würde ja im Bruch $\frac{x}{y}$ stehen und dann müsste man darauf achten, was passiert wenn $y=0$ ist. Das können wir uns mit Sinus und Kosinus sparen, weil wir da durch $r$ teilen. Das kann natürlich auch 0 sein, aber dann sind wir eh schon fertig (siehe Abschnitt zum Sonderfall r=0 unten).
<h3>Punkte im zweiten Quadranten</h3>
Was ist aber nun, wenn $p$ nicht im ersten Quadranten liegt, sondern im zweiten Quadranten, also $x<0$ und $y \geq 0$? Dann liegt der gesuchte Winkel nicht mehr innerhalb des rechtwinkligen Dreieks, aber die trigonometrischen Funktionen sind trotzdem definiert. Deren Definitionen möchte ich hier nicht durchgehen, aber ich möchte mal zeigen, wie man anhand von Additionstheoremen der trigonometrischen Funktionen zeigen kann, dass das ganze auch bei Winkeln in den anderen Quadranten funktioniert.


<img src="{{ site.baseurl }}/assets/polarkoordinaten2.png" alt="Ein Punkt in Polarkoordinaten im zweiten Quadranten">


Wir haben hier also wieder ein rechtwinkliges Dreieck mit Seitenlängen $-x$ (ja, $-x$, denn $x$ ist ja negativ und eine Seitenlänge ist immer positiv), $y$, und $r$. Natürlich gilt dort auch wieder der Kosinus und wir haben $\cos(\alpha) = \frac{-x}{r}$. Und es gilt offenbar $\varphi = \pi - \alpha$. Damit und mit dem Satz über Kosinus, dass $\cos(\pi - x) = -\cos(x)$ ist (wie gesagt, das muss man nicht unbedingt auswendig wissen, aber man sollte wissen, dass es sowas gibt) können wir auch für ein $p$ im zweiten Quadranten unsere Formel herleiten:

$$ \begin{align} \cos(\alpha) &= \frac{-x}{r} \\ \cos(\pi - \varphi) &= \frac{-x}{r} \\ -\cos(\varphi) &= \frac{-x}{r} \\ \varphi &= \arccos(\frac{x}{r}) \end{align} $$
<h4>Punkte unter der x-Achse: vierter Quadrant</h4>
Wenn der Punkt unter der x-Achse liegt, können wir es so ähnlich machen. Beispielsweise im vierten Quadranten: Dann haben wir auch ein rechtwinkliges Dreieck, mit den Seitenlängen $x$, $-y$ und $r$ ($y$ ist negativ, deshalb das Minus). Außerdem haben wir den Zusammenhang $\varphi = 2\pi - \alpha$.

Dann nutzen wir wieder die Formel für Kosinus wie eben, und die Formel $\cos(-x) = \cos(x) $.

$$ \begin{align} \cos(\alpha) &= \frac{-x}{r} \\ \cos(2\pi - \varphi) &= \frac{-x}{r} \\ \cos(\pi - (\varphi - \pi)) &= \frac{-x}{r} \\ -\cos(\varphi-\pi) &= \frac{-x}{r} \\ -\cos(\pi-\varphi) &= \frac{-x}{r} \\ \cos(\varphi) &= \frac{-x}{r} \\ \varphi &= \arccos(\frac{-x}{r}) \end{align} $$


<img src="{{ site.baseurl }}/assets/polarkoordinaten3.png" alt="Ein Punkt in Polarkoordinaten im vierten Quadranten">


<h3>Punkt im dritten Quadranten</h3>

Probiert einmal selbst aus, dort auf die Fomel zu kommen!

<h3>Zusammenfassung: Berechnung von $\varphi$</h3>
Insgeamt ergibt sich nun für den Winkel $\varphi$:

$$ \varphi =  \begin{cases} \arccos(\frac{x}{r}) & y \geq 0 \\ 2\pi-\arccos(\frac{x}{r}) & y < 0 \end{cases} $$
<h4>Noch ein kurzer Hinweis zum Winkel: Winkel in bestimmten Intervallen</h4>
Es gibt bei dieser Formel noch ein kleines Problem. Wie ihr wissen solltet, sind Sinus und Kosinus periodisch, der Funktionswert ist nämlich alle $2\pi$ gleich, also z.B. $cos(0) = cos(2\pi) = cos(4\pi)$ und so weiter. Das bedeutet, dass der Punkt mit Polarkoordinaten $(r, \varphi)$ derselbe ist wie $(r, \varphi + 2\pi)$. Bei der Berechnung oben ist der Winkel so definiert, dass er im Intervall $[0, 2\pi)$ liegt und damit genau dem Winkel ausgehend von der x-Achse im Uhrzeigersinn entspricht. In der Regel ist das die Winkeldefinition, die man haben will.

Ab und an will man aber den Winkel auch mal im Interval $(-\pi, \pi]$ haben, also ausgehend von der x-Achse maximal 180° im Uhrzeigersinn, oder 180° gegen den Uhrzeiger sinn. Für diesen Fall, benutzt einfach folgende Gleichung:

$$ \varphi =  \begin{cases} \arccos(\frac{x}{r}) & y \geq 0 \\ -\arccos(\frac{x}{r}) & y < 0 \end{cases} $$
Der Sonderfall r=0

In diesem Fall kann man jeden beliebigen Winkel nehmen, denn wenn $r=0$, dann kann der Punkt nur auf dem Ursprung liegen, das sollte klar sein. Der Einfachheit halber nimmt man einfach $\varphi = 0$.
<h2>Umrechnung von Polarkoordinaten in kartesische Koordinaten</h2>
Diese Richtung der Umrechnung ist viel leichter, weil man sich den Käse mit den Winkeln sparen kann, ob die in einem bestimmten Intervall liegen oder nicht. Das heißt, wir haben bereits einen Winkel $\varphi$ und einen Radius $r$ gegeben und können wieder die geometrischen Funktionen von Sinus und Kosinus ausnutzen um auf x (die Ankathete von $\varphi$) und y (die Gegenkathete) zu kommen.

Also:

$$ \sin(\varphi) = \frac{\mbox{Gegenkathete}}{\mbox{Hypothenuse}} = \frac{y}{r} \\ \Rightarrow y = r\sin(\varphi) $$

Genauso kommt man dann auf

$$ x = r\cos(\varphi) $$

Für die Fälle in den anderen Quadranten würde man dann wieder mittels der Additionstheoreme auf dasselbe kommen.
