# Nastavení SSH v Gitu

_Tento návod je určen pro Windows. Pro mac a Linux by byl návod téměř totožný, lišit se bude akorát cesta k Public key_

V jakémkoliv příkazovém řádku - cmd/powershell - napište následující příkaz (email zvolte stejný, kterým jste se registrovali na Githubu)

```
ssh-keygen -t ed25519 -C "tvuj_mail@priklad.cz"
```

Vyskočí na vás tato hláška - stiskněte ENTER

```
> Generating public/private ed25519 key pair.
> Enter file in which to save the key (C:\Users\Jmeno/.ssh/id_nejakecislo):
```

Vyskočí nová hláška o zadání passphrase (jedná se o heslo k SSH klíči - pro lepší zabezpečení můžete vyplnit, ale není nutně potřeba) - pro zjednodušení práce nemusíte heslo vyplňovat, jen stistkněte ENTER:

```
> Enter passphrase (empty for no passphrase):
```

Podobná hláška znovu, opět ENTER

```
> Enter same passphrase again:
```

**Tím jsme vytvořili pár klíčů: Public key a Private key**

_Private key zůstává na vašem počítači a s nikým ho nesdílíte. Public key nahrajeme na Github a pomocí něj budeme ověřovat připojení_

Klíče bydlí ve složce C:\Users\\**Jmeno**\\.ssh (Jmeno je vaše jméno ve Windows), kam se přesuneme v příkazovém řádku pomocí

```
cd C:\Users\Jmeno\.ssh
```

Zkontrolujeme název klíče

```
dir
```

Pomocí notepadu otevřeme náš Public key, který má koncovku .epub

```
notepad id_nejakecislo.epub
```

**Číslo z notepadu zkopírujeme (Ctrl+C) a otevřeme si Github**

V Githubu klikneme vpravo nahoře na naší ikonu

![image](https://github.com/JS-Trebesin/WET-materialy/assets/84028625/ef11f56b-1553-4e3f-950b-e897446120a5)

Settings

![image](https://github.com/JS-Trebesin/WET-materialy/assets/84028625/ec7b5b3a-1d62-4976-b263-f8a1db8bd8b4)

V levé části SSH and GPG keys

![image](https://github.com/JS-Trebesin/WET-materialy/assets/84028625/1b3eaad6-a944-49c7-8cc4-7552fe656a46)

Vpravo nahoře New SSH key

![image](https://github.com/JS-Trebesin/WET-materialy/assets/84028625/0f8ba9e3-f740-4474-b7ab-eaef30d17aae)

Do title napsat cokoliv, do pole Key nakopírovat náš Public key a kliknout na Add SSH key

![image](https://github.com/JS-Trebesin/WET-materialy/assets/84028625/ab996405-f313-4e3a-83bd-9ef231c569ba)

Hotovo. Nyní můžete používat SSH připojení a nemusíte ověřovat přihlašování přes prohlížeč.

Při klonování repozitářů nyní budete volit SSH

![image](https://github.com/JS-Trebesin/WET-materialy/assets/84028625/3f9af04b-0138-4981-a424-e47f9de102f8)
