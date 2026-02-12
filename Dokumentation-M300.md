# 10 - ToolUmgebung
## 01 - GitHub Account
### Account + Repository erstellen

Zu aller erste erstellen wir unseren Github Account und erstelle dann unser erstes Projekt darin. Auf der Willkomensseite können wir ein Projekt  mit **"Start a project"** erstellen. Dann definieren wir einen Namen wie als bsp. M300-Services, optionalerweise kann man auch eine Beschreibung hinzufügen. Dann gehen wir weiter zu den Buttons, dort lassen wir denn Radio Button auf Public sodass andere Personen unsere gepushten Files anschauen können. Denn Haken bei **"Initialize this repository with a README"** setzen sodass man mahl das Base File hat. Dann nach kann man das Repository erstellen.

### SSH-Key erstellen (lokal)

Wenn noch nicht vorhanden Git/Bash installieren, dies ist eine Shell von Linux welche wir brauchen zum weiter arbeiten. Alternativ kann auch im Windows Powershell gearbeitet werden, ich habe hier mit Git/Bash gearbeitet.

| Befehl                                                                                                          | Erklärung                                          |
| --------------------------------------------------------------------------------------------------------------- | -------------------------------------------------- |
| $  ssh-keygen -t rsa -b 4096 -C "xxx@gmail.com"                                                                 | Account Email von Github einfügen                  |
| Generating public/private rsa key pair.                                                                         | SSH-Key wird erstellt                              |
| Enter a file in which to save the key (~/.ssh/id_rsa): [Press enter]                                            | Name für Speicherung festlegen, Enter für Standard |
| Enter passphrase (empty for no passphrase): [Passwort]<br>  Enter same passphrase again: [Passwort wiederholen] | Passwort festlegen für den Key                     |

![](Pastedimage20260210085701.png)

### SSH-Key dem SSH-Agent hinzufügen

Nun brauchen wir den SSH Key welchen wir oben erstellt haben und kopieren ihn. Wir brauchen Ihn für den nächsten Schritt.

ssh-rsa AAAAB3NzaC1yc2EAAXXXXX......................== [grundlfelicitas08@gmail.com](mailto:grundlfelicitas08@gmail.com)

### SSH-Key hinzufügen

Jetzt brauchen wir wieder unser Github Konto, auf dem gehen wir jetzt auf unser Konto und rufen dann die **Settings** auf. Dann wechseln wir in dem Menubereich auf den Abschnitt **SSH und GPG keys**. Dann erstellen wir einen neuen SSH Key, im Fomular vergeben wir Titel und Bezeichnung. Dann fügen wir denn oben kopierten SSH Key ein und speichern den SSH Key ab.


![](Pastedimage20260210094638.png)

## 02 - Git Client

Damit alles lokal gespeichert werden kann muss der **Git Client** installiert werden, der ermöglicht dann die Repositories sich zu klonen, zu pushen und zu pullen.

### Client installieren + konfigurieren
Die Installation herunterladen und durch klicken bis es fertig ist, nacher öffnen. Nacher müssen wir noch das Git konfigurieren mit den Infos des GitHub-Accounts.

| Befehl                                             | Erklärung       |
| -------------------------------------------------- | --------------- |
| $ git config --global user.name "< xxx >"          | Username konfig |
| $ git config --global user.email "<xxx@gmail.com>" | Mail Konfig     |

![](Pastedimage20260210095613.png)

*Fehler: aufpassen wenn man den Code kopiert das man die $ nicht mitnimmt*

### Repository klonen

Zum testen klonen wir jetzt ein Repository.

| Befehle                            | Erklärung                                    |
| ---------------------------------- | -------------------------------------------- |
| $ git clone https://gitlab.com/xxx | Repository klonen                            |
| $ cd M300                          | Ins Verzeichnis wechseln                     |
| $ git pull                         | Repository aktualisieren                     |
| $ git status                       | Repository Überprüfung mit dem Origin/Master |


![](Pastedimage20260210100111.png)
![](Pastedimage20260210100128.png)

### Repository herunterladen & aktualisieren (clone/pull)

| Befehle                                            | Erklärung                 |
| -------------------------------------------------- | ------------------------- |
| $ cd xxx<br>                                       | Ins Verzeichnis wechseln  |
| $ mkdir xxx                                        | Ordner erstellen          |
| $ git clone git@github.com:<Mein Name>/my_M300.git | Repository mit SSH klonen |
| $ git pull                                         | Repository aktualisieren  |

![](Pastedimage20260210102759.png)

### Repository hochladen (Push)

