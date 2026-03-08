---
layout: page
title: Lineare Unabhängigkeit
nav: true
permalink: /lineare-unabhaengigkeit/
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


<script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/three@0.128/examples/js/controls/OrbitControls.js"></script>





Die lineare Unabhängigkeit bereitet vielen Studenten Kopfzerbrechen. Was bedeutet sie überhaupt?

Anschauliche Definition: Eine Gruppe von Vektoren ist linear unabhängig, wenn keiner der Vektoren durch eine Linearkombination der anderen dargestellt werden kann.

In einem jeden dieser Vektoren muss also Information enthalten sein, die in den anderen nicht steht. Schauen wir uns mal folgende Visualisierung an. Ihr könnt klicken und ziehen zum drehen, und scrollen zum rein- bzw rauszoomen. Falls ihr hier keine Visualisierung seht, bitte Javascript aktivieren, oder Blocker deaktivieren!



<div id="plot3d" style="width:500px; height:500px; text-align: center;"><b>Wenn ihr hier nichts seht, Javascript aktivieren oder Blocker deaktivieren.</b></div>


<script>
const container = document.getElementById("plot3d");

// Scene
const scene = new THREE.Scene();
scene.background = new THREE.Color(0xffffff);

// Camera
const camera = new THREE.PerspectiveCamera(
  60,
  container.clientWidth / container.clientHeight,
  0.1,
  1000
);
camera.position.set(10, 10, 10);
camera.lookAt(0, 0, 0);

// Renderer
const renderer = new THREE.WebGLRenderer({ antialias: true });
renderer.setSize(container.clientWidth, container.clientHeight);
container.appendChild(renderer.domElement);

// Controls
const controls = new THREE.OrbitControls(camera, renderer.domElement);
controls.enableDamping = false;

// Axes
scene.add(new THREE.AxesHelper(5));

// Grid
const grid = new THREE.GridHelper(10, 10, 0x000000, 0xcccccc);
//grid.rotation.x = Math.PI / 2; // horizontal
scene.add(grid);


// three.js has z axis as second axis!
const vectors = [
  [-1,3,5],
  [5,1,3],
  [1,1,2],
  [3,2,1],
  [-1,4,-2],
  [4,4,-7]
];

vectors.forEach((v,i) => {
  const dir = new THREE.Vector3(v[0], v[1], v[2]);
  const length = dir.length();
  dir.normalize();
  const color = (i >= 3) ? 0xff0000 : 0x0000ff;

  const arrow = new THREE.ArrowHelper(dir, new THREE.Vector3(0,0,0), length, color, 0.5, 0.3);
  scene.add(arrow);
});

// Render loop
function animate() {
  requestAnimationFrame(animate);
  controls.update();
  renderer.render(scene, camera);
}

animate();
</script>


Zieht mal die Visualisierung so, dass ihr aus ungefähr der Richtung schaut, in die die blauen Vektoren zeigen. Ihr solltet im richtigen Winkel erkennen können, dass diese drei Vektoren in einer Ebene liegen! Das heißt, dass obwohl wir drei Vektoren in einem dreidimensionalen Raum haben, der dritte dieser Vektoren gar keine neue Richtung dazu bringt. Er bleibt in der Ebene der anderen beiden drin, hat also keine neue Richtungsinformation mehr, die nicht schon in den anderen beiden enthalten ist. Die blauen Vektoren sind also linear abhängig.

Anders die roten Vektoren: Wie man es dreht und wendet, wir bekommen die drei Vektoren nicht in eine Ebene. Jeder der Vektoren hat Richtungsinformation, die in den anderen beiden überhaupt nicht drin ist. Die roten Vektoren sind also linear unabhängig, man sagt, sie *spannen drei Dimensionen auf*.

Rechnerisch heißt diese Formulierung “Ein Vektor enthält Information, die die anderen nicht enthalten”, dass sich dieser Vektor nicht durch Kombination der anderen Darstellen lässt. Das sollte einleuchtend sein, denn wir können zwei der roten Vektoren niemals so kombinieren, dass der dritte herauskommt. Schauen wir uns dazu ein paar Zahlenbeispiele an.

## 1. Beispiel

Die Vektoren $v = \begin{pmatrix} 1 \\ 2 \\ 3 \end{pmatrix}$ und $w = \begin{pmatrix} 2 \\ 4 \\ 6 \end{pmatrix}$ sind <strong>linear abhängig, </strong>weil sich $w$ durch $v$ darstellen lässt: $w = 2v$.


## 2. Beispiel

