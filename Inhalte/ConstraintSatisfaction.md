# Constraint Satisfaction Problem

## Aus Zusammenfassung

- Auf den ersten Blick würde man denken es hat nichts mit den ersten beiden Punkten zu tun. Das CSP ist primär ein Problem über nur einzige Entscheidung, und zwar "eine Karte anzufertigen oder alle Variablen zu beziffern".
- Das CSP ist im Grunde genommen nicht sequenziell, sondern es ist nach einer Komplettlösung gefragt.
- Um eine Entscheidung zu finden ist der Standardansatz das Sequenzialisieren - **sequential assignment**.
- Es gäbe auch andere Methodiken, die eher auf (parallelen) Optimierungs- oder Interferenzprozessen basieren, aber der Standardansatz ist, das Problem sequenziell zu zerlegen.
- Das bedeutet, dass man zum Beispiel Werte der Karte sequenziell zuweist. Hier ist die Lösung **Backtracking** und **Treesearch**.
- Methodisch macht man dann Constraint Propagation, was sehr eng mit dynamischem Programmieren verwandt ist, weil bei CP die Funktion, mit der wir jetzt die Variablen festlegen, die Indikatorfunktion ist, die aussagt welche Belegungen überhaupt noch erlaubt sind.
- Die Constraint Satisfaction nutzt die Constraints der benachbarten Variablen um die Belegungen aus dem Raum der möglichen Werte herauszustreichen, um herauszufinden welche Variablen für dieses Feld denn noch möglich sind.
- Diese Propagation ist sehr ähnlich zum dynamischen Programmieren.

## Inferenz

**Given some pieces of information on some things (observed variabes, prior, knowledge base) what is the implication (the implied information, the posterior) on other things (non-observed variables, sentence)**

Entscheidungen können als Inferenz betrachtet werden: Das Wissen, das wir über das Spiel haben ist die Prior, unsere Entscheidung die Posterior.

Wir behandeln in dieser Vorlesung:

- "Deterministische" Inferenz in CSPs
- Probabilistische Inferenz in [Graphischen Modellen](GraphicalModels.md)
- Logische Inferenz in "propositional & FO logic"

## Generelles zu CSP

-

## Prüfungsrelevant ist vor Allem

- Backtracking und die Heuristiken, die wir gelernt haben.
- "Sie sind in einer gegebenen Situation, die sie mit Backtracking/CSP lösen. Welche Variablen picken sie sich raus?" --> testet Variable Order (Min. Remaining Value etc.)
- Constraint Propagation: "Hier sind die Variablen, die sie kennen und die Constraints, die sie erfüllen, angenommen Sie führen jetzt Constraint Porpagation aus ohne Backtracking. Wohin konvergiert das? Was sind die verbleibenden Domains und Wertelängen?"
