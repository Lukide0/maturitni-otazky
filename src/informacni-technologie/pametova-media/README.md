# Paměťová média

- slouží k uchování dat
- **výměnné médium**
  - možno vyjmout a zasunout při běhu systému
- **Úložiště**
  - hardwarové rozhran, přes které je pamět. médium připojeno
  - mechanika disku, USB rozhraní, ...
- **dělení**
  - podle stálosti připojení
    - rezidentní
      - nelze je běžně vyjmout
      - uvnitř skříně
    - vyměnitelná
      - připojuje se vně či uvnitř skříně
      - médium lze lehce vyjmout
      - optická mechanika
  - podle způsobu přístupu k médiu
    - sekvenční
      - pro přečtení určitých dat musíme přečíst i data předchozí
      - zálohovací pásky
    - asociativní
      - adresou je klíčová hodnota ukládaná s informací
    - s přímým přístupem
      - podle adresy
        - lineární
          - jednoduchá adresa
          - např. LBA (Logical Block Addressing)
        - vícerozměrná
          - adresa je složena z více částí
          - např. CHS u HDD (Cylindr-Hlava-Sektor)
  - podle principu čtení/zápis
    - papírová média
    - magnetická a magnetooptická média
      - na principu magnetismu
      - HDD, disketa,
      - magnetooptický disk
        - záznam
          - zaměření laser. paprsku + působení magnet. pole
        - kapacita až 10 GB
    - optická média
      - využití vlastností světla
        - CD, DVD, Blu-ray
    - elektronická média
      - USB flash disky, SSD

## HDD

- velikost disku
  - v palcích
  - průměr ploten disku (1”, 2.5”, 3.5”, ...)
- kapacita disku
  - využívá se SI soustava (násobky 10)
    - `1MB = 1 000 000 B` vs `1MiB = 2^20 = 1 048 576 B`
- RPM
  - počet otáček ploten za min
- plotna
  - disk může obsahovat více ploten
  - může se na ně zapisovat z obou stran
- stopa
  - soustředná kružnice na povrchu
- sektor
  - výsek Stopy
- cylindr
  - všechny stopy se stejným průměrem přes všechny povrchy
- cluster/blok
  - nejmenší jednotka na HDD
  - pracuje s ní OS
  - 4 KB u NTFS
