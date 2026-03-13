---
layout: page
title: Eigenwerte und Eigenvektoren
nav: true
permalink: /eigenwert-und-eigenvektoren/
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

# Eigenwerte und -vektoren: Was ist das eigentlich??

Was sind eigentlich Eigenwerte und Eigenvektoren? Der Definition zufolge sind Eigenvektoren einer <strong>quadratischen(!)</strong> Matrix $A$ gerade die Vektoren $v \neq 0$, für die gilt

$$ Av = \lambda v$$

und $\lambda$ ist dann ein Eigenwert zu diesem Eigenvektor.

Das heißt, dass, wenn wir die Matrix $A$ an $v$ ranmultiplizieren, wieder ein vielfaches von $v$ herauskommt.

Anschaulich erhält man durch eine Multiplikation von einer Matrix mit einem Vektor $ Av $ irgend einen neuen Vektor, d.h. die Multiplikation mit $A$ kann Streckungen und Drehungen eines Vektors bewirken. Je nachdem, wie $A$ und $v$ aussehen, wird ein Vektor durch Multiplikation mehr oder weniger gestaucht oder gedreht. Nehmen wir für den Vektor $$ v = \begin{pmatrix} 2 \\ 1 \end{pmatrix} $$  als Beispiel $$ A = \begin{pmatrix} 2 & 0 \\ 0 & 2 \end{pmatrix} $$, dann findet nur eine Streckung um $2$ statt, bei $$ B = \begin{pmatrix} 2 & 1 \\ 0 & 1 \end{pmatrix} $$ erhalten wir sowohl Streckung als auch Drehung, siehe Bild. Eigenvektoren sind dann genau die Vektoren, wo nur eine Streckung stattfindet. Je nach $A$ findet man dazu viele oder nur wenige Vektoren. Im Beispiel hier ist also der Vektor $v$ ein Eigenvektor zu $A$, und zwar zum Eigenwert $2$.


<img src="{{ site.baseurl }}/assets/matrixmultivektor.png" alt="Darstellung von Eigenvektoren">

Noch einmal kurz, damit es nicht vergessen wird: Eigenwerte und Eigenvektoren gibt es <strong>nur</strong> bei quadratischen Matrizen.

Das klingt erstmal alles nicht besonders spannend, aber damit kann man ganz schön viel machen. Insbesondere kann man es mittels Eigenvektoren und Eigenwerten schaffen, eine Matrix auf Diagonalform zu bringen, dass die Matrix also nur aus Diagonaleinträgen besteht und ansonsten alle Einträge gleich Null sind. Das vereinfacht Berechnungen ungemein und wird im [Beitrag über Diagonalisierbarkeit]({% link diagonalisierbarkeit_matrix.markdown %}) erklärt. Schauen wir uns hier zunächst einmal die Eigenvektoren und Eigenwerte an sich an.
<h3>Berechnung von Eigenwerten</h3>
Die Gleichung $Av=\lambda v$ ist recht schwer zu handhaben. Aber wir können sie ein wenig umformen, um sie etwas einfacher zu machen:

$$ \begin{align*} Av &= \lambda v \\ Av &= \lambda \mathbb{I}v \\ (A-\lambda \mathbb{I})v &= 0 \end{align*} $$

Wir haben nun einfach ein lineares Gleichungssystem, denn $A-\lambda \mathbb{I}$ ist auch einfach nur eine Matrix. $v$ ist ein unbekannter Vektor und wir suchen eine Lösung $v$ für das obige lineare Gleichungssystem. Naja, aber $\lambda$ ist ja auch unbekannt. Schlecht. Was machen wir nun?

Wenn wir in Lineare Algebra ein bisschen aufgepasst haben, wissen wir genau, wann eine Gleichung $Ax = 0$ lösbar ist. Die Lösung $x=0$ geht natürlich immer. Aber wann gibt es noch andere Lösungen? Richtig, genau dann, wenn $A$ <strong>nicht</strong> [invertierbar]({% link invertierbare_matrizen.markdown %}) ist (oder äquivalent: wenn die Spalten von A [linear abhängig]({% link lineare_unabhaengigkeit.markdown %}) sind, denn sonst gäbe es ausschließlich die Triviallösung). Und was ist wiederum äquivalent dazu? Dass die Determinante von $A$ gleich Null ist! Also folgt:

