# Programovací jazyky a zpracování zdrojového kódu

## programovací jazyk

- je to komunikační nástroj mezi programátorem a počítačem
- jejich počet se každým rokem zvyšuje
- **turing-complete (Turingovská úplnost)**

  - musí umět vše co umí turing machine (Turingovský stroj)
    - hypotetický stroj s nekonečnou páskou, na které jsou napsány 1 a 0, a hlavičkou, která umí zapisovat a číst
    - pohybuje hlavičku do leva a do prava
  - **musí umět cykly, podmínky a operace**

- sémantika
  - může být definovaná
    - pomocí specifického dokumentu
      - C má ISO standard dokumenty
      - JavaScript má ECMAScript
    - referenční implementace
      - nedodržují formy
      - předchází standardu
      - prototyp
    - kombinace
      - základ standard
      - rozšíření ref. impl.
- má svoji gramatiku/syntax
  - definuje strukturu výrazů
  - neověřuje
    - validitu typů
    - validitu výrazu
  - např. `var x = new Person();`, `var x = 1 * "text" / "text";`
- mají svojí sémantiku
  - ověřuje typy
    - `var x = new Person();`
      - error Person neexistuje
  - ověřuje zda li je výraz validní
    - `var x = 1 * "text" / "text";`
      - error string nelze převést na int
- dělí se

  - dle míry abstrakce

    - časem se mění jaké jsou low level a které high level
      - např. C bylo High level, dnes se řadí Low level, ale jsou zde spory
        - pokud programujeme v assembly, tak je pro nás High level
        - pokud programujeme v C#, tak je pro nás Low level

    | Typ        | Srozumitelnost | Závislost na HW/OS | Překlad                 | Rychlost | Debug         | Příklady               |
    | ---------- | -------------- | ------------------ | ----------------------- | -------- | ------------- | ---------------------- |
    | High level | :smiley:       | Ne                 | Kompilátor, Interpreter | :snail:  | :innocent:    | C#, PHP, Python, Java  |
    | Low level  | :alien:        | Ano                | Assembler               | :car:    | :smiling_imp: | Assembly, Machine code |

    - High level
      - lépe srozumitelný
    - Low level

  - dle způsobu překladu
    - kompilované
    - interpretované
  - dle použití
    - univerzální
    - doménově specifické
      - HTML

## Zpracovaní kódu

- **interpreter**
  - provádí řádku po řádce
  - přímo provádí zdroj. kód
  - typy
    - přímo spouští
      - unix shell interpreter
    - přeloží na mezikód
      - předkompilovaný kód
      - uložího a při příštím spuštění ho spustí
      - JIT
        - PHP, Python
  - rychlejší zpracování
  - pomalejší program
  - potřebuje více paměti
  - **je potřeba mít interpreter**
    - nelze spustit Python bez interpreteru
- **kompilátor**
  - převádí celý kód
    - výsledek je
      - spustitelný soubor (.exe)
        - je závislý na platformě
          - nelze spustit binárku pro windows na linuxu a obráceně
            - ! lze, ale je nutné mít nainstalovaný nástroje pro jejich spuštění
              - není optimální
      - knihovna
        - statická (.so)
          - program, který jí potřebuje, tak během kompilace je přidána do spustitelného souboru
        - dynamická (.dll)
          - program, který jí potřebuje, tak během spuštění si jí načte
            - např. error chybý dynamická knihovna
  - není potřeba mít kompilátor ke spuštění programu
  - vygenerovaný soubor je většinou optimalizovaný
  - může kompilovat jiného nižšího jazyka
    - TypeScript
  - může kompilovat do vyššího jazyka
    - dekompilátor
  - typy
    - jednoprůchodový
      - není optimalizovaný dostatečně
      - ihned generuje strojový kód
      - rychlé
    - víceprůchodový
      - předává výsledky z průchodu dalšímu průchodu
        - optimalizace
      - pomalé
      - menší vygenerovaný soubor
      - fáze
        1. Front-end
           - syntax a sémantika
        2. Middle-end
           - optimalizace
        3. Back-end
           - překlad na cílový jazyk (machine code, js, ...)
