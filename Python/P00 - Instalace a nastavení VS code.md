# Instalace a základní nastavení

## Instalace

Abyste mohli Python začít používat ve Windows nebo na Mac, musíte jej nejdřív stáhnout na internetu a nainstalovat do počítače. Doporučuji nepoužívat Windows store a stáhnout Python z [oficiálních stránek](https://www.python.org/downloads/). Ve VS code nezapomeňte přidat extension Python.

**Důležité! Při instalaci zaškrněte**

-   [x] Add Python to PATH

### Nastavení extension pro Python

**Důležité!** Abychom se vyvarovali budoucím chybám, je potřeba změnit nastavení Python extensio ve VS code

Proklikejte se do nastavení přes _File -> Preferences -> Settings_ (nebo klávesovou zkrátkou _ctrl + ,_) a do vyhledávacího pole napište _python terminal execute_ a zaškrtněte položku **_Python > Terminal: Execute In File Dir_**

### Spuštění souboru

V terminálu ve VS code zadejte správnou cestu k souboru (může se hodit: pravým klik na soubor a Open in Integrated Terminal) a napište příkaz: `python nazevsouboru.py`, alternativně stačí `py nazevsouboru.py`

V Linuxu nebo na Macu je potřeba napsat `python3 nazevsouboru.py`

Pokud jste správně nastavili extension (viz odstavec výš), můžete spustit souboru pomocí symbolu play <| v pravém horním rohu
