---
layout: page
title: Gruppen, Ringe, Körper
nav: true
permalink: /gruppen-ringe-koerper/
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


<h3>Was sind Gruppen, Ringe oder Körper ganz allgemein?</h3>
Gruppen, Ringe und Körper sind algebraische Strukturen, die aus der Kombination einer Menge (das können Zahlen, Matrizen, aber zum Beispiel auch Funktionen sein) mit verschiedenen mathematischen Verknüpfungen (Additionen, Multiplikationen) entstehen und dabei gewisse Anforderungen erfüllen.
<h3>Wozu braucht man Gruppen, Ringe und Körper?</h3>
Vielen fällt es schwer, den Sinn hinter diesen Strukturen zu erkennen. Meistens deshalb, weil es so trivial scheint: Man lernt beispielsweise die Eigenschaften, die die reellen Zahlen zu einem Körper machen, erst in der Uni, nachdem man schon viele Jahre völlig selbstverständlich mit diesen Eigenschaften gerechnet hat. Und dann wird auch noch hinterfragt, ob denn $1 \cdot 5$ wirklich $5$ ist.

Aber das ist wichtig. Sicherlich müssen die wenigsten von euch später nochmal darauf zurückgreifen, aber es sind die absoluten Grundlagen auf denen die Mathematik aufbaut. Deshalb muss man einmal auch diese Grundlagen durchkauen, denn in der Mathematik muss jede Aussage beweisbar sein und das geht nur, wenn auch die kleinsten Bausteine bewiesen sind. Darauf kann man dann aufbauen und "richtige" Mathematik betreiben.

Die Grundlagen und einige Beispiele wollen wir hier kurz anschauen.
<h3>Gruppen</h3>
Eine Gruppe ist eine Kombination aus einer Menge $G$ und einer Verknüpfung $*$ von Elementen $a,b,c$ von $G$, für die gilt:
<ol>
	<li>Assoziativität, also $(a*b)*c = a*(b*c)$</li>
	<li>Es gibt ein neutrales Element $e \in G$, sodass gilt $a*e=e*a=a$</li>
	<li>Es gibt zu jedem Element $a\in G$ ein inverses Element, welches wir hier mit $a^{-1}$ bezeichnen, für das gilt: $a*a^{-1}=a^{-1}*a=e$</li>
	<li>Zusätzlich heißt die Gruppe <strong>abelsch</strong>, wenn auch Kommutativität gilt, also $a*b=b*a$.</li>
</ol>
An dieser Stelle muss man die Dinge, die man schon über Mathematik kennt, ein bisschen über Bord werfen, denn man fängt quasi nochmal bei Null an. Beispielweise ist einem ja schonmal ein $a^{-1}$ über den Weg gelaufen, das $a^{-1}$ kann aber hier verschiedenste Bedeutungen haben, je nach Art der Verknüpfung $*$, wie wir in den Beispielen sehen:
<h4>Beispiele und Gegenbeispiele für Gruppen</h4>
Die reellen Zahlen und die uns bekannte, "normale" Addition bilden eine Gruppe $(\mathbb{R}, +)$. Das neutrale Element ist hier $e=0$ und $a^{-1}$ ist einfach $-a$. Diese Gruppe ist abelsch.

Die reellen Zahlen und die uns bekannte, "normale" Multiplikation bilden "fast" eine Gruppe $(\mathbb{R}, \cdot)$. Das neutrale Element ist dann $e=1$ und $a^{-1}=\frac{1}{a}$. Warum nur "fast"? Nun, zur Zahl $0 \in \mathbb{R}$ gibt es leider kein inverses Element, da wir nicht $\frac{1}{0}$ berechnen können. Wenn wir die Null aber herausnehmen, dann passt es, $(\mathbb{R} \setminus \{0\}, \cdot)$ ist eine Gruppe. Und sie ist abelsch.

$(\mathbb{Q},+)$ sowie $(\mathbb{Q} \setminus \{ 0 \}, \cdot)$ sind abelsche Gruppen. Bei der zweiten Gruppe müssen wir die Null herausnehmen, da zur Null kein inverses Element existiert.

$(\mathbb{Z},+)$ ist eine abelsche Gruppe.