Lösungen $v\neq 0$ für

$$ (A-\lambda \mathbb{I})v = 0 $$

gibt es genau dann, wenn

$$ det(A-\lambda \mathbb{I}) = 0$$

Wir müssen also schauen, für welche $\lambda$ das der Fall ist. Ab hier bietet es sich an, an einem Beispiel weiter zu machen.
<h2>Eigenwerte und Eigenvektoren - Erklärung an einem Beispiel</h2>
Gegeben sei die Matrix

$$ A = \begin{pmatrix} -2 &-4 & 2 \\ -2 & -4 & -3 \\ 1 & 2 & -2 \end{pmatrix} $$

Wir müssen nun also schauen, wann $ det(A-\lambda \mathbb{I}) = 0$. Also:
<h3>1. Bilden von $A-\lambda\mathbb{I}$</h3>
$$ A-\lambda \mathbb{I} = \begin{pmatrix} -2 &-4 & 2 \\ -2 & -4 & -3 \\ 1 & 2 & -2 \end{pmatrix} - \lambda \begin{pmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 1 \end{pmatrix} = \begin{pmatrix} -2-\lambda &-4 & 2 \\ -2 & -4 -\lambda & -3 \\ 1 & 2 & -2 -\lambda \end{pmatrix} $$
<h3>2. Bilden von $det(A-\lambda\mathbb{I})$: Das charakteristische Polynom</h3>
Und jetzt wenden wir einfach die bekannte Regel von Sarrus an (auch Lattenzaunregel), um die Determinante zu bestimmen:

$$ \begin{align*} det(A-\lambda\mathbb{I}) = & (-2-\lambda)(-4-\lambda)(-2-\lambda) + (-4)(-3)1 + 2(-2)2) \\ &- 1(-4-\lambda)2 - 2(-3)(-2-\lambda) - (-2-\lambda)(-2)(-4) \end{align*} $$

Und wenn wir da nun fleißig ausmultiplizieren, kommen wir auf das sogenannte <strong>Charakteristische Polynom:</strong>

$$ -\lambda^3 - 8\lambda^2 - 16\lambda $$
<h3>3. Eigenwerte finden: Die Nullstellen des charakteristischen Polynoms</h3>
Hinweis: Es lohnt sich nicht immer, gleich komplett auszumultiplizieren. Hier haben wir zwar Glück, aber in der Regel lassen sich bei kubischen Polynomen nicht so leicht die Nullstellen berechnen, sondern wir müssen eine Nullstelle raten und dann Polynomdivision machen. Manchmal kann man aber auch schon geschickt ausklammern und sich das ganze sparen, das sehen wir in einem späteren Beispiel noch. Jetzt rechnen wir erstmal weiter, wir wollen, dass $ det(A-\lambda \mathbb{I}) = 0$, also

$$ -\lambda^3 - 8\lambda^2 - 16\lambda = 0 $$

Durch ausklammern von $\lambda$ finden wir direkt den ersten Eigenwert: $\lambda_1 = 0$. Dann haben wir noch die quadratische Gleichung $ -\lambda^2 - 8\lambda - 16 = 0 $ welche wir mittels p-q- oder Mitternachts-Formel bestimmen können und erhalten $\lambda_2 = -4$ und $\lambda_3=-4$, das ist also ein doppelter Eigenwert. Man sagt auch, ein <strong>Eigenwert mit arithmetischer Vielfachheit 2</strong>. Damit haben wir also zwei Eigenwerte! Für jeden dieser Eigenwerte ist jetzt also noch ein Gleichungssystem zu lösen. Ich zeige es mal für $\lambda_2 = -4$ und gebe für den anderen Eigenwert nur die Lösung direkt an.


<h3>4. Eigenvektoren finden: Lösung des Gleichungssystem $(A-\lambda\mathbb{I})v = 0$ für jeden Eigenwert $\lambda$</h3>


