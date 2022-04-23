# GPU

- grafický procesor
- architekturou připomíná CPU
- vlastné API
  - Vulkan, OpenGL, DirectX, ...
- používají se k
  - vykreslování dat uložených v paměti na zobrazovacím zařízení
  - dalším výpočtům, které nejsou nutné pro zobrazování dat
- mají více pipelines
- pracují paralelně
- obvykle je použito více jader

  - stream procesory (desítky až stovky)

    - označován jako shader
    - TPC
      - stream procesory sdruženy do clusteru
    - postup/typy
      1. Geometry Shader
         - upravuje geometrii obrazce
      2. Vertex Shader
         - určuje viditelnost objektů
         - spolupracuje na převodu z 3D do 2D
      3. Pixel Shader
         - pracuje s
           - barvou
           - průhledností
           - texturami
         - anti-aliasing
      4. výstup 2D pole pixelů

  - slučují se do clusterů
  - na 1 výpočetním vlákně 1 cluster pracuje
  - cluster vykonává 1 operaci

## Struktura ve stručnosti

- napájení je buď ze sběrnice nebo externě
- grafiký procesor
- paměť RAM (např. GDDR5)
- RAMDAC (D/A převodník)
- chlazení
- VIVO (Video-in, Video-out)
- BIOS
- Cache

## Renderování

- tvorba reálného obrazu na základě počítačového modelu
- **Raytracing**
  - sledování paprsků

## Konektory ve stručnosti

- HDMI
  - 1.0
    - 2002
  - 1.4
    - podpora 3D
  - 2.0
    - propustnost 18 Gb/s
  - 2.1
    - propustnost 48 Gb/s
    - podpora 4K 120FPS / 8K 60FPS
- DVI
  - DVI-D => dig. signál
  - DVI-I => dig. a analog. signál
  - DVI-A => analog. signál
- Display Port
  - podporuje barevné hloubky 6,8,10,12 a 16 bit
- Thunderbold
- USB

## SLI

- propojení více GPU
- poprvé u karet 3dfx Voodoo 2
- metody
  - Split Frame Rendering (SFR)
  - Alternate Frame Rendering (AFR)
    - liché, sudé
  - SLI Antialiasing
    - vzlepšuje vyhlazovací výkon
    - nabízející lepší kvalitu obrazu
- problém slabší karty
- nutná podpora HW a SW
- Nvidia SLI
  - byla ukončena
  - rozděluje celý obraz v určitém poměru
  - je zohledněna složitost jednostlivý částí
- Crossfire
  - AMD CrossfireX
  - podpora až 4 GPU
  - nutná optimalizace ze strany vývojářů
  - nutnost kompatibilní základní desky
