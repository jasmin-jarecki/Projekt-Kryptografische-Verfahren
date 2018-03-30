# Projekt-Kryptografische-Verfahren

#### **Inhaltsverzeichnis**
<ol>
  <li>Einleitung</li>
  <li>Aufgaben</li>
  <ol>
    <li> Alphabetisch Einordnen</li>
    <li> Caesar-Verschlüsselung</li>
    <li> ROT13-Verfahren</li>
    <li> Hill-Verfahren</li>
    <li> RSA-Verschlüsselung</li>
  </ol>
  <li>Projektverlauf</li>
  <li>Zusammenfasssung</li>
 </ol>

### Einleitung<a name="Einl"></a>

Das Projekt befasst sich mit einfachen Kryptographischen Verfahren zur Ver- und Entschlüsselung von Daten insbesondere Texten. Die einzelnen Verfahren sollen zunächst beschrieben und erklärt werden. Wie wurden sie entwickelt, wie funktionieren sie, welche Vor- un Nachteile gibt es und welche Anwendungen finden sie?
Des Weiteren soll gezeigt werden, wie diese in Python-Programme umgesetzt werden können. Dafür werden für ausgewählte Methoden Programme zur Ver- und Entschlüsselung von Texten geschrieben und der Verlauf in diesem Bericht dokumentiert. Die Programme werden zusätzlich hier verlinkt und als Python-Dateien im Repository zu finden sein. 


### 2. Aufgaben<a name="Auf"></a>

#### 2.i Alphabetisch Einordnen<a name="Aph"></a>

