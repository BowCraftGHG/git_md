# Git auf Windows installieren
Git kann ganz einfach über die [.exe](https://git-scm.com/download/win) installiert werden oder über das winget tool
bash
winget install --id Git.Git -e --source winget


!Eine Bildanleitung erfolgt weiter unten!

Bei der Installation über die executable Datei, sind folgende Schritte im Installer notwendig:
1. Executable ausführen
2. Lizenz akzeptieren
3. Installationspfad angeben
4. Zu installierende Komponenten auswählen (Die Standard Auswahl ist meist vollkommen ausreichend)
5. Start Menü Order festlegen
6. Bei der Editor-Auswahl "Vim" auswählen
7. Den Standard Branch Namen durch das untere Auswahlmenü auf "main" setzen
8. Git erlauben durch die Befehlszeile und Drittanbietersoftware genutzt zu werden
9. "Use bundeled OpenSSH" auswählen
10. "Use the OpenSSL library" auswählen
11. "Checkout Windows-style, commit Unix style line endings" auswählen
12. "Use Windows' default console window" auswählen
13. "Fast-forward or merge" auswählen
14. "Git Credential Manager" auswählen
15. "Enable file system caching" auswählen
16. Installation abschließen

    Hier die Bildanleitung:
![WhatsApp Bild 2024-05-02 um 14 11 54_6f20f7c5](https://github.com/BowCraftGHG/git_md/assets/168099471/894d83af-e8a5-4914-b350-74f878c8b3e8)
![WhatsApp Bild 2024-05-02 um 14 12 46_d1bb5da1](https://github.com/BowCraftGHG/git_md/assets/168099471/bb10b190-3c1f-4f30-8221-99a88f179157)
![WhatsApp Bild 2024-05-02 um 14 12 51_f6ec8a30](https://github.com/BowCraftGHG/git_md/assets/168099471/40b30f58-46ee-45c0-a16c-d1ad712e3c85)
![WhatsApp Bild 2024-05-02 um 14 12 56_1e7b1846](https://github.com/BowCraftGHG/git_md/assets/168099471/d8221e68-9f5e-440a-b727-b8fd127f1ab1)
![WhatsApp Bild 2024-05-02 um 14 14 22_db8cc9f7](https://github.com/BowCraftGHG/git_md/assets/168099471/f8838b72-7398-4fe5-89d7-65e48e2bcb45)
![WhatsApp Bild 2024-05-02 um 14 15 04_f8bd5d84](https://github.com/BowCraftGHG/git_md/assets/168099471/99842cf9-300d-4fd5-b85e-f1c4d44d96d4)
![WhatsApp Bild 2024-05-02 um 14 15 24_a4c2bb47](https://github.com/BowCraftGHG/git_md/assets/168099471/15a90df8-acd2-407a-8979-55a12d3ed370)
![WhatsApp Bild 2024-05-02 um 14 15 51_5092c1e2](https://github.com/BowCraftGHG/git_md/assets/168099471/e4ae5b02-7e61-433b-8110-061b28fc9d68)
![WhatsApp Bild 2024-05-02 um 14 16 25_6deb97ae](https://github.com/BowCraftGHG/git_md/assets/168099471/dc11f06d-f695-4cfb-8fcd-64344bf8e3f5)
![WhatsApp Bild 2024-05-02 um 14 17 16_900eeadd](https://github.com/BowCraftGHG/git_md/assets/168099471/94e2cbce-3bb6-4723-943b-ba0619a251a6)
![WhatsApp Bild 2024-05-02 um 14 17 43_113832c6](https://github.com/BowCraftGHG/git_md/assets/168099471/dc990d41-27af-4798-aa60-55d57701bb44)
![WhatsApp Bild 2024-05-02 um 14 18 14_374c69b3](https://github.com/BowCraftGHG/git_md/assets/168099471/090ddad7-7ff4-41b6-a684-15b911b6ae20)
![WhatsApp Bild 2024-05-02 um 14 19 37_5316cf19](https://github.com/BowCraftGHG/git_md/assets/168099471/2557de54-66b3-4334-b709-2659f7020958)
![WhatsApp Bild 2024-05-02 um 14 19 40_bbd183f2](https://github.com/BowCraftGHG/git_md/assets/168099471/0b346030-0f97-4324-8a0f-217a9fc7398c)
![WhatsApp Bild 2024-05-02 um 14 19 42_906ca2b6](https://github.com/BowCraftGHG/git_md/assets/168099471/7a5343fe-0ed0-4a92-b910-d2562a035741)
![WhatsApp Bild 2024-05-02 um 14 20 24_5c264b35](https://github.com/BowCraftGHG/git_md/assets/168099471/59cc90ac-070c-4d0d-96a3-d81f6cbb42bb)


# Name und Email hinterlegen 
```bash
git config --global user.name "Name" 
git config --global user.email "Email"  
```
Diese Informationen werden genutzt um bei commits den Bearbeiter zu setzen.
 
# Account auf GitHub erstellen 
www.github.com 

# Login auf SSH umstellen 
## Schlüssel erzeugen
SSH-Key erzeugen und den Public key in GitHUB hochladen 
```bash
ssh-keygen –b 4096 
```
 
## SSH- key in der config hinterlegen 
In Datei: `.ssh/config` 
```bash
Host github.com 
  IdentityFile ~/.ssh/privatKeyForGitHub 
```

Wenn verschiedene keys verwendet werden sollen. Z.B. für Arbeitsrepos: 
Zusätzlich eintragen: 
```bash
Host github-work.com 
  Hostname   github.com 
  IdentityFile  ~/.ssh/privateKeyForGitHubWork 
```
Dann muss beim ersten `git clone` die Url github-work verwendet werden. Damit die Umleitung zum anderen Key funktioniert. 
```bash
git clone git@github-work.com:ACCOUNT/REPO.git 
```
 
# Repository auf SSH umstellen 
```bash
git remote set-url origin git@github.com:ACCOUNT/REPO.git 
```
 

 
