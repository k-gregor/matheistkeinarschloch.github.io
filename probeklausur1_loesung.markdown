---
layout: page
title: Probeklausur1 Lösung
nav: true
permalink: /probeklausur1-loesung/
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



Hier sind die Lösungen zu den Aufgaben der [Probeklausur 1]({{ "/probeklausur1/" | relative_url }}). Falls ihr einen Fehler findet, oder etwas unklar ist, schreibt mir!

<h3>Aufgabe 1</h3>
<h5>zu 1.1: Zwischenergebnisse beim Invertieren</h5>

$$
\begin{pmatrix} 1 & 4 & -2 &1 & 0 & 0 \\ 0 & 0 & 1 & 0 & 1 & 0 \\ 1 & 2 & 0 & 0 & 0 & 1  \end{pmatrix}

\begin{pmatrix} 1 & 4 & -2 &1 & 0 & 0 \\ 0 & 0 & 1 & 0 & 1 & 0 \\ 0 & -2 & 2 & -1 & 0 & 1  \end{pmatrix}
$$

$$
\begin{pmatrix} 1 & 4 & -2 &1 & 0 & 0 \\ 0 & -2 & 2 & -1 & 0 & 1\\  0 & 0 & 1 & 0 & 1 & 0 \end{pmatrix}

\begin{pmatrix} 1 & 4 & -2 &1 & 0 & 0 \\ 0 & 1 & -1 & \frac{1}{2} & 0 & -\frac{1}{2}\\  0 & 0 & 1 & 0 & 1 & 0 \end{pmatrix}
$$

$$
\begin{pmatrix} 1 & 0 & 2 & -1 & 0 & 2 \\ 0 & 1 & -1 & \frac{1}{2} & 0 & -\frac{1}{2}\\  0 & 0 & 1 & 0 & 1 & 0 \end{pmatrix}

\begin{pmatrix} 1 & 0 & 2 & -1 & 0 & 2 \\ 0 & 1 & 0 & \frac{1}{2} & 1 & -\frac{1}{2}\\  0 & 0 & 1 & 0 & 1 & 0 \end{pmatrix}
$$

$$
\begin{pmatrix} 1 & 0 & 0 & -1 & -2 & 2 \\ 0 & 1 & 0 & \frac{1}{2} & 1 & -\frac{1}{2}\\  0 & 0 & 1 & 0 & 1 & 0 \end{pmatrix}
$$

<h5>zu 1.2</h5>
sollte klar sein
<h5>zu 1.3</h5>
Mit der Regel von Sarrus ist $\det(A) = 0+4+0-0-2-0 = 2$.
<h5>zu 1.4</h5>
Das geht für jedes $b$, die Matrix ist schließlich invertierbar. Die Lösung wäre $x=A^{-1}b$.
<h3>Aufgabe 2</h3>
<h5>zu 2.1</h5>
Eigenwerte mittels charakteristischem Polynom:

$$ \det(\lambda \mathbb{I} - A) = \det \begin{pmatrix} \lambda -2 & 1 \\ 1 & \lambda - 2 \end{pmatrix} = (\lambda-2)^2 -1$$

Null setzen und auflösen $\Rightarrow \lambda_1 = 1, \lambda_2 = 3 $.

Die Eigenvektoren sind

$$ v_1 = \begin{pmatrix} 1 \\ 1 \end{pmatrix}, v_2 = \begin{pmatrix} 1 \\ -1 \end{pmatrix} $$ (oder vielfache davon).

Beispielhaft für $\lambda = 1$:

$$ \begin{pmatrix} 2 & -1 \\ -1 & 2 \end{pmatrix} \begin{pmatrix} x \\ y \end{pmatrix} = 1 \begin{pmatrix}x \\ y \end{pmatrix} $$