s. [Python-Skript "Alphabetisch Einordnen"](https://github.com/jasmin-jarecki/Projekt-Kryptografische-Verfahren/blob/master/Alphabetisch%20Einordnen.ipynb)

Die Verschlüsselung eines Textes, indem die Buchstaben des Eingabetextes in alphabetische Reihenfolge gebracht werden, ist
in Python ein relativ einfach zu programmierendes Verfahren. Der eingegebene Text wird so sortiert, dass zunächst die 
Großbuchstaben in alphabetische Reihenfolge gebracht werden und anschließend die Kleinbuchstaben, dabei werden die
ursprünglichen Wortlängen beibehalten.<br />

In Python kann diese Verschlüsselungsmethode wiefolgt umgesetzt werden. Zunächst wird eine Liste mit den Elementen des
Alphabets als Groß- und Kleinbuchstaben definiert.<br>

![Screenshot (1)](https://github.com/jasmin-jarecki/Projekt-Kryptografische-Verfahren/blob/master/Berichtbilder/Screenshot%20(1).png)

Anschließend wird die Verschlüsselungsfunktion definiert mit den Argumenten 'Text', an dessen Stelle der zu verschlüs-
selnde Text geschrieben wird, und 'Alphabet', wo das zu nutzende Alphabet eingetragen wird.
Die Funktion beginnt damit, dass der als string eingegebene Text zu einer Liste K gemacht wird, in der die einzelnen 
Elemente aus den Buchstaben, Leer- und Satzzeichen bestehen.<br>
Im Anschluss wird eine zweite Liste K2 erstellt, die nur noch die Buchstaben enthält.
Diese Liste wird im Folgenden dann, wie oben beschrieben, sortiert. Im letzten Schritt sollen die Leer- und Satzzeichen in
die verschlüsselte Nachricht in einer dritten Liste K3 eingefügt werden. Dies gelingt, indem die Elemente der ersten Liste
K betrachtet werden. Sind diese auch Elemente des definierten Alphabets, werden sie durch die entsprechenden Elemente aus
der sortierten Liste K2 ersetzt, ist es aber ein Leer- oder Satzzeichen, so werden diese direkt übernommen.<br> 

![Screenshot (5)](https://github.com/jasmin-jarecki/Projekt-Kryptografische-Verfahren/blob/master/Berichtbilder/Screenshot%20(5).png)

Diese Liste wird letztlich von der Verschlüsselungsfunktion als string ausgegeben.

![Screenshot (6)](https://github.com/jasmin-jarecki/Projekt-Kryptografische-Verfahren/blob/master/Berichtbilder/Screenshot%20(6).png)


#### 2.ii Caesar-Verschlüsselung<a name="Cae"></a>

Die Caesar-Chiffre funktioniert, indem jedem Buchstaben a mithilfe eines geheimen Schlüssels c ein
anderer Buchstabe b zugeordnet wird.<br />
b = a+c mod 26.<br />
Diese Art der Verschlüsselung wurde bereits von dem römischen Feldherr Julius Caesar verwendet,
und trägt deshalb seinen Namen.
Bei der Caesar-Verschlüsselung ergeben sich jedoch einige Nachteile, die im Folgenden weiter
betrachtet werden sollen.<br>
Da das Alphabet nur 26 Buchstaben besitzt, gibt es nur 25 verschiedene Schlüssel, um einen Text zu
ver- bzw. entschlüsseln.
Selbst wenn man jedem Buchstaben einen beliebigen anderen zuordnen würde, ergäben sich zwar
26! Möglichkeiten, doch wesentliche Probleme bleiben die gleichen. Hier ist zu nennen, dass man
zum Ver- und Entschlüsseln denselben Schlüssel benötigt. Des Weiteren variiert die Häufigkeit der
vorkommenden Buchstaben bei typischem Sprachgebrauch je nach Sprache. So sind im Deutschen
Buchstaben wie e und n durch ihre deutliche Präsenz zu idetifizieren.


#### 2.iii ROT13-Verfahren<a name="ROT"></a>

s. [Python-Skript "ROT13-Verfahren"](https://github.com/jasmin-jarecki/Projekt-Kryptografische-Verfahren/blob/master/ROT13-Verfahren.ipynb)

Die ROT13-Chiffre ist eine Caesar-Verschlüsselung mit dem Schlüssel c = 13. Dieser kann aber frei gewählt werden. Betrachtet man allerdings nur das gewöhnliche Alphabet mit den 26 Buchstaben, ist eine Nachricht relativ leicht zu dechiffrieren, da man die Zeichen nur entsprechend verschoben werden müssen. Da das Alphabet nur 26 Buchstaben müsste man höchstens 25 Verschiebungen ausprobieren.
<br />
Auch dieses Verfahren ist relativ einfach umzusetzten.<br>
Zunächst wird wieder ein Alphabet definiert. Ein String, der alle Elemente enthalten soll, die in der Eingabenachricht vorkommen können. So schließt er sowohl Klein- als auch Großbuchstaben, Zahlen, Leer- und Satzzeichen ein. Dies hat im Folgenden die Auswirkung, dass die Summe aus dem Buchstaben a und dem Schlüssel c module der Anzahl der Elemente des Alphabets n genommen wird.<br>
Die Verschlüsselungsfunktion enthält die Argumente 'Text', für den zu verschlüsselnden Text, 'Alphabet', wo das zu nutzende Alphabet eingetragen werden soll, und 'Shift=13', wobei dieser Schlüssel frei gewählt werden kann.<br>
In dieser Funktion wird ein Dictionairy angelegt, sodass jedem Buchstaben aus dem Alphabet ein neuer um Shift=13 Stellen veschobener Buchstabe zugeordnet wird. 

![Screenshot()](https://github.com/jasmin-jarecki/Projekt-Kryptografische-Verfahren/blob/master/Berichtbilder/Screenshot%20(7).png)

Nun wird jeder Buchstabe der Eingabe mithilfe des Dictionairys ersetzt, zu einer neuen Liste hinzugefügt, die letztlich als String wieder ausgegeben wird.<br/>
Dadurch, dass das Alphabet eigens definiert werden muss, ist es nicht mehr so leicht ohne Kenntniss des Schlüssels den verschlüsselten Text zu dechiffrieren. Für die Entschlüsselung muss man sowohl die Länge des Alphabets als auch die Reihenfolge der Zeichen kennen.<br />
Somit funktioniert die Entschlüsselung entsprechend, der ursprüngliche Buchstabe a ergibt sich durch: a = b-c mod n.

![Screenshot (9)](https://github.com/jasmin-jarecki/Projekt-Kryptografische-Verfahren/blob/master/Berichtbilder/Screenshot%20(9).png)


#### 2.iv Hill-Verfahren<a name="Hill"></a>

s. [Python-Skript "Hill-Verfahren"](https://github.com/jasmin-jarecki/Projekt-Kryptografische-Verfahren/blob/master/Hill-Verfahren.ipynb)

Das Hill-Verfahren wurde 1929 von dem New Yorker Professor Lester Hill entdeckt, es basiert auf der Substitution der Buchstaben des Alphabets.<br />
Die Verschlüsselung funktioniert wie folgt:<br>
n Zeichen werden mithilfe einer nxn-Matrix multipliziert. Damit die Nachricht auch wieder zu entschlüsseln ist, muss die nxn Matrix invertierbar sein. Anschließend wird vom Produkt modulo 26 errechnet. Um eine Nachricht zu verschlüsseln, lassen sich z.B. die Buchstaben zu Dreierkonstellationen zusammenfassen. Die nun in Zahlen umgewandelt werden müssen. Dies kann z.B. ähnlich zustande kommen wie beim Rot-Verfahren. Die 3x3-Matrix, um nun die drei Buchstaben zu verschlüsseln ist der Schlüssel.<br />
Die Entschlüsselung funktioniert wie folgt: 
Zum Entschlüsseln, wie es in Aufgabe 2 gefordert wird, wird nun die verschlüsselte Matrix mit der inversen Matrix multipliziert, anschließend ist wieder die Operation modulo 26 durchzuführen.<br>
Die Anforderungen an den Schlüssel sind wie folgt:
Die Matrix muss invertierbar sein, d.h. die Determinante muss ungleich 0 sein. Auch darf die Matrix, damit sie im Hill-Verfahren angewendet werden kann, nicht einen gemeinsamen Teiler mit den Primfaktoren der modularen Zahl haben, bei 26 wären das 2 und 13.<br />

Das Hill-Verfahren wird als Definition Verschlüsselung2 in dem Programm umgesetzt. Die Definition ist charakterisiert durch die Eingabe, das verwendete Alphabet, sowie die Schlüsselmatrix M. Es wird auf  die Bibliothek Numpy zurückgegriffen. Anfangs wird das Alphabet in einer Liste notiert, um anschließend mithilfe einer for-Schleife, die Stellen im Alphabet des eingetragenen Ausdruckes als weitere Liste ausgeben zu können. Hiernach wird diese Liste L in einen Vektor v umgewandelt. Dieser muss allerdings, um anschließend mit der Matrix multipliziert zu werden, transponiert werden. <br> Nun gilt es, den Vektor in mehrere 3x1-Vektoren umzuwandeln. Das Programm schafft es leider nicht, Ausdrücke mit nicht durch drei teilbarer Buchstabenanzahl zu codieren. In dieser while-Schleife werden die Elemente der Indizes i, i+1, und i+2 des transponierten Vektors v zu einem Vektor v1 gemacht, und dann mit der Schlüsselmatrix M multipliziert. Es folgt die Ausgabe des Produktes. Durch die Erhöhung von i um drei zum Ende der Schleife bewirkt, dass die nächsten drei Zahlen den selben Vorgang durchlaufen. Die while-Schleife stoppt, wenn i gleich oder größer der Länge von v ist. Somit liefert das Programm in der Ausgabe schließlich die verschlüsselten 3x1-Vektoren.<br />

![Screenshot 13](https://github.com/jasmin-jarecki/Projekt-Kryptografische-Verfahren/blob/master/Berichtbilder/Screenshot%20(13).png)

s. [Python-Skript "A2 Entschlüsselung Hill-Verfahren"](https://github.com/jasmin-jarecki/Projekt-Kryptografische-Verfahren/blob/master/A2%20Entschlüsselung%20Hill-Verfahren.ipynb)

Die Entschlüsselung des Hill-Verfahrens, Aufgabe 2, wird analog umgesetzt. Zuvor muss jedoch noch die inverse Matrix berechnet werden. Die Definition ist in Abhängigkeit der verschlüsselten Vektoren, der Schlüsselmatrix M und des Alphabets. Das Alphabet kann wie bereits beim Verschlüsselungsvorgang beschrieben als Liste fungieren, sodass die Indizes dann ausreichen, um die entschlüsselten Zahlen wieder zu Buchstaben werden zu lassen. Die Schwierigkeit in diesem Verfahren der Entschlüsselung, die inverse Matrix von M zu bilden, lässt sich mittels 1/det /* adj(M)(die adjunkte Matrix von M) berechnen.<br>
Allerdings gelingt die Entschlüsselung noch nicht korrekt, für Einzelheiten s. [Projektverlauf](#Pro)

![Screenshot 18](https://github.com/jasmin-jarecki/Projekt-Kryptografische-Verfahren/blob/master/Berichtbilder/Screenshot%20(18).png)


#### 2.v RSA-Verschlüsselung<a name="RSA"></a>

s. [Python-Skript "RSA-Verschlüsselung"](https://github.com/jasmin-jarecki/Projekt-Kryptografische-Verfahren/blob/master/RSA-Verschlüsselung.ipynb)

Das von Rivest, Shamir und Adelson 1980 patentierte Verschlüsselungsverfahren ist heute das
weitgenutzte Verfahren der Verschlüsselung, es findet Anwendung in der Internet- und
Telefoninfrastruktur, sowie der E-Mail Verschlüsselung und vielem mehr.<br>
Bei dem RSA-Verschlüsselungsverfahren handelt es sich um ein asymmetrisches
Verschlüsselugsverfahren. Bei diesem Verfahren wird ein Klartext m mit dem public key des
Empfängers verschlüsselt, der Empfänger kann den Geheimtext c anschließend mit dem private key d
entschlüsseln. Das Verfahren basiert auf der Schwierigkeit, die Verschlüsselung c=m^e mod n zu
lösen.<br>
c wird wie folgt berechnet<br />
c = m^e mod n,<br/>
wobei gilt<br />
n = p /* q.<br />
Für die beiden Primzahlen p und q gilt, dass deren Entschlüsselung mithilfe von n durch Faktorisieren
zu rechenaufwendig ist, n groß genug ist. Hierbei geht es heutzutage um Größenordnungen von
mehreren hundert bit.<br>
Für e gilt<br />
ggt(e,phi(n)) = 1, 1 <e < phi(n)<br />
wobei phi(n) = (p-1) /* (q-1).<br>
Phi(n) gibt die Anzahl der Teilerfremden Zahlen von n, die kleiner als n sind, an.<br>
Zum Entschlüsseln wird der private Schlüssel d benötigt<br />
d /* e mod phi(n) = 1, d.h.<br>
d /* e = k mod phi(n)+1,<br/>
wobei k Element der natürlichen Zahlen ist.
Nach dem Satz von Euler folgt daraus<br />
m^k^phi(n) m mod n = m.<br />
Um den Geheimtext c zu verschlüsseln, geschieht folgendes<br />
c^d mod n = m^d m^-d mod n<br>
= m^k^phi(n) m mod n<br>
= m.<br />
Um den Geheimtext c als Dritter zu bestimmen, muss man entweder d aus e oder Phi bestimmen.
Dies ist alles recht ähnlich in der rechnerischen, praktischen Durchführbarkeit der Bestimmung von p
und q aus n. Ebenfalls die e-te Wurzel aus c zu berechnen scheitert am Rechenaufwand.<br />

In Python ist die grundsätzliche Ver- und Entschlüsselung nach RSA-Verfahren nicht schwer umzusetzten, da die Formeln für den Geheimtext c und den Klartext m direkt eingegeben werden können, die Voraussetzung dafür ist, dass die beiden Schlüssel bekannt sein müssen.<br>

![Screenshot ](

Die eigentliche Schwierigkeit liegt darin, die Schlüssel zu erzeugen.<br>
Für den Schlüssel e werden alle Zahlen i von z bis phi(n) auf den größten gemeinsamen Teiler von i und phi(n) überprüft, wenn dieser 1 ist, eignet sich i als öffentlicher Schlüssel e. Das Argument z wird eingeführt, damit das Programm nicht bei den kleinen Zahlen abbrechen soll. So kann etwas Einfluss auf die Höhe des Betrags von e genommen werden. <br />

### 3. Projektverlauf<a name="Pro"><a/>

Im Rahmen des von uns ausgewählten Projektes beschäftigten wir uns mit verschiedenen kryptographischen 
Verfahren. Wir haben uns für dieses Projekt entschieden, da uns dieses Thema aufgrund seiner Präsens im täglichen Leben,
als auch aufgrund seines mathematischen Orientierung interessierte.<br>
Anfangs galt es, die Verfahren zu verstehen, um diese dann in einem Code in Python umzusetzen. Die erste von uns 
bearbeiteten Verfahren waren die in Aufgabe 1 geschilderten Verfahren, der alphabetischen Sortierung und das 
Rot-13-Verfahren.<br>
Mit der Python built-in-Methode für Listen ist die Verschlüsselung sehr einfach umzusetzten. <br>
Die Entschlüsselung bei diesem Verfahren war uns nicht möglich, die Komplexität, die durch den fehlenden Schlüssel entsteht, 
erlaubt nur eine sehr aufwändige Entschlüsselung.<br>
Auch die Umsetztung des Rot-Verfahren war relativ einfach. In der Verschlüsselung werden in einem Dictionairy dem ursprüng-
lichen Buchstaben ein um den Wert des Schlüssels verschobenen neuen Buchstaben ersetzt. Die Entschlüsselung funktioniert
analog. Schwierigkeiten bereiteten hier die Verwendung von Sonderzeichen, wie z. B. Umlauten. So war es nötig, die 
Verwendung des Unicodes zu verstehen, um hier die Ver- und Entschlüsselung korrekt vorzunehmen. Auch hielt auf, dass sobald
das Zeichen "ß" auf die Verschlüsselung angewendet worden war, ein "key-error" zurückgegeben wurde. Nach einiger Suche trat 
hervor, dass sich das "ß" im gewählten Alphabet, das auf das Verschlüsselungsdictionairy angewendet wurde, sich von dem in
der Eingabe optisch unterschied, was den key-error erklärte, da dem eingegebenen "ß" kein anderes Zeichen zugeordnet werden
konnte.<br />

![Screenshot 4](https://github.com/jasmin-jarecki/Projekt-Kryptografische-Verfahren/blob/master/Berichtbilder/Screenshot%20(4).png)

Nach diesen Verfahren wandten wir uns dem Hill-Verfahren zu. Erst nach einer Wiederaneignung der Matrizenrechnung und 
-programmierung war es uns möglich, die Verschlüsselung zu verstehen, und anschließend den 
Code zu verfassen. Eine besondere Schwierigkeit bildeten hier die Dreierbuchstabenkonstellationen. Das Prinzip der Hill-Ver-
schlüsselung beruht darauf, dass den Buchstaben zunächst die entsprechende Stelle im Alphabet zugeordnet wird und diese 
nacheinander als 3x1-Vektoren mit der Schlüsselmatrix multipliziert werden. Unsere erste Lösung (Verschluesselung1) gab 
zu Anfang nur die ersten drei Buchstaben verschlüsselt wider. Da die Ausgabe als Vektoren erfolgte, mussten diese 
anschließend noch manuell zurück in Buchstaben umgewandelt werden.<br> 

![Sreenshot 25](https://github.com/jasmin-jarecki/Projekt-Kryptografische-Verfahren/blob/master/Berichtbilder/Screenshot%20(25).png)

Durch Einfügen einer Schleife, die solange lief, bis die Zählvariable größer der Anzahl der Buchstaben in der Eingabe ist,
kann die Verschlüsselung für alle Buchstaben vorgenommen werden, solange die Anzahl der Buchstaben der Eingabe durch drei
teilbar ist.
![Screenshot 24](https://github.com/jasmin-jarecki/Projekt-Kryptografische-Verfahren/blob/master/Berichtbilder/Screenshot%20(24).png)

Auch hier müssen die ausgegebenen Vektoren manuell zurück in Buchstaben umgewandelt werden. Zudem werden alle
Zeichen, die nicht im definierten Alphabet vorkommen, in der Verschlüsselung nicht berücksichtigt. Somit muss bei der 
Eingabe darauf geachtet werden, dass beispielsweise Umlaute oder andere Sonderbuchstaben mit im Alphabet vorkommenden 
Zeichen ersetzt werden.<br>
Die Entschlüsselung, die in Aufgabe 2 betrachtet wird, bereitete allerdings mehr Probleme. Wieder müssen 3x1-Vektoren mit 
einer Matrix, nämlich der inversen Matrix zur zuvor genutzten Schlüsselmatrix, multipliziert werden. Allerdings ist es
bisher nicht gelungen die verschlüsselten Texte wieder zu entschlüsseln. Die Überprüfung der inversen Matrix, indem sie mit
der zugehörigen Matrix multipliziert wird, was die Einheitsmatrix ergeben müsse, zeigt an drei Stellen leichte Abweichungen
von der Einheitsmatrix.
![Screenshot 15](https://github.com/jasmin-jarecki/Projekt-Kryptografische-Verfahren/blob/master/Berichtbilder/Screenshot%20(15).png)

So kann man vermuten, dass durch die Multiplikation mit der inversen Matrix abweichenden Vektoren
ausgegeben werden. <br />
Zuletzt gelangten wir zum RSA-Verfahren. Hierbei kamen die Schwierigkeiten bei der Generierung der Schlüssel für die Ver- 
und Entschlüsselung zutage. Die erste Herausforderung ergab sich mit der Implementierung des Euklidischen Algorithmus', mit 
dem der größte gemeinsame Teiler zweier Zahlen berechnet werden soll. Mit dessen Hilfe können die Bedingungen für den 
öffentlichen Schlüssel e erfüllt werden. Da die Mathematik, die hinter dem privaten Schlüssel d steht, uns noch nicht ganz
klar wurde, konnen wir dessen Erzeugung nicht implementieren.
<br />
Durch die Überarbeitung, mit zusätzlichen, weiteren Kommentaren, sowie das Resumieren und Auswerten der jeweiligen 
Verfahren gelangen wir zu dem Schluss, das richtige Projekt gewählt zu haben und sind zufrieden mit der entstandenen Arbeit.


### 4. Zusammenfassung

In diesem Projekt über kryptographische Verfahren ist es uns gelungen, uns erfolgreich mit verschiedenen Verfahren auseinanderzusetzen und sie so nachvollziehen und anwenden zu lernen. Unsere Erwartung für dieses vorgeschlagene Projekt, dass das interessante Thema dadurch uns näher gebracht wird, ist somit gelungen und hat uns in unserem Programmierverständnis durchaus vorangebracht. So galt es, die mathematischen Verschlüsselungskonzepte in einen ansprechenden Code zu formen. Besonders dieser Punkt hat den Reiz dieses Projektes ausgemacht.

### 5. Literatur

(1) https://www.scai.fraunhofer.de/content/dam/scai/de/documents/Mediathek/Mathematik%20f%C3%BCr%20die%20Praxis/rsa_skript_und_arbeitsblaetter.pdf (06.03.2018) <br>
(2) http://www.deutschlandfunkkultur.de/codes-und-chiffren.950.de.html?dram:article_id=135754 (06.03.2018)
(3) https://de.wikipedia.org/wiki/Hill-Chiffre (27.03.2018)<br>
(4) http://www.inf.fh-flensburg.de/lang/krypto/protokolle/rsa.htm (06.03.2018)<br>
(5) https://www.cs.uni-potsdam.de/ti/lehre/06-Kryptographie/slides/slides-06.pdf (06.03.2018)
