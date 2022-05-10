# Metodiky vývoje software

- koordinace vývoje SW na kterém pracují menší i větší támy
- vývoj SW se dělí do jednotlivých fází
  1. způsob dělení
  - definování požadavků
  - vytvoření konceptuálního modelu
  - vytvoření implementačního modelu
  - implementační zavedení
  - testování softwaru
  - udržování systému a provoz
  - stažení systému z užívání
  2. způsob dělení
  - akvizice
  - vývoj
  - provoz
  - údržba
  - vyřazení
- **důvod použití metodiky**

  - zjednodušení a koordinace vývoje

- **metoda**
  - návod či postup získávání poznatků
  - definuje jak dosáhnout požadovaného cíle
  - odpovídá na otázky typu JAK
- **metodika**
  - souhrn doporučených praktik a postupů, pokrývajících celý životní cyklus vytvářené aplikace
  - odpovídá na otázky typu CO, KDY, KDO, PROČ

## Modely

- **vodopád**
  - klade důraz na plánování, termíny a časový rozvrh prací
  - v praxi se příliš nepoužívá
    - je spíše teoretický
  - etapy bez cyklických návratů zpět
  - faze
    - požadavky
    - návrh
    - implementace
    - verifikace
    - údržba
  - výhody
    - jednoduchý z hlediska řízení
    - při stálých požadavcích, nejlepší struktura výsledného produktu
  - nevýhody
    - zákazník není schopen přesně stanovit veškeré požadavky předem
    - není flexibilní
    - nedostatky jsou odhaleny příliš pozdě
- **spirála**
  - odvozen od vodopádu
  - pokud u spirálového modelu chceme přejít do další fáze (etapy), je nutné provést důslednou analýzu možných problémů a rizik
  - analýza rizik je prováděna v každém cyklu
  - vývoj je rozdělen na menší části
  - umožňuje během vývoje upřesnění a rozpracovat jednostlivé detaily
  - fáze
    - analýza
      - cíle, rozsah cyklu, alternativy
    - vyhodnocení
      - vyhodnocení alternativc, řešení rizik a jejich identifikace
    - vývoj
    - plánování
      - plánování další iterace/cyklu
      - podmínky úspěšného dalšího cyklu
  - výhody
    - vhodné i pro velké projekty
  - nevýhody
    - komplikovaný
    - zákazník vidí až konečný výsledek
- **výzkůmník**
  - uváděn spíše jako negativní případ přístupu k vývoji IS
  - jeho použití svědčí o tom, že řešitelský tým neovládá dobře danou problematiku
- **prototyp**
  - plánovaný a řízený inkrementální přístupu k vývoji IS
  - prototyp
    - částečná implementaci produktu
    - v logické nebo fyzické formě
  - uživatelé IS se s prototypem seznamují a testují jej
    - na základě jejich připomínek je upřesňována specifikace požadavků na systém
    - prototyp je upravován a dále doplňován až do podoby výsledného systému

## Metodiky

- **Rapid Application Development (RAD)**
  - rychlý vývoj, vysocekvalitní systémy, nízké náklady
  - rozdělení vývoje na menší segmenty
  - umožnění změn během vývoje
  - velký důraz na prototypování ve všech stádiích vývoje
  - aktivní zapojení uživatelů a automatických nástrojů při vývoji
  - je vytvářena dokumentace pro snazší budoucí vývoj
- **Rational Unified Process (RUP)**
  - použitelná pro jakýkoliv rozsah projektu, ale vhodnější spíše pro rozsáhlejší projekty a větší vývojové týmy
  - klade důraz na
    - analýzu
    - design
    - plánování
    - řízení zdrojů
    - dokumentaci

### Agilní metodiky

- umožňují rychlý vývoj softwaru
- na začátku není podrobně určené zadání
- dokáže reagovat na změnu požadavků v průběhu vývojového cyklu

- **SCRUM**
  - je schopen řešit složité problémy
  - zaměřuje a spoléhá se na transparentnost, monitorování a neustálou přizpůsobivost
  - soustředí se na maximální schopnost týmu rychle dodat část s nejvyšší prioritou a reagovat na nové požadavky
  - rovozuje se tzv. sprint, nebo denní scrum
  - sprinty mají dopředu definovanou jejich délku (od 1 týdne do 1 měsíce)
  - Nejčastější délka sprintu je 1-2 týdny
- **Kanban**
  - japonsky cedule
  - tabule s několika sloupci
    - jednotlivé úkoly se postupně přesouvají
  - má tři pravidla
    - vizualizovat
    - minimalizovat čas průchodu
    - limitovat WIP (work in progress)
  - nástroj Trello
- **Extrémní programování**
  - dodává se co nejjednodušší možná verze
  - bez testování
    - jen unit testy
  - programování v páru
    - jeden píše, druhý kontroluje
    - střídají se
  - krátké cykly (hodiny až dny)
  - důležitá je
    - komunikace
    - zpětná vazba