| Befehle               | Erklärung                     |
| --------------------- | ----------------------------- |
| $ cd xxx              | Ins Verzeichnis wechseln      |
| $ git add -A .        | Dateien dem Upload hinzufügen |
| $ git commit -m "xxx" | Upload commiten               |
| $ git push            | Upload pushen                 |

![](Pastedimage20260210103224.png)

### Übersicht "How to Push"

| Befehle                | Erklärung                                             |
| ---------------------- | ----------------------------------------------------- |
| $  cd xxx              | Ins Verzeichnis wechseln                              |
| $  git status          | Veränderte Dateien werden rot angezeigt               |
| $  git add -A          | Dateien werden zum Uplode hinzugefügt                 |
| $  git status          | Dateien sollten grün sein, alles ist ready zum upload |
| $  git commit -m "xxx" | Upload wird commitet                                  |
| $  git status          | Datein sind zum pushen bereit                         |
| $  git push            | Dateien werden gepusht                                |

## 03 - Virtualbox

Virtualisierung von Computersystemen, dazu gibt es viele Möglichkeiten wir nutzen hier jetzt mal Virtualbox.

### Software herunterladen/installieren + ISO Datei herunterladen

Zuerst müssen wir uns Virtualbox herunterladen und danach die Installation durchklicken. Danach müssen wir die ISO noch herunterladen, wir nehmen Ubuntu Desktop. Auch herunterladen und abspeichern. Nacher weiter gehen zu VM erstellen.

### VM erstellen

Jetzt erstellen wir die VM, wichtig ist das man alle Infos schon von Anfang hat sodass die Erstellung einfacher ist.

| Bild Beispiel                      | Was tun                                                  |
| ---------------------------------- | -------------------------------------------------------- |
| ![](Pastedimage20260210104554.png) | VM Name festlegen / Speicherort / ISO Datei angeben      |
| ![](Pastedimage20260210104606.png) | Benutzername / Passwort / Hostname / Domainame   angeben |
| ![](Pastedimage20260210104620.png) | Speicher / CPUs / Grösse angeben                         |
| ![](Pastedimage20260210104627.png) | Kontrolle                                                |
| ![](Pastedimage20260210104634.png) | VM starten, kann lange dauern                            |
| ![](Pastedimage20260210104642.png) | VM beendet letzte Einstellungen                          |
| ![](Pastedimage20260210104651.png) | Fertig, VM ist ready                                     |

### VM einrichten

Die VM ist jetzt fertig und ready zum genutz werden. Hier arbeiten wir weiterhin mit dem Terminal (Bash).

| Befehle                                   | Erklärung                                               |
| ----------------------------------------- | ------------------------------------------------------- |
| $  sudo apt-get update   <br><br><br><br> | Update liste aufrufen                                   |
| $  sudo apt-get upgrade                   | Bereits installierte Pakete werden auf Upgrades geprüft |
| $  sudo reboot                            | Neustart                                                |
| $  sudo apt-get install xxx               | App / Programm installieren                             |

Zuerst installieren wir Synaptic über Bash danach starten wir denn Synaptic Package Manger und starten ihn. Dann suchen wir innerhalb des Synaptic Package Manger nach apache oder auch dem Webserver Programm, und installieren ihn. Danach ein System Neustart durchführen. Dann im Web Browser mit http:127.0.0.01:80 (localhost) testen ob er erreichbar ist. Nacher VM wieder herunterfahren.


![](Pastedimage20260210125651.png)
![](Pastedimage20260210125703.png)
![](Pastedimage20260210125728.png)
![](Pastedimage20260210125738.png)
![](Pastedimage20260210125817.png)

*Fehler: Aufpassen mit https und http*
## 04 - Vagrant


Da Virtualbox relativ lang dauert und es einige Möglichkeiten gibt wie es einfacher ist, nehmen wir noch einen leichtere und schnellere Option. Hier kommt Vagrant ins Spiel.

### Software herunterladen / installieren + VM erstellen

Wir laden die Anwendung wieder von der Webseite herunter und gehen die Installation durch. Nacher erstellen wir unsere erste VM in Vagrant.

| Befehle                            | Erklärung                |
| ---------------------------------- | ------------------------ |
| $ cd xxx<br>                       | Ins Verzeichnis wechseln |
| $ mkdir xxx                        | Ordner erstellen         |
| $ vagrant init ubuntu/xenial64     | Vagrantfile erstellen    |
| $ vagrant up --provider virtualbox | VM erstellen + starten   |

VM ist nun in Betrieb und kann via SSH Zugriff bedient werden.

