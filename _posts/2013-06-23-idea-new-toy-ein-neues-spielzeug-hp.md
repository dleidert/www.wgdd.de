---
title: 'Idee: Ein neues Spielzeug ... HP Microserver N54L'
date: '2013-06-23T20:04:00.000+02:00'
category:
- debian
- planet-debian
- hardware
tags:
- backup
- hardware
- n54l
- nas
- htpc
- debian
- microserver
last_modified_at: '2015-02-11T21:20:49.057+01:00'
redirect_from:
- /2013/06/idea-new-toy-ein-neues-spielzeug-hp.html
---

Ich fertige regelmäßig Backups meiner Systeme an. Diese werden auf der
Systemplatte meines Notebooks abgelegt und via `rsync` auf mobilen Speicher
dupliziert. Hierzu verwende ich eine [USB-Festplatte]. Diese enthält auch
Medien-Dateien und wird regelmäßig an den Fernseher angeschlossen. Prinzipiell
halte ich meine Daten daher für sicher. Aber vor kurzem stieß ich an die
Grenzen ihrer Kapazität.

[USB-Festplatte]: /2009/12/testing-smart-status-of-my-toshiba-usb.html

Schon länger habe ich nach einer Alternative gesucht, nicht zuletzt da heute
viel größere Festplatten möglich sind und mein Laptop über einen
eSATA-Anschluss verfügt, der schneller als USB2.0 ist. Meine bevorzugte
Variante war ein [FANTEC DB-ALU3e] Gehäuse mit einer [WD Red WD20EFRX 2TB (5400
RPM)] Festplatte, die für den 24/7 Betrieb zertifiziert ist (und zudem über
eine ausgezeichnete Reputation verfügt). Die Kombination lief sehr gut und
schnell, sieht edel aus, benötigt aber eine externe Stromversorgung. Ich kann
Sie als Speicherlösung absolut empfehlen.

[FANTEC DB-ALU3e]: https://www.fantec.de/produkte/speicherprodukte/festplattengehaeuse/35-zoll-festplattengehaeuse/produkt/details/artikel/1479_fantec_db_alu3e/
[WD Red WD20EFRX 2TB (5400 RPM)]: https://www.wdc.com/global/products/specs/?driveID=1086&amp;language=1

Allerdings hatte ich zu diesem Zeitpunkt noch weitere Ansprüche, die mit der
o.g. Lösung nicht zu befriedigen sind. So trage ich mich bereits länger mit dem
Gedanken an ein [RAID-1]-[NAS]. Außerdem spiegelt sich die Beanspruchung meiner
Notebook-Festplatte durch das Pakete-Bauen für [Debian] im [S.M.A.R.T.]-Status
wieder. Daher wollte ich diese Arbeit an einen robusten lokalen
[buildd]-Boliden abgeben und habe über den Kauf eines günstigen Rechners
nachgedacht. Ein NAS verbraucht aber deutlich weniger Strom als ein
Desktop-Rechner.

[RAID-1]: https://de.wikipedia.org/wiki/RAID#RAID_1:_Mirroring_.E2.80.93_Spiegelung
[NAS]: https://de.wikipedia.org/wiki/Network_Attached_Storage
[Debian]: https://www.debian.org
[S.M.A.R.T.]: https://de.wikipedia.org/wiki/Self-Monitoring,_Analysis_and_Reporting_Technology
[buildd]: https://wiki.debian.org/buildd

Also wie lässt sich ein buildd und ein energiesparendes NAS vereinen? Per
Zufall stieß ich bei einem lokalen Händler auf den [HP ProLiant MicroServer
N40L][N40L]. Das Angebot klang super und so entschied ich mich zum Kauf meines
neuen Spielzeuges: ein [HP ProLiant MicroServer N54L][N54L], der zukünftig
folgende Aufgaben verrichten soll:

Datensicherung
: Die Sicherung der Daten erfolgt `cron`-gesteuert auf den RAID-Verbund in eine
gesonderte (verschlüsselte) Partition. Der S.M.A.R.T.-Status der Festplatten
wird via `smartd` überwacht. Sollte eine Platte kaputt gehen, bestehen gute
Aussichten, die Daten zu retten. Eine zukünftige Option wäre auch noch ein
[RAID-6] Verbund.

NAS / File-Server
: Das Gerät verfügt über bis zu 6 SATA Anschlüsse. Davon werden vier
standardmäßig via Wechselrahmen belegt. Die mitgelieferte 250GB Festplatte wird
vorerst das Betriebssystem aufnehmen und an den drei verbleibenden Anschlüssen
werden zunächst drei [WD Red WD20EFRX 2TB (5400 RPM)] Festplatten als
[RAID-5]-Verbund für den notwendigen Platz sorgen. Letzterer lässt sich ohne
Erweiterung nur via Software-Raid und `mdadm` realisieren.