$(\mathbb{N},+)$ ist keine Gruppe, denn es existiert kein Inverses! (Das Inverse zu $5\in\mathbb{N}$ müsste ja $-5$ sein, aber das ist keine natürliche Zahl!

$(\mathbb{Z},\cdot)$ ist keine Gruppe, denn auch hier ist das Inverse zu $z \in \mathbb{Z}$, welches $\frac{1}{z}$ wäre, nicht in $\mathbb{Z}$.

Alle Matrizen bilden mit der Matrixaddition eine abelsche Gruppe $(\mathbb{R}^{n\times m}, +)$. Das inverse Element (Vorsicht! Hier ist das inverse Element in dieser Gruppe gemeint, was nicht die "inverse Matrix" ist, wie wir sie kennen (oder später noch kennen lernen werden), das Wort "invers" bezieht sich immer auf eine Verknüpfung und hier geht es ja gerade um die Addition). In der Gruppe $(\mathbb{R}^{n\times m}, +)$ ist das neutrale Element also gerade die Nullmatrix und das inverse Element zu einer Matrix $A$ gerade die Matrix $-A$.

Die invertierbaren Matrizen (bezeichnet mit $GL_n(\mathbb{R})$) bilden mit der Matrixmultiplikation eine Gruppe die <strong>nicht abelsch</strong> ist. Das neutrale Element ist die Einheitsmatrix und das Inverse ist gerade die inverse Matrix $A^{-1}$. Die Gruppe ist nicht abelsch, weil für Matrizen im Allgemeinen nicht gilt, dass $A\cdot B = B\cdot A$. Für die Eigenschaft der Gruppe ist nötig, dass die Koeffizienten der Matrix aus einem Körper (siehe unten) stammen, dies ist nötig damit für eine Matrix wirklich eine multiplikative Inverse exisiteren kann: Die invertierbaren Matrizen, die nur ganzzahlige Koeffizienten haben, bilden mit der Multiplikation zum Beispiel keine Gruppe, weil die inversen Matrizen zu diesen Matrizen in der Regel keine ganzzahligen Koeffizienten haben.

Die reellen Zahlen und die Potenzierung $\hat{ }$ (damit ist gemeint $a\hat{ } b$ bzw einfach $a^b$) bilden <strong>keine</strong> Gruppe, weil die Assoziativität nicht gilt: $(a^b)^c \neq a^{(b^c)}$! Beispiel: $(2^2)^3 = 4^3 = 64$, aber $2^{(2^3)} = 2^8 = 256$.

Die Polynome bilden mit der Addition eine abelsche Gruppe, wenn die Koeffizienten aus einer abelschen Gruppe kommen. Die uns bekannten "normalen" Polynome, wo die Koeffizienten reelle Zahlen sind, bilden also eine abelsche Gruppe. Das inverse Element zu jedem Polynom ist einfach das Polynom, wo jeder Koeffizient gerade der inverse Koeffizient ist, also ist zum Beispiel das inverse Element zu $4x^2 + x -1$ einfach $-4x^2 - x + 1$. Daran sieht man auch gleich, dass die Koeffizienten aus einer abelschen Gruppe kommen müssen, sonst würde das nicht funktionieren.

&nbsp;
<h3>Ringe</h3>
Elemente nur addieren oder nur multiplizieren reicht offensichtlich nicht aus, um richtige Mathematik zu machen, wir brauchen beide Verknüpfungen. Hier kommen Ringe ins Spiel (wobei mit "Ring" weniger etwas kreisrundes gemeint ist, sondern eher die Bedeutung "Zusammenschluss von Dingen"). Fangen wir mit der Definition an:

Ein Ring $(G, +, \cdot)$ ist eine Kombination aus einer Menge $G$ und zwei Verknüpfungen, für welche Gilt:
<ol>
	<li>$(G, +)$ ist eine abelsche Gruppe</li>
	<li>Für $\cdot$ gilt die Assoziativität: $a\cdot (b \cdot c) = (a \cdot b) \cdot c$</li>
	<li>Es gelten die Distributivgesetze: $a \cdot(b + c) = a\cdot b + a\cdot c$ und $(a+b)\cdot c = a\cdot c + b\cdot c$.</li>
</ol>
Man möchte meinen, dass der dritte Punkt in sich doppelt gemoppelt ist, aber das stimmt nicht. Für Matrizen zum Beispiel braucht man wirklich beide Gleichungen, da sich die eine nicht aus der anderen folgt. Das liegt einfach daran, dass die Matrixmultiplikation nicht kommutativ ist und es also einfach etwas anderes ist, ob man die Matrix von links oder von rechts an die Klammer multipliziert. Deshalb braucht man also beide Gleichungen in (3).

Das neutrale Element aus der Eigenschaft (1) wird als Nullelement bezeichnet.

Zusätzlich kann man einen Ring noch unitären Ring oder Ring mit Eins nennen, wenn es auch ein neutrales Element bezüglich der Multiplikation gibt. Dies muss für Ringe im allgemeinen nicht gelten.

Quizfrage: Findet einen kommutativen Ring, der kein unitärer Ring, also kein Ring mit Eins ist. Lösung am Ende der Beispiele für Ringe.
<h3>Beispiele für Ringe</h3>
$(\mathbb{R}, +, \cdot)$ bildet einen unitären Ring.

$(\mathbb{Z}, +, \cdot)$ ist ein unitärer Ring

Der Ring $(\{0\}, +, \cdot)$ ist ein (ziemlich langweiliger) unitärer Ring, der als Element nur die Zahl Null enthält. Hierbei ist das neutrale Element bezüglich der Addition gleich dem neutralen Element bezüglich der Multiplikation! Die "Eins" in diesem Ring ist also tatsächlich die Null. Ein bisschen komisch, aber halt auch einfach nur ein ziemlich konstruiertes Beispiel, für das alle Eigenschaften eines unitären Rings gelten.

Die Polynome mit reellen Koeffizienten bilden einen Ring mit Eins. (Das gilt auch für jene Polynome, welche als Koeffizienten Zahlen aus einem Ring mit 1 haben. Da das Rechnen mit Polynomen im Prinzip nur Rechnen mit den Koeffizienten ist, übertragen sich die Eigenschaften der Koeffizienten direkt auf die Polynome. Das Einselement ist einfach die relle Zahl $1$, beziehungsweise das Polynom $1x^0$

Die quadratischen Matrizen ($\mathbb{R}^{n,m}, +, \cdot)$ bilden einen unitären Ring. Nullelement ist die Matrix, die komplett aus Nullen besteht, Einselement die Einheitsmatrix.

Der Ring der geraden Zahlen mit der normalen Addition und Multiplikation bildet einen kommutativen Ring ohne Eins. Das Inverse zu jedem Element bezüglich der Addition ist offenbar vorhanden, Assoziativ- und Distributivgesetze gelten auch. Aber es gibt kein Einselement, denn es müsste die Zahl $1$ sein, welche natürlich keine gerade Zahl ist.
<h3>Körper</h3>
Nun kommen wir zur wichtigsten algebraischen Struktur, dem Körper. Fangen wir mit der Definition an:

Ein Körper $(G, +, \cdot)$ ist eine Kombination einer Menge $G$ mit den Verknüpfungen $+$ und $\cdot$, für den gilt
<ol>
	<li>$(G, +)$ ist eine abelsche Gruppe</li>
	<li>$(G \backslash \{0\}, \cdot)$ ist eine abelsche Gruppe</li>
	<li>Es gelten die Distributivgesetze: $a \cdot(b + c) = a\cdot b + a\cdot c$ und $(a+b)\cdot c = a\cdot b + b\cdot c$.</li>
</ol>
Bei (2) ist wichtig, dass das Nullelement ausgeschlossen wird. Warum? Nunja, zu diesem Element gibt es kein multiplikatives Inverses! Also wäre es keine Gruppe!

Körper bilden die Grundlage für Vektorräume: Die Skalare aus einem Vektorraum müssen einem Körper entstammen, nur dann ist gewährleistet, dass die Eigenschaften eines Vektorraums gelten, wir brauchen dafür sowohl additive, als auch multiplikative Inverse, sowie Assoziativ- und Distributivgesetze.
<h3>Beispiele für Körper</h3>
Die rationalen Zahlen $(\mathbb{Q}, +, \cdot)$ bilden einen Körper.

Die reellen Zahlen $(\mathbb{R}, +, \cdot)$ bilden einen Körper.

Die komplexen Zahlen Zahlen $(\mathbb{C}, +, \cdot)$ bilden einen Körper.

Die quadratischen Matrizen bilden keinen Körper, weil nicht zu jedem Element ein multiplikatives Inverses existiert und weil die Multiplikation nicht kommutativ ist.
