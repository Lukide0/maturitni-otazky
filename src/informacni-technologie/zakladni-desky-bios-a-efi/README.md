# Základní desky, BIOS a EFI

## Základní desky

Základní hardware pro většinu počítačů, který slouží k propojení jednotlivých komponent a jejich následnému napájení. V dnešní době mají běžné desky mnoho možností připojení pomocí konektorů na zadním panelu.

**PCB** (Printed Circuit Board - deska tištěných spojů) - základní deska je tvořena několika vrstvami (slouží pro komunikaci) + jsou zde umístěny další obvody a konektory

Desky jsou rozlišovány v mnoha vlastnostech:

- rozměry desky
- způsob uchycení/typ napájecích konektorů
- výrobce
- vybavenost rozhraní a patice procesoru
- chipset
- způsob chlazení komponent
- možnost přetaktování (závisí na BIOSu)

### Form factor základních desek (příklady):

- ATX (305 x 244 mm) - Intel, rok 1995 - standard od 1999
- micro-ATX (244 x 244 mm) - méně slotů
- mini-ITX (170 x 170 mm) - netbooky
- BTX (s ATX nekompatibilní) - Intel, rok 2004, zlepšení cirkulace vzduchu
- pro servery: EATX (rack servery), WTX (tower servery)

### Rozhraní

- Rozšíření funkcí pomocí konektorů na desce (socket/patice procesoru, I/O panel, konektory apod.)
- I/O front/back panel - možnost zapojení externích zařízení do základní desky (myš, klávesnice, tiskárna, atd.)

#### Sběrnice

Slouží k přenosu dat mezi elektronickými zařízeními.

Můžeme je dělit více způsoby:

1. Dělení 1

   - Paralelní sběrnice - přenos n bitů zároveň přes n vodičů současně
     - řídící část: řídící signály
     - adresová část: přenos adres (umístění)
     - datová část: přenos dat
   - Sériové sběrnice - přenos bitů postupně po jednom vodiči

2. Dělení 2

   - Interní - propojují vnitřní komponenty počítače
   - Externí - propojují rozšiřující komponenty s počítačem

3. Dělení 3
   - Synchronní - pracují synchronně s procesorem (většina sběrnic)
   - Pseudosynchronní - možnost zpoždění přenosu o určitý počet taktů
   - Lokální sběrnice - náročné operace s daty jsou prováděny přes rychlou systémovou sběrnici

##### Interní sběrnice

- ISA (_Industry Standard Architecture_) - paralelní
  - starší sběrnice od IBM (1981 - 1993)
  - 8 nebo 16 bitová šířka
  - rychlost 8 nebo 16 MB/s
  - Extended ISA - 32 bitová s teoretickou rychlostí 33 MB/s
- PCI (_Peripheral Component Interconnect_) - paralelní
  - od Intelu - od roku 1992
  - 32 nebo 64 bitová šířka
  - teoretické rychlosti přenosů:
    - 32 bit, 33 MHz -> 133 MB/s
    - 32 bit, 66 MHz -> 266 MB/s
    - 64 bit, 33 MHz -> 266 MB/s
    - 64 bit, 66 MHz -> 533 MB/s
- AGP (_Accelerated Graphics Port_) - paralelní
  - od roku 1997
  - modifikace PCI pro grafické karty
  - propustnost až 2 GB/s
- PCIe (_PCI Express_) - sériová
  - od roku 2004
  - komunikační pásmo rozděleno do kanálů (linky)
  - v dnešní době nejpoužívanější rozšiřující sběrnice
  - fyzické rozhraní má 1, 4, 8, 16 linek - liší se v délce (x1, x4, x8, x16)
  - rychlosti (_1 linka (x1)_, _16 linek (x16)_):
    - v1.x: x1 -> 250 MB/s, x16 -> 4 GB/s
    - v2.x: x1 -> 500 MB/s, x16 -> 8 GB/s
    - v3.x: x1 -> 985 MB/s, x16 -> 15,75 GB/s
    - v4.0: x1 -> 1,97 GB/s, x16 -> 31,5 GB/s
    - v5.0: x1 -> 3,94 GB/s, x16 -> 63 GB/s
    - v6.0: x1 -> 7,56 GB/s, x16 -> 121 GB/s

##### Externí sběrnice

- USB
- Thunderbolt
- FireWire (IEEE 1394)
- eSATA

### Chipset (čipová sada)

Integrované obvody, které slouží ke komunikaci mezi jednotlivými komponentami (procesor, paměti, rozšiřující karty, BIOS a konektory).

Chipsety dnes navrhuje například NVIDIA, AMD, VIA a Intel. Intel, ATI (dnes součástí AMD) a VIA je dokonce i vyrábí.

#### Struktura

- systémový řadič - řídí spolupráci jednotlivých obvodů základní desky
- řadič sběrnice - zabezpečuje komunikaci mezi systémovou a rozšiřující sběrnicí
- buffer dat - slouží k zachycování dat a jejich přepínání mezi datovými sběrnicemi

#### North-South bridge design

- North bridge (_serverní můstek_) - vysokorychlostní komunikace mezi grafickou kartou, operační pamětí a procesorem
- South bridge (_jižní můstek_) - pomalejší komunikace mezi pomalými rozšiřujícími kartami, disky, řadiči externích rozhraní a různými mechanikami + zprostředkovává službu BIOSu
- Dnes se objevuje více one chip design
- North bridge může být integrován přímo do pouzdra procesoru

![](./images/chipset.png)
