---
layout: page
title: Folgen und Grenzwerte
nav: true
permalink: /folgen-und-grenzwerte/
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


<h3>Was ist eine Folge?</h3>
Eine Folge in der Mathematik eine Sammlung von Objekten, das sind meistens Zahlen, können aber auch Mengen oder Funktionen sein. Eine Folge kann endlich oder auch unendlich viele Folgenglieder enthalten. In den meisten Fällen geht es um Folgen mit unendlich vielen Folgegliedern, alles andere wäre ja auch langweilig.

Die Elemente einer Folge sind mit natürlichen Zahlen (und manchmal der Null) nummeriert, also z.B. $(a_0, a_1, a_2, a_3, \ldots)$. Für eine unendliche Folge schreibt man auch $(a_n)_{n\in \mathbb{N}_0}$. Oft lässt man auch das $n\in \mathbb{N}_0$ oder $n\in \mathbb{N}$ weg, sodass nur noch die Klammern die Folge andeuten: $(a_n)$. Ohne die Klammern wäre $a_n$ dann einfach das $n$-te Folgeglied.
<h3>Beispiele für Folgen</h3>
<ul>
	<li>$(a_n)_{n\in \mathbb{N}_0}$ mit $a_n = n$, also $(0, 1, 2, 3, 4, \ldots)$, die Folge der natürlichen Zahlen (mit Null)</li>
	<li>$(b_n)_{n\in \mathbb{N}_0}$ mit $b_n = (-1)^n$, also $(1, -1, 1, -1, 1,\ldots)$, eine alternierende Folge</li>
	<li>$(c_n)_{n\in \mathbb{N}}$ mit $c_n = \frac{1}{n}$, also $(1, \frac{1}{2}, \frac{1}{3}, \frac{1}{4},\ldots)$, eine Folge, die gegen Null geht ("konvergiert")</li>
	<li>$(d_n)_{n\in \mathbb{N}_0}$ mit $d_0=0$, $d_1=1$ und $d_n+2=d_n+d_{n+1}$, eine rekursiv definierte Folge, in der jedes Glied die Summe der beiden vorherigen ist: $(0, 1, 1, 2, 3, 5, 8, \ldots)$. Diese berühmte Folge heißt <em>Fibonacci-Folge</em>.</li>
</ul>

<h3>Konvergenz und Divergenz von Folgen</h3>

Wirklich interessant sind Folgen eigentlich nur, wenn sie unendlich viele Glieder haben. Dann kann man nämlich schauen, ob eine solche Folge einen Grenzwert hat, also <em>konvergent</em> ist, oder nicht, dann nennen wir sie <em>divergent. </em>Bei letzerem unterscheidet man noch zwischen divergent und bestimmt divergent. Hierbei heißt <em>bestimmt divergent</em> einfach, dass die Folge gegen $+\infty$ oder $-\infty$ geht, und zwar nur gegen eins von beiden, und nicht wild hin und her hüpft.<em>
</em>

Anschaulich erklärt bedeutet ein Grenzwert, dass eine Folge auf einen bestimmten Wert "zuläuft".

### Beispiele

<ul>
	<li>$(a_n)_{n\in \mathbb{N}} = (1+\frac{1}{n})_{n\in \mathbb{N}}$ geht gegen Eins, weil der Bruch $\frac{1}{n}$ immer kleiner wird und irgendwann verschwindend gering ist. Diese Folge ist konvergent mit Grenzwert 1. Weiter unten ist diese Folge abgebildet.</li>
	<li>$(n)_{n\in \mathbb{N}}$, also (1, 2, 3, 4, 5, ...) ist <em>bestimmt divergent</em>, sie geht gegen Unendlich</li>
	<li>$((-1)^n)_{n\in \mathbb{N}}$ ist divergent, sie springt ("alterniert") immer zwischen $-1$ und $1$.</li>
	<li>$((-1)^n~ n)_{n\in \mathbb{N}}$, also (-1, 2, -3, 4, -5, 6, ...), ist nur<em> divergent</em>, da sie sozusagen gegen $+\infty$ und $-\infty$ gleichzeitig geht: Alle Folgeglieder für gerade $n$ gehen gegen $+\infty$, die ungeraden gegen $-\infty$. Man sagt dazu auch "Teilfolgen"</li>
	<li>$((-1)^n\frac{1}{n})_{n\in \mathbb{N}}$ ist konvergent. Sie alterniert zwar, geht aber trotzdem gegen Null.</li>
	<li>$(e^{-n})_{n\in \mathbb{N}}$ ist konvergent, sie konvergiert gegen Null.</li>
	<li>$(1)_{n\in \mathbb{N}}$, also die konstante Folge $(1, 1, 1, 1, 1, \ldots)$ ist konvergent mit Grenzwert 1.</li>