$$
\begin{align*}
\begin{pmatrix} -2-(-4) &-4 & 2 \\ -2 & -4- (-4) & -3 \\ 1 & 2 & -2- (-4) \end{pmatrix}v &= 0 \\
\begin{pmatrix} 2 &-4 & 2 \\ -2 & 0 & -3 \\ 1 & 2 & 2 \end{pmatrix}v &= 0
\end{align*}
$$

Aus der zweiten Gleichung bekommen wir $v_3 = -\frac{2}{3}v_1$, eingesetzt in die dritte Gleichung: $v_1 + 2v_2 - \frac{4}{3}v_1 = 0$, also $v_2 = \frac{1}{6}v_1 $. Alles zusammen in die erste Gleichung kommt heraus:

$$
\begin{align*}
2v_1 - \frac{4}{6}v_1 - \frac{4}{3}v_1 &= 0 \\
0 &= 0
\end{align*}
$$

äh, und nun? Naja, das bedeutet: Egal, wie $v_1$ aussieht, wenn wir $v_2$ und $v_3$ entsprechend unserer Berechnungen wählen, geht die Gleichung auf! Zum Beispiel können wir $v_1 = 6$ wählen und bekommen damit $v_2 = 1$ und $v_3 = -4$!

Das heißt:

$$ v = \begin{pmatrix} 6 \\ 1 \\ -4 \end{pmatrix} $$

ist ein Eigenvektor von $A$ zum Eigenwert $-4$! Wenn wir $v_1$ anders gewählt hätten, hätten wir einen anderen Vektor bekommen, aber der wäre einfach ein vielfaches von $v$ gewesen. Es gibt also immer unendlich viele Eigenvektoren zu einem Eigenwert und wir suchen uns einfach einen aus.

Wenn ihr das ganze nun für $\lambda = 0$ probiert, erhaltet ihr zum Beispiel folgenden Vektor (oder eben ein Vielfaches davon):

$$ v = \begin{pmatrix} -2 \\ 1 \\ 0 \end{pmatrix} $$

Zusammengefasst haben wir also zur Matrix $A$ zwei Eigenwerte mit jeweils einem Eigenvektor gefunden, das bedeutet, zu jedem der beiden Eigenwerte ist die <strong>geometrische Vielfachheit</strong> 1. Diese kann auch größer als 1 sein, wir können durchaus zu einem Eigenwert mehrere (linear unabhängige) Eigenvektoren finden. Auch dazu folgen noch Beispiele.
<h2>Eigenwerte und Eigenvektoren - Beispiel mit Polynomdivision</h2>
Bestimme Eigenwerte und -vektoren zu

$$ A = \begin{pmatrix} 1 & -2 & -1 \\ -6 & 2 & -2 \\ 15 & 6 & 9 \end{pmatrix} $$
<h3>1. Bilden von $A-\lambda\mathbb{I}$</h3>
$$ A-\lambda\mathbb{I} = \begin{pmatrix} 1-\lambda & -1 & -1 \\ -6 & 2-\lambda & -2 \\ 15 & 6 & 9-\lambda \end{pmatrix} $$
<h3>2. Bilden von $det(A-\lambda\mathbb{I})$: Das charakteristische Polynom</h3>
Auch an dieser Stelle kann man nicht geschickt ausklammern, sodass man das charakteristische Polynom bis zuletzt ausrechnet:

$$det(A-\lambda\mathbb{I}) = -\lambda^3 + 12\lambda^2 - 44\lambda + 48 $$
<h3>3. Eigenwerte finden: Die Nullstellen des charakteristischen Polynoms</h3>
Die Nullstellen zu finden ist hier nicht ganz einfach. Wir müssen tatsächlich eine Nullstelle raten und dann Polynomdivision machen. Beim Nullstellenraten sollte man zunächst die einfachen Stellen 0, 1 und 2 usw probieren. Wenn der Funktionswert des Polynoms an einer Stelle negativ und an der anderen positiv ist, muss die Nullstelle dazwischen sein! Auf diese Weise können wir uns zur Nullstelle heranarbeiten.

Hier findet man bald, dass $\lambda_1 = 2$. Dann machen wir eine Polynomdivision:

