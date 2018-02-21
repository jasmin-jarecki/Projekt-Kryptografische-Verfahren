# Projekt-Kryptografische-Verfahren

#### **Inhaltsverzeichnis**
[1. Einleitung](#Einl)

[2. Caesar-Verschlüsselung](#Cae)

[3. ...](#...)

[4. Zusammenfasssung](#Zusam)

### Einleitung<a name="Einl"></a>

Das Projekt befasst sich mit einfachen Kryptographischen Verfahren zur Ver- und Entschlüsselung von Daten insbesondere Texten. Die einzelnen Verfahren sollen zunächst beschrieben und erklärt werden. Wie wurden sie entwickelt, wie funktionieren sie, welche Vor- un Nachteile gibt es und welche Anwendungen finden sie?
Des Weiteren soll gezeigt werden, wie diese in Python-Programme umgesetzt werden können. Dafür werden für ausgewählte Methoden Programme zur Ver- und Entschlüsselung von Texten geschrieben und der Verlauf in diesem Bericht dokumentiert. Die Programme werden zusätzlich hier verlinkt und als Python-Dateien im Repository zu finden sein. 


### 2. Caesar-Verschlüsselung<a name="Cae"></a>

Die Caesar- oder ROT(n)-Verschlüsselung ist ein Verfahren zur Verschlüsselung von Texten, das auf Gaius Julius Caesar zurückzuführen ist. Der römische Kaiser nutzte dieses Verfahren ebenfalls, um Briefe und Nachrichten zu chiffrieren.
Diese Methode beruht darauf, dass das Alphabet um n Stellen verschoben wird, sodass jedem Buchstaben ein neuer zugeordnet wird. Der Schlüssel zum decodieren des Textes ist dann die Zahl n, die verrät, um wieviele Stellen das Alphabet verschoben wurde. Dabei ist zu beachten, dass bereits ab Null gezählt wird. Wird das Alphabet um 13 Stellen verschoben, so lautet der Schlüssel 12.

## 2.1 Alphabetisch Einordnen