Die Vektoren $v_1 = \begin{pmatrix} 2 \\ 0 \end{pmatrix}$,&nbsp; $ v_2 = \begin{pmatrix} 0 \\ 1 \end{pmatrix}$ und&nbsp;$ v_3 = \begin{pmatrix} 5 \\ 3 \end{pmatrix}$ sind <strong>linear abhängig, </strong>weil sich $v_3$ durch $v_1$ und $v_2$ darstellen lässt: $v_3 = 2.5v_1 + 3v_2$.

## 3. Beispiel

Die Vektoren $v_1 = \begin{pmatrix} 1 \\ 0 \\ 0 \end{pmatrix}$,&nbsp; $ v_2 = \begin{pmatrix} 0 \\ 1 \\ 0 \end{pmatrix}$ und&nbsp;$ v_3 = \begin{pmatrix} 5 \\ 3 \\ 1 \end{pmatrix}$ sind <strong>linear unabhängig, </strong>weil sich keiner der drei Vektoren durch eine Kombination der anderen darstellen lässt: egal, wie oft wir $v_1$ und $v_2$ miteinander kombinieren, in der dritten Koordinate wird niemals eine 1 stehen können, also können wir die beiden niemals zu $v_3$ kombiniern! Das heißt, es gibt keine reelen Zahlen $\lambda_1$ und $\lambda_2$, sodass $v_3 = \lambda_1v_1 + \lambda_2v_2$. Das gleiche gilt für die anderen Kombinationen.
(Bemerkung: ich lasse hier ein kleines Detail aus, auf das ich unten näher eingehen werde).
<h2>Die formale Definition</h2>
<blockquote>Eine Gruppe von Vektoren $v_1, v_2, \ldots v_n \in \mathbb{R}^n$ heißt linear unabhängig, wenn die Gleichung

$$ \lambda_1v_1 + \lambda_2v_2 + \cdots + \lambda_nv_n = 0 $$

nur durch $\lambda_1 = \lambda_2 = \cdots = \lambda_n = 0 $ gelöst werden kann.</blockquote>
Beachtet den Unterschied zwischen den zwei "Nullen": in der Linearkombination ist der Nullvektor gemeint, bei den $\lambda_i$ einfach die reelle Zahl Null.
Die Lösung, wo alle $\lambda_i$ Null sind, wird auch die "Triviallösung" genannt. <strong>Diese Lösung erfüllt die Gleichung immer! </strong>Schließlich addieren wir dann einfach nur Nullen auf. Uns interessiert nun einfach, ob es noch weitere Lösungen gibt! Wenn wir die Gleichung ein wenig umstellen, kommen wir auch wieder auf unsere anschauliche Definition von oben. Wir können beispielsweise den Vektor $v_1$ auf die andere Seite ziehen, und erhalten

$$ \lambda_1v_2 + \lambda_2v_3 + \cdots + \lambda_nv_n = -\lambda_1v_1 $$

Wenn wir also jetzt $\lambda$s finden, sodass die Gleichung erfüllt wird, heißt das, dass wir eine Kombination von $v_2, \ldots, v_n$ gefunden haben, mit denen sich $-\lambda_1v_1$ darstellen lässt. Das ist ein klein bisschen anders als unsere Definition vorher, wo wir wollten dass sich $v_1$ durch den Rest darstellen lässt, und jetzt steht hier aber noch ein $-\lambda_1$. Aber, falls $-\lambda_1 \neq 0$, können wir die Gleichung durch $-\lambda_1$ teilen und wir haben genau das was wir wollen. $\lambda_1$ könnte aber auch Null sein. Der Fall war einfach in unserer ursprünglichen anschaulichen Definition noch nicht enthalten. Ein Beispiel dazu wäre z.B. $ v_1 = \begin{pmatrix} 1 \\ 0 \\ 0 \end{pmatrix},&nbsp;v_2 = \begin{pmatrix} 3 \\ 0 \\ 0 \end{pmatrix},&nbsp;v_3 = \begin{pmatrix} 0 \\ 0 \\ 1 \end{pmatrix} $. Dann wäre nämlich $0v_3 = 1v_1 - \frac{1}{3}v_2$. Diese drei sind also linear abhängig.



# Die Beispiele aus der Visualisierung einmal durchgerechnet

## Beispiel 1


Schauen wir uns zunächst die blauen Vektoren an, diese lauten

