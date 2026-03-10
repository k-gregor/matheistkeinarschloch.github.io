---
layout: page
title: Reihen (Grundlagen)
nav: true
permalink: /reihen-grundlagen/
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


<h2>Was ist eine Reihe?</h2>
Eine Reihe ist im Wesentlichen eine Summe von Folgegliedern einer unendlichen [Folge]({{ "/folgen-grenzwerte/" | relative_url }}) $a_n$. Wir kennen ja alle die Folge $(\frac{1}{n})_{n\in \mathbb{N}}$, die entsprechende Reihe dazu wäre also die Summe der einzelnen Folgeglieder: $a_1 + a_2 + a_3 + \ldots$, also $1 + \frac{1}{2} + \frac{1}{3} + \ldots $
Dies schreibt man so auf:

$$ S = \sum_{k=1}^\infty \frac{1}{k} $$

Das bedeutet: Wir summieren für jedes $k$ von $1$ bis $\infty$ die Werte für $\frac{1}{k}$ auf. Eine Reihe kann auch bei Null anfangen, in diesem Beispiel geht das nur nicht, weil wir beim ersten Summanden durch Null teilen würden. Oft schreibt man auch nur $\sum a_k$, wenn klar ist, wo die Summe losgeht.

Teilweise werden auch Teilsummen bis zu einem bestimmten Wert von $k$ berechnet, diese nennen wir die $n$-te Partialsumme:

$$ S_n = \sum_{k=1}^n \frac{1}{k} $$

Die Partialsummen bilden eine Folge (bestehend aus $S_1, S_2, S_3$ und so weiter). Es gilt offenbar $\lim_{n\rightarrow \infty} S_n = \lim_{n\rightarrow \infty} \sum_{k=1}^n a_k = \sum_{k=1}^\infty a_k = S $.
<h2>Definition: Konvergenz und Divergenz</h2>
Die Frage, die sich nun stellt, ist, was herauskommt, wenn man man alle Glieder der Reihe aufsummiert, dies nennt man den Summenwert. Dabei gibt es drei Möglichkeiten:
<ol>
 	<li>Die Reihe ist <strong>konvergent</strong>, d.h. die Summe nimmt einen endlichen Wert an</li>
 	<li>Die Reihe ist <strong>absolut konvergent</strong>, d.h. auch die dazugehörige Reihe der Beträge $\sum |a_k|$ konvergiert</li>
 	<li>Die Reihe ist <strong>bestimmt divergent</strong>, d.h. die Summe hat den Wert $\infty$ oder $-\infty$</li>
 	<li>Die Reihe ist <strong>unbestimmt divergent</strong>, wenn weder 1) noch 2) noch 3) zutreffen.</li>
</ol>
Beispiele:
<ol>
 	<li><strong>Konvergent</strong>: $ \sum_{k=1}^\infty \frac{1}{k^2} = 1 + \frac{1}{4} + \frac{1}{9} + \cdots$
Diese Reihe konvergiert gegen $\frac{\pi^2}{6}$. Das ist auf den ersten Blick etwas erstaunlich, aber dazu kommt später mehr.</li>
 	<li><strong>Absolut konvergent: </strong>Jede konvergente Reihe, deren Glieder positiv sind, ist automatisch absolut konvergent, denn es gilt $|a_k| = a_k$, also auch $\sum a_k = \sum |a_k|$. Die Reihe $\sum (-1)^k \frac{1}{k}$ ist konvergent (nach Leibnizkriterium), aber nicht absolut konvergent, da die Reihe $\sum | (-1)^k \frac{1}{k}| = \sum \frac{1}{k}$ divergiert.</li>
 	<li><strong>Bestimmt divergent</strong>: $ \sum^{\infty}_{k=1} 1 = 1 + 1 + 1 + 1 + \cdots $
Wir addieren hier also unendlich viele Einsen auf. Das Ergebnis ist deshalb natürlich $\infty$.</li>
 	<li><strong>Unbestimmt divergent</strong>: $ \sum_{k=0}^\infty (-1)^k ~k = 0 -1 +2 -3 +4 -5 + \cdots $
