# Paměti počítačů

- zařízení pro ukládání dat a programů v počítači
- dělí se na
  - volatilní
    - energeticky závislé
    - bez elektřiny jsou data ztracena
    - jsou většinou rychlejší než vnější paměť (např. HDD)
    - např. RAM,ROM
  - nevolativní
    - energeticky nezávislé
    - uchovovávají data bez elektřiny
    - např. SSD, HDD, Flash, ...

## ROM

- Read Only Memory
- lze jen číst
- data jsou uložena přímo výrobcem
- druhy
  - PROM
    - data jsou nahrávány při výrobě
  - EPROM
    - možno speciálním technologickým postupem zapsaná data vymazat a zapsat nová
  - EEPROM (Flash)
    - lze zapsat i vymazat data elektrickou cestou a přesto zůstanou zachována po vypnutí napájení
- aplikace
  - Flash BIOS
  - paměťové karty digitálních fotoaparátu

## RAM

- Random Access Memory
- možno libovolně přistupovat a cokoli měnit
- podle principu činnosti tuto paměť rozdělujeme na statickou a dynamickou
  - statické
    - SRAM
    - uchovávají informaci v sobě uloženou po celou dobu, kdy jsou připojeny ke zdroji elektrického napájení
    - nízká přístupová doba (15-20ns)
    - složitější
    - nejčastěji pro realizaci pamětí typu cache
  - dynamické
    - DRAM
    - informace je uložena pomocí elektrického náboje na kondenzátoru
      - náboj má však tendenci se vybíjet
      - nutné periodicky provádět tzv. refresh
    - nízké výrobní náklady
    - přístupová doba 60-70ns

### DRAM druhy

- SDRAM
  - pro systémy s procesory s 64-bit architekturou
  - osazují se do DIMM modulů
- DDR
  - dvojnásobná datová rychlost
  - také se osazují do DIMM
    - mají klíče
      - jinak umístěné výřezy
      - nelze zasunout do patic pro SDRAM
- RDRAM
  - mnoho firem v čele s Rambus a Intelem
  - také mají klíče
  - používá se označení RIMM pro moduly a patice
- XDR DRAM
  - také Rambus
  - propustnost až 28.8 GB/s
  - XDR
    - frekvence 3.2GHz
    - např. PlayStation 3
  - XDR2
    - 2x větší propustnost než GDDR5
    - teoriticky propustnost přes 500GB/s
    - cíl je systém s celkovou propustností 1TB/s
- DDR4 SDRAM
  - 2015
  - na začátku příliš vysoká cena výroby
- DDR5

### Patice

- SIMM patice
  - jednoduchý obvod sloužící k instalaci operační paměti (RAM) do počítače
  - 32bit
- DIMM patice
  - s nástupem procesorů Intel Pentium
  - předchůdcem byly paměti SIMM
  - na obou stranách samostatné elektrické kontakty
  - 64bit
- SO-DIMM patice
  - menší rozměrově DIMM (1/2)

## Flash

- typ EEPROM
- narozdíl od EEPROM lze každý blok plnit informacemi samostatně
- typy flash paměti
  - NOR (aka EEPROM)
    - starší
    - přistupují se jednotlivé bity dat
  - NAND
    - novější typ
    - čtení a zápis se provádějí po stránkách
    - mazání se provádí po blocích
