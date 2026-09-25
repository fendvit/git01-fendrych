Moje řešení

Distribuce a verze: Debian GNU/Linux 13 (trixie), kernel 6.12.48+deb13-amd64

Použitý Vagrant box: bento/debian-13

Adresář serveru: srv01/ (v kořeni repozitáře, obsahuje Vagrantfile zkopírovaný ze vzoru Vagrantfile-debian)

Výsledek spuštění a přihlášení:

Po příkazu vagrant up si Vagrant nejprve stáhl box bento/debian-13 a vytvořil virtuální stroj ve VirtualBoxu. První spuštění proto trvalo výrazně déle než další, kdy už se box bere z lokální cache. Příkaz vagrant status následně hlásil stav running (virtualbox) a přihlášení pomocí vagrant ssh proběhlo bez problémů — přihlásil jsem se jako uživatel vagrant na hostname debian13.

Uvnitř serveru jsem distribuci ověřil příkazem cat /etc/os-release, který vypsal PRETTY_NAME="Debian GNU/Linux 13 (trixie)". Ze serveru jsem se odhlásil příkazem exit a po dokončení práce jej vypnul příkazem vagrant halt v adresáři srv01.

Případné problémy a jejich řešení:

Zásadní problém jsem neřešil. Za zmínku stojí dvě věci:

Soubor Vagrantfile-debian bylo potřeba po zkopírování přejmenovat přesně na Vagrantfile bez jakékoli přípony — s původním názvem Vagrant v adresáři žádnou konfiguraci nenajde a vagrant up skončí chybou.
Adresář srv01/.vagrant/ vzniká hned při prvním vagrant up. Pravidlo .vagrant/ v .gitignore jsem proto vytvořil ještě před spuštěním serveru, aby se místní stav VM vůbec nedostal do sledovaných souborů. Ověřil jsem si to příkazem git status, kde se .vagrant/ neobjevuje.

Kontrolní kód a záznam ze serveru:

Kontrolní kód: SPOS-3I-68b01bf9eeb981523deb4e09f947d4d8796919ddfc94573508b2079580c0387a

text
Úloha: git-vagrant / SPOŠ / 3. I / v1
Distribuce: Debian GNU/Linux 13 (trixie)
Hostname: debian13
Kernel: 6.12.48+deb13-amd64
Virtualizace: oracle
Čas UTC: 2026-09-25T06:27:51Z
Náhodné ID: a7090183-4944-4523-a417-619faf84ae38

Bonus – AI obrázek a použitý prompt:

Obrázek: Images/tucnak-na-kopci.jpg

Použitý AI nástroj: (doplň konkrétní nástroj, který jsi použil)

Použitý prompt:

Tučňák Tux stojící na vrcholu kopce, pod ním krajina s datovými centry a servery. Nad scénou se vznášejí větvící se linky jako schéma Git historie. Digitální ilustrace, výrazné barvy, téma Linux, Git, Vagrant a virtuální servery.