Diese Summe geht springt immer hin und her, und wird dabei vom Betrag her größer. Sie geht allerdings nicht gegen $\infty$ oder $-\infty$ (sondern quasi gegen beides gleichzeitig)</li>
</ol>
<h2>Wann ist eine Reihe konvergent, und wann ist sie divergent?</h2>
Damit wir überhaupt nur an Konvergenz denken können, muss die [Folge]({{ "/folgen-grenzwerte/" | relative_url }}), deren Glieder wir aufsummieren, schonmal eine Nullfolge sein, d.h. die Folgeglieder müssen gegen Null gehen. Denn nur dann werden die Summanden immer kleiner, bis sich der Gesamtwert der Reihe irgendwann so gut wie nicht mehr ändert. Aber das reicht erstaunlicherweise leider als Kriterium nicht aus! Denn es gibt Reihen, die Summanden aufaddieren, die gegen Null gehen, aber trotzdem divergent sind! Einfach, weil die Summanden nicht schnell genug gegen Null gehen!


### Die harmonische Reihe

Das klassische Beispiel dafür ist die <strong>harmonische Reihe</strong> $\sum \frac{1}{n}$. Diese Reihe ist divergent! Die Reihe $\sum \frac{1}{n^2}$ allerdings ist konvergent. Das klingt erstmal total seltsam, aber wird klarer, wenn man sich das mal an einem Bild anschaut. Die blauen Punkte beschreiben die Folgen, $\frac{1}{n}$ bzw. $\frac{1}{n^2}$. Und die roten Punkte bilden die sogenannte "Partialsumme", also immer die Summe, aufsummiert bis zum $n$-ten Glied.

<img class="alignnone wp-image-844" src="http://matheistkeinarschloch.de/wp-content/uploads/2016/11/reihe1-300x240.png" alt="Die Partialsummen der harmonischen Reihe wachsen immernoch sehr stark an, die Reihe divergiert" width="399" height="320">

<img class="alignnone wp-image-843" src="http://matheistkeinarschloch.de/wp-content/uploads/2016/11/reihe2-300x240.png" alt="Die Partialsummen dieser Reihe wachsen schnell kaum noch an, die Reihe konvergiert" width="399" height="320">

Man sieht hier sehr schön, wie die Partialsummen von $\sum \frac{1}{n}$ immernoch sehr stark ansteigen, die Partialsummen von $\sum \frac{1}{n^2}$ aber schon sehr schnell kaum noch anwachsen. Obwohl beide Folgen recht schnell gegen Null gehen (die blauen Punkte), sodass wir in dieser Grafik eigentlich kaum einen Unterschied erkennen können, reicht dieser Unterschied aus, dass die eine Reihe konvergent ist und die andere divergent. Eine genauere mathematische Erklärung, warum die harmonische Reihe divergiert findet ihr in dem Artikel [Reihen (Konvergenzkriterien und Beispiele)]({{ "/reihen-konvergenzkriterien-beispiele/" | relative_url }})

<img class="size-medium wp-image-912 aligncenter" src="http://matheistkeinarschloch.de/wp-content/uploads/2016/11/meme_harmonicseries-300x226.jpg" alt="meme_harmonicseries" width="300" height="226">

Das geschulte Auge wird von dem Bild der Reihe $\sum \frac{1}{n}$ an den Logarithmus erinnert, welcher zwar auch immer schwächer steigt, aber eben doch immer weiter ansteigt, bis $\infty$.
<h2>Kriterien, um zu bestimmen ob eine Reihe konvergent oder divergent ist</h2>
Es gibt einige Kriterien, mit denen man Reihen auf Konvergenz prüfen kann, diese findet ihr in folgendem Artikel: [Reihen (Konvergenzkriterien und Beispiele)]({{ "/reihen-konvergenzkriterien-beispiele/" | relative_url }})



<h2>Die wichtigsten Reihen und ihre Grenzwerte:</h2>
Zuletzt noch eine kleine Liste von Reihen, die ihr unbedingt auswendig können solltet:
<ul>
 	<li>$ \sum_{k=1}^\infty \frac{1}{k} = \infty$, die "harmonische Reihe"</li>
 	<li>$ \sum_{k=1}^\infty \frac{1}{k^2} = \frac{\pi^2}{6}$</li>
 	<li>$ \sum_{k=0}^\infty \frac{1}{k!} = e$</li>
 	<li>$ \sum_{k=0}^\infty \frac{x^k}{k!} = e^x$</li>
 	<li>$\sum_{k=0}^\infty (-1)^k \frac{x^{2k+1}}{(2k+1)!} = \sin(x)$</li>
 	<li>$\sum_{k=1}^\infty (-1)^k \frac{x^{2k}}{(2k)!} = \cos(x)$</li>
 	<li>$ \sum_{k=0}^\infty x^k$, die "geometrische Reihe", sie konvergiert für $|x|&lt;1$ gegen $\frac{1}{1-q}$ und divergiert andernfalls. Hierzu ist bereits ein Artikel in Arbeit.</li>
</ul>