</ul>

<br/>

<h3>Definition von Konvergenz einer Folge</h3>


Der Grenzwert einer Folge ist über den Abstand der Folge zum Grenzwert definiert: Eine Folge $(a_n)_{n\in \mathbb{N}}$ hat einen Grenzwert $a$, wenn für alle $\varepsilon>0$ ab einem gewissen $N\in \mathbb{N}$ für alle $n\geq N$ gilt, dass:

$$|a_n - a| < \varepsilon$$

Das bedeutet anschaulich: Für jeden noch so kleinen Abstand $\varepsilon$ sind alle Folgeglieder ab einem gewissen Glied näher an diesem Grenzwert als der Abstand.

Man schreibt dann $\lim_{n\rightarrow \infty} a_n = a$, oder auch $a_n \rightarrow a$, also $a$ ist der Grenzwert der Folge $(a_n)_{n\in \mathbb{N}}$.



<img src="{{ site.baseurl }}/assets/grenzwert_def.png" alt="Folge mit Grenzwert">


Das ist eine Folge mit Grenzwert 1. Ab einem gewissen N sind alle Folgeglieder weniger als Epsilon von 1 entfernt. Und egal wie klein dieses Epsilon ist, irgendwann sind alle nah genug dran. Wenn das Epsilon sehr klein ist, dauert es einfach etwas länger, bis man zu diesem Punkt kommt.


<h3>Grenzwert vs. Häufungspunkt</h3>


Es gibt noch eine kleine Unterscheidung bei Grenzwerten: Wir haben gelernt, der Grenzwert ist der Punkt, dem ab einem gewissen $n$ alle Folgeglieder sehr nahe sind. Es gibt noch einen zweiten interessanten Punkt, nämlich einen <strong>Häufungspunkt</strong>. Das ist ein Punkt, dem unendlich viele Folgeglieder nahe sind. Wo ist der Unterschied? Naja, die Folge $((-1)^n)_{n\in \mathbb{N}}$ hat die Häufungspunkte $1$ und $-1$, denn unendlich viele Folgeglieder sind sehr nahe bei $1$ (sie sind sogar exakt 1), und unendlich viele Folgeglieder sind sehr nahe an $-1$. Diesen beiden Punkten sind also unendlich viele Folgeglieder nahe, aber nicht alle ab einem gewissen $n$. Diese Folge hat also keinen Gernzwert, aber zwei Häufungspunkte. Anders herum ist aber ein Grenzwert auch immer ein Häufungspunkt, denn wenn ab einem $n$ alle Folgeglieder dem Grenzwert sehr nahe sind, dann sind das ja auch unendlich viele.


<h3>Konvergenz prüfen anhand der Definition</h3>


Wir wollen nun mittels der Definition beweisen, dass eine Folge einen Grenzwert hat. Nehmen wir hierfür als Beispiel die Folge $(a_n)_{n\in \mathbb{N}}$ mit $a_n = \frac{1}{n}$. Zunächst braucht man einmal eine Vermutung für den Grenzwert, welche wir dann mittels der Definition überprüfen. Um eine Vermutung zu bekommen, schaut man sich erstmal die ersten Folgeglieder an und guckt dann nochmal, was für große $n$ passiert. Ich denke, hier ist offensichtlich, dass die Folge gegen $0$ geht. Also müssen wir zeigen:

Für jedes $\varepsilon > 0$ existiert ein $N\in \mathbb{N}$, sodass $\|a_n - 0\| < \varepsilon$ für alle $n \geq N$.

