# Projekt-Kryptografische-Verfahren

#### **Inhaltsverzeichnis**
[1. Einleitung](#Einl)

[2. Aufgaben](#Auf)

[2.1 Alphabetisch Einordnen](#Alph)

[2.2 Caesar-Verschlüsselung](#Cae)

[2.3. RSA-Verschlüsselung](#RSA)

[3. ...](#...)

[4. Zusammenfasssung](#Zusam)

### Einleitung<a name="Einl"></a>

Das Projekt befasst sich mit einfachen Kryptographischen Verfahren zur Ver- und Entschlüsselung von Daten insbesondere Texten. Die einzelnen Verfahren sollen zunächst beschrieben und erklärt werden. Wie wurden sie entwickelt, wie funktionieren sie, welche Vor- un Nachteile gibt es und welche Anwendungen finden sie?
Des Weiteren soll gezeigt werden, wie diese in Python-Programme umgesetzt werden können. Dafür werden für ausgewählte Methoden Programme zur Ver- und Entschlüsselung von Texten geschrieben und der Verlauf in diesem Bericht dokumentiert. Die Programme werden zusätzlich hier verlinkt und als Python-Dateien im Repository zu finden sein. 


### 2. Aufgaben<a name="Auf"></a>

#### 2.1 Alphabetisch Einordnen<a name="Aph"></a>

s. Python-Skript "Alphabetisch Einordnen"

Die Verschlüsselung eines Textes, indem die Buchstaben des Eingabetextes in alphabetische Reihenfolge gebracht werden, ist
in Python ein relativ einfach zu programmierendes Verfahren. Der eingegebene Text wird so sortiert, dass zunächst die 
Großbuchstaben in alphabetische Reihenfolge gebracht werden und anschließend die Kleinbuchstaben, dabei werden die
ursprünglichen Wortlängen beibehalten.<br />

In Python kann diese Verschlüsselungsmethode wiefolgt umgesetzt werden. Zunächst wird eine Liste mit den Elementen des
Alphabets als Groß- und Kleinbuchstaben definiert.<br>

[Bild 1] <br />

Anschließend wird die Verschlüsselungsfunktion definiert mit den Argumenten 'Text', an dessen Stelle der zu verschlüs-
selnde Text geschrieben wird, und 'Alphabet', wo das zu nutzende Alphabet eingetragen wird.
Die Funktion beginnt damit, dass der als string eingegebene Text zu einer Liste K gemacht wird, in der die einzelnen 
Elemente aus den Buchstaben, Leer- und Satzzeichen bestehen.<br>
Im Anschluss wird eine zweite Liste K2 erstellt, die nur noch die Buchstaben enthält.
Diese Liste wird im Folgenden dann, wie oben beschrieben, sortiert. Im letzten Schritt sollen die Leer- und Satzzeichen in
die verschlüsselte Nachricht in einer dritten Liste K3 eingefügt werden. Dies gelingt, indem die Elemente der ersten Liste
K betrachtet werden. Sind diese auch Elemente des definierten Alphabets, werden sie durch die entsprechenden Elemente aus
der sortierten Liste K2 ersetzt, ist es aber ein Leer- oder Satzzeichen, so werden diese direkt übernommen.<br> 
Diese Liste wird letztlich von der Verschlüsselungsfunktion aus string ausgegeben.<br />

In Python3 ist es durch die list.sort() Methode sehr leicht ein Programm für eine Verschlüsselung zu schreiben. Eine
Entschlüsselung hingegen ist nicht so einfach und je länger die verschlüssele Botschaft wird, desto schwieriger wird es 
auch diese zu entschlüsseln. <br>
Da es wenige Anhaltspunkte gibt, nämlich Wortlängen, Anzahl der Großbuchstaben und gegebenenfalls auf bestimmte Sprachen
hindeutende Zeichen, macht es eine Entschlüsselung schwer. Dafür müsste man jede mögliche Kombination der einzelnen 
Buchstaben ausprobieren und prüfen, welche Sinn ergeben. In manchen Fällen ist es zudem möglich, dass mehrere Kombina-
tionen sinnvoll sind.


### 2.2 Caesar-Verschlüsselung<a name="Cae"></a>

Die Caesar-Chiffre funktioniert, indem jedem Buchstaben a mithilfe eines geheimen Schlüssels d ein
anderer Buchstabe b zugeordnet wird.
b = a+c mod 26.
Diese Art der Verschlüsselung wurde bereits von dem römischen Feldherr Julius Caesar verwendet,
und trägt deshalb seinen Namen.
Bei der Caesar-Verschlüsselung ergeben sich jedoch einige Nachteile, die im Folgenden weiter
betrachtet werden sollen.
Da das Alphabet nur 26 Buchstaben besitzt, gibt es nur 25 verschiedene Schlüssel, um einen Text zu
ver- bzw. entschlüsseln.
Selbst wenn man jedem Buchstaben einen beliebigen anderen zuordnen würde, ergäben sich zwar
26! Möglichkeiten, doch wesentliche Probleme bleiben die gleichen. Hier ist zu nennen, dass man
zum Ver- und Entschlüsseln denselben Schlüssel benötigt. Des Weiteren variiert die Häufigkeit der
vorkommenden Buchstaben bei typischem Sprachgebrauch je nach Sprache. So sind im Deutschen
Buchstaben wie e und n durch ihre deutliche Präsenz zu idetifizieren.


## ROT13-Verfahren

Die ROT13-Chiffre funktioniert genauso, wie die Caesar-Verschlüsselung, nur das der Schlüssel b = 13 ist. 

Empfänger muss genaues Alphabet kennen
nicht unbedingt für jede Sprache anwendbar wegen fehlender Zeichen

eigene Probleme: 'ß' einbinden

### 3. RSA-Verschlüsselung<a name="RSA"></a>

Das von Rivest, Shamir und Adelson 1980 patentierte Verschlüsselungsverfahren ist heute das
weitgenutzte Verfahren der Verschlüsselung, es findet Anwendung in der Internet- und
Telefoninfrastruktur, sowie der E-Mail Verschlüsselung und vielem mehr.
Bei dem RSA-Verschlüsselungsverfahren handelt es sich um ein asymmetrisches
Verschlüsselugsverfahren. Bei diesem Verfahren wird ein Klartext m mit dem public key des
Empfängers verschlüsselt, der Empfänger kann den Geheimtext c anschließend mit dem private key d
entschlüsseln. Das Verfahren basiert auf der Schwierigkeit, die Verschlüsselung c=m^e mod n zu
lösen.
c wird wie folgt berechnet
c = m^e mod n,
wobei gilt
n = p q.
Für die beiden Primzahlen p und q gilt, dass deren Entschlüsselung mithilfe von n durch Faktorisieren
zu rechenaufwendig ist, n groß genug ist. Hierbei geht es heutzutage um Größenordnungen von
mehreren hundert bit.
Für e gilt
ggt(e,phi(n)) = 1,
wobei phi(n) = (p-1) (q-1).
Phi(n) gibt die Anzahl der Teilerfremden Zahlen von n, die kleiner als n sind, an.
Zum Entschlüsseln wird der private Schlüssel d benötigt
d*e mod phi(n) = 1, d.h.
d*e = k mod phi(n)+1,
wobei k Element der natürlichen Zahlen ist.
Nach dem Satz von Euler folgt daraus
m^k^phi(n) m mod n = m.
Um den Geheimtext c zu verschlüsseln, geschieht folgendes
c^d mod n = m^d m^-d mod n
= m^k^phi(n) m mod n
= m.
Um den Geheimtext c als Dritter zu bestimmen, muss man entweder d aus e oder Phi bestimmen.
Dies ist alles recht ähnlich in der rechnerischen, praktischen Durchführbarkeit der Bestimmung von p
und q aus n. Ebenfalls die e-te Wurzel aus c zu berechnen scheitert am Rechenaufwand.