$$ (-\lambda^3 + 12\lambda^2 -44\lambda + 48) : (\lambda - 2) = -\lambda^2 + 10\lambda -24 $$

Die Nullstellen des quadratischen Terms können wir wieder mit den bekannten Formeln herausbekommen und sie lauten

$$\lambda_2 = 4,~~\lambda_3 = 6$$
<h3>4. Eigenvektoren finden: Lösung des Gleichungssystems $(A-\lambda\mathbb{I})v = 0$ für jeden Eigenwert $\lambda$</h3>
Man sollte auf folgenden Eigenvektoren (oder eben jeweils ein Vielfaches davon) kommen:

$$ v_1 = \begin{pmatrix} -1 \\ -1 \\ 3 \end{pmatrix},~v_2 = \begin{pmatrix} -1 \\ 0 \\ 3 \end{pmatrix}, ~ v_3 = \begin{pmatrix} 0 \\ -1 \\ 2 \end{pmatrix} $$

Zusammengefasst haben wir also zur Matrix $A$ drei Eigenwerte mit jeweils einem Eigenvektor gefunden. Die <strong>geometrische Vielfachheit</strong> eines jeden Eigenwertes ist 1, ebenso wie die <strong>arithmetische Vielfachheit</strong>. Insbesondere ist die Matrix $A$ diagonalisierbar!
<h2>Eigenwerte und Eigenvektoren - Beispiel mit geschicktem Ausklammern</h2>
Gegeben sei die Matrix

$$ A = \begin{pmatrix} 1 & 0 & 0 \\ 3 & -2 & 2 \\ 6 & 3 & -1 \end{pmatrix} $$

Wenn man hier das charakteristische Polynom mittels der Regel von Sarrus bestimmt, so kommt man auf

$$ det(A - \lambda \mathbb{I}) = (1-\lambda)(-2 -\lambda)(-1 -\lambda) + 0 + 0 - 0 - (3 \cdot 2 \cdot (1- \lambda)) -0 $$

An dieser Stelle ist es besser, nicht auszumultiplizieren, sondern geschickt auszuklammern, um schnell an die Nullstellen zu kommen:

$$ (1-\lambda)(-2 -\lambda)(-1 -\lambda) - (6(1- \lambda)) = (1 - \lambda) \left[ (-2-\lambda)(-1-\lambda) - 6 \right] $$

Dieser Term ist genau dann Null, wenn einer der Faktoren Null ist. Die erste Nullstelle können wir also gleich aus dem ersten Faktor $(1 -\lambda)$ ablesen: $\lambda_1=1$. Den zweiten Faktor bestimmen wir wie gewöhnlich mit Ausmultiplizieren und der p-q-Formel und erhalten $\lambda_2 = 1$ sowie $\lambda_3 = -4$.

Durch das Ausklammern von $ (1-\lambda)$ konnten wir direkt eine Nullstelle ablesen und haben uns eine Polynomdivision gespart. Man sollte deshalb beim bestimmen des charakteristischen Polynoms immer Ausschau halten, ob man am Anfang einen solchen Term ausklammern kann. Das geht natürlich nicht immer, aber ab und an hat man Glück.
<h2>Eigenwerte und Eigenvektoren - Übungsaufgabe:</h2>
Zeigt, dass ein Eigenvektor $v$ zum Eigenwert $\lambda$ von $A$ niemals auch ein Eigenvektor zu einem anderen Eigenwert $\mu \neq \lambda$ sein kann!
<h4>Lösung</h4>
Wenn $v$ ein Eigenvektor zum Eigenwert $\lambda$ von $A$ ist, gilt per Definition $Av = \lambda v$. Wenn $v$ nun also auch Eigenvektor zum Eigenwert $\mu$ sein soll, müsste auch $Av = \mu v$ gelten und damit also $\lambda v = \mu v$. Umgeformt heißt das $(\lambda - \mu)v = 0$ und da $\mu \neq \lambda$, kann diese Gleichung nur aufgehen, wenn $v = 0$. Per Definition ist aber ein Eigenvektor $v \neq 0$. $v$ kann also nicht Eigenvektor zu $\lambda$ und $\mu$ gleichzeitig sein.