Heißt also: Für jeden noch so kleinen Abstand zur Null gibt es ein Folgeglied, ab welchem alle Folgeglieder noch näher an Null sind, als dieser Abstand. Zunächst einmal vereinfachen wir den Term $\|a_n - 0\|$:

$$ |a_n - 0| = |\frac{1}{n}-0| = |\frac{1}{n}| = \frac{1}{n} $$

Nun müssen wir für jedes $\varepsilon>0$ ein $N$ finden, sodass $\|a_n - 0\| < \varepsilon$, beziehungsweise also $\frac{1}{n}<\varepsilon$ für alle $n\geq N$ gilt. Das können wir noch umstellen zu:

$$n>\frac{1}{\varepsilon}$$

Wir müssen also ein $N$ (in Abhängigkeit von $\varepsilon$) finden, ab welchem diese Aussage gilt. Nunja, und das <em>archimedische Axiom</em> sagt (im Wesentlichen) über die natürlichen Zahlen: zu jeder beliebigen reellen Zahl finden wir eine natürliche Zahl $N$, sodass $N$ größer ist als diese Zahl. Also finden wir auch zu $\frac{1}{\varepsilon}$, was ja auch nur eine reelle Zahl ist, immer ein $N$ welches größer ist, nämlich gerade die Zahl, die wir durch aufrunden erhalten (es sei denn, die vorgegebene Zahl ist bereits eine natürliche Zahl, dann addieren wir einfach eine 1 und haben eine größere).

<h3>Hä? Was bedeutet das archimedische Axiom?</h3>

Klingt irgendwie doof oder? Aber das tut es nicht mehr, wenn man sich das ganze nochmal am Beispiel vor Augen hält: Wir sagen: "Der Grenzwert der Folge $\frac{1}{n}$ ist Null". Jemand zweifelt es an und sagt: "Findet ihr denn auch zu $\varepsilon = 0.00001$ ein $N$, sodass ab diesem $N$ alle Folgeglieder näher an Null sind als $0.00001$?"

Und wir sagen: "Ja sicher, wir müssen nur eine natürliche Zahl finden, die größer ist als $\frac{1}{\varepsilon}$", also größer als $\frac{1}{0.00001} = 100000$. Also bitte: Ab $N=100001$ sind alle Glieder unserer Folge näher an Null als $0.00001$. Und dass dies für wirklich jedes beliebige Epsilon funktioniert, genau das sagt uns das archimedische Axiom!

<h3>Ein Beispiel mit falschem Grenzwert</h3>


Das ganze eben klang schon etwas weit hergeholt, aber schauen wir mal, was passiert wäre, wenn unsere ursprüngliche Vermutung falsch war, wenn wir gesagt hätten, der Grenzwert sei $1$:

$$ | a_n - 1| = |\frac{1}{n} -1 |  = 1 - \frac{1}{n} < \varepsilon \Leftrightarrow n-1 < n\varepsilon \Leftrightarrow n(1-\varepsilon) < 1 \Leftrightarrow n < \frac{1}{1-\varepsilon} $$

Nunja, und wenn wir jetzt ein Epsilon gegeben bekommen, z.B. $\varepsilon=0.1$, steht dort $n < \frac{1}{0.9}$, also $n<1.\overline{1}$, und da $n$ eine natürliche Zahl ist, bedeutet dies dasselbe wie $n\leq 1$. Das heißt, $a_n$ ist nur für alle $n\leq 1$ "nah" an dem hypothetischen Grenzwert $1$ ist. Und das stimmt ja auch, das erste Folgeglied ist genau 1. Und dann gehen die Folgeglieder weg von 1.
Die Grenzwertdefinition ist also nicht erfüllt, also war $1$ nicht der Grenzwert!


<h3>Rechenregeln und Grenzwertsätze</h3>