Daraus ergeben sich  $x = y$ und $-x = -y$, de fakto also nur eine Gleichung, aber zwei Variablen. Wir können $x=1$ wählen und damit ist auch $y = 1$. Der Fall mit $\lambda = 3$ ist sehr ähnlich.
<h5>zu 2.2</h5>
$v_1$ und $v_2$ sind offensichtlich linear unabhängig. $A$ ist also diagonalisierbar.
<h3>Aufgabe 3</h3>
$$ \begin{align} \int_0^\pi \int_0^1 3x^2 +x\sin(y) dx dy &= \int_0^\pi [ x^3 +\frac{1}{2}x^2 \sin(y) ]_{x=0}^1 dy  \\ &=  \int_0^\pi (1 + \frac{1}{2}\sin(y) - 0) dy \\ &= \left[y - \frac{1}{2}\cos(y)\right]_{y=0}^\pi = \pi + 1 \end{align} $$
<h3>Aufgabe 4</h3>
Wenn man sich das Dreieck mal aufmalt, kommt man darauf, dass die Hypothenuse durch $y = \pi - \pi x$ oder alternativ $x= 1 - \frac{y}{\pi}$ gegeben ist.

Das zu berechnende Integral ist also

$$ \int_0^\pi \int_0^{1-\frac{y}{\pi}} \sin(y) x dx dy$$ oder

$$ \int_0^1 \int_0^{\pi-\pi x} \sin(y)x dy dx $$.

Welches man nimmt ist egal (Fubini). Letzteres ist tatsächlich etwas einfacher, da man dort bei den Zwischenschritten nur einmal Produktintegration machen muss, bei ersterem zweimal. Deshalb zeige ich hier nur die Lösung für erstere Variante:

$$ \begin{align} \int_0^\pi \int_0^{1-\frac{y}{\pi}} \sin(y) x dx dy  &= \int_0^\pi \left[ \frac{1}{2}\sin(y)x^2 \right]_{x=0}^{1-\frac{y}{\pi}} dx dy = \int_0^\pi \frac{1}{2}\sin(y) \cdot \left(1-\frac{y}{\pi}\right) ^2 dy \\ & \stackrel{(*)}{=} \left[-\frac{1}{2}\cos(y)\left(1-\frac{y}{\pi}\right)^2\right]_{y=0}^\pi - \int_0^\pi -\frac{1}{2}\cos(y)\left(-\frac{2}{\pi}\right)\left(1-\frac{y}{\pi}\right) dy \\ & \stackrel{(*)}{=}  \left(\frac{1}{2}\right) - \frac{1}{\pi} \left( \left[\sin(y)(1-\frac{y}{\pi})\right]_{y=0}^\pi - \int_0^\pi \sin(y) \left(-\frac{1}{\pi}\right) dy \right) \\  & = \frac{1}{2} ~ - \frac{1}{\pi} \left( 0 + \frac{1}{\pi} \left[-\cos(y) \right]_{y=0}^\pi \right)= \frac{1}{2} ~ - \frac{2}{\pi^2} \end{align} $$

Bei den beiden Gleichungen mit dem Sternchen ist jeweils Produkt-Integration gemacht worden.
<h3>Aufgabe 5</h3>
$$\nabla f(x,y,z) = \begin{pmatrix} 12x -4yz + 8z^2 \\ -4xz +2z \\ -4xy +2z \\ -4xy +2y + 16xz \end{pmatrix} $$

$$\nabla f(x,y,z) = \begin{pmatrix} 28 \\ -4 \\ 28 \end{pmatrix} $$

$$\mbox{d}f(x,y,z) = 28\mbox{dx} -4 \mbox{dy} + 28 \mbox{dz} $$
<h3>Aufgabe 6</h3>
Zunächst die Ableitungen und $p$ dort einsetzen:

$$ \begin{align} f(x) &= \sin(2x + \pi) &\Rightarrow f(p) = 0 \\ f'(x) &= 2\cos(2x+\pi)  &\Rightarrow f'(p) = 2 \\ f''(x) &= -4\sin(2x + \pi) &\Rightarrow f''(p) = 0 \end{align} $$

Das Taylorpolynom sieht also folgendermaßen aus:

$$ T_2^p(x) = f'(p)(x-p) = 2x - \pi $$


<h3>Aufgabe 7</h3>


<h5>zu 7.1</h5>
Was ist zu zeigen? Wir müssen für jedes beliebige $\varepsilon > 0$ ein $\delta > 0$ finden, sodass aus $|x-1| < \delta$ folgt, dass $|\sqrt{x} - \sqrt(1)| < \varepsilon$.

