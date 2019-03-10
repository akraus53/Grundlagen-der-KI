# Probabilities

## Generelles aus [Zusammenfassung](Zusammenfassung.md)

- Wir haben genau das gleiche gemacht wie bei den Entscheidungsprozessen, nur im Propabilistischen.
- Die propabilistischen Formulierungen, die dabei rauskamen, waren (defakt?) Entscheidungen
- Markow Entscheidungsprozesse (MDPs)
- Eine bestimmte Entscheidung läuft beim Deterministischen einen bestimmten Pfad den Baum herunter. Den Baum haben wir in der Modellierung ersetzt durch den **Markow Entscheidungsprozess**, durch diesen propabilistischen Prozess.
- Das heißt bezüglich der Algorythmik, dass eine Baumsuche durch dynamisches Progammieren ersetzt wurde.

## Motivation

Die Umwelt ist oft nicht deterministisch sondern *stochastisch*, auch kann oft nicht die gesamte Umwelt wahrgenommen werden, wenn es zum Beispiel einen nicht-deterministischen Gegner/Agenten neben der AI gibt. Der Satz von Bayes ist fundamental für die Wahrscheinlichektisrechnung, auch bei AI.

**“Inference”** = Given some pieces of information (prior, observed variabes) what is the implication (the implied information, the posterior) on a non-observed variable?

## Generelle Wahrscheinlichkeitsrechnung

- Domain `\Omega` = z.b. `\{1,2,3,4,5,6\}`
- Probability `P(A \in \Omega) = [0,1]`
- Axiome
  - P nicht negativ
  - Additivität: `P(A) \cup P(B) = P(A) + P(B)` wenn `A \cap B = \{\}`
  - Normalisation: `P(\Omega) = 1`

### Implikationen

- `0 <= P(A) <= 1`
- `P(\{ \}) = 0`
- `A \subset  B \implies P(A) < P(B)`
- `P(\Omega /A) = 1 - P(A)`
  
### Zufallsvariablen: `X` mit `dom(X) = \Omega`

- `\forAll x \in \Omega: 0 <= P(X=x) <= 1`
- `\sum {x \in \Omega} P(X = x) = 1`

### Zufallsverteilungen

- `P(X)` ist die Wahrscheinlichkeitsverteilung aller `X \in \Omega`
- In Implementationen werden Zufallsverteilungen oft als arrays dargestellt
- Notation für Summen über ZVs: `\sum {x \in dom(X) P(X = x) = \sum {X} P(X)`  

### Joint Distributions - Vereinigungen mehrerer ZVs
  Typ|Definition
  ---:|---
Joint: | `P(X,Y)`
Marginal: | `P(X) = \sum{Y} P(X,Y)`
Conditional: | `P(X|Y) = P(X,Y) / P(Y)`

## Der Satz von Bayes

**"Knowing the conditional probability of B given A, what is the conditional probability of A given B?"**

`P(X|Y) = {P(Y|X) * P(X)} / {P(Y)} `

`posterior = likelyhood * prior / normalization`

## Mehrere ZVs

Analog folgt für n Variablen:

Typ|Definition
---:|---
Joint:|`P(X_{1:n})`
Marginal:| `P(X_1) = \sum {X_2:n} P(X_1:n)`
Conditional:| `P(X_1|X_2:n) = P(X_1:n) / P(X_2:n)`



### Prüfungsrelevant ist

- Standardpolynomsatz (?)
- Was ist eine Marginalwahrscheinlichkeit?
- Was ist eine Konditionalwahrscheinlichkeit?
- Beides auch mit 3 Variablen
- Bayessche Regeln verstehen
- "Verbundwahrscheinlichkeit"