Für zwei konvergente Folgen $a_n \rightarrow a$ und $b_n \rightarrow b$ gelten die Rechenregeln
<ul>
	<li>$ \lim_{n\rightarrow \infty}(a_n + b_n) =  \lim_{n\rightarrow \infty} a_n +  \lim_{n\rightarrow \infty}b_n = a+b$</li>
	<li>$ \lim_{n\rightarrow \infty} (a_n - b_n) =  \lim_{n\rightarrow \infty} a_n -  \lim_{n\rightarrow \infty} b_n =  a-b$</li>
	<li>$ \lim_{n\rightarrow \infty}(c\cdot a_n) = c \cdot  \lim_{n\rightarrow \infty}a_n = c \cdot a$</li>
	<li>$ \lim_{n\rightarrow \infty}(c + a_n) = c +  \lim_{n\rightarrow \infty}a_n = c + a$</li>
	<li>$ \lim_{n\rightarrow \infty}(a_n \cdot b_n) = ( \lim_{n\rightarrow \infty}a_n )\cdot ( \lim_{n\rightarrow \infty} b_n) = a\cdot b$</li>
	<li>$ \lim_{n\rightarrow \infty}\frac{a_n}{b_n} = \frac{ \lim_{n\rightarrow \infty}a_n}{ \lim_{n\rightarrow \infty}b_n} = \frac{a}{b}$, falls $b_n\neq 0$ ab einem gewissen $n$ (damit ist auch $b\neq 0$).</li>
</ul>
Hier mit kann man dann für kompliziertere Folgen den Grenzwert bestimmen:

$$ \lim_{n\rightarrow \infty}\frac{5}{n} \cdot (1+\frac{1}{n}) + 3 = 5 (\lim_{n\rightarrow \infty} \frac{1}{n}) \cdot ( \lim_{n\rightarrow \infty} 1 + \frac{1}{n}) + 3 = 5 \cdot 0 \cdot 1 + 3 = 3 $$

Dabei muss man unbedingt beachten, dass alle Folgen in unserem Term auch wirklich konvergent sind! Diese Rechnungen darf man nämlich nur dann ausführen, sonst würde so etwas passieren:

$$ \lim_{n\rightarrow \infty} 1 = \lim_{n\rightarrow \infty} \frac{n}{n} = ( \lim_{n\rightarrow \infty} n) \cdot ( \lim_{n\rightarrow \infty} \frac{1}{n}) = \infty \cdot 0 $$.

Naja, und da kommt nur falsches bei heraus. Deshalb:

<img src="{{ site.baseurl }}/assets/memes/meme_folgen.jpg" alt="Bei Grenzwertsätzen immer Konvergenz aller Teile prüfen">


<h4>Grenzwertbestimmung durch Ausklammern</h4>
Ein typisches Verfahren bei Folgen mit Brüchen ist das Ausklammern der höchsten Potenz und dann kürzen, hier ein Beispiel:

$$ \lim_{n\rightarrow \infty}\frac{4n^2 + 3n -1}{2n^2 -2n +8} = \lim_{n\rightarrow \infty} \frac{n^2 (4  + \frac{3}{n} - \frac{1}{n^2})}{n^2(2 - \frac{2}{n} + \frac{8}{n^2})} =  \lim_{n\rightarrow \infty} \frac{(4  + \frac{3}{n} - \frac{1}{n^2})}{(2 - \frac{2}{n} + \frac{8}{n^2})} $$

An dieser Stelle haben wir nur noch einen Term mit lauter konvergenten Folgen und können daher die Grenzwertsätze anwenden. Da $\frac{2}{n}$, $\frac{8}{n^2}$ usw. gegen Null gehen, bleibt insgesamt:

$$ \lim_{n\rightarrow \infty} \frac{(4  + \frac{3}{n} - \frac{1}{n^2})}{(2 - \frac{2}{n} + \frac{8}{n^2})} = \frac{4+0-0}{2-0+0} = 2$$
<h3>Wichtige Grenzwerte</h3>
Die folgenden Grenzwerte solltet ihr unbedingt wissen:
<ul>
	<li>$\frac{1}{n} \rightarrow 0 $</li>
	<li>$\frac{1}{n^2} \rightarrow 0 $</li>
	<li>$\frac{1}{n^k} \rightarrow 0 $ für jedes $k\geq 1$</li>
	<li>$(1+\frac{1}{n})^n \rightarrow e $</li>
	<li>$(1+\frac{x}{n})^n \rightarrow e^x $</li>
	<li>$ \sqrt[n]{n} \rightarrow 1$</li>
</ul>