Sei uns also ein solches $\varepsilon > 0$ gegeben. Der Ansatz ist nun wie immer, aus $\|\sqrt{x} - \sqrt{1}\|$ müssen wir irgendwie auf einen Term mit $\|x-1\|$ kommen. Hier erweitern wir den Term einfach geschickt.

$$ |\sqrt{x} - \sqrt{1}| = |\sqrt{x} - 1| = |\sqrt{x} - 1| \frac{\sqrt{x} + 1}{ \sqrt{x} + 1} = \frac{|x - 1|}{ \sqrt{x} + 1}$$

Nun gilt für den letzten Term (da $\sqrt{x}>0$):

$$ \frac{|x - 1|}{ \sqrt{x} + 1} < | x - 1| $$

Insgesamt folgt also
$$
|\sqrt{x} - \sqrt{1}| < | x - 1|
$$

Zu einem gegebenen $\varepsilon > 0$ können wir nun einfach $\delta = \varepsilon $ wählen, denn dann folgt:

$$
|x -1| < \delta \Rightarrow |x-1| < \varepsilon \Rightarrow |\sqrt{x} -1| < \epsilon
$$

Damit ist die Stetigkeit gezeigt.
<h5>zu 7.2</h5>
Die erste Ableitung ist $f'(x) = \frac{1}{2\sqrt{x}}$. Dies ist offenbar $>0$ für alle $x>0$. Damit ist die $f$ schonmal streng monoton steigend für alle $x>0$.

Für $x=0$ gilt folgendes: Für jeden Wert $y>0$ gilt $f(0) = 0 < \sqrt{y} = f(y)$. Also ist $f$ auf ganz $[0, \infty)$ streng monoton steigend.
<h5>zu 7.3</h5>
Hier ist eine Grenzwertbetrachtung erforderlich. Die erste ist sehr einfach: $\lim_{x \rightarrow \infty} g(x) = \lim_{x \rightarrow \infty} xe^x = \infty$ (das reicht bereits, hier gibt es keine speziellen Vorkommnisse).

Für $\lim_{x \rightarrow -\infty} g(x)$ muss die Regel von de l'Hôpital angewandt werden (weil dort quasi $  -\infty \cdot 0 $ steht). Es folgt:

$\lim_{x \rightarrow -\infty} g(x) = \lim_{x \rightarrow -\infty} xe^x = \lim_{x \rightarrow -\infty} \frac{x}{e^{-x}} = \lim_{x \rightarrow -\infty} \frac{1}{-e^{-x}} = 0$.
<h3>Aufgabe 8</h3>
<h5>zu 8.1</h5>
$$\mathcal{L}(x,y,\lambda) = 2x^2 + 4xy + 4y + \lambda(x^2 -y -6) $$

$$ \nabla \mathcal{L}(x,y,\lambda) = \begin{pmatrix} 4x +4y +2\lambda x \\ 4x +4 - \lambda \\ x^2 -y -6 \end{pmatrix} $$

Dies wird Null gesetzt, und man bekommt z.B. heraus, dass $y = x^2 -6$ und $\lambda = 4x + 4$. Dies wieder in die erste Zeile eingesetzt ergibt $ x_1 = 1, y_1 = -5, \lambda_1 = 8, f(x_1, y_1) = -38 $ und $x_2 = -2, y_2 = -2, \lambda_2 = -4, f(x_2, y_2) = 64 $.
<h5>Zu 8.2</h5>
Die geränderte Hessematrix ist

$$ \begin{pmatrix} 0 & 2x & -1 \\ 2x & 4+2\lambda & 4 \\ -1 & 4 & 0 \end{pmatrix} $$

mit der Determinante $-16x -4 -2\lambda$. Für $p_1$  ist diese Determinante also $-30$, wir haben also ein Minimum, für $p_2$ erhalten wir als Determinante $36$, es ist also ein Maximum. (Natürlich nur unter der Nebenbedingung. Das heißt nicht, dass sie auch Extrempunkte von $f$ sind).
