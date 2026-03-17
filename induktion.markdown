---
layout: page
title: Induktion (Beweismethode)
nav: true
permalink: /induktion/
description: Eine verständliche Erklärung der Beweisführung via vollständiger Induktion.
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

<h2 style="text-align: left;">Induktion - Wozu das ganze? Was macht man damit?</h2>
Induktion (auch "vollständige Induktion") ist eine Art der mathematischen Beweisführung. Mit dieser Beweismethode werden z.B. Formeln gezeigt, die für alle natürlichen Zahlen (oder alle natürlichen Zahlen ab einem bestimmten Wert) gelten sollen.
<h2 style="text-align: left;">Wie wird eine Induktion ganz grob gemacht?</h2>
Es funktioniert so, dass man die Aussage oder Formel, die für alle natürlichen Zahlen gelten soll, zunächst für den Fall n=1 zeigt (man nennt das <em>Induktionsanfang</em>). Dies geschieht einfach durch einsetzen und ausrechnen. Nachdem dies geschehen ist, wird der <em>Induktionsschritt </em>gezeigt: Vorrausgesetzt, die Formel gilt für ein gewisses <em>n, </em>so zeigen wir, dass diese Formel dann auch für (<em>n+1</em>) gilt. Das war's. Denn da wir es für n=1 gezeigt haben, haben wir mit dem Induktionsschritt auch gezeigt, dass es für n+1, also 2, genauso gilt. Weil wir nun wissen, dass es für n=2 gilt, folgt aus dem Induktionsschritt, dass es auch für n+1, also 3, gilt und so weiter und so fort. Damit haben wir es automatisch für alle natürlichen Zahlen gezeigt. Wie bereits angedeutet, kann der allererste Wert auch verschieden von 1 sein, häufig 0 oder 2, manchmal aber eben auch irgendeine andere natürliche Zahl.

Obwohl meist unterschiedlich schwierig, sind <em>Induktionsanfang </em>und<em> Induktionsschritt </em>gleichermaßen wichtig. Nur wenn beide sauber gezeigt wurden, ist die Aussage bewiesen.

Der Induktionsschritt ist natürlich schwieriger. In der Regel muss man hier aber einfach folgende Idee verfolgen: man schreibt die Formel für (n+1) auf, und versucht so bald wie möglich die Annahme an n einzusetzen. Schauen wir uns ein simples Beispiel an:
<h3>Erklärung von Induktion an einem Beispiel</h3>
Um zu zeigen wie Induktion funktioniert, möchte ich das Beispiel der so genannten geometrischen Reihe benutzen. Die Formel, die hieraus entsteht, ist eine sehr wichtige und es ist immer gut, sie im Hinterkopf zu behalten. Sie lautet:

$$ \sum_{k=0}^n q^k = \frac{1 - q^{n+1}}{1-q}, ~ \forall n \geq 0 $$

Wir wollen also zeigen, dass diese Formel für alle Zahlen ab n=0 gilt, das heißt wir beginnen mit dem Induktionsanfang für die erste mögliche Zahl, also eben n=0:
<h4>Induktionsanfang</h4>
Der Induktionsanfang wird oft unterschätzt, da er oft sehr leicht ist. Es ist aber extrem wichtig, dass er korrekt und sauber gemacht wird, will heißen, es muss <strong><em>klar erkenntlich sein</em></strong>, dass wirklich die gegebene Formel für das erste n gezeigt wurde. Dies geht zum Beispiel so, dass man die zu zeigende Formel in die rechte Seite (RS) und linke Seite (LS) aufteilt, und zeigt, dass diese beiden für n=0 gleich sind. Das würde dann z.B. so aussehen:

$$ \begin{align*} \mbox{LS} &= \sum_{k=0}^{0} q^k = q^0 = 1 \\
\mbox{RS} &= \frac{1-q^{0+1}}{1-q} = \frac{1-q}{1-q} = 1
\end{align*}
\Rightarrow \mbox{LS}=\mbox{RS}$$

Was nicht geht, wäre nur die erste Zeile aus obigem Bild als Induktionsanfang zu nehmen. 80% der Studenten würden das als Induktionsanfang nehmen und dann noch einen Haken dahinter setzen. Es ist aber nicht ausreichend, da damit nicht der nötige Zusammenhang zwischen linker Seite und rechter Seite der Gleichung gezeigt würde. Man könnte den Induktionsanfang auch folgendermaßen schreiben, das wäre auch ok, sozusagen von rechts und von links kommen und in der Mitte treffen:

$$ LS = \sum_{k=0}^{0} q^k = q^0 = 1 = \frac{1-q}{1-q} = \frac{1-q^{0+1}}{1-q} = RS $$

Auch hier ist eindeutig, dass die zu beweisende Formel für n=0 gezeigt wurde.
<h4>Induktionsvoraussetzung (auch Induktionsannahme)</h4>
Hier reicht es zu schreiben, dass wir annehmen, dass die zu beweisende Formel für ein n aus den natürlichen Zahlen gelte. Im Induktionsschritt werden wir dann diese Annahme benutzen, um zu zeigen, dass es dann auch für den Nachfolger (n+1) gilt. Für die Induktionsvoraussetzung schreiben wir also wörtlich:

