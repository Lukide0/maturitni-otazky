# Animační a vizualizační systémy

- jsou to programy pro tvorbu a animaci 3D grafiky

## Modelování 3D objektů

- existuje několik základních způsobů tvoření (modelování) 3D objektů:

### Polygonové modelování

- model se tvoří z jednotlivých polygonů (zpravidla čtyřúhelných nebo trojúhelných)
- zpravidla se nejprve vytvoří jednoduchý objekt, například krychle
  - z té se následně pomocí nástrojů vytvoří požadovaný výsledek
- nejběžnější způsob modelování, často se používá například pro hry nebo animace
- podporuje to většina běžných 3D programů, jako například Maya, 3DS Max, Cinema 4D, Blender, Nuke, Houdini

### Sculpting (lepení)

- používá se polygonální model, ale s velmi vysokou hustotou polygonů, často řádově milionů
- ten se následně deformuje různými štětci, stimulujícími lepení
- díky tomu lze vytvořit velice detailní modely, ale ty nelze použít v jiných programech, například pro animaci nebo hry
- to se řeší zapékáním detailů do textury (zpravidla Normal Map), která se pak aplikuje na verzi toho samého modelu s menším počtem polygonů
- často se používá na přidání drobných detailů k polygonálním modelům
- mezi specializované programy pro sculpting patří například ZBrush, Autodesk Mudbox
  - některé základní nástroje jsou i v Maya, 3DS Maxu, Cinema 4D a v Blenderu

### NURBS modelování

- modelování objektů pomocí křivek
- obdoba vektorové grafiky
- obtížnější na výpočet, ale přesnější než polygonální modelování
- používá se zpravidla pro technické věci
  - přesný návrh přístrojů, letadel, vesmírných lodí, karosérií aut, jiné techniky
- podporují to běžné 3D programy a CAD programy
- o něco složitější způsob modelování než polygonální

## Animace 3D objektů

### Keyframe animace

- definuje se poloha objektů v klíčových snímcích
- mezisnímky program dopočítává automaticky

### Animace pomocí kostry

- model (například člověka) se napojí na "kostru"
- následně se keyframe animací animuje poloha kostí v kloubech
- model se deformuje v závislosti na poloze kostry
- také je možnost použít tzv inverzní kinematiku
  - v tom případě se nemusí definovat poloha každého kloubu ale jen některých
  - například zatáhne se za dlaň a program sám vypočítá polohu loktu
- vhodný na organické animace
  - lidi, živočichové a podobně

### Fyzikální simulace

- simulace fyzikálních interakcí objektů
- jdou simulovat nárazy tvrdých objektů, tekutin, plynů, měkkých objektů (například oblečení)
- také jdou simulovat například efekty rozbíjení objektů nárazem a podobně
- bývá poměrně výpočetně náročná, obzvlášť v případě tekutin

## Nasvícení

- existují různé typy světel svítící
  - do všech stran (omni)
  - v jednom směru (linear)
  - kuželovitě z jednoho bodu (spotlight)
- na některé typy renderu, fungují pouze určená světla (Arnold)
- u světla jde nastavit intenzita, barva, typ stínu(ray-tracing) a jiné parametry
- také existují zdroje světla simulující sluneční světlo v určitý čas
  - fyzikální obloha

## Materiály a texturování

- definuje vzhled objektu
  - barvu, lesklost, průhlednost, lom světla při průchodu skrz objekt a podobně
- na shader lze aplikovat textury
  - nejčastěji pro barvu (diffuse) ale můžou definovat i různou míru odrazivosti (specular), nerovnosti (bump)
- pro správné zobrazení textury bez defektů je potřeba nastavit tzv UV mapping
  - správné rozložení textury po objektu
    - ručně, automaticky

## Rendering

- vypočítává se vzhled všech objektů, materiálů, textur, světel, stínů, efektů a podobně
- výpočetně náročné a v závislosti na složitosti scény, nastavení renderingu a výkonu počítače může trvat hodiny, dny nebo i týdny
- lze renderovat přes GPU nebo CPU, CPU je přesnější, vykresluje se po segmentech
- Často se používají tzv render farmy
  - výkonné servery
