# Übersicht: 04.02.2019

## Mitschrieb zum Schaubild 
### Search
- Wichtig ist hier die **Tree Search**
- Unser Entscheidungsprzess ist **deterministisch**, also "unfrei"
- Projiziert auf ein Spiel ist das Gegenüber/der Gegner nicht deterministisch, daher haben wir ihn durch 
einen deterministischen Gegner ersetzt. Dieser Gegner war Min, als wir über MiniMax geredet haben (der böseste mögliche Gegner). 

Im Zweiten Teil der Vorlesung haben wir das propabilistisch analysiert

### Propabilistic
- Wir haben genau das gleiche gemacht wie bei den Entscheidungsprozessen, nur im Propabilistischen.
- Die propabilistischen Formulierungen, die dabei rauskamen, waren (debug? #TODO: nachschauen!) Entscheidungen 
- Markow Entsvcheidungsprozesse (MDPs)
- Eine bestimmte Entscheidung läuft beim deterministischen einen bestimmten Pfad den Baum herunter. 
Den Baum haben wir in der Modellierung ersetzt durch den **Markow Entscheidungsprozess**, durch diesen propabilistischen Prozess.
- Das heißt bezüglich der Algorythmik, dass eine Baumsuche durch dynamisches Progammieren ersetzt wurde.

### Reinforcement Learning
- Hier betrachten wir die Umwelt nicht nur propabilistisch, wir kennen die Umwelt nicht einmal. 
- Das heißt, der Agent kennt die Umwelt gar nicht, das heißt die einzige Chance, mit der Umwelt umzugehen, ist die Umwelt zu explorieren. - Das nennt sich **Reinforcement Learning**
- Methodisch passiert hierbei folgendes: Aus dynamischem Programmieren mit einem Modell der Welt (Sie nehmen eine Wertefunktion, die Ihnen die optimale Strategie beschreibt. Die Wertefuntion ist rekursiv aufgebaut und sie können zurückiterieren und so die optimale Entscheidung treffen) wird **Q-Learning** oder ältere Formen wie TD-Learning oder SARSA.
- Es ist wichtig zu verstehen, dass wenn ich ein Modell, das ich kenne, stochastisch mache indem ich es ersetze durch Daten, hierbei Q-Learning herauskommt.

*Der Agent, der eine Entscheidung treffen soll hat keine Ahnung von der Umwelt, er kann nur mit der Blackbox interagieren. Die Blackbox gibt nur einen Reward für die Aktion aus.*

*Es ist eine stochastische Variante von dynamischem Programmieren*

### Constraint Satisfaction Problem
- Auf den ersten Blick würde man denken es hat nichts mit den ersten beiden Punkten zu tun. Das CSP ist primär ein Problem über nur einzige Entscheidung, und zwar "eine Karte anzufertigen oder alle Variablen zu beziffern". 
- Das CSP ist im Grunde genommen nicht sequenziell sondern per Definition ein Problem wo man sagt: "Geben sie mir eine Lösung!" und die Lösung ist ein assignment zu allen Variablen, aber um eine Entscheidung zu finden ist der Standardansatz das Sequenzialisieren - **sequential assignment**. 
- Das mag zwar nicht wichtig erscheinen aber es ist ein ziemlich konzeptioneller Punkt, denn anfangs ist es nicht klar, dass man das tun muss. Es gäbe auch andere Methodiken, die eher auf (parallelen) Optimierungs- oder Interferenzprozessen basieren, aber der Standardansatz ist, das Problem sequenziell zu zerlegen. Das bedeutet, dass man zum Beispiel Werte der Karte sequenziell zuweist. Hier ist die Lösung **Backtracking** und **Treesearch**. 
- Methodisch macht man dann Constraint Propagation, was sehr eng mit dynamischem Programmieren verwandt ist, weil bei CP die Funktion, mit der wir jetzt die Variablen festlegen, die Indikatorfunktion ist, die aussagt welche Belegungen überhaupt noch erlaubt sind. 
- Die Constraint Satisfaction nutzt die Constraints der benachbarten Variablen um die Belegungen aus dem Raum der möglichen Werte herauszustreichen, um herauszufinden welche Variablen für dieses Feld denn noch möglich sind. Diese Propagation ist sehr ähnlich zum dynamischen Programmieren.

### Graphical Models
- Message parsing, insbesondere auf Bäumen 
- "Loopy"
- Es gibt auch andere Möglichkeiten, Wahrscheinlichkeiten zu schätzen, wenn der Graph nicht als Baum darstellbar ist
- Als Spezialfall: HMMs
- Wichtig ist: Man merkt, das (hinbug??) Modelle ein Spezialfall sind von graphischen Modellen ist
- Von der Problemstellung sind graphische Modelle nichts anderes als constraint satisfaction probleme, aber propabilistisch. Dementsprechend ist von der Methodik her Message Parsing nichts anderes als eine propabilistische Version von Constraint Propagation, wo bei CP wir Indikatiorfunktionen hatten, die zu jeder Domain sagen, ob ein Wert möglich ist oder nicht (Eine richtige binäre Funktion mit nur zwei möglichen Outputs), und das übersetze ich in Messages, in reelle Zahlen, die man aufmultipliziert um rauszufinden was denn wahrscheinlich vorliegt. 

### Machine Learning
*war fast nicht in der Vorlesung

- Machine Learning als Spezialfall von graphischen Modellen betrachtet, also als propabilistische Interferenz

``` 
            P(D|f) * P(f)       
P(f|D) =  ----------------- 
                P(D)
``` 
- Machine Learning kann genutzt werden um bei Reinforcement Learning die value- oder Q-Funktion zu bestimmen oder ein `P(s'|s,a)` oder `R(s|a)` zu lernen

## Überblick:
Type          | sequential Decisions   | Interference
------------- | ---------------------- | ------------  
deterministic | Search                 | (Constraint Propagation?)
propabilistic | Propabilistic          | Graphical Models
learning      | Reinforcement Learning | Machine Learning


## Hinweise zum Skript
- Generell ist das Inhaltsverzeichnis wichtig


Telegram Memo @ 31:00
