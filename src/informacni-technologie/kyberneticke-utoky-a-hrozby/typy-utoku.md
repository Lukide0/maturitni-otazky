# Typy útoků

## Social Engineering

Přistupový útok s cílem zmanipulovat uživatele, aby provedl určitou akci. Může jít o sdělení hesla, udělení přístupu, nebo dokonce poskytnutí platebních údajů.

### Příklady

- **telefonát zaměstnanci** s přístupem do systému

  > „Jedná se o kritickou situaci, potřebuju heslo...“

- **email od supportu (pretexting)** na steamu
  (proto je v těch chatech nahoře ta notifikace, ať nikomu nedáváte heslo)

  > „Máme problém s vaším účtem, můžete nám dát přihlašovací údaje, abychom se na to podívali?“

- **fyzický vstup (tailgating)**, social engineering se vztahuje i na fyzická místa, můžete požádat někoho, ať jde třeba zkontrolovat serverovnu, a budete ho tam sledovat…

- **něco za něco (quid pro quo)** - přijde vám mail, že princ Habíbo u vás potřebuje schovat 50 kg diamantů, ale potřebuje peníze na dopravu…

Sociální inženýrství je v dnešní době nejsilnější/nejefektivnější způsob útoků. Většina systémů je dobře zabezpečena a vyžadují velkou dovednost, aby jste se do nich dostali, nicméně využít hlouposti lidí je děsně jednoduché.

### Phishing

Druh sociálního inženýrství, jehož principem je odesílání emailu a vydávání se za něhoko jiného. Cílem může být nainstalování software nebo sdílení osobních informací.

#### Spear phishing

Lepší verze phishingu, která je cílená na konkrétní osobu.

Útok probíhá prvotním zjišťováním informací o určené osobě. Poté útočník využije tyto informace a vytvoří útok specificky pro tuto osobu. Příklad - cíl se zajímá o auta, tak se útočník přidá do stejné FB skupiny a pošle cíli nabídku na prodej auta s odkazem. Odkaz povede na stránku obsahující zavirovaný obrázek, což povede k nakažení cíle.

#### Baiting

Sociální inženýrství soustředící se na nálákání cíle a vzbuzení jeho zvědavosti.

Nejčastějším případem je zanechání přenosného média někde na
veřejném místě. Po zasunutí média do pc je cíl infikován malwarem.

## Password cracking (Bruteforce)

Typ útoku, který zkouší každou kombinaci k prolomení hesla. Lze využít třeba k prolomení hesla do šifrovaného souboru, účtu, WiFi. Samotný útok není moc efektivní, trvá dlouho a spoléhá na raw výkon počítače, než na zranitelnost systému.

Útok lze usnadnit využítím seznamu hesel (wordlist). Tyto seznamy lze stáhnout na internetu a obvykle jde o často používaná hesla a odcizená hesla. Nyní nejčetnější seznam se nazývá "RockYou.txt" a obsahuje 32 milionů hesel.

### Něco málo k bezpečnosti hesel

K vytvoření účtu potřebujete heslo a to má obvykle nějaké parametry (8
znaků, velké a malé písmeno, čislo a speciální symbol...).

Tyto informace jsou nápomocné ale i hackerovi - ví, co heslo musí obsahovat, aby ho prolomil. Nejbezpečnější je stanovit větší minimální
délku (například 16 znaků), protože tak by bruteforce trval moc dlouho.

Dále se dělá, že hesla nesmí obsahovat slova a při zadávání hesla je heslo ověřováno se slovníkem. To také ale není bezpečné, protože uživatelé si to heslo pak nebudou pamatovat, takže si ho někam napíší (papírek, který si přilepí na monitor). Proto je opět nejbezpečnější mít dlouhé, ale ne moc složité heslo, než mít super silné heslo, ale mít ho napsané na papíře u monitoru.

## Exploiting

Využívání zranitelností je jedna z nejčastějších metod útoků. Spoléhá na nalezení chyby (v kódu OS, specifické aplikace či protokolu).

Ke zranitelnosti se útočník dostane oskenováním cílového počítače a zjištěním co nejvíce informací (os a jeho verze, běžící služby a jejich verze, otevřené porty).

Po zjistění relevantních informací útočník vyhledá, zda pro ně už neexistuje nějaký exploit (viz [https://www.exploit-db.com/](https://www.exploit-db.com/)). Pokud ano, tak ho útočník využije a dostane se třeba ke vzdálenému přístupu.

### Příklady

- **hack herních konzolí** - po nalezení chyby v os je možné instalovat vlastní SW

- **intel meltdown** - Hardware zranitelnost Intel procesorů. Jde o race condition (popsáno pozdeji) mezi zadáváním instrukcí a ověřením práv.

- **shellshock** - Exploit v unixu, jde o neautorizované spouštění příkazů v BASH. Pokud byl kód přidán na konec proměnné, tak byl vykonán a to už bez ověření práv. Je to jedna z nejznámějších bezpečnostích chyb. Objevena byla v roce 2014, ale v systému byla již od roku 1992.

## Denial of service (DoS)

Druh síťového útoku. Jde o flood útok, kdy útočník z jednoho počítače odesílá velký počet bezúčelných paketů.

Cílem útoku je znemožnit přístup k určité službě a tím zamezit jejímu použití (ztráta peněz cílové společnosti).

DoS útoky jsou snadné na provedení a proto představují velký risk.

### Typy

- **kvantita** - Cíl zahlcen tolika požadavky, že nezvládne zpracovat
  další.

- **špatně formátovaný paket** - Paket je formátován tak, že jej cíl nedokáže zpracovat (obsahuje chyby). Cílové zařízení je proto zmatené a může crashnout.

## Distributed DoS (DDoS)

Zjednodušeně jde o koordinovaný DoS z více zdrojů. Obvykle je proveden pomocí botnetu složeného ze "zombie počítačů" (nakažené pc bot
malwarem, takže vykonávají akce útočníka).

## Man-in-the-middle (MITM)

Útok, během kterého útočník naruší komunikaci svým zařízením a odposlouchává/upravuje komunikaci. Lze mu snadno předejít šifrováním komunikace. Pokud ale útočník zachytí výměnu klíčů, tak je komunikace prozrazena.

**nejčastější druhy:**

- **ARP poisoning** - utočník se v sítí bude vydávat za router, tudíž přesměruje celou komunikaci přes něj

- **DNS spoofing** - otrávení DNS tabulky, takže pak bude přesměrovávat na chybnou adresu, obvykle útočníkovu

## SQL injection

Jedna z nejčastěji používaných technik útoku na web. Upravení SQL dotazu
na webu tak, aby vracel například všechny záznamy (leak celé DB). Toho
lze docílit přidáním vždy správné podmínky (\... OR 1 = 1). To vrátí vše
z tabulky.

## SEO poisoning/Spamdexing

Útočník může uměle zlepšit vyhledávací skóre podvodné stránky obsahující malware, aby byla častěji zobrazována. Více navštěv = více lidí, kteří se mohou nakazit.