- jak funguje
  - čtecí a zapísová hlava
  - plotna nestále rotuje a hlava je nad ní nadnášena vzduchovým polštářem (méně než 1 mikrometr)
  - **zápis**
    - hlavou protéká el. proud
    - vytváří se magnetický tok, který ovlivňuje povrch disku
    - [typy](https://www.svethardware.cz/funkcnost-rozhrani-a-technologie-pevnych-disku/16088/img/body-23.49A8.gif)
      - podélný zápis
        - vodorovně s povrchem
        - vyšší hustota => chyby
      - kolmý zápis (od 2005)
        - přidána nová vrstva pod vrstvu s data
  - **čtení**
    - hlavy reagují na magnetické reverzace, které vyvolávají magnetický tok
    - magnetický tok => elektrický impuls
- způsoby adresování
  - CHS
    - víceúroňové adresování
    - dnes se nepoužívá
    - možná adresace 512MB
  - ECHS
    - 7.88 GB
  - LBA (Logical Block Adressing)
    - lineární adresování
    - 48 bit adresa
    - logický blok má v HDD velikost 512B
      - SDD 1024B
      - optická média 2048B
- parkování hlav
  - umístění hlav
  - zamezení poškození
    - porušení vzduch. polštáře
  - autopark
    - po vypnutí PC

### Technologie

- NCQ
  - řadič disku rozhoduje o pořadí čtení dat
  - snaží se minimalizovat počet otáček
  - nejedná se vždy o zrychlení
    - seřazení trvá nějakou dobu
- AHCI
  - Intel
  - rozhraní pro komunikaci se SATA řadičem
  - nezávislé na HW
  - musí být podporováno
    - OS
    - čipsetem
    - koncovým paměťovým zařízením
  - funkce
    - NCQ
    - Hot Plug
      - připojení/odpojení jednotek za běhu
    - vylepšení řízení spotřeby
  - AFC
    - vylepšení kolmého zápisu
    - vyšší hustota záznamu
  - HAMR
    - 100x větší objem dat na palec oproti AFC
    - až 4TB na čtvereční palec
    - laserový ohřev místa zápisu
    - Seagate 20 TB disk
  - S.M.A.R.T.
    - nezávislý na OS
    - řadič sleduje hodnoty a zapisuje na stanovené místo
    - specializovaný program čte tyto dataa případně vyvolá poplach
    - pokud je disk odepsaný podle SMARTu, tak ale může ještě několik let fungovat
    - měřené hodnoty
      - počet startů plotny
      - počet odpracovaných hodin
      - teplota
    - **pokud jsou výsledky dobré nebo špatné, zálohujte svá data!**

### Raid

- snaha o zpracování dat paralelně
- důvod
  - zvýšení spolehlivosti a rychlosti přístupu k datům
  - reakce na zvyšující se rychlost procesorů
- výhradně na serverech
- pro OS vypadá jako jeden velký disk
- typy
  - HW podpořený
    - základní deska, řadič, ...
  - SW podpořený
    - Linux v jádře kernel
- 7 úrovní
  - RAID 0
    - všechny disky mají unikátní data
      - žádná redundance
    - možné číst data rychleji
  - RAID 1
    - mirror
    - nákladné
  - RAID 2
    - disky jsou synchronizovány
    - data stripovány po bitech
      - hlavy na stejné pozici
    - 1 disk má data a další disk obsahuje bity vygenerované jako Hammingův kód z odpovídajících datových bitů
      - 2 disky + 2 paritní disky
    - velká redundance
    - nákladné
  - RAID 3
    - podobně jako RAID 2
    - N disků + 1 paritní
      - paritní disk je bottle neck
    - vysoká rychlost přenosu
  - RAID 4
    - data stripovány po blocích
    - parita je ukládana po blocích
    - výhody a nevýhody stejné jako u RAID 3
  - RAID 5
    - podobné jako RAID 4
    - parita je uložena na všech discích
    - pokud odejde
      - 1 disk => OK
      - více disků => neřešitelné
    - min. 3 disky
    - rychlé čtení
    - pomalejší zápis
  - RAID 6
    - počítají se 2 parity
    - min. 4 disky
    - pokud odejde
      - 2 disky => OK
      - 3 disky => neřešitelné
    - výhodné využít 5+ disků
  - RAID 1+0
    - min. 4 disky
    - 2x RAID 1 a to celé v RAID 0

## SSD

- založené na flash pamětech
- rychlost přístupu HDD vs SSD
  - HDD v milisekundách
  - SSD v mikrosekundách
- připojení přes
  - SATA, mSATA
  - PCI-Express
  - PCMCIA
  - M.2
  - NVNE M.2 SSD
    - paralelistmus
    - 2x nižší latence než AHCI

### typy

| Název | Počet bit v buňce | Počet zápisů do buňky | Kapacita                             | Rychlost           | Cena                                                   |
| ----- | ----------------- | --------------------- | ------------------------------------ | ------------------ | ------------------------------------------------------ |
| SLC   | 1                 | 100 000               | :x:                                  | :heavy_check_mark: | :x:                                                    |
| MLC   | nejčastěji 2      | 10 000                | :heavy_check_mark:                   | :x:                | :heavy_check_mark:                                     |
| TLC   | 3                 | 5000                  | :heavy_check_mark::heavy_check_mark: | :x::x:             | :heavy_check_mark::heavy_check_mark:                   |
| QLC   | 4                 | 1000                  | 1TB                                  | :x::x::x:          | :heavy_check_mark::heavy_check_mark::heavy_check_mark: |
