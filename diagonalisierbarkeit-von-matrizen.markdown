---
layout: page
title: Diagonalisierbarkeit von Matrizen
nav: true
permalink: /diagonalisierbarkeit-von-matrizen/
---

# Diagonalisierbarkeit - Worum geht's?

Eine <strong>quadratische</strong> Matrix $A$ lässt sich unter bestimmen Anforderungen diagonalisieren, d.h. es gibt eine invertierbare Transformationsmatrix $U$ und eine Diagonalmatrix $D$ (also eine Matrix, die außerhalb der Diagonalen nur Nullen enthält), sodass gilt

$$ A = UDU^{-1}$$
<h2>Diagonalisieren - Wozu das ganze?</h2>
Diagonalmatrizen sind super praktisch, weil man mit ihnen so leicht rechnen kann. Da sie nur auf der Diagonalen Einträge haben, ist eine Matrixmultiplikation unglaublich einfach, weil wir nur die Diagonalelemente multiplizieren müssen:

$$ \begin{pmatrix} 3 &amp; 0 &amp; 0 \\ 0 &amp; 4 &amp; 0 \\ 0 &amp; 0 &amp; -1 \end{pmatrix} \cdot \begin{pmatrix} 2 &amp; 0 &amp; 0 \\ 0 &amp; -6 &amp; 0 \\ 0 &amp; 0 &amp; -2 \end{pmatrix} = \begin{pmatrix} 6 &amp; 0 &amp; 0 \\ 0 &amp; -24 &amp; 0 \\ 0 &amp; 0 &amp; 2 \end{pmatrix} $$

Auch die Inverse können wir damit total leicht bestimmen, indem wir die Kehrwerte auf der Diagonalen nehmen:

$$ \begin{pmatrix} 3 &amp; 0 &amp; 0 \\ 0 &amp; 4 &amp; 0 \\ 0 &amp; 0 &amp; -1 \end{pmatrix}\cdot \begin{pmatrix} \frac{1}{3} &amp; 0 &amp; 0 \\ 0 &amp; \frac{1}{4} &amp; 0 \\ 0 &amp; 0 &amp; -1 \end{pmatrix} = \begin{pmatrix} 1 &amp; 0 &amp; 0 \\ 0 &amp; 1 &amp; 0 \\ 0 &amp; 0 &amp; 1 \end{pmatrix} $$

(An dieser Stelle sieht man, dass eine Diagonalmatrix nur dann invertierbar ist, wenn keine Null auf der Diagonalen steht)

Wenn wir nun eine Potenz unserer Matrix $A$ berechnen wollen z.B. $A^5$, dann wäre das sehr umständlich. Wenn wir allerdings wissen, dass $ A = UDU^{-1}$, geht es ganz leicht:

$$ \begin{align*} A^5 &amp;= (UDU^{-1})^5 = (UDU^{-1}) (UDU^{-1}) (UDU^{-1}) (UDU^{-1}) (UDU^{-1}) \\ &amp;= UD(U^{-1}U)D(U^{-1}U)D(U^{-1}U)D(U^{-1}U)DU^{-1} = UD^5U^{-1} \end{align*} $$

$D^5$ können wir ganz leicht bestimmen, und dann müssen wir nur noch zwei Matrixmultiplikationen machen anstatt 4.

# Wie kann man eine Matrix diagonalisieren? Allgemeine Erklärung
Wann kann man nun eine Matrix $A \in \mathbb{R}^n$ diagonalisieren? Wenn wir $n$ linear unabhängige Eigenvektoren finden! Wir erinnern uns, $v$ ist ein Eigenvektor zu $A$, wenn $Av = \lambda v$ für ein $\lambda \in \mathbb{R}$, ein so genannter Eigenwert. Wenn wir nun $n$ unabhängige Eigenvektoren $v_1, v_2, \ldots, v_n$ haben, können wir diese hintereinander zu einer Matrix $U$ schreiben, welche aufgrund der linearen Unabhängigkeit der Spalten invertierbar ist:

$$ U = \left( \begin{array}{c|c|c|c} v_1 &amp; v_2 &amp; \cdots &amp; v_n \end{array} \right) $$