- většina programů na grafiku mají nějaký integrovaný renderer
- pro realističtější výsledky se ale často instalují další v podobě pluginů
  - například V-Ray, Arnold, Mental Ray, Renderman

### Globální osvětlení

- pro realistický výsledek renderingu je také důležité tzv **globální osvětlení**
  - využití při výpočtu osvětlení scény nejen přímého světla ze zdrojů, ale také světla odraženého od objektů, podobně jak je tomu v reálném světě

#### Sledování paprsků (raytracing)

- zpětné sledování paprsků vycházejících z oka (kamery) a jejich kolizí s objekty, procházení skrz průhledné objekty, lom světla atd
- na rozdíl od reálného světa se nesleduje cesta paprsky ze zdroje světla do oka ale obráceně
  - ze zdroje světla totiž vychází nekonečno paprsků a nemá smysl počítat ty, které ve fináli nedopadnou do kamery a uživatel je tedy nevidí
- nové grafické karty (Nvidia GeForce RTX) umí počítat raytracing i v reálném čase, takže jde použít i ve hrách

#### Radiozita

- realistický výpočet odraženého světla od matných objektů
- dělí polygony na malé plošky a počítá jejich vzájemný vliv
- výpočetně náročný
- nemusí se přepočítávat při změně úhlu kamery
- Často se používá v kombinaci s raytracingem pro realistické zobrazení i průhledných objektů a odrazů
- zpravidla se počítá po krocích

#### Ambient Occlusion

- nejedná se přímo o technologii globálního osvětlení, ale o jeho hrubé napodobení
- funguje na principu vyzařování paprsků z ploch objektů všemi směry
- paprsky které nenaráží na žádné objekty plochu zesvětlují
- díky tomu se místa kde je hodně objektů vedle sebe jeví tmavší, zatímco místa kde kolem není moc objektů se jeví světlejší
- efekt připomíná rozptýlené venkovní osvětlení při zatažené obloze
- nenáročné na výpočet a realističtější než jen obyčejné přímé světlo, ale nevhodné pro fotorealistickou grafiku

## Software pro 3D grafiku

### Autodesk Maya

- původně vyvíjena firmou Alias Systems, později koupena Autodeskem(2005)
- profesionální software používaný zejména pro pokročilou animaci a filmové efekty, her
- v Česku používána TV novou pro grafiku Televizních Novin
- 1\. verze 1998, aktuální verze 22
- podporuje scripting v jazyce MEL (Maya Embedded Language)
- $1 620 ročně -- proprietární
- podporuje Windows, macOS a Linux
- vyvíjena v C++, Python

### Autodesk 3DS Max

- nejčastěji se používá pro architekturní vizualizace
- jde ale použít i pro ostatní účely (grafika do her, animace, filmové efekty atd)
- původně se jmenoval 3D Studio Max
- projekty -- Halo 2, AC
- 1\. Verze 1990, aktuální 22
- $1 620 ročně
- podporuje pouze Windows, x86
- vyvíjeno v C++

### Cinema 4D

- program pro 3D grafiku (modelování, animaci, materiály i rendering) od německé společnosti Maxon
- má o něco jednodušší ovládání než Maya a 3DS Max
- jazyk pro skriptování COFFEE
- vývíjena v C++
- 1\. Verze 1990
- $719 ročně
- podporuje Windows a macOS
- vlastní plugin na render server

### Blender

- open-source program pro 3D grafiku
- zdarma i pro komerční využití
- podporuje Windows, macOS, Linux, FreeBSD, IRIX a Solaris
- jednoduše rozšiřitelný pomocí Python skriptů

## 2D Animace

- animace jde dělat i ve 2D

### Frame by frame animace

- kreslí se každý jednotlivý záběr, a ty se následně spojují do videa
  - hodně pracný a časově náročný způsob
  - používá se například pro animované filmy

### Keyframe animace

- podobné jako v 3D se vytváří jen klíčové záběry, a software dopočítává zbytek záběrů
- často se používá například pro video efekty a celkově při editace videa
  - nastavují se parametry efektů v klíčových záběrech a zbytek dopočítává program
- příklady programů, které se k tomu využívaj
  - Adobe After Effects, Adobe Premiere, Blackmagic DaVinci Resolve, Apple Final Cut Pro X, Apple Motion
