# Objektově orientované programování (OOP)

Je to programovací paradigma jehož základní jednotkou je **objekt**, který odpovídá nějakému objektu z reálného světa (např. člověk, auto). Je to soběstačná entita, která obsahuje **atributy** a **metody**.

Paradigma je způsob, jak třídit programovací jazyky na základě jejich vlastností. Mezi nejznámější patří OOP, POP, FOP a DOP.

OOP je způsob myšlení, designu a implementace, kde klademe důraz na znovupoužitel­nost. Oproti procedurálnímu programování nespočívá jen v psaní kódu jiným způsobem, ale dokonce v uvažování jiným způsobem. Cílem je vytvářet **malé, relativně samostatné** a v různých aplikacích opakovaně použitelné jednotky.

## výhody

- snažší a rychlejší vývoj
- snadnější údržba
- menší chybovost

## nevýhody

- správa objektů zabere určité systémové prostředky

## OOP stojí na základních třech pilířích

### Zapouzdření (encapsulation)

- umožňuje znepřístupnit/skrýt některé metody a atributy třídy tak, aby zůstaly použitelné jen pro třídu zevnitř
- public, private, protected
- vidíme jen to, co tvůrce třídy zpřístupnil

### Dědičnost (inheritance)

- slouží k tvoření nových datových struktur na základě starých
- příklad:
  - Uživatel (jmeno, prijmeni, email + zmenit_email(),...)
  - Administrátor (zdědí atributy a metody uživatele + má své vlastní atributy a metody -- smazat_uzivatele())

### Polymorfismus (polymorphism)

- umožňuje implementovat (či přepsat existující) děděnou metodu u podtřídy
- díky tomuto lze volat metodu různých podtříd a nemusí nás zajímat o jakou se jedná
- příklad:
  - budeme mít třídu GeometrickyUtvar s atributem `barva` a metodou `Vykresli()`
  - u objektů čtverec a kruh budeme volat stejnou metodu `Vykresli()`, ale ta bude u ubou implementována jinak (přepíšeme defaultní implementaci)

## Pojmy

- **třída**
  - vzor, podle kterého se objekty vytvářejí
  - definuje vlastnosti a metody
  - udáva jen jaké vlastnosti bude mít každý objekt dané třídy
- **instance**
  - konkrétní objekt vytvořený ze třídy
- **metoda**
  - schopnosti, které objekt umí vykonávat
  - např. u člověka: JdiDoPrace()
- **statická metoda**
  - umožňuje volat metodu bez vytvoření instance třídy
- **abstraktní metoda**
  - je definovaná ve třídě
  - podtřídy musí tuto třídu implementovat
- **atribut**
  - vlastnosti/data objektu
  - např. u člověka: jméno a věk
  - proměnné, o kterých někdy hovoříme jako o vnitřním stavu objektu

## Další paradigmata

- **POP**
  - procedurálně orientované programování
  - program je rozdělen do menších celků (funkcí)
  - program musí obsahovat main funkci
  - např. C, Pascal, Fortran, Rust, ...
- **FOP**
  - funkcionální programování
  - snaží se zabránit měnění stavu a mutaci dat
    - neexistuje
      - deklarace proměnných
      - cykly
  - funkce můžou být parametry i vraceny
  - funkce musí vždy vracet na stejné vstupy stejný výsledek
  - založeno na výrazech
  - např. Haskell, Dart, Scala, F#, ...
- **DOP**
  - v OOP se zaměřujeme na jediný objekt, zde se zaměřujeme na uchování a zpracování dat
  - např. SQL
