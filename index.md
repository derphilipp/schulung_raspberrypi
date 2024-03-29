name: inverse
layout: true
class: left, middle
---
# Raspberry Pi Grundlagen

Philipp Weißmann

[mail@philipp-weissmann.de](mailto:mail@philipp-weissmann.de)
---

# Agenda

---
## Agenda
- Hardware
- Betriebssystem
- Inbetriebnahme
- Systemprogramme
- Navigation im Dateisystem
- Installation von Programmen
- Netzwerkkonfiguration
- Weiteres

---

# Hardware

---

## Varianten
Der Raspberry Pi hat 5 "normale" Ausführungen:

Feature/ Modell | A      | B      | B+       | 2 B      |3 B       | Zero    | 4 B
----------------|--------|--------|----------|----------|----------|---------|-----
RAM (MB)        | 256    | 512    | 512      | 1024     | 1024     | 512     | bis 8 GB
USB Schnittst.  | 1      | 2      | 4        | 4        | 4        | 1 (1)   | 4 (3)
Ethernet-Port   | Nein   | Ja     | Ja       | Ja       | Ja (2)   | Nein    | Ja
Speichermedium  | SD     | SD     | Micro-SD | Micro-SD | Micro-SD | Micro-SD| Micro-SD
Pins            | 26     | 26     | 40       | 40       | 40       | 40      | 40
CPU             | 1      | 1      | 1        | 4        | 4        | 1       | 4
Architektur     | ARM11  | ARM11  | ARM11    | ARM A7   | ARMv8    | ARM11   | ARMv8
MHZ             | 700    | 700    | 700      | 900      | 1.200    | 1.000   | 1.500

Ergänzung:
    - (1): Micro USB; Bei W-Modell: Wifi
    - (2): Zudem: Wifi, Bluetooth 4.1
    - (3): Zudem: Wifi, Bluetooth 5.0
---
## Prozessoren
   - 700/1000 Mhz Arm11 (v6) Prozessor
   - 900 MhZ Arm A7 Prozessor, 4 Kerne oder
   - 1200 Mhz ArmV8 Prozessor, 4 Kerne
   - 1500 Mhz Cortex-A72 (ARM v8), 4 Kerne

   - GPU
     - OpenGL
     - H.264 En-/Dekodieren in Hardware
     - VC1 & Mpeg2 En-/Dekodieren in Hardware per Lizenz (kostenpflichtig)
---

## Anschlüsse 1

### Video
  - HDMI Ausgang (Zero: Mini-HDMI, ab 4: Micro-HDMI)
  - Composite-Video (ab B+: Nur per Klinkenstecker)

### Audio
  - Digital: Via HDMI
  - Analog: Klinkenstecker für Audio (nicht Zero)
---
## Anschlüsse 2
### Weitere
  - CSI: Kamera-Schnittstelle
  - 26 Pins (ab B+: 40)
    - Davon 17 Pins frei programmierbar
    - u.a. 5V, 3.3V, SPI, I2C und UART möglich

### Sonstiges
  - Stromversorgung: Micro USB. Empfehlung: 2 Ampere
  - Ab Rpi 3B: Mindestens 2 Ampere
  - Ab Rpi 3B+: Mindestens 2.5 Ampere
  - Ab Rpi 4B+: Mindestens 3 Ampere
  - LEDs für Netzwerkzugriff

### Beachtenswert
  - Keine Real-Time Clock
  - Kein An- oder Ausschalter
  - Keine A/D oder D/A Wandler
---
## Erweiterungen 1

### Raspberry Pi Camera Board
  - Photo-Auflösung bis 2592 x 1944
  - Video-Auflösung bis 1080p, 30 fps
  - Keine Schärfenstellung
  - Variante ohne Infrarot-Filter erhältlich (NoIR)

### Raspberrpi Display
  - Anschluss via Display Kabel, HDMI damit frei
  - 7 Zoll, 800x600 Pixel, 10 Finger kapazitiver Touch

### Gertboard
  - LEDs
  - Mehr Ein- und Ausgänge
  - u.a. A/D und D/A Wandler
---
## Erweiterungen 2
### IR Remote Control
  - Infrarot-Fernbedienung, per USB Anschluss

### USB Soundkarte
  - Für besseren Klang
---
## Erweiterungen 3