| Befehle             | Erklärung                |
| ------------------- | ------------------------ |
| $ cd xxx/Vagrant-VM | Ins Verzeichnis wechseln |
| $ vagrant ssh       | SSh verbindung zur VM    |

![](Pastedimage20260210131347.png)
![](Pastedimage20260210131407.png)
![](Pastedimage20260210131413.png)

### VM erstellen (Vagrant Box auf Netzwerkshare)

| Befehle                            | Erklärung                |
| ---------------------------------- | ------------------------ |
| $ cd xxx<br>                       | Ins Verzeichnis wechseln |
| $ mkdir xxx                        | Ordner erstellen         |
| $ vagrant init ubuntu/xenial64     | Vagrantfile erstellen    |
| $ vagrant up --provider virtualbox | VM erstellen + starten   |
| $ cd xxx/Vagrant-VM                | Ins Verzeichnis wechseln |
| $ vagrant ssh                      | SSh verbindung zur VM    |
Schlussfolgerung keinen Unterschied zum ersten.
![](Pastedimage20260210131705.png)

### Apache Webserver automatisiert aufsetzen

Um den Automatisierungsgrad hervorzuheben, erstellen wir eine VM die mit einem Apache Webserver startet.

| Befehle              | Erklärung                |
| -------------------- | ------------------------ |
| $ cd xxx             | Ins Verzeichnis wechseln |
| $ vagrant up         | VM starten               |
| $ vagrant destroy -f | VM löschen               |

Nachdem wir die VM geöffnet haben schauen wir auf http://127.0.0.01:8080 (localhost) ob die Webseite erreichbar ist. Nacher noch probiern etwas zum ändern zum die Veränderung zu sehen. Anschliessend wieder löschen.

![](Pastedimage20260210132456.png)
![](Pastedimage20260210132512.png)
![](Pastedimage20260210132519.png)

## 05 - Visual Studio Code


Als nächstes brauchen wir eine Entwicklungsumgebung die es ermöglicht alle Repositories an einem Ort zu verwalten. Genau das ermöglicht Visual Studio Code. Dies haben wir bereits mehrfach im Unterricht verwendet. Zusätzliche Extensions noch installieren.

### Einstellungen anpassen

Unter File > Preferences > Settings (Ctrl +, ) auf Open Settings klicken. Zu dem Abschnitt mit "Configure glob Patterns..." den nachstehenden Code einfügen und speichern.


![](Pastedimage20260210133103.png)

### Repository hinzufügen und pushen

Eine Datei fertig bearbeiten, mit ctrl + s speichern, dann in der linken Seite das Symbol mit einer 1 aufrufen. Im Abschnitt "Changes" die files stagen (aufs + drücken) dann eine Naricht hinter lassen bsp was für ein commit es ist. (Bsp Test01Speicher) Nacher commiten und bei den 3 Punkten pushen, warten bis alle Dateien vollständig gepusht wurden.
![](Pastedimage20260210133557.png)
![](Pastedimage20260210133624.png)

*Fehler: Am Schluss als ich commiten wollte ist kein einziges Bild erschienen, am Schluss mussten ich alle Fotos nochmals bearbeiten (Namen umändern, Abstände rausnehmen und Klammern umändern)*


# 20 - Infrastruktur
## 01 - Cloud Computing

# 30 - Container
## 01 - Container.

### Container

Container ändern grundlegend die Entwicklung, Verteilung und den Betrieb von einer Software. Sie erlauben es Entwicklern lokale Anwendungen zu erstellen und sicherzustellen, dass diese in jeder anderen Umgebung identisch funktionieren, unabhängig davon ob sie auf einem Server im firmeneigenen Rechenzentrum, auf dem Laptop eines Benutzers oder in einem Cloud-Cluster laufen. So werden typische Schwierigkeiten, die durch verschiedene Systemumgebungen verursacht werden, vermieden.  
  
Container sind besonders leichtgewichtig und verursachen kaum Overhead, da sie sich die Ressourcen des Host Betriebssystems teilen. Sie können in Sekundenbruchteilen gestartet und gestoppt werden, was ihnen eine hohe Flexibilität und Effizienz im laufenden Betrieb verleiht. Zugleich ist es ohne Weiteres möglich auf einem System viele Container gleichzeitig auszuführen.

Administratoren können durch den Einsatz von Containern entlastet werden anstatt Zeit für die Konfiguration einzelner Umgebungen und das Lösen von Problemen aufzuwenden, haben sie mehr Zeit sich auf die Netzwerke, Ressourcennutzung und Systemverfügbarkeit zu konzentrieren.  Alles in allem sind Container ideal für moderne Cloud-Umgebungen und bilden eine wesentliche Basis für cloud-native Anwendungen.

