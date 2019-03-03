# Übersicht: 04.02.2019

## Search
- Wichtig ist hier die **Tree Search**
- Unser Entscheidungsprzess ist **deterministisch**, also "unfrei"
- Projiziert auf ein Spiel ist das Gegenüber/der Gegner nicht deterministisch, daher haben wir ihn durch 
einen deterministischen Gegner ersetzt. Dieser Gegner war Min, als wir über MiniMax geredet haben (der böseste mögliche Gegner). 

Im Zweiten Teil der Vorlesung haben wir das propabilistisch analysiert

## Propabilistic
- Wir haben genau das gleiche gemacht wie bei den Entscheidungsprozessen, nur im Propabilistischen.
- Die propabilistischen Formulierungen, die dabei rauskamen, waren (debug? #TODO: nachschauen!) Entscheidungen 
- Markow Entsvcheidungsprozesse (MDPs)
- Eine bestimmte Entscheidung läuft beim deterministischen einen bestimmten Pfad den Baum herunter. 
Den Baum haben wir in der Modellierung ersetzt durch den **Markow Entscheidungsprozess**, durch diesen propabilistischen Prozess.
- Das heißt bezüglich der Algorythmik, dass eine Baumsuche durch dynamisches Progammieren ersetzt wurde.

## Reinforcement Learning
- Hier betrachten wir die Umwelt nicht nur propabilistisch, wir kennen die Umwelt nicht einmal. 
- Das heißt, der Agent kennt die Umwelt gar nicht, das heißt die einzige Chance, mit der Umwelt umzugehen, ist die Umwelt zu explorieren. - Das nennt sich **Reinforcement Learning**
- Methodisch passiert hierbei folgendes: Aus dynamischem Programmieren mit einem Modell der Welt (Sie nehmen eine Wertefunktion, die Ihnen die optimale Strategie beschreibt. Die Wertefuntion ist rekursiv aufgebaut und sie können zurückiterieren und so die optimale Entscheidung treffen) wird **Q-Learning** oder ältere Formen wie TD-Learning oder SARSA.
Methodisch ist es wichtig zu verstehen, dass wenn ich ein Modell, das ich kenne, stochastisch mache indem ich es ersetze durch Daten, hierbei Q-Learning herauskommt.

Telegram MEMO @ 03:39