### Touchscreen
  - Per Anschluss auf Board
  - Per Anschluss auf GPIO
  - Per Anschluss USB + HDMI

### USB Wifi-Dongle
  - z.B. EDIMAX EW-7811UN Wireless USB Adapter
---
# Betriebssysteme
---
## Raspbian - heute "Raspberry Pi OS"
  - Linux
  - Aktuell: Debian 10 ("Buster")
  - Vorgänger: Debian 9 ("Stretch")
  - ca. 3 GB Image ("Light": Schmaler Platzbedarf, "Normal": GUI, "Full": Empfohlene Programme)
  - Basis für diesen Kurs
  - De-Facto Standard für die meisten Projekte
  - Download über Raspberry Pi Webseite
      - [https://www.raspberrypi.org/downloads/raspbian/](https://www.raspberrypi.org/downloads/raspbian/)
---
## Mehr Linux
- [RetroPi](https://retropie.org.uk/)
- [OpenSUSE](https://en.opensuse.org/openSUSE:Raspberry_Pi)
- [Kali Linux](http://de.docs.kali.org/armel-armhf-de/installation-von-kali-arm-auf-einem-raspberry-pi)
- [Pidora](http://pidora.ca/)
- [Ubuntu Mate](https://ubuntu-mate.org/raspberry-pi/)
- [Snappy Ubuntu Core](https://developer.ubuntu.com/en/snappy/start/#snappy-raspi2)
- [Manjaro Linux](https://manjaro.org/)
- u.v.m.
---
## Kodi: Multimedia
- Multimedia Software um den Raspberry Pi als Multimedia Rechner zu nutzen
- Varianten
  - [OpenELEC](http://openelec.tv/) (persönliche Empfehlung)
  - [OSMC](https://osmc.tv/)
  - [XBian](http://www.xbian.org/)
---
## Weitere Betriebssysteme
- [RISCO OS 5](http://www.raspberry-pi-geek.de/Magazin/2014/02/Workshop-RISC-OS-auf-dem-RasPi-Teil-1)
- [Plan 9](http://heise.de/-1761392)
- [FreeBSD](https://wiki.freebsd.org/FreeBSD/arm/Raspberry%20Pi)
- [NetBSD](http://wiki.netbsd.org/ports/evbarm/raspberry_pi/)
- [Android](https://groups.google.com/forum/#!forum/android-rpi)
- [Windows 10 IOT Core](http://ms-iot.github.io/content/en-US/Downloads.htm)
- [Windows 11 Preview](https://www.heise.de/news/Windows-11-laeuft-auf-dem-Raspberry-Pi-4-6127592.html)
---
## Sonstiges
- Image "NOOBS", installiert verschiedene Systeme auf Wunsch
  - [https://www.raspberrypi.org/downloads/noobs/](https://www.raspberrypi.org/downloads/noobs/)
- Durch Installer schauen und Images ausprobieren!

## Imager Software:
- [Raspberry Pi Imager, Empfehlung](https://www.raspberrypi.org/software/)
- [Balena Etcher](https://www.balena.io/etcher/)
---
# Alternativen zum Raspberry Pi
---
## Direkte Konkurrenz 1
- Banana Pi
- Cubieboard
- Beagleboard
- ...
---
## Direkte Konkurrenz 2
### Vorteile
- Mehr Speicher
- Schnellere CPU
- Mehr Schnittstellen

### Nachteile
- Nicht kompatibel zu Raspberry Pi
- Deutlich weniger Komponenten/Anleitungen/Bauteile verfügbar
- Höherer Preis
- Kleinere Community
- Weniger aktuelle Software (!)
---
## Arduino
### Unterschiede
- Raspberry Pi: Embedded Rechner mit "vollem" Linux
- Arduino: Soft- und Hardwareplattform für embedded-Entwicklung.

### Charakteristika
- Programmierung in C/C++, teilweise (Micro)python, Lua oder Javascript
- Kein "volles" Betriebssystem
- Kein kompletter Rechner, sondern embedded Plattform
- Sehr modular, oft sehr günstig
---

# Vorraussetzungen

---
## Notwendig zum Betrieb...
- Raspberry Pi
- Stromversorgung
- SD Karte / Micro SD Karte, >= 4 GB

---
## Optional zum Betrieb...
- Gehäuse
- Netzwerkkabel
- Tastatur
  - Tipp: Manche Tastaturen haben einen eingebauten USB Hub. Dieser kann einen hohen Stromverbrauch haben und damit den Raspberry Pi evtl. instabil machen
- Maus
- Bildschirm an HDMI oder Komponentenanschluss
- USB Hub mit seperater Stromversorgung
---
# Installation und erster Login
---
## Bootvorrausetzungen
- Raspberry Pi hat kein klassisches BIOS
- Ohne Betriebssystem bleibt der Pi stumm
- Pi kann nur von SD Karte booten (kein USB!)
- Seit Raspberry Pi 4: Booten von USB nach Firmware update möglich

## Start von SD
- Auf die SD Karte kommt ein startfähiges System
- Später: Keine Installationsprozess, nur Anpassung des Systems
- Schreiben von "Image" auf SD Karte notwendig
- Flash-Programm notwendig (je nach Betriebssystem)
---
## SD Karte vorbereiten
- System auf SD Karte schreiben
- Dies überschreibt die gesamte SD Karte!
- Damit wird SD Karte bootfähig
- Achtung: SD Karte nich einfach formatieren und Image kopieren!
- Flash-Programm notwendig (Profis: `dd`)
  - Kann Images auf SD Karte schreiben
  - Kann aus SD Karte Image erstellen (z.B. für Backup oder Klon)
---
## SD Karte schreiben
### Ablauf
1. Image herunterladen (z.B. Raspbian)
2. Flash-Programm starten
3. SD Karte einlegen
4. Inhalt prüfen: Sind wichtige Daten vorhanden?
5. Nochmal: Sind nicht vielleicht doch wichtige Daten vorhanden?
6. SD Karte beschreiben
7. SD Karte "auswerfen" (*unmount*, je nach Betriebssystem/Programm)
8. SD Karte entfernen
---
## SD Karte einlegen
### Ablauf
1. Gerät stromlos machen
2. Einlegen der SD Karte
3. Notwendige Kabel anschließen
4. Gerät an Strom nehmen

### Hinweis
Vor dem Ausschalten sollte das Betriebssystem zuvor heruntergefahren werden
---
## Jessie vs. Wheezy
- Wheezy: Starten auf Konsole
- Jessie: Starten auf grafischer Oberfläche
---
## Erster Start von Raspbian
- Hinweis: Wenn zum Zeitpunkt des Bootens kein HDMI Bildschirm angeschlossen ist, wird Composite benutzt.
- System zeigt Betriebssystem-Informationen an
- System startet das Systemprogramm "raspi-config"
- Mindestens sollte das System-Image auf die Größe der SD-Karte angepasst werden:
  - "Resize Filesystem"
- Nach den Einstellungen muss das System neugestartet werden (Akzeptieren)

---

## Login (weitere Starts)
- Vor dem Login-Prompt werden Prozesse gestartet
- Benutzername: `pi`
- Passwort: `raspberry` (Achtung: `y` vs. `z`)
- Hinweis: Die Passworteingabe erfolgt verdeckt mit Sternchen
- Achtung: Wenn Sie im vorherigen Schritt nicht das Tastaturlayout geändert haben, nutzen Sie jetzt ein Britisches Tastaturlayout. Für das Passwort tippen Sie dann `raspberrz`

---

# Grundlagen des Systems
---

## man 1
Der erste und wichtigste Befehl ist `man`.

`man` ruft die Hilfeseite eines Programms auf, falls diese installiert ist. Für praktisch alle aus dem Repository installierten Programme ist dies der Fall.

Beispiele:
  - `man man`
  - `man ls`

(Hinweis: Programm beenden mit `q`)
---
## man 2
Weitere Hinweise:
- Sehr viele Programme beherrschen die Kommandozeilenoption `--help` . Hiermit wird die Benutzung bzw. die Aufrufparameter des Programms detailliert erklärt.
- Beispiel: `man --help`
- Bei mehrdeutigen Befehlen (z.B. `printf`) muss die Kategorie der Hilfsseite angegeben werden (siehe `man man`):
  - `man 3 printf` gibt die Hilfeseite der C-Funktion *printf*
  - `man 1 printf` gibt die Hilfeseite des Kommandozeilenbefehls *printf*
---
## sudo
- Der Benutzer *pi* hat Rechte als superuser (meist 'root') zu agieren.
- Um einen Befehl mit höheren Rechten auszuführen, kann man diesen mit dem Befehl `sudo` ausführen
- Beispiel: `raspi-config` wird zu `sudo raspi-config`
---
## Softwarerepository
- Unter Raspbian werden Programm üblicherweise aus einem zentralen Repository (=Quelle) installiert
- Diese sollten immer wieder aktualisiert werden um Patches einzuspielen
- Das Repository enhält neben Systemprogrammen extrem vieles: Editoren, Compiler, Spiele, Office-Programme, Serverdienste, usw.
---
# Navigation im Dateisystem
---
## ls

ls |               | Listet Dateien und Verzeichnisse auf
---|---------------|-------------------------------------------------
   | `ls /home/pi` | ... im Verzeichnis /home/pi
   | `ls -a`       | ... inklusive versteckter Dateien/Verzeichnisse

---

## cd

 cd    |                 | Wechselt in das gegebene Verzeichnis
-------|-----------------|----------
       | `cd /home/pi`   | Wechselt nach /home/pi
       | `cd`            | Wechselt in das Benutzerverzeichis

---
## pwd
 pwd   |               | Gibt das gegenwärtige Verzeichnis aus
-------|---------------|--------------------------------------------------
       | `pwd`         |

---
## mkdir, rmdir

 mkdir |               | Legt ein Verzeichnis an
-------|---------------|--------------------------------------
       | `mkdir hello` | Legt das Verzeichnis *hello* an



 rmdir |               | Löscht ein leeres Verzeichnis
-------|---------------|---------------------------------------
       | `rmdir hello` | Löscht das leere Verzeichnis *hello*
---

## rm
 rm |                 | Löscht eine Datei
----|-----------------|-----------------------------
    | `rm mysong.mp3` | Löscht die Datei *mysong.mp3*
    | `rm -r vz`      | Löscht das Verzeichnis *vz* und alle Dateien darin
---
## touch
 touch |                   | Lege Datei an oder setze ihr Änderungsdatum auf *jetzt*
-------|-------------------|--------------------------------
       | `touch hello.txt` | ... der Datei *hello.txt*
---
## du, df
 du |                   | Gibt den Speicherverbrauch einer Datei / eines Verzeichnisses aus
----|-------------------|--------------------------------------------
    | `du mysong.mp3`   | Gib Speicherverbrauch von *mysong.mp3* aus
    | `du -h mysong.mp3`| Gibt den Speicherverbrauch von *mysong.mp3* menschenlesbar aus (Einheiten wie MB, GB)


 df |               | Gibt den verfügbaren/benutzten Speicher der eingebundenen Geräten aus
----|---------------|--------------------------------------------
    | `df -h`         | ... menschenlesbar (Einheiten wie MB, GB)
---

# Im Dateisystem
---
## Allgemeines
- Unter Linux/Unix/OS X gibt es keine Laufwerksbuchstaben
- Es gibt einen Verzeichnisbaum für alles
- Speicherorte (z.B. Festplatten, Netzwerk-Freigaben, USB-Sticks) können in den Baum eingehängt werden
---
## Übersicht 1
 Ort     | Beschreibung
---------|---------------------------------------------------------
 `/`     | Erste Hierarchiebene
 `/bin`  | Executables von Basis-Werkzeugen
 `/sbin` | Executables von Basis-Werkzeugen, auch bei unvollständigem Booten vorhanden
 `/lib`  | Bibliotheken für Programme in /bin und /sbin
 `/opt`  | Optionale Software Pakete
 `/boot` | Daten zum Booten des Systems (z.B. Kernel)
 `/home` | Verzeichnisse der Benutzer des Systems, z.B. */home/pi*
 `/root` | Verzeichnis des Benutzers *root*

---
## Übersicht 2

 Ort          | Beschreibung
--------------|-----------------------------------------------------
 `/etc`       | Konfigurationsdaten für Systemeinstellungen und Dienste
 `/mnt`       | Üblicher Ort um Dateisysteme (temp.) einzubinden
 `/media`     | Üblicher Ort um Wechseldatenträger einzubinden
 `/usr`       | Zweite Hierarchiebene, Pfad für weitere Programme. Es gibt viele Pfade nochmals unter `/usr`, z.B. `/usr/bin`, `/usr/lib`, ...
 `/usr/local` | Dritte Hierarchiebene, Pfad für weitere Programme. Empfehlung: Programme, die man manuell installiert, hierhin installieren

---
## Übersicht 3
 Ort           | Beschreibung
---------------|--------------------------------------------------
 `/dev`        | Virtuelles Dateisystem: Enthält Geräte (Devices)
 `/sys`        | ... Enthält Systeminformationen
 `/proc`       | ... Enthält Prozessinformationen
 `/run`        | ... Systeminformationen seit dem letzten Boot
 `/srv`        | Daten, die von System *geserved* werden
 `/tmp`        | Temporäre Dateien
 `/var`        | Dateien variabler Größe,  z.B. Mailqueues, Logdaten, usw.
 `/lost+found` | Ort für wiederhergestellte Dateien

---

## Besondere Ordner

- Reale und virtuelle Geräte sind Verzeichnisse/Dateien.
- Beispiele:
  - Partition 1 von IDE Festplatte ist `/dev/hda1`
  - `/dev/null` enthält *null*
  - `/dev/rand` enthält Pseudo-Zufallswerte
- Geräte werden durch Treiber (automatisch) eingebunden

---

## Rechte
### Konzepte
- Benutzer sind natürliche oder virtuelle Benutzer
- Nicht jeder Benutzer kann sich anmelden
- Dienste laufen oftmals als spezialisierter Benutzer
- Ein Benutzer kann beliebig vielen Gruppen zugehörig sein

---

### Besitzer

- Eine Datei/Verzeichnis hat 3 Rechte:
  - Für den Besitzer (user)
  - Für die Gruppe (group)
  - Für alle anderen (others)

- Ändern der Zugehörigkeit einer Datei/VZ zu...
  - Besitzer: `chown`
  - Gruppe: `chgrp`

- Beispiele:
  - `chown jens meinprogramm`
  - `chgrp buchhaltung jahresplan.csv`
---
### Dateirechte 1

- Für ...
  - Besitzer (*User*): *u*
  - Gruppe (*Group*): *g*
  - Andere (*Others*): *o*
- Welches Recht...
  - Lesen (*Read*): *r*
  - Schreiben (*Write): *w*
  - Ausführen (*eXecutable): *x*
---
### Dateirechte 2
- Anzeigen: `ls -l`
- Ändern der Rechte einer Datei: `chmod`

- Beispiele:
  - `chmod u+x meinprogramm`
  - `chmod g+rw unser_projekt.txt`
  - `chmod o-r mein_tagebuch.txt`
- Hinweis:
  - Unter erfahrenen Benutzern ist oftmals die Oktal-Notation genutzt, z.B. `chmod 750 meinprogramm`
---
# Systemprogramme
---
## Verschiedenen Systemprogramme 1
 `raspi-config` | Programm zur Verwaltung der grundliegenden Funktionalitäten des Raspberry Pi. Wird beim ersten Booten gestartet
----------------|--------------------------------------------
                | Hinweis: Root Rechte erforderlich!

Hinweis: Seit Version "Jessie" auch mit grafischer Oberfläche
---
## Verschiedenen Systemprogramme 2
 apt-get                | Programm zur Verwaltung, De- und Installation von Softwarepaketen
------------------------|-----------------------------------------
 `apt-get update`       | Aktualisiert die Liste der verfügbaren Software (z.B. neue Softwarepakete, aktualisierte Softwarepakete)
 `apt-get upgrade`      | Aktualisiert die auf dem System vorhandenen und installierten Programme
 `apt-get dist-upgrade` | Wie "apt-get upgrade", löst jedoch zusätzlich Abhängigkeiten auf und deinstalliert evtl. nicht mehr benötigte Bibliotheken. Tipp: Dann benutzen, wenn `apt-get upgrade` Pakete "zurückhält"
 `apt-get install FOO`  | Installiert Paket "FOO" und alle dazu notwendigen Vorraussetzungen
 `apt-get remove FOO`   | Deinstalliert das Paket "FOO", Konfiguration verbleibt jedoch auf dem System
 `apt-get purge FOO`    | Deinstalliert das Paket "FOO" und entfernt auch alle Konfigurationsdateien

---

## Verschiedenen Systemprogramme 3
### Jessie und spätere (systemd basiert)
 systemctl                  | Verwaltet Systemdienste
----------------------------|------------------------------
 `systemctl status nginx`   | Zeigt den Status des Dienstes *nginx*
 `systemctl start nginx`    | Startet den Dienst *nginx*
 `systemctl stop nginx`     | Stoppt den Dienst *nginx*
 `systemctl restart nginx`  | Neustart des Dienstes *nginx*
 `systemctl enable nginx`   | Startet den Dienst *nginx* beim Systemstart
 `systemctl disable nginx`  | Startet den Dienst *nginx* nicht (mehr) beim Systemstart

---
## Verschiedenen Systemprogramme 4
### Wheezy (init)
 service                 | Startet und Stoppt Dienste
-------------------------|------------------------------
 `service nginx stop`    | Stoppt den Dienst *nginx*
 `service nginx start`   | Startet den Dienst *nginx*
 `service nginx restart` | Neustart des Dienstes *nginx*


 update-rc.d                  | Konfiguriert, welche Dienste beim Systemstart gestartet werden
------------------------------|------------------------------
 `update-rc.d nginx defaults` | Startet den Dienst *nginx* beim Systemstart (Webserver)
 `update-rc.d nginx disable`  | Startet den Dienst *nginx* nicht (mehr) beim Systemstart
---

## Verschiedenen Systemprogramme 6
 `reboot`          | Startet das System neu
-------------------|---------------------------------------------
 `shutdown`        | Zum Herunterfahren / Neustarten des Systems
 `shutdown now -h` | Fahre das System jetzt herunter und bleibe dann stehen (kein Neustart)

---

## Verschiedenen Systemprogramme 7
 passwd      | Setzt das eigene Passwort / das Passwort eines anderen Benutzers neu
-------------|-------------------------------------------
 `passwd`    | Setze mein Passwort neu
 `passwd pi` | Setzt das Passwort des Benutzers *pi* neu

---

# SSH
---
## Motivation
- Gerät wird oftmals verbaut (Garage, Schrank, ...)
- Zugriff aus der Ferne
- Zugriff: SSH
- Verschlüsselt, sicherer Zugriff auf System
- Läuft als Dienst (default: An)
- Verschiedene Authentifizierungsmöglichkeiten, z.B.
  - Passwort
  - Private / Public Key
- Windows-Client: putty
- Login: Wie Benutzer (siehe *Login*)

---
- Die hier genannten Verfahren sind eventuell nicht mehr sicher wenn Sie dieses Dokument lesen
## Warnung
- Konsultieren Sie bei Sicherheitsfragen Spezialisten
- Halten Sie ihr System aktuell und spielen Sie Sicherheitspatches ein
- Machen Sie dezentrale, verschlüsselte Backups
- Verschlüsseln Sie Sicherheitskritische Daten sicher
- Kein System ist unangreifbar

---

## Login ohne Passwort 1
  - Schlüssel erzeugen (neue Anleitung):
    - Windows/MacOS/Linux: `ssh-keygen -t ed25519
  - Schlüssel erzeugen (alte Anleitung):
     - [Putty Key Generator](http://www.chiark.greenend.org.uk/~sgtatham/putty/download.html) starten
     - "Numbers of bits in a generated key" sollte mindestens 2048 betragen
     - Generate Key
     - Save private key (speichern als `id_rsa`)
     - Save public key (speichern als `id_rsa.pub`)

  - Auf Server Schlüssel eintragen
     - Auf lokalem Rechner:
       - Text von Schlüssel in Zwischenablage kopieren (*Public key for pasting...*)
     -  Auf SSH Server (Raspberry Pi):
       - Verzeichnis anlegen
       - `mkdir ~/.ssh/`
       - Datei authorisierter Schlüssel editieren
       - `nano authorized_keys`
       - Am Ende der Datei Inhalt aus Zwischenablage einfügen
       - Datei speichern

---
## Login ohne Passwort 2
  - Via Windows SSH:
    - `ssh pi@IP_ADRESSE`
    - Alternativ: `config` Datei in `.ssh` ändern
  - Via Putty:
    - In Putty eintragen
      - Menüpunkt *Connection -> SSH -> Auth*
      - In *Private key file for authentication* gespeicherte Datei z.B. `id_rsa` eintragen
      - Unter *Session* Servername eintragen (optional: `Benutzername@Servername` übergibt Benutzernamen sofort)
      - Namen (*Saved Sessions*) vergeben und mit *Save* speichern
    - Bei jedem weiteren Öffnen von Putty: Doppelklick auf Servername
---
## Login ohne Passwort 3
### Hinweise:
  - Private Key *sicher* aufbewahren!
  - Man kann dem Private Key eine *Passphrase* vergeben, damit ist ein Passwort zur Nutzung des Schlüssels notwendig
  - Dies macht ein Passwort wieder notwendig, aber erhöht die Sicherheit
  - Möglich: Serverseitig Login mit Passwort komplett deaktivieren
---
# Netzwerk-Einstellungen
---
## Netzwerk 1
- Achtung: Bitte die aktuelle Nutzung von DHCPCD diesen beenden oder auf statische IP Konfigurieren
- Neuere Versionen:
- IP-Einstellungen finden sich unter `/etc/dhcpcd.conf`
- Öffnen also z.B. mit `nano /etc/dhcpcd.conf`
- Danach Dienst neu starten

---
### Inhalt neu (statisches Beispiel)
```
interface enxb827ebd19329
static ip_address=192.168.1.30
static routers=192.168.1.1
static domain_name_servers=8.8.8.8,192.168.1.30
```

---
### Inhalt alt
```
iface lo inet loopback
iface eth0 inet dhcp
```

### Bedeutung
 Bestandteil | Erklärung
-------------|-------------------------------------------
 iface       | Interface
 lo          | *Loopback*:  Dies ist ein Netzwerkgerät für Netzwerkkommunikation, die den Rechner nicht verlässt.
 inet        | Ip-Netzwerk (IPv4)
 loopback    | Betreibe es als Loopback-Device
 eth0        | Name des Geräts, hier: *eth0* für *Ethernet, Gerät Nummer 0*
 dhcp        | Benutze DHCP, d.h. beziehe IP-Adresse von DHCP Server (oft: Router)
---

## Netzwerk 4
### Feste IP-Adresse
```
iface lo inet loopback
iface eth0 inet static
address 192.168.1.150
netmask 255.255.255.0
gateway 192.168.1.1
```
### Bedeutung
 Bestandteil | Erklärung
-------------|---------------------------------------------------
 static      | Benutze eine fest zugewiesene IP-Adresse
 address     | Setze das Device auf diese IP Adresse
 netmask     | Setze das Device auf diese Netzmaske
 gateway     | Setze das Device auf diesen Gateway (oft: Router)
---

# Mounten
---
## Mounten
- Laufwerke und Netzdienste bekommen unter Linux/Unix/OS X keinen Laufwerksbuchstaben
- Statt Laufwerksbuchstaben werden diese in das vorhandene Dateisysten eingebunden
- Beispiele:
  - `mount` gibt die aktuell eingebundenen Pfade aus
  - `mount /dev/sda1 /mnt/meinUSBStick` bindet das Gerät mit der Adresse */dev/sda1* im Verzeichnis */mnt/meinUSBStick* ein
  - `umount /mnt/meinUSBStick` wirft das Gerät aus, welches bei */mnt/meineUSBStick* eingebunden ist
- Die Datei `/etc/fstab` beschreibt die automatische Einbindung von Geräten beim Systemstart
---

# SMB Share
---
## SMB 1
- *Windows Freigaben* sind im *SMB-Protokoll* implementiert
- Dies ist auch unter dem Pi möglich
- Wir richten eine Freigabe ein
---
## SMB 2
- Software installieren
  - `sudo apt-get install samba samba-common-bin`
- Samba konfigurieren
  - `sudo nano /etc/samba/smb.conf`
  - Ersetzen:
    `# Security = user`
  durch
    `Security = user`
- Benutzer für Windows-Freigaben anlegen
  - Achtung: Der User ist nicht der Raspberry-Pi User!
  - `sudo smbpasswd -a pi`
---
## SMB 3
- Rechte auf Freigabe setzen
  - (Beispiel hier: USB-Stick/Festplatte an /media/usb1)
  - Ändere das Besitztum rekursiv auf den Benutzer *pi*, die Gruppe *pi* - von folgendem Verzeichnis: */media/usb1*
  - `sudo chown -R pi:pi /media/usb1`
- Freigabe einrichten
  - `sudo nano /etc/samba/smb.conf`
  - Folgendes Eintragen:
```
[MeineFreigabe]
path = /media/usb1
writeable = yes
guest ok = no
```

  - Anmerkung:
`guest ok = yes`
lässt auch Gastbenutzer zu
---
## SMB 4
- Optional: Andere Arbeitsgruppe festlegen
  - `sudo nano /etc/samba/smb.conf`
  - Folgendes ersetzen:

    `workgroup = WORKGROUP`

    mit

    `workgroup = MEINEARBEITSGRUPPE`
- Dienst (neu)starten:

   `sudo systemctl restart samba`

   bzw.

   `sudo service samba restart`
---
# Cronjob
---
## Cronjob 1
- Sollen Aufgaben regelmässig ausgeführt werden, erfolgt dies i.d.R. per *Cronjob*
- Anlegen eines Cronjobs:
  1. Einloggen, als Benutzer, unter dem der Job laufen soll
  2. `crontab -e`
      - Öffnet eine Cron-Datei mit dem Editor;
      - Meldet beim Beenden falls Fehler vorliegen
  3. Job eintragen
  4. Editor beenden
---
## Cronjob 2
### Syntax mit Beispielen

 Min.       | Std. | Tag | Mon | WTag | Befehl
------------|------|-----|-----|------|------------------------
 42         |    4 | *   | *   | *    | `rm -rf /tmp/temp.jpg`
 *          |    * | *   | *   | *    | `ping -c1 google.com`
 0,15,30,45 | 7-20 | *   | *   | *    | `/home/pi/myscript.sh`

### Was tut was?
1. Lösche jede Nacht um 4 Uhr 42 die Datei */tmp/temp.jpg*
2. Sende jede Minute einen(!) Ping an *google.com*
3. Starte zwischen 7 und 20 Uhr  alle Viertelstunde das Skript */home/pi/myscript.sh*
---

# Supervisor
Anmerkung: Für Wheezy interessant, Ab Jessie, etc.: Systemd Skripte schreiben
---
## Supervisor
### Selbstgeschriebene Programme bei Systemstart starten
- Nach Neustart soll Programm gestartet werden
- Bei Fehler soll Programm neugestartet werden
- Bei anhaltenden Fehlern soll Programm deaktiviert werden
---
## Lösung 1
### Programm initial mit System starten
- Programm initial mit System starten
  - `/home/pi/myprogram.sh`
- Nachteil: Bei Programmfehler kein erneuter Start
- Nachteil: Nicht standardisiert
---
## Lösung 2
### Programm in Endlosschleife mit System starten
- Programm in Endlosschleife mit System starten
```bash
while true
    do /home/pi/myprogram.sh
done
```
- Nachteil: Bei Programmfehler endlose Produktion von Fehlermeldungen
- Nachteil: Nicht standardisiert
---
## Lösung 3
### Init-Skript selbst schreiben
- Init-Skript selbst schreiben
- Sehr gut integriert
- Nachteil: Fuer Unerfahrene schwer zu schreiben und fehleranfällig
- Hinweis: Mit *systemd* extrem einfach
---
## Lösung 4
### Programm Supervisor
- Startet bei Systemstart eigene Programme
- Bei Programmfehler: erneuter Start
- Bei stetigem Abbruch: Beenden von Programm
---
## Nutzung 1
### Installation
- `apt-get install supervisor`
### Erstellen von Eintrag
- `nano /etc/supervisor/conf.d/myprogram.conf`
### Konfigurationsdatei

```conf
[program:myprogram]
command = /home/pi/myprogram.sh
directory = /home/pi
user = pi
environment=HOME="/home/pi", USER="pi"
```
---
## Nutzung 2
### Dienst aktivieren, starten
- Siehe Kapitel!
- `update-rc.d supervisor defaults`
- `service supervisor start`
- Tipp: Restart: `service supervisor restart`
---
## Nutzung 3
### Supervisorctl Dienstübersicht
- `supervisorctl status`
### Supervisorctl Dienst starten
- `supervirsorctl start myprogram`
### Supervisorctl Dienst neu starten
- `supervisorctl restart myprogram`
### Supervisorctl Dienst stoppen
- `supervisorctl stop myprogram`
---
## Nutzung 4
### Supervisorctl Dienst löschen
- `supervisorctl remove myprogram`
### Supervisorctl Dienst (wieder) hinzufügen
- `supervisorctl add myprogram`
---
# Kontakt:
- Philipp Weißmann
- [mail@philipp-weissmann.de](mail@philipp-weissmann.de)