Mit der Definition der Eigenvektoren (Gleichung *) ist dann:

$$ \begin{align*} A\cdot U &amp;= A \cdot \left( \begin{array}{c|c|c|c} v_1 &amp; v_2 &amp; \cdots &amp; v_m \end{array} \right) = \left( \begin{array}{c|c|c|c} Av_1 &amp; Av_2 &amp; \cdots &amp; Av_n \end{array} \right) \\ &amp;\stackrel{*}{=} \left( \begin{array}{c|c|c|c} \lambda_1v_1 &amp; \lambda_2v_2 &amp; \cdots &amp; \lambda_nv_n \end{array} \right) = \left( \begin{array}{c|c|c|c} v_1 &amp; v_2 &amp; \cdots &amp; v_n \end{array} \right) \begin{pmatrix} \lambda_1 &amp; &amp; &amp; \\ &amp; \lambda_2 &amp; &amp; \\ &amp; &amp; \ddots &amp; \\ &amp; &amp; &amp; \lambda_n \end{pmatrix} \\ &amp;= U \cdot D \end{align*} $$

Wem es nicht direkt klar ist, sollte nochmal kurz durchrechnen, dass es tatsächlich $U \cdot D$ ist, und nicht umgekehrt.

Aus den Gleichungen haben wir nun also das was wir wollten: $ A\cdot U = U\cdot D$, denn wir wissen ja dass $U$ invertierbar ist und es folgt damit:

$$ A = UDU^{-1}$$

Wir haben also unsere Transformationsmatrix $U$ und unsere Diagonalmatrix $D$ gefunden, $U$ bestehend aus den Eigenvektoren und $D$ bestehend aus den Eigenwerten.

# Wie kann man eine Matrix diagonalisieren? Erklärung am Beispiel

Wenn wir also eine Matrix $A$ diagonalisieren wollen - bzw. schauen, ob es überhaupt geht - dann müssen wir offensichtlich die Eigenwerte und Eigenvektoren bestimmen. Wenn dann <strong>zu jeden Eigenwert die geometrische Vielfachheit gleich der algebraischen Vielfachheit</strong> ist, bedeutet dass, dass wir $n$ linear unabhängige Eigenvektoren gefunden haben, denn dann haben wir für jeden $k$-fachen Eigenwert auch $k$ linear unabhängige Eigenvektoren. Zusätzlich sind Eigenvektoren zu unterschiedlichen Eigenwerten immer zueinander linear unabhängig!

Gegeben sei die Matrix

$$ A = \begin{pmatrix} 1 &amp; -2 &amp; -1 \\ -6 &amp; 2 &amp; -2 \\ 15 &amp; 6 &amp; 9 \end{pmatrix} $$

Wie in den Erklärungen zu Eigenwerten und -vektoren berechnet, sind die Eigenwerte:

$$\lambda_1 = 2, ~~\lambda_2 = 4,~~\lambda_3 = 6$$

jeweils mit arithmetischer Vielfachheit 1. Zu jedem Eigenwert fanden wir dort auch nur einen Eigenvektor, die geometrischen Vielfachheiten sind also auch jeweils 1 und damit gleich den geometrischen. $A$ ist also diagonalisierbar. Die Eigenvektoren lauteten, wobei $v_1$ zu $\lambda_1$ gehört usw:

$$ v_1 = \begin{pmatrix} -1 \\ -1 \\ 3 \end{pmatrix},~v_2 = \begin{pmatrix} -1 \\ 0 \\ 3 \end{pmatrix}, ~ v_3 = \begin{pmatrix} 0 \\ -1 \\ 2 \end{pmatrix} $$

Um die Diagonalierung vollständig zu machen, schreiben wir nun noch die tatsächliche Diagonalmatrix $D$ auf, bestehend aus den Eigenwerten:

$$ D = \begin{pmatrix} 2 &amp; 0 &amp; 0 \\ 0 &amp; 4 &amp; 0 \\ 0 &amp; 0 &amp; 6 \end{pmatrix} $$

Mit zugehöriger Transformationsmatrix $U$, bestehend aus den Eigenvektoren (in der richtigen Reihenfolge, passend zu den Eigenwerten!!!):

