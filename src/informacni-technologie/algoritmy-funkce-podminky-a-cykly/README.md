# Algoritmy, funkce, podmínky a cykly

## Algoritmy

- návrh řešení
  - jde přirovnat k receptu
- jde o posloupnost nějakých elementárních kroků
- definice
  - musí bát popsaný
  - vždy musí přinést výsledek
  - musí být složen z jednoduchých instrukcí
    - dokážeme bez otázek či přemýšlení provést
  - musí být jasný postup
    - jaká instrukce následuje
    - vždy musí bát jasné, co dělat dál
- vlastnosti
  - elementární
    - skládá se z konečného počtu jednoduchých kroků
  - deterministický
    - po každém kroku lze rozhodnout, zda proces skončil
  - konečný
    - má konec
  - hromadný
    - lze jej použít prořešení více podobných úloh
- základní komponenty
  - posloupnost příkazů
  - podmínky
  - cyklus
- zápis
  - grafický zápis
    - vývojový diagram
      - Šilhán - Vlk, Ovce, Zelí
    - struktogram
  - struktorovaný přirozený jazyk
    ```
      1. Tiskni: Zadej poloměr
      2. Čti: r
      3. Jestliže je r < 0, krok 7
      4. o = 2\*3,14*r
      5. Tiskni: Obvod je o
      6. Konec
      7. Tisk: Chyba: Polomer je záporný
      8. Konec
    ```
  - pseudojazyk
    - využíváme syntax prog. jazyka, ale příkazy píšeme větami
      - často volnou formou
    - fizzbuzz
      - fortran
        ```
        program fizzbuzz
        Do i = 1 to 100
          set print_number to true
          If i is divisible by 3
            print "Fizz"
            set print_number to false
          If i is divisible by 5
            print "Buzz"
            set print_number to false
          If print_number, print i
          print a newline
        end do
        ```
      - C
        ```
        void function fizzbuzz {
          for (i = 1; i <= 100; i++) {
            set print_number to true;
            If i is divisible by 3 {
              print "Fizz";
              set print_number to false; }
            If i is divisible by 5 {
              print "Buzz";
              set print_number to false; }
            If print_number, print i;
            print a newline;
          }
        }
        ```
- techniky návrhu algoritmu
  - rozděl a panuj
    1. rozdělení problému na menší
    2. rekurzivní volání sama sebe na menší problém
    3. sestavení výsledného řešení
  - hrubá síla
    - všechna možná řešení
    - tic-tac-toe
  - hladový algoritmus
    - vybírá se aktuální optimální řešení
    - nezajímají nás následky
    - nezaručuje optimální výsledek
  - dynamické programování
    - podobné k rozděl a panuj
    - používají výsledky minulého běhu
    - problém je rozdělen na několik podproblémů
      - výsledek z každého podproblému si ukládá
    - např. fibonacciho posloupnost
  - backtracing
    - rekurzivní řešení
    - algoritmus zpětného sledování řeší dílčí problém a pokud se mu nepodaří problém vyřešit, zruší poslední krok a začne znovu hledat řešení problému
    - [ukázka](https://rosettacode.org/mw/images/9/90/Mazesolve_bbc.gif)
- druhy
  - rekurzivní
    - volají sámi sebe
    - používá se systémový zásobník => vyžaduje více paměti
  - pravděpodobnostní
    - některá rozhonutí provádějí náhodně
  - paralelní
    - algoritmus lze rozdělit na více úloh, které mohou běžet na dalším vlákně
  - genetické
    - napodobování biologických evolučních procesů
  - heuristické
    - nehledají přesné řešení
    - pokud nemáme dostatek zdrojů

## Funkce

- část programu, kterou lze opakovaně volat
- funkce mohou
  - mít parametry
  - vracet hodnotu
    - pokud nevrací jedná se o procedůru
- funkce lze volat rekurzivně
- většina prog. jaz. dovoluje mít výchozý hodnoty parametrů
  - nemusíme tedy je zadávat
  - parametry s výchozý hodnotou musí být za parametry bez hodnoty
- funkce mohou v některých jazycích být asynchroní

## Podmínky

- větvení programu
- je proveda určitá akce (blok kódu), pokud jsou všechny podmínky splněny
- podmínka může být
  - pravda (true)
  - nepravda (false)
- každý jazyk má lehce jinou syntaxy podmínek
- **if**
  - pokud je podmínka true
  - nemusí mít za sebou else
- **else if**
  - následuje za if
  - pokud byla první podmínka false, tak se provede kontrola této
- **else**
  - následuje za if
  - pokud je podmínka false
- **switch**
  - většina jaz. převede switch na několik if
  - obsahuje ramena (case)
    - mohou být seskupené
    - musí pokrývat všechny možnosti
    - musí obsahovat break příkaz
  - je zde rameno default
    - vše co nebylo zachyceno rameny

## Cykly

- je to blok kódu, který se opakuje po dobu, kdy je podmínka splněna
- existují příkazy
  - break
    - zastavení cyklu
  - continue/pass
    - přeskočení
- typy
  - **for**
    - iterátor
  - **while**
  - **Do while**
  - **Do until**
    - někde
