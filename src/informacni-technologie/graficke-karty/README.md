# Grafické karty

- úkolem je zpracovávat a transformovat grafická data do podoby, kterým rozumí zobrazovací zařízení
- mohou být
  - integrovaná na základní desce
  - v procesoru
  - případně dedikovaná
- výrobci
  - ATI/AMD
  - Nvidia
  - ARM
  - Imagination Technologies
- připojení
  - PCI, AGP
  - PCIe x16
- integrované
  - dostatečný výkon na základní práci
  - levné a slabé
  - paměť si bere z RAM
    - zatěžuje základní desku a další komponenty

## Typy zobrazení

### textový režim

- umožňuje zobrazovat jen text
- případná podpora barev a velmi jednoduchých animací
- podpora několika rozlišení
- obrazovka je rozdělna na řádky a sloupce (buňky)
- buňka
  - uložena ve videopaměti
  - obsahuje ASCII kód + atribut
    - atribut (8bitů) je barva (popředí 4bit, pozadí 3bit) a jestli má blikat 1bit
- stránky ve videopaměti
  - stránka
    - paměťový blok
    - obsah jedné obrazovky
  - v grafickém režimu odpovídá rozlišení a barevné hloubce
- 80x25
  - kolik se vejde na obrazovku znaků?
  - vleze se jedna normostrana?
- kódová tabulka
  - pole znaků
  - znak má svůj index
  - MS-Dos
    - Latin 2
  - Windows
    - Windows 1250
    - UTF-8 od verze 2000
  - Linux
    - UTF-8
  - UTF-8
    - kódovaný znak má 8, 16, 24 nebo 32 bitů
    - proměnlivá délka
      - problém s výkonem
      - menší soubory s velkým množstvým znaků

### Grafický režim

- umožňuje zobrazovat matici pixelů
  - zobrazitelné body
- pixel
  - základní jednotka
  - každý má svou barvu z palety barev
- ve videopaměti je uložena informace o každém pixelu zvlášť
  - Frame Buffer
- množství potřebné videopaměti
  - odvíjí se od rozlišení a barevné hloubky
  - místo znaku jsou uložiny barvy

### pseudografika

- nabízí možnost pracovat s grafickými objekty v textovém režimu
- objekty se vytváří pomocí speciálních znaků
- Latin 2, BIOS

## Vývoj ve stručnosti

- CGA (Color Graphics Adapter)
  - 4 barvy
- MDA (Monchrome Display Adapter)
  - 2 barvy (černá a bílá)
- Hercules
  - MDA + monochromatický grafický režim
- EGA
  - 16 barev z palety 64 možných
- VGA
  - 16 barev z palety 2^18^
  - 640x480
- SVGA
  - grafické akcelerátory
  - 800x600
- PAL
  - Evropský standard
  - 768x576
  - 23.5 FPS

## 3D akcelerátory

- název skupiny odvozen od urychlení zobrazení
- grafický chipset
  - ulehčuje práci procesoru
- obsahoval jednoduché grafické API
- zpracovával 3D prezentaci obrazu na 2D pole pixelů

## DirectX

- Microsoft DirectX
- cíl
  - max využití možností hardwaru i max výkonu
- původně měla API samostatná jména
  - Direct3D
  - DirectDraw
  - DirectMusic
  - ...
- DirectX 11
  - podpora GPGPU
  - vícejádrová podpora pro game developer
  - přímá součást Windows 8
- DirectX 12
  - nutný pro běh Windows 11

## OpenGL

- multiplatformní API
- používá se při
  - tvorbě počítačových her
  - CAD programů
  - apliací virtuální reality
  - vědeckotechnické vizualizace
  - ...
- ARB konsorcium
  - Architecture Review Board
  - NVIDIA, SGI, Microsoft, AMD, ...

## Vulkan

- alternativa

## Metal

- Apple
