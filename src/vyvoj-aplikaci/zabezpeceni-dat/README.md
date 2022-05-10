# Zabezpečení dat

- **proč?**

  - hardwarové problémy
    - restarty počítače – přehřívání zdroje a procesoru, chyby RAM a pevného disku…
    - nefunkční počítač – havárie disku, zdroje nebo základní desky
  - softwarové problémy
    - pády OS – neudržovaný systém, smazané systémové soubory, nevhodné ovladače …
    - nefunkční OS – působení virů a škodlivého obsahu
  - personální problémy
    - nešikovní uživatelé – nechtěné akce – ztráta dat
    - zákeřní uživatelé – záměrné akce – ztráta a zneužití firemních nebo osobních dat
  - komunikační problémy
    - návštěva zákeřných stránek – zneužití osobních dat
    - stahování a spouštění škodlivých souborů – možnost ztráty nebo zneužití dat
    - přijímání škodlivých mailů – otevírání škodlivých příloh

- **způsoby ochrany**

  - ukládání/zálohování
    - zálohování
      - druhy
        - mauální
        - automatické
      - typy
        - plná záloha
        - inkrementální záloha
          - jen rozdíly oproti minulé záloze
        - rozdílová
          - jen rozdíly oproti poslední plné záloze
    - průběžné ukládání rozpracované práce
    - chrání před chybami SW nebo operačního systému -> kdyby SW nebo operační systém náhle přestal fungovat, máme uložený alespoň část práce
  - fyzická ochrana
    - ochrana před přírodními hrozbami a fyzickými útočníky
      - zamezit fyzickému přístupu k serverům nebo jiným zařízením nepovolaným osobám
  - RAID
    - metoda proti selhání pevného disku

- **sdílení a oprávnění**
  - využití uživatelských účtů s různým oprávněním
  - data a nastavení odděleny v uživatelských profilech
  - souborům můžeme nastavit různá oprávnění - kdo je může číst, upravovat či spouštět
- **bezpečnostní aktualizace**
  - operačního systému, prohlížeče, ...
  - najde se díra v systému -> vývojáři vydají bezpečnostní aktualizaci, při neprovedení aktualizace je systém stále zranitelný

## Firewall

- zabraňuje komunikaci na určitém portu nebo pro určitou aplikaci
  - blokuje nebo povoluje navazované komunikace na základě předdefinovaných nebo dynamických pravidel a politik
- filtruje příchozí i odchozí komunikaci do vnitřní sítě
- 2 metody principu
  - vše je povoleno, něco zakázáno
  - vše je zakázáno, něco povoleno
- generace
  - první
    - filtrovala pakety
    - porovnávala jejich základní informace s předdefinovaným seznamem pravidel
      - zdroj
      - cíl
      - použité porty
      - protokoly
  - druhá
    - technologie stavu připojení
      - umožňuje rozeznat, zda komunikaci zahájil paket, který je její součástí
  - třetí
    - přidala možnost filtrovat informace napříč vrstvami modelu OSI
      - umožňuje firewallu rozpoznat aplikace a často používané protokoly

## Šifrování

- zajištění nečitelnosti uložených nebo zasílaných dat pro nepovolané uživatele
- **symetrické šifry**
  - algoritmy - AES, HMAC
  - jeden klíč
- **asymetrické šifry**
  - algoritmy - RSA
  - 2 klíče
    - veřejný šifrovací klíč
      - bude všeobecně znám a kdokoli může zprávu tímto klíčem zašifrovat
    - tajný/soukromý dešifrovací klíč
      - pouze tímto klíčem lze dešifrovat zprávu
      - většinou se ze soukromého klíče vytvoří pomocí algoritmu veřejný klíč
