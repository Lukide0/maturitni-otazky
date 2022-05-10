# Formáty pro výměnu dat (XML, JSON, CSV)

- **výměna dat**
  - proces převzetí dat strukturovaných podle zdrojového schématu a jejich transformace na data strukturovaná podle cílového schématu
- **formát pro výměnu dat**
  - jazyk/formát nezávislý na doméně
  - může být použit pro data z jakéhokoliv oboru
- kde se využívají
  - prostě skoro všude tam, kde se nějakým způsobem předávají data
  - např.
    - webové služby
    - komunikace mezi aplikacemi
    - export a import dat u aplikací
    - výměna obsahu webových stránek
    - ukládání, archivace dokumentů
    - ukládání vektorové grafiky

## XML (Extensible Markup Language)

- snadno čitelný a jasný
- používá se pro serializaci dat, v čemž soupeří např. s JSON
- určen především pro
  - výměnu dat mezi aplikacemi
  - publikování dokumentů
- obsahuje pouze text a značky (tagy) podobné HTML
  - definují se vlastní značky
- stal hlavním formátem pro elektronickou výměnu dat (EDI)
- je zjednodušenou podobou staršího jazyka SGML
- použití
  - RSS
    - poskytuje uživatelům a aplikacím možnost číst novinky webu
  - SVG
    - popisuje 2D vektorovou grafiku
  - SOAP
    - protokol pro výměnu zpráv přes počítačové sítě založených na XML
  - XHTML
    - XML alternativa jazyka HTML
  - Office Open XML
    - souborové formáty určené k ukládání a výměně dokumentů

## JSON (JavaScript Object Notation)

- datově méně náročnější, rychlejší a jednodušší oproti XML
- nejpoužívanější pro přenos dat u aplikací
- předává se ve formě řetězce a ten se následně “parsuje”
  - většina programovacích jazyků má zabudovanou implementaci, jiné potřebují externí knihovny
- datové typy
  - textové řetezce
  - čísla
  - boolean
  - pole
  - objekty
  - null

## CSV (Comma Separated Values)

- jednoduchý souborový formát určený pro výměnu tabulkových dat
- skládá se z
  - řádků
  - položek v řádcích
    - odděleny čárkou nebo středníkem
- programy, které dokáží pracovat s CSV formátem
  - Microsoft Excel
  - LibreOffice