$$ \mbox{Die Formel } \sum_{k=0}^n q^k = \frac{1 - q^{n+1}}{1-q} \mbox{ gelte für ein beliebiges, aber festes } n\in\mathbb{N} $$
<h4>Induktionsschritt</h4>
Dies ist der schwierigste Teil, aber er folgt eigentlich immer demselben Konzept: Zunächst schauen wir, was eigentlich zu zeigen ist (wir schreiben uns also einmal die Formel für (n+1) auf), und müssen dann versuchen, die Induktionsvoraussetzung einzusetzen, um die Formel zu beweisen. Das ist schließlich der Kerngedanke: Wir wollen etwas für (n+1) zeigen, unter der Annahme, dass etwas für n schon gilt.

Schreiben wir also zunächst einmal auf, was wir zeigen wollen, die Formel der geometrischen Reihe für (n+1):

$$ \sum_{k=0}^{n+1} q^k = \frac{1 - q^{n+2}}{1-q} $$

Wir müssen uns nun überlegen, wie wir die Induktionsvoraussetzung einfließen lassen können, das heißt, wir fangen zum Beispiel mit der linken Seite an, und versuchen, den Term so umzuschreiben, dass eine Seite der Induktionsvoraussetzung da steht. Hierfür muss man immer ein bisschen überlegen, wie das geschickt gehen kann. In diesem Beispiel ist es recht simpel: Die zu zeigende Summenformel kann aufgeteilt werden in die Summe bis n, plus dem (n+1). Summanden, also so:

$$ \sum_{k=0}^{n+1} q^k = \sum_{k=0}^{n} q^k + \sum_{k=n+1}^{n+1} q^k = \underline{\sum_{k=0}^{n} q^k} + q^{n+1} $$

Jetzt haben wir unter anderem die linke Seite unserer Induktionsvoraussetzung in der Formel stehen (der unterstrichene Teil). Die wollen wir jetzt einsetzen. Hierbei ist besonders wichtig dass wir <strong><em>erkenntlich machen, wo die Induktionsvoraussetzung eingeht. </em></strong>Das geht zum Beispiel, wenn wir über das Gleichheitszeichen eine kleine Bemerkung machen, wie im folgenden gezeigt. Danach formen wir die Terme so um, dass wir schließlich auf die rechte Seite der zu zeigenden Fomel kommen. Hier funktioniert das mit ein paar Bruchrechnungen. Der komplette Induktionsschritt ist also:

$$ \begin{align*}
\sum_{k=0}^{n+1} q^k &= \sum_{k=0}^{n} q^k + \sum_{k=n+1}^{n+1} q^k = \sum_{k=0}^{n} q^k + q^{n+1} \\
&\stackrel{IV}{=} \frac{1-q^{n+1}}{1-q} + q^{n+1} = \frac{1-q^{n+1}}{1-q} + q^{n+1}\frac{1-q}{1-q} \\
&= \frac{1-q^{n+1}}{1-q} + \frac{q^{n+1} - q^{n+2}}{1-q} = \frac{1-q^{n+2}}{1-q}
\end{align*} $$

Das wars! Wir haben die Formel für das erste n gezeigt, und unter der Annahme, dass sie für ein beliebiges n gilt, gezeigt, dass sie dann auch für den Nachfolger gilt. Damit haben wir die Ausgangsformel mittels vollständiger Induktion für alle natürlichen Zahlen gezeigt.
<h2>Ein zweites Beispiel</h2>
Auch Ungleichungen können oft mittels vollständiger Induktion gezeigt werden. Hierfür ein kleines Beispiel. Zu zeigen ist die so genannte Bernoulli-Ungleichung:

$$ (1+x)^n \geq 1+nx, n \geq 0 $$
<h4>Induktionsanfang</h4>
Wie oben besprochen, zeigen wir die Formel für n=0 und achten auf saubere Darstellung:

$$ (1 + x)^0 = 1 = 1 + 0x $$

(aus der Gleichheit folgt natürlich insbesondere $(1+x)^0 \geq 1+0x $)
<h4>Induktionsvoraussetzung</h4>
Auch hier wieder nur die Formulierung:

$$ \mbox{Die Formel } (1+x)^n \geq 1+nx \mbox{ gelte für ein beliebiges, aber festes } n\in\mathbb{N} $$
<h4>Induktionsschritt</h4>
Zunächst wieder die Formel, für n+1 hingeschrieben, um vor Augen zu haben, was wir zeigen müssen:

$$ (1+x)^{n+1} \geq 1 + (n+1)x $$

Wir beginnen zum Beweis wieder mit der linken Seite, und formen so um, dass wieder ein Teil der Induktionsvoraussetzung dasteht. Diese setzen wir dann ein und markieren dies über dem Ungleichheitszeichen. Schlussendlich dann noch eine simple Ungleichung (diese gilt, weil $n\geq0$ und $x^2\geq 0$) und wir sind fertig:

$$ \begin{align*}
(1+x)^{n+1} &= (1+x)(1+x)^n \stackrel{IV}{\geq} (1+x) (1+nx) \\
&= 1 + x + nx + nx^2 = 1+(n+1)x + nx^2 \geq 1+(n+1)x \end{align*} $$
