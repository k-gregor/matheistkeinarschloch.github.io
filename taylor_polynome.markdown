---
layout: page
title: Taylor-Polynome
nav: true
permalink: /taylor-polynome/
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


<h2>Wozu das ganze überhaupt? Was macht man damit?</h2>

Es gibt Funktionen, die sind kompliziert und unschön zu handhaben. Polynome hingegen sind schön, wohlbekannt und gut zum Rechnen. Mit einer Taylor-Entwicklung können wir eine Funktion f an einer Stelle p durch ein Polynom (Taylor-Polynom) beschreiben welches dann sehr ähnlich wie f ist. In einem kleinen Umkreis um p können wir dann Aussagen über f durch Aussagen über das Taylor-Polynom ersetzen. Mit Polynomen können wir halt gut rechnen und zum Beispiel leicht herausfinden, welche Werte ein Polynom in einem gewissen Intervall annimmt. Diese Aussagen können wir dann grob auf f übertragen und somit interessante Erkenntnisse über f selbst bekommen. Jedoch immer nur in einer kleinen Umgebung von p. Wie klein, das hängt vom Grad der Taylorentwicklung ab (und macht man auch ein bisschen Pi mal Daumen).
<h2>Wie wird das ganz grob gemacht?</h2>
Gegeben sei eine Funktion f und ein Punkt p, die so genannte Entwicklungsstelle. Des Weiteren brauchen wir den Grad n, welches unser Taylor-Polynom T später haben soll. Je höher der Grad, desto genauer wird unser Polynom unsere Funktion f annähern.

T wird dann dadurch bestimmt, dass im Punkt p sowohl der Funktionswert als auch die ersten n Ableitungen in T und f gleich sind, also folgendes Gleichungssystem aufgeht:

$$ \begin{align*} f(p) &= T(p) \\ f'(p) &= T'(p) \\ f^{\prime\prime}(p) &= T^{\prime\prime}(p) \\ &\cdots \\ f^{(n-1)}(p) &= T^{(n-1)}(p)\\ f^{(n)}(p) &= T^{(n)}(p) \end{align*} $$

Wir werden dies jetzt anhand eines Beispiels durchrechnen. Später gibt es dann aber eine allgemeine Formel, aus der man T berechnen kann.
<h2>Herleiten eines Taylorpolynoms anhand eines Beispiels</h2>
Schauen wir einfach mal an, wie das Taylorpolynom einer bestimmten Funktion lautet. <em><strong>Bitte beachtet,</strong> dass niemand das Taylorpolynom auf diese Weise berechnen würde, sondern nur mit der Formel im späteren Abschnitt. Das Beispiel soll aber das Grundkonzept von Taylorpolynomen zeigen.</em>

Gegeben sei uns die Funktion

$$ f(x) =  e^{2x} + 1 $$

und wir wollen das Taylorpolynom 2. Grades von f an der Stelle p=1 berechnen. Es müssen also Funktionswert, erste und zweite Ableitung des Taylorpolynoms im Punkt p=1 mit denjeningen von f übereinstimmen. Die nötigen Gleichungen sind also

$$ \begin{align*} f(1) &= T(1) \\ f'(1) &= T'(1) \\ f^{\prime\prime}(1) &= T^{\prime\prime}(1) \end{align*} $$

Wir brauchen offensichtlich die ersten beiden Ableitungen von f und diese lauten:

$$ \begin{align*} f'(x) &= 2e^{2x} \\ f^{\prime\prime}(x) &= 4e^{2x} \end{align*} $$

Da wir schon wissen, dass unser T vom Grad 2 sein soll, hat es folgende Form:

$$ T(x) = a_2x^2 + a_1x + a_0 $$

und damit natürlich die Ableitungen

$$ \begin{align*} T'(x) &= 2a_2x + a_1 \\ T^{\prime\prime}(x) &= 2a_2 \end{align*} $$

Unser Gleichungssystem wird also, wenn wir alles einsetzen, zu:

$$ \begin{align*} e^2 + 1 &= 2a_2 + 2a_1 + a_0 \\ 2e^2 &= 2a_2 + a_1 \\ 4e^2 &= 2a_2 \end{align*} $$

Lösen wir dieses System, erhalten wir die Werte der Koeffizienten des Taylorpolynoms und sind damit auch schon fertig! $ a_2 = 2e^2 $ folgt direkt aus der dritten Gleichung, welches wir in die zweite einsetzen, um $ a_1 = -2e^2 $ zu erhalten und schließlich aus der ersten Gleichung $ a_0 = $ zu bekommen.

Unser Taylor-Polynom lautet also:

$$ T(x) = 2e^2x^2 - 2e^2x + e^2 + 1 $$

Folgende Graphik zeigt die Funktion f und ihr Taylor-Polynom T. Wie wir sehen, nähert das Taylor-Polynom die Funktion im Bereich [0,5 ; 1,5] sehr gut an.

<img src="{{ site.baseurl }}/assets/taylor2.png" alt="Ein Taylorpolynom vom Grad 2">

<h2>Die allgemeine Formel</h2>
Wie erwähnt, würde niemand mehr ein Gleichungssystem wir oben aufstellen, um das Taylor-Polynom zu berechnen. Denn es gibt eine Formel, die einem das Taylor-Polynom direkt ausspuckt. Und diese Formel für das Taylor-Polynom für f mit Grad n und Entwicklungsstelle p:

$$ \begin{align*} T_{f,p}^n(x) &= \sum_{k=0}^n \frac{f^{(k)}(p)}{k!}(x-p)^k \\ &= \frac{f^{(n)}(p)}{n!}(x-p)^n + \frac{f^{(n-1)}(p)}{(n-1)!}(x-p)^{(n-1)} + \cdots + \frac{f^{(2)}(p)}{2}(x-p)^2 + f'(p)(x-p) + f(p) \end{align*} $$

wobei $ f^{(n)} $ die n-te Ableitung bezeichnet und $ f^{(0)} = f $ ist. Außerdem nicht vergessen, dass $0! =1 $ gilt, was beim letzten Summanden eingeht.
<h2>Bestimmen des Taylor-Polynoms anhand der Formel: Vorgehensweise</h2>
Wir wollen nun die Formel benutzen, um das Taylor-Polynom zu berechnen. Der Grad sei wieder $ n=2 $ und $ p=1 $.
<h4>Schritt 1: Ableitungen bestimmen</h4>
Da wir das Taylor-Polynom vom Grad 2 bestimmen wollen, brauchen wir die ersten beiden Ableitungen, diese sind wir oben:

$$ \begin{align*} f'(x) &= 2e^{2x} \\ f^{\prime\prime}(x) &= 4e^{2x} \end{align*} $$
<h4>Schritt 2: Entwicklungsstelle in f und die Ableitungen einsetzen</h4>
Für die Formel brauchen wir die Werte von f und den Ableitungen an der Stelle p. Daher setzen wir p ein:

$$ \begin{align*} f(p) &= f(1) = e^{2}+1 \\ f'(p) &= f'(1) = 2e^{2} \\ f^{\prime\prime}(p) &= f^{\prime\prime}(1) = 4e^{2} \end{align*} $$
<h4>Schritt 3: Einsetzen in die Formel</h4>
Indem wir einsetzen und alles auflösen bekommen wir:

$$ \begin{align*} T(x) &= \frac{ f^{\prime\prime}(1)}{2!}(x-p)^2 + f'(1)(x-p) + f(p) \\ &= \frac{4e^2}{2}(x-1)^2 + 2e^2(x-1) + e^2 + 1 \\ &= 2e^2(x^2 -2x + 1) + 2e^2x - 2e^2 + e^2 +1 \\ &= 2e^2x^2 - 4e^22x + 2e^2 + 2e^2x - 2e^2 + e^2 +1 \\ &= 2e^2x^2 -2e^2x + e^2 +1 \end{align*} $$

Also genau das was wir vorher hergeleitet hatten!
<h2>Höhere Genauigkeit bei höherem Grad n</h2>
Vorhin habe ich erwähnt, dass sich das Taylor-Polynom immer besser an f annähert, wenn sein Grad immer höher wird. Klar, denn dann stimmen immer mehr Ableitungen von T mit denen von f überein und die Krümmung von T wird immer mehr wie die von f. Als kleines Beispiel hierfür habe ich das Taylorpolynom von f mit Grad n=5 berechnet und zeichnen lassen. Wir sehen, dass die Annäherung schon viel besser ist als bei n=2:

<img src="{{ site.baseurl }}/assets/taylor2und5.png" alt="Taylorpolynome mit Grad 2 und Grad 5">


<h2>Weitere Beispiele</h2>
<h3>Das Taylorpolynom eines Polynoms</h3>
Quizfrage: Was ist das Taylor-Polynom zweiten Grades der Funktion $ f(x) = x^2 $ an der Stelle p = 3? Mal kurz überlegen, bevor ihr es ausrechnet!

Wir gehen wieder die drei Schritte durch:
<h4>Ableitungen</h4>
$$ \begin{align*} f'(x) &= 2x \\ f^{\prime\prime}(x) &=2 \end{align*} $$
<h4>Entwicklungsstelle p in f und Ableitungen einsetzen</h4>
$$ \begin{align*} f(3) &= 9 \\ f'(3) &= 6 \\ f^{\prime\prime}(3) &=2 \end{align*} $$
<h4>Einsetzen in die Formel</h4>
$$ \begin{align*} T(x) &= \frac{2}{2!}(x-3)^2 + 6(x-3) + 9 \\ &= x^2 - 6x + 9 + 6x - 18 + 9 \\ &= x^2\end{align*} $$

Das Ergebnis ist also wieder die Funktion selbst! Das wäre natürlich auch mit jeder anderen Entwicklungsstelle passiert. Schließlich soll das Taylor-Polynom eine Funktion f durch ein Polynom annähern. Wenn dieses f bereits ein Polynom ist, muss natürlich nichts mehr angenähert werden, und das Taylor-Polynom ist gleich der Funktion. Vorausgesetzt natürlich, der Grad von T entspricht dem Grad von f oder ist höher!

Was passiert, wenn wir das gleiche Spiel mit einem höheren Grad machen, z.B. n=4? Das Ergebnis bleibt dasselbe, denn:

$$ \begin{align*} f^{(3)}(x) &= 0 \\ f^{(4)}(x) &=0 \end{align*} $$

Alle weiteren Ableitungen sind Null, die weiteren Summanden der Taylor-Formel fallen also weg.

Wenn der Grad kleiner ist, also n=1, dann kommt natürlich nicht $x^2$ heraus, denn das Taylor-Polynom kann keinen quadratischen Term enthalten. In diesem Fall wäre das Taylor-Polynom $T(x) = 6x - 18 + 9 $.
