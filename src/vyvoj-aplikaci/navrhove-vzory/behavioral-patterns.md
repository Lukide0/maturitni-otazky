# Behavioral patterns

## Memento

Umožňuje nám vrátit (undo) předchozí stav i bez přístupu k implementaci objektu. V podstatě je to takový snapshot.

Příkladem může být undo v editoru.

**Problém:**

![](./images/behavioral-patterns-momento-problem.png)

**Řešení:**

![](./images/behavioral-patterns-momento-solution.png)

## Observer

Umožňuje informovat objekty, které chtějí být informovány (subscribed), o provedení nějaké akce.

Tento pattern můžeme znát také pod názvy Event-Subscriber nebo Listener.

**Problém**:

- čekání na nový produkt
- buď posíláme informaci nikomu nebo všem zákazníkům

![](./images/behavioral-patterns-observer-problem.png)

**Řešení**:

- vytvoření objektu, který bude obsahovat všechny odběratele

![](./images/behavioral-patterns-observer-solution.png)

## Chain of Responsibility

Umožňuje předávat požadavky řetězci zpracovatelů (handlers). Zpracovatel musí buď požadavek zpracovat nebo poslat dalšímu zpracovateli.

![](./images/behavioral-patterns-chain-of-responsibility.png)

**Problém**:

- vyřešení požadavku na objednávací systém

![](./images/behavioral-patterns-chain-of-responsibility-problem.png)

**Řešení**:

- vytvoření řetězce zpracovatelů

![](./images/behavioral-patterns-chain-of-responsibility-solution.png)
