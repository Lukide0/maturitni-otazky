# Síťové modely

- dříve byly sítě od jednotlivých výrobců nekompatibilní
  - proto se vytvořil jednotný síťový model
- je to ucelená představa o tom, jak mají být sítě řešeny
  - nezahrnuje konkrétní protokoly
- komunikace je rozdělena do několika nezávislých úrovní
  - vrstev
  - každá řeší pouze určité kroky spojené s přenosem info
  - pro svou činnost komunikuje vyšší vrstvou
  - v každé vrstvě se přidávají dopňkové informace
- **služba**
  - vertikální komunikace
    - mezi vrstvami
- **protokol**
  - horizontální komunikace
    - mezi stejnými vrstvami
      - např. transportní-transportní
## ISO/OSI

- **ISO**
  - mezinárodní org. pro normalizaci
  - vytvořili referenční model pro propojování otevřených systémů (OSI)
- specifikuje komunikační protokoly
  - definují
    - navázání spojení
    - adresování
    - přenos dat
    - zpracování chyb
    - řízení toku dat
- 7 vrstev
| Název | S čím pracuje | Přirovnání | Příklad |
| ----- | ------------- | ---------- | ------- |
| Aplikační | Zpráva | Manager - diktuje, píše | HTTP, FTP, POP3, DHCP |
| Prezenční | Zpráva | Asistent - opravuje chyby| komprese, dekomprese |
| Relační | Zpráva | Sekretářka - poskytuje potřebné adresy | navázání a ukončení spojení | 
| Transportní | datagram | Řidič | TCP a UDP |
| Síťová | paket | Přijem a řazení | IP, směrování |
| Linková | rámec | Balení | spojení mezi konc. zařízením na LAN, MAC adresa |
| Fyzická | fyzický paket | Nakládání | kabely, konektory |

## TCP/IP

- 4 vrstvy
- místo
  - aplikační, prezenční a relační vrstvy
    - aplikační vrstva
  - linkové, fyzické vrstvy
    - vrstva síťového rozhraní
      - zajišťuje přenos rámců
- vrstva síťová
  - IP protokol
  - ICMP
  - ARP
- aplikační vrstva
  - rozšířena o porty
  - 0-65535 porty
    - 80 HTTP
    - 21 FTP
    - 110 POP3
    - 25 SMTP

## Srovnání

| TCP/IP | ISO/OSI |
| ------ | ------- |
| nejdříve vznikaly protokoly | nejdříve vznikaly vrstvy |
| praktický přístup | teoretický přístup |
