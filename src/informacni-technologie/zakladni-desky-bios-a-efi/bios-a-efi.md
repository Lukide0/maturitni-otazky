# BIOS a EFI

## BIOS

- Basic Input/Output System
- Firmware pro osobní počítače (základní rozhraní)
- Původně od IBM - bylo nutno od nich kupovat kvůli kompatibilitě
- Slouží k inicializaci a konfiguraci hardware v počítači a následnému spuštění operačního systému
- Uložen je na základní desce v nevolatilní paměti (většinou v ROM - _Read-Only Memory_ - nebo modernější flash paměti)
- V případě chyby při inicializaci systému na ni upozorní
- **Možnosti nastavení:**
  - Nastavení taktu procesoru, operační paměti
  - Nastavení napětí procesoru
  - Nastavení cache
  - Detekce harddisků, CD-ROM
  - Nastavení periferií
  - Bootovací sekvence (HDD, CD-ROM, USB, LAN, FDD)
  - HW monitor
  - Power management

## EFI

- Extensible Firmware Interface
- Nástupce BIOSu s otevřeným kódem
- Původně vyvinuto společností Intel
- V dnešní době nahrazeno UEFI (_Unified EFI_)
- **Vlastnosti:**
  - Grafické rozhraní (GUI) - lepší pro běžné uživatele
  - Vlastní koncepce ovladačů
  - Podpora šifrování a autentizace po síti
  - Mnohonásobně větší než BIOS (desítky MB, BIOS jen pár KB) - ukládáno do flash paměti
  - Podpora větších uložišť

### UEFI

- Podpora secure boot
  - Při startu pouze certifikovaný software dle výrobce
  - Kontrola elektronických podpisů
  - Pokus Microsoftu o znemožnění instalace jiného operačního systému
- kritika UEFI kvůli komplikovanosti
- Pokud bychom chtěli využít nějakou alternativu, musíme použít více softwarů zároveň
  - například: CoreBoot + SeaBIOS
