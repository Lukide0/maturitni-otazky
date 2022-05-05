# Internetworking (pasivní a aktivní prvky sítí)

- zkráceně internet
- vzájemné propojování celých sítí (nebo jejich dílčích částí: segmentů)
- proč

  - překonat omezený dosah přenosového média (kabeláž)
  - zpřístupnění vzdálených zdrojů
    - FTP
    - WWW
  - optimalizace datových toků
  - ochrana a obrana
    - firewall
  - potřeba zajistit fungování velké soustavy vzájemně propojených sítí
  - potřeba řešit přístupová práva

- podstata
  - dvě či více částí (sítě, segmenty) se propojí pomocí vhodného propojovacího zařízení
  - zařízení se pojmenovává podle
    - vrstvy na které pracuje
      - opakovač(repeater), most(bridge), směrovač(switch)
    - způsobu jak pracuje
      - rozbočovač, firewall, proxy brána

## Pasivní prvky sítí

- nepracují s tím, co přenáší
- např.
  - kabely (koaxiální, optické, kroucená dvojlinka)
  - konektory (RJ45, ...)
  - rozbočky
  - zásuvky
  - skříně (rack)

## Aktivní prvky sítí

- pracují aktivně s daty, které jimi protékají
- **filtrování**
  - propojovací uzel
    - už musí fungovat na vyšší úrovni, nejméně na L2
    - už nemůže fungovat jako opakovač
  - zamezuje šíření dat, která mají začátek i konec ve stejné segmentu
- **forwarding**
  - cílené předávání
  - požadavky jsou stejné jako u filtrování
  - data jsou posílána pouze do určitého cílového segmentu
  - vyžaduje
    - znát adresy příjemce/odesílatele
    - informace o topologii sítě
- **plochá síť**
  - koncové uzly
    - nevidí propojovací uzly/zařízení
    - nevnímají rozdělení do segmentů
    - myslí si, že jsou propojeny se všemi ostatními uzly přímo
    - vnímají síť jako plochu
- **směrovací tabulka**

  - obsahuje pravidla o směrování datagramů do konkrétních podsítí
  - statické směrování
    - ručně
    - nereaguje na změny v síti
    - používá se u malých sítí
  - dynamické směrování
    - pomocí směrovacích protokolů
      - RIP
        - nejstarší routovací protokol
        - není vhodný pro větší sítě
      - IGRP
      - OSPF
    - lepší pro větší sítě

- **Opakovač**

  - neukládá data do žádné vyrovnávací paměti
  - data prochází opakovačem s konstantním zpožděním
  - opakovače mohou propojovat pouze segmenty se stejnou přenosovou rychlostí
  - opakovače musí propouštět kolize
  - závislé na technologii, použité na linkové vrstvě
  - opakuje do všech směrů
  - 10 megabitového Ethernetu platí pravidlo 5:4:3
    - max. 5 segmentů
    - max. 4 opakovače
    - max. 3 obydlené segmenty
  - propojené segmenty mají sdílenou přenosovou kapacitu

- **Router**

  - propojuje různé sítě
  - funguje na vrstvě síťové (L3)
  - používá routovací tabulku

- **Gateway**
  - propojuje dvě sítě pracující s odlišnými komunikačními protokoly
  - vykonává i funkce routeru

## Bridge vs Switch

| Vlastnost              | Bridge        | Switch         |
| ---------------------- | ------------- | -------------- |
| Zařízení               | staré         | nové           |
| Optimalizace           | filtrování    | forwarding     |
| Počet portů a segmentů | Malé množstvý | Velké množstvý |

- nepropouští kolize
- jak znají svoje okolí
  - statické nastavení
  - dynamicky
    - metodou zpětného učení
      - používají mosty a přepínače v Ethernetu
      - nemusí se nic konfigurovat a nastavovat
      - v síti nesmí být cykly
    - metodou source routing
      - používají mosty v Token Ringu