buildd
: Betriebssystem wird [Debian GNU/Linux][Debian] sein. Der Hauptspeicher wird
auf mindestens 8GB ECC-Ram aufgerüstet.

[HTPC] (mit [XBMC])
: Der Microserver lässt sich nicht als Massenspeicher an einen Fernseher
anschließen. Daher soll vorr. [XBMC] in Verbindung mit einem USB3.0 BR/DVD-Player den Server zum Entertainment-Gerät erheben.

[N40L]: http://www8.hp.com/de/de/products/proliant-servers/product-detail.html?oid=4248009
[N54L]: http://www8.hp.com/de/de/products/proliant-servers/product-detail.html?oid=5336624
[RAID-6]: http://de.wikipedia.org/wiki/RAID#RAID_6:_Block-Level_Striping_mit_doppelter_verteilter_Parit.C3.A4tsinformation
[RAID-5]: http://de.wikipedia.org/wiki/RAID#RAID_5:_Leistung_.2B_Parit.C3.A4t.2C_Block-Level_Striping_mit_verteilter_Parit.C3.A4tsinformation
[HTPC]: http://de.wikipedia.org/wiki/HTPC
[XBMC]: http://xbmc.org/

Das ganze soll möglichst wenig Strom verbrauchen und leise sein. Zum Anschluss
an das lokale Netzwerk habe ich mich für WLAN entschieden, da kein
Gigabit-Ethernet vorhanden ist. Folgende Teile benötige ich für "meinen"
Server:

Server
: HP ProLiant N54L MicroServer mit Turion II Neo 2,2 GHz, 2GB RAM/250GB HDD *ca. 200 EUR*

Belüftung / Lautstärke
: Scythe Slip Stream Gehäuselüfter 120mm 800RPM 11dB *ca. 9 EUR* (*SY1225SL12L*)
: Scythe Slip Stream Gehäuselüfter 120mm 500RPM 7,5dB *ca. 8 EUR* (*SY1225SL12SL*)

Netzwerk
: TP-Link TL-WN722N(C) 150Mbps USB-Adapter *ca. 15 EUR* (*TL-WN722N(C)*)

File-Server
: 3x WD Red WD20EFRX 2TB 5400 RPM SATA600 für NAS 24/7 *ca. 95 EUR/St.* (*WD20EFRX*)

buildd
: 8GB (2x4GB) Kingston ValueRAM DDR3-1333 CL9 ECC Modul RAM-Kit *ca. 85 EUR* (*KVR1333D3E9SK2/8G*)
: 16GB (2x8GB) Kingston ValueRAM DDR3-1333 CL9 ECC Modul RAM-Kit *ca. 145 EUR* (*KVR1333D3E9SK2/16G*)

HTPC / Grafik
: Sapphire Radeon HD 5450/6450/6570/6670/7750 PCIe 16x Low-Profile passiv/aktiv *ca. 25..100 EUR* (*11166-45-20G*, *11190-09-20G*, *11191-27-20G*, *11191-02-20G*, *11192-18-20G*, *11202-10-20G*)
: SILVERSTONE PCIe 1x USB3.0 2xInt 2xExt *ca. 21 EUR* (*SST-EC04-P*)
: Logitech K400 od. Keysonic ACK-540RF *ca. 40 EUR* (*920-003100* bzw. *ACK-540 RF*)
: BR/DVD-Player od. Brenner mit USB3.0 Anschluss *50..100 EUR*

[LCD-Mod]
: LDC Display Modul mind. 4x20 *ca. 10 EUR*

Interessant ist auch noch die Option einer echten RAID-Karte. Ich stieß dabei
auf die IBM ServeRAID M1015 (*46M0831*) und [diesen] Hinweis. Kauft man
stattdessen den "Schlüssel" zur Freischaltung des vollen Funktionsumfanges,
dann bezahlt man zusätzlich *ca. 150 EUR*! Aber das nur BTW.

[LCD-Mod]: http://geekbox.ch/lcd-display-hp-proliant-n40l/
[diesen]: http://tamcore.eu/raid-controller-fur-meinen-hp-microserver/

##### Nützliche Links:

* [HP MicroServer N40L Wiki](http://n40l.wikia.com/wiki/HP_MicroServer_N40L_Wiki)
* [HP ProLiant MicroServer N36L/N40L/N54L Sammelthread](http://www.hardwareluxx.de/community/f101/hp-proliant-n36l-n40l-n54l-microserver-752079.html#post15468196)

*[NAS]: Network Attached Storage
*[S.M.A.R.T.]: Self-Monitoring, Analysis and Reporting Technology
*[ECC]: Error Correction Code
*[HTPC]: Home Theatre Personal Computer
*[XBMC]: XBMC Media Center
*[RAID]: Redundant Array of Independent Disks
*[BTW]: By the way

<!-- vim: set tw=79 ts=2 sw=2 ai si et: -->