### Geschichte

Das Konzept der Container existiert schon lange und hat sich über viele Jahre weiterentwickelt. Bereits bot **chroot** in UNIX-Systemen eine einfache Dateisystem-Isolation, die mit **FreeBSD Jails** ab 1998 auf Prozesse erweitert wurde. Ab 2001 wurden umfassendere Container-Ansätze wie **Solaris Zones** und **Virtuozzo/OpenVZ** eingeführt, jedoch waren diese teilweise plattformspezifisch oder kommerziell.  
  
Die zentralen Kernel-Funktionen wurden zu einer vollständigen Containerlösung kombiniert, als Google und das Linux Containers Project (LXC) 2008 **cgroups** einführten. Die Technologie gelang schließlich 2013 mit **Docker** in den Mainstream, das Container einfach nutzbar und weit verbreitet machte.

### Microservices

Microservices stellen einen der bedeutendsten Anwendungsfälle dar und sind die stärkste Kraft für den Aufstieg von Containern. Ein Ansatz zur Entwicklung und Kombination von Softwaresystemen besteht in Microservices. Dabei bestehen die Systeme aus kleinen, voneinander unabhängigen Komponenten die über das Netzwerk miteinander kommunizieren. Dies steht im Gegensatz zum traditionellen, monolithischen Ansatz der Softwareentwicklung, bei dem es ein einziges, großes Programm gibt.

Wenn ein solcher Monolith skaliert werden muss, bleibt meist nur die Option, vertikal zu skalieren, wobei zusätzliche Anforderungen durch mehr RAM und höhere Rechenleistung erfüllt werden. Im Gegensatz dazu sind Microservices so konzipiert, dass sie horizontal skaliert werden können, indem zusätzliche Anforderungen von mehreren Rechnern verarbeitet werden auf die die Last verteilt werden kann.

In einer Microservices System ist es möglich, nur die Ressourcen zu skalieren, die für einen bestimmten Service benötigt werden, und sich damit auf die Flaschenhälse des Systems zu beschränken. In einem Monolith wird alles oder gar nichts skaliert, was zu verschwendeten Ressourcen führt. Eine Microservices System ermöglicht es nur die Ressourcen zu skalieren, die für einen bestimmten Service erforderlich sind und sich damit auf die Flaschenhälse des Systems zu konzentrieren. Ein Monolith ermöglicht nur eine vollständige Skalierung aller Komponenten, was zu Ressourcenverschwendung führt.


## 02 - Docker

Docker hat die bestehenden Linux Containertechnologien integriert und maßgeblich verbessert. Dank portabler Container Images und einer simplen und mehrheitlichen anwenderfreundlichen Handhabung entwickelte sich Docker zu einer umfassenden Lösung für das erstellen, ausführen und verteilen von Containern.  
  
Die Docker-Plattform setzt sich im Wesentlichen aus zwei Hauptkomponenten zusammen:  
Die **Docker Engine** baut Container und führt sie auch aus. Der **Docker Hub** hingegen ist ein Cloud-Dienst der das speichern und teilen von Container Images ermöglicht.  
  
Docker wurde ursprünglich für **64-Bit-Linux-Systeme** entwickelt. Auf macOS und Windows kann Docker jedoch verwendet werden, indem Linux Container mit einer Virtualisierungslösung wie VirtualBox oder einer integrierten VM ausgeführt werden.

### Architektur

Docker Daemon:
- Genutzt zum erstellen, ausführen und überwachen der Container
- Genutzt zu bauen und speichern von Images
- Gestartet durch Host Betriebssystem

Docker Client:
- Wird über CLI (Kommandozeile) bedient
- Kommuniziert per HTTP TEST mit Docker Daemon
- Einfache Verbindungen mit entfernten Docker Daemons
- Einfache Entwicklung von Bindings 

Images:
- Gebuildete Umgebung können als Container starten
- Images nicht veränderbar (nur neu erstellen)
- Images haben Name und eine Version (TAG)

Container:
- Container sind die ausgeführten Images
- Image kann beliebig oft als Container geöffnet werden
- Container Inhalte können verändert werden (mit Union File Systems)
- Veränderungen werdem zum originale Image gespeichert

Docker Registry:
- Hier werden Images gespeichert und verteilt
- Standard Registry ist der Docker Hub
- Docker Hub hat viele öffentliche Images zur Verfügung
- Firmen haben oft eigene Registries um den Overhead zu vermeiden.