$$ U = \left( \begin{array}{c|c|c} v_1 &amp; v_2 &amp; v_3 \end{array} \right) = \begin{pmatrix} -1 &amp; -1 &amp; 0 \\ -1 &amp; 0 &amp; -1 \\ 3 &amp; 3 &amp; 2 \end{pmatrix} $$

Ihr könnt euch nochmal rechnerisch vergewissern, dass es stimmt, indem ihr zeigt, dass $A = UDU^{-1}$. Kleiner Tipp: zeigt einfach $AU = UD$, dann müsst ihr $U$ nicht invertieren ;-)

# Weitere Beispiele

## Ein Beispiel mit mehrfachen Eigenwerten

--&gt; folgt in Kürze!

## Ein Beispiel, einer nicht diagonalisierbaren Matrix

Für die Matrix

$$ A = \begin{pmatrix} -2 &amp;-4 &amp; 2 \\ -2 &amp; -4 &amp; -3 \\ 1 &amp; 2 &amp; -2 \end{pmatrix} $$

hatten wir auf der Erklärungsseite für Eigenwerte und -vektoren bereits berechnet, dass die Eigenwerte lauten: $\lambda_1 = 0$ mit geometrischer und arithmetischer Vielfachheit 1, und $\lambda_2 = -4$ mit arithmetischer Vielfachheit 2 aber geometrischer Vielfachheit 1. $A$ ist also nicht diagonalisierbar.
<h2>Diagonalisierbarkeit heißt nicht gleich Invertierbarkeit!</h2>
Abschließend möchte ich noch zwei Beispiele bringen, die die Zusammengehörigkeit von Invertierbarkeit und Diagonalisierbarkeit widerlegen. Studenten sagen in Prüfungen gerne mal das das eine das andere impliziert oder umgekehrt, aber das ist schlicht falsch.
<h3>Diagonalisierbarkeit impliziert nicht Invertierbarkeit</h3>
Auch wenn Diagonalisierbarkeit einer Matrix eine ziemlich starke Eigenschaft ist, muss die Matrix deshalb nicht invertierbar sein. Die folgende Matrix ist beispielsweise diagonalisierbar (denn sie ist bereits diagonal), ist aber nicht invertierbar, denn es steht eine Null auf der Diagonalen (also ist ein Eigenwert Null bzw die Determinante ist Null)

$$ A = \begin{pmatrix} 1 &amp; 0 &amp; 0 \\ 0 &amp; 1 &amp; 0 \\ 0 &amp; 0 &amp; 0 \end{pmatrix} $$
<h3>Invertierbarkeit impliziert nicht Diagonalisierbarkeit</h3>
Auch andersrum geht es nicht: Nehmen wir beispielsweise die Matrix

$$ A = \begin{pmatrix} 1 &amp; 1 \\ 0 &amp; 1 \end{pmatrix} $$

die offenbar invertierbar ist, da ihre Determinante 1 ist. Damit sie diagonalisierbar ist, müssten die geometrischen Vielfachheiten der Eigenwerte gleich der algebraischen Vielfachheiten derselben sein. Das charakteristische Polynom ist:

$$ det(\begin{pmatrix} 1-\lambda &amp; 1 \\ 0 &amp; 1-\lambda \end{pmatrix}) = (1-\lambda)(1-\lambda) \stackrel{!}{=}0 $$

Es hat also die doppelte Nullstelle $\lambda_1 = \lambda_2 = 1$. Der einzige Eigenwert ist also 1 <strong>mit algebraischer Vielfachheit 2</strong>

Schauen wir uns die geometrische Vielfachheit an:

$$ (A-\lambda\mathbb{I})v = \begin{pmatrix} 0 &amp; 1 \\ 0 &amp; 0 \end{pmatrix}v \stackrel{!}{=} 0 $$

Das impliziert $v_2 = 0$. Wir finden also nur den Eigenvektor $v = \begin{pmatrix} 1 \\ 0 \end{pmatrix}$. Die geometrische Vielfachheit von $\lambda_1$ ist also nur 1 und damit ungleich der geometrischen. $A$ ist also nicht diagonalisierbar.