$$
v_1 = \begin{pmatrix} -1 \\ 5 \\ 3 \end{pmatrix}, v_2 = \begin{pmatrix} 5 \\ 3 \\ 1 \end{pmatrix}, v_3 = \begin{pmatrix} 1 \\ 2 \\ 1 \end{pmatrix}
$$

Stellen wir einmal die Formel für lineare Unabhängigkeit auf und schauen, ob sie sich lösen lässt:

$$\lambda_1 \begin{pmatrix} -1 \\ 5 \\ 3 \end{pmatrix} + \lambda_2\begin{pmatrix} 5 \\ 3 \\ 1 \end{pmatrix} + \lambda_3\begin{pmatrix} 1 \\ 2 \\ 1 \end{pmatrix} = \begin{pmatrix} 0 \\ 0 \\ 0 \end{pmatrix}$$

Formen wir die dritte Gleichung um, erhalten wir $ \lambda_3 = -\lambda_2 -3\lambda_1 $, welches wir in die zweite Gleichung einsetzen können um $ \lambda_1 = \lambda_2 $ zu bekommen. Daraus folgt wieder mit der dritten dann $\lambda_3 = -4\lambda_2$, und wenn wir alles in die erste einsetzen kommt:

$$
\begin{align*}
-\lambda_1 +5\lambda_2 +\lambda_3 &= 0 \\ -\lambda_2 +5\lambda_2 -4\lambda_2 &= 0 \\ 0 &= 0 \end{align*}
$$

$0=0$? Und nun? Naja, das heißt ganz einfach: Es gibt unendlich viele Lösungen für unser Gleichungssystem! Die Lösung $\lambda_1=\lambda_2=\lambda_3=0$ ist eine davon, wie immer, aber es gibt eben noch viel mehr, nämlich gerade diejenigen, welche die berechneten Zusammenhänge zwischen den unterschiedlichen $\lambda_i$ enthalten. Eine Lösung ist zum Beispiel $\lambda_1 = 1, \lambda_2=1, \lambda_3=-4$, woraus folgt:

$$ 1 \begin{pmatrix} -1 \\ 5 \\ 3 \end{pmatrix} + 1\begin{pmatrix} 5 \\ 3 \\ 1 \end{pmatrix} -4\begin{pmatrix} 1 \\ 2 \\ 1 \end{pmatrix} = \begin{pmatrix} 0 \\ 0 \\ 0 \end{pmatrix}$$

Und der Anschaulichkeit halber noch einmal umgeformt:

$$ 1 \begin{pmatrix} -1 \\ 5 \\ 3 \end{pmatrix} = -1\begin{pmatrix} 5 \\ 3 \\ 1 \end{pmatrix} + 4\begin{pmatrix} 1 \\ 2 \\ 1 \end{pmatrix} $$

Heißt also: unser $v_1$ lässt sich durch die anderen beiden Vektoren darstellen! Die Vektoren sind also <strong>linear abhängig</strong>, wie wir das erwartet haben.

## Beispiel 2

Die roten Vektoren waren:

$$
v_1 = \begin{pmatrix} 3 \\ 1 \\ 2 \end{pmatrix}, v_2 = \begin{pmatrix} -1 \\ -2 \\ 4 \end{pmatrix}, v_3 = \begin{pmatrix} 4 \\ -7 \\ 4 \end{pmatrix}
$$

Das Gleichungssystem lautet

$$\lambda_1\begin{pmatrix} 3 \\ 1 \\ 2 \end{pmatrix} + \lambda_2 \begin{pmatrix} -1 \\ -2 \\ 4 \end{pmatrix}+ \lambda_3 \begin{pmatrix} 4 \\ -7 \\ 4 \end{pmatrix} = \begin{pmatrix} 0\\0\\0 \end{pmatrix} $$

Wenn wir die erste Gleichung nach $\lambda_2$ auflösen und in die zweite einsetzen erhalten wir $-3\lambda_3 = \lambda_1$. Setzen wir dies wieder in die erste, bekommen wir $\lambda_2 = -5\lambda_3$. Alles kombiniert in die dritte gesetzt erhalten wir

$$ \begin{align*} -6\lambda_3 -20\lambda_3 +4\lambda_3 &= 0 \\ -22\lambda_3 &= 0 \end{align*} $$

Daraus folgt also $\lambda_3=0$, und mit den anderen Informationen auch $\lambda_2=0$ und $\lambda_1=0$! Dieses Gleichungssystem ist also eindeutig lösbar und die einzige Lösung ist die Triviallösung! Keiner der Vektoren lässt sich also durch Linearkombination der anderen darstellen. Das heißt, die Vektoren sind linear unabhängig!
