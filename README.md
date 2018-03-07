# Projekt-Kryptografische-Verfahren

#### **Inhaltsverzeichnis**
[1. Einleitung](#Einl)

[2. Caesar-Verschlüsselung](#Cae)

[3. RSA-Verschlüsselung](#RSA)

[4. ...](#...)

[5. Zusammenfasssung](#Zusam)

### Einleitung<a name="Einl"></a>

Das Projekt befasst sich mit einfachen Kryptographischen Verfahren zur Ver- und Entschlüsselung von Daten insbesondere Texten. Die einzelnen Verfahren sollen zunächst beschrieben und erklärt werden. Wie wurden sie entwickelt, wie funktionieren sie, welche Vor- un Nachteile gibt es und welche Anwendungen finden sie?
Des Weiteren soll gezeigt werden, wie diese in Python-Programme umgesetzt werden können. Dafür werden für ausgewählte Methoden Programme zur Ver- und Entschlüsselung von Texten geschrieben und der Verlauf in diesem Bericht dokumentiert. Die Programme werden zusätzlich hier verlinkt und als Python-Dateien im Repository zu finden sein. 


### 2. Caesar-Verschlüsselung<a name="Cae"></a>

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

## 2.1 Alphabetisch Einordnen

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