### Befehle

| Befehle                                        | Erklärung                                                            |
| ---------------------------------------------- | -------------------------------------------------------------------- |
| docker run                                     | Startet des Containers (Universal)                                   |
| docker run hello-world                         | Standard Dockertest                                                  |
| docker run -it ubuntu /bin/bash                | Startet den Container mit Shell                                      |
| docker run -d ubuntu sleep 20                  | Startet Container der im Hintergrund läuft                           |
| docker run -d --rm ubuntu sleep 20             | Startet Container im Hintergrund + löscht sich nach Beenden des Jobs |
| docker run -d ubuntu touch /tmp/lock           | Startet Container im Hintergrund + legt Datei an                     |
| docker run -d ubuntu ls -l                     | Startet Container im Hintergrund + gibt ROOT Verzeichnis aus         |
| docker ps                                      | Aktive Container anzeigen                                            |
| docker ps -a                                   | Alle Container anzeigen (egal ob an oder aus)                        |
| docker ps -a -q                                | Gibt nur ID aus                                                      |
| docker images                                  | Gibt Lokales Image                                                   |
| docker image ls                                | Gibt Lokales Image                                                   |
| docker rm                                      | Entfernt Container (Kein befehl)                                     |
| docker rmi                                     | Entfernt Images (Kein befehl)                                        |
| docker rm [xxx]                                | Löscht Container                                                     |
| docker rm `docker ps -a -q`                    | Alle Beendete Container löschen                                      |
| docker rm -f `docker ps -a -q`                 | Alle Container löschen                                               |
| docker rmi ubuntu                              | Löscht Images                                                        |
| docker rmi `docker images -q -f dangling=true` | Zwischenimages löschen                                               |
| docker create                                  | Container erstellen                                                  |
| docker start                                   | Startet alle Container                                               |
| docker start [id]                              | Startet Container neu                                                |
| docker stopp                                   | Stoppt laufenden Container                                           |
| docker kill                                    | Löscht Docker Container                                              |
| docker logs                                    | Gibt LOGs für Container aus                                          |
| docker inspect                                 | Gibt genauerer Infos                                                 |
| docker diff                                    | Gibt Änderungen an                                                   |
| docker top                                     | Gibt Infos zu laufenden Prozessen                                    |

### Dockerfile

So kann man ein Dockerfile erstellen nach dem man ein Verzeichnis und ein Datei darin erstellt hat:

| Befehl                                | Erklärung                     |
| ------------------------------------- | ----------------------------- |
| docker build -t mysql .               | Image builden                 |
| docker run --rm -d --name mysql mysql | Image starten                 |
| docker exec -it mysql bash            | Funktionsfähigkeit überprüfen |
| ps -ef<br>netstat -tulpen             | Überprüfung im Container      |

### Kozepte

Build Context
- Erforderlich für docker build
- Enthält Dockerfile + lokale Dateien/Verzeichnisse
- Definiert meist als Verzeichnispfad

Layer / Imageschichten
- Jede Dockerfile-Anweisung = neue Imageschicht
- Schichten sind wiederverwendbar (Caching)
- Temporärer Container pro Anweisung
- Container wird nach erfolgreichem Schritt gelöscht

Anweisungen im Dockerfile
FROM 
- Basis Image

ADD 
- Kopiert Dateien aus Build Context oder URLs
- Entpackt Archive automatisch

COPY
- Kopiert Dateien aus Build Context

RUN
- Führt Befehle beim Image-Build aus
- Erstellt neue Layer

CMD
- Standardbefehl beim Containerstart
- Kann überschrieben werden

ENTRYPOINT
- Festes Startkommando des Containers
- CMD/Argumente werden übergeben
- Oft für Start-Skripte genutzt

ENV
- Setzt Umgebungsvariablen im Image

EXPOSE
- Dokumentiert offene Ports des Containers

HEALTHCHECK
- Prüft regelmäßig den Zustand der Anwendung

MAINTAINER
- Autor-/Kontaktinformationen (veraltet, Metadaten)

SHELL
- Definiert Shell für "run"

USER
- Setzt Benutzer für folgende Befehle

VOLUME
- Deklariert persistente Datenverzeichnisse

WORKDIR
- Setzt Arbeitsverzeichnis für folgende Anweisungen: RUN, CMD, ENTRYPOINT, ADD, COPY

## 03 - Netzwerkanbindungen (optional)

## 04 - Volumes (optional)

## 05 - Image Bereitstellung

