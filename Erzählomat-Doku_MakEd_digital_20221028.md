---
title:  Der Erzählomat - ein pädagogisches Maker-Projekt
author: Projekt MakEd_digital / www.maked-digital.de / CC BY
date: \today{}
meta:  OER für den Einsatz bzw. Bau des Erzählomaten im Unterricht 
geometry:
- top=2.6cm
- left=2.8cm
- right=4.0cm
- bottom=2.8cm
linestretch: 1.25
lang: de-de
numbersections: true

fontfamily: helvet
header-includes:
  - \renewcommand{\familydefault}{\sfdefault}
  - \setlength{\skip\footins}{0.65cm}
---

\tableofcontents
\pagebreak

\vspace*{6\baselineskip}
# Präambel
Das Projekt „MakEd_digital“ zielt auf die Entwicklung digitalisierungsbezogener Kompetenzen von (zukünftigen) Lehrpersonen zur Nutzung, Entwicklung und Reflexion digitaler Medien und Werkzeuge in Lehr-Lern-Kontexten. Steigern wollen wir diese Kompetenzen, indem an den Stuttgarter und Ludwigsburger Verbundhochschulen pädagogisch-didaktische Makerspaces etabliert werden. In den Makerspaces erhalten Studierende und Lehrende in den Lehramtsstudiengängen Unterstützung bei der Erstellung, dem Einsatz und der Reflexion von digitalen Materialien im Unterricht. Helfende Expertise kommt dabei von Mitarbeitenden mit Hintergründen in Medientechnik, -pädagogik und -didaktik, Bildungswissenschaften und Fachdidaktiken.

Ein zentrales Ziel des Projekts ist die Schaffung von frei nutzbaren Unterrichtsmaterialien (OER). Diese Dokumentation ist ein solches Produkt, mit dem wir viel Freude wünschen. Bei Unklarheiten, Fehlern, Nachfragen oder Anregungen bitten wir freundlichst um Feedback.

Mehr zum Projekt finden Sie unter:   
https://www.pse-stuttgart-ludwigsburg.de/projekte/maked-digital/
  
\vspace*{2\baselineskip}

Stuttgart, im Oktober 2022   
  _Wiebke Renz, Jan Vanvinkeroye, Claus Wilcke_

\pagebreak
# Einführung

Dass Geniales einfach ist, zeigt der Siegeszug der Tonieboxen[^1] durch die Kinderzimmer der Welt: Eine Lausprecherbox mit eigener Stromversorgung erzählt Geschichten, sobald eine entsprechende Figur die auf die Box gestellt wird. Historisch ist dies die Nachfolge der viel geliebten Kassettenrekorder der 80er und 90er Jahre, die - im Gegensatz zu den Eltern - eine Geschichte von etwa Benjamin Blümchen beliebig oft hintereinander erzählen konnten. 

Heute hat die Technik der Toniebox die Kassetten überflüssig gemacht. Nun verarbeitet ein Mikrocomputer einzelne MP3-Files, die entweder im Netz oder auf einem Speichermedium vorgehalten werden. Dank RFID-Technik wird berührungslos erkannt, welches File zu welcher Figur gehört und also abgespielt werden muss. Als Auslöser fungiert dabei ein entsprechender RFID-Chip den jede Figur trägt, die auf die Box gestellt wird. Welcher Soundfile mit diesem speziellen Chip verbunden ist, also welche Geschichte erzählt wird, kann vorab eingestellt werden. Durch die integrierte Stromversorgung ist die Box maximal mobil, durch das Fassungsvermögen des digitalen Speichers ist die Anzahl der möglichen Geschichten praktisch unbeschränkt. 

Eine Abwandlung der Anwendung, nicht aber des Prinzips, stellt das in England gefertigte _Museum in a Box_[^2] dar. Entwickelt von einer auf Museumspädagogik spezialisierten Bildungsagentur, werden hier unterschiedliche Museumsexponate (oder deren verkleinerte Nachbildungen) auf die Box gestellt  und können nachfolgend die Geschichte ihrer Herkunft bzw. Entstehung und Verwendung erzählen. Hier ist der Übergang zum pädagogisch-didaktischen Einsatz, den dieses Howto beschreibt.

Der Siegeszug der Tonieboxen durch Kinderzimmer erzeugte im Nachgang auch eine Open Source Community, die selbst diese Boxen bauen wollte. Zwei Gründe ddafür gab es:  Zum einen der relativ hohe Preis für das Wiedergabegerät selbst, zum zweiten der potenziell unbegrenzte Mittelbedarf für den Einkauf weiterer Spielfiguren, also Geschichten. 

Diese Community gruppiert sich um die Webseite plus Forum von Thorsten Voß aus Recklinghausen. Unter dem Namen "Tonuino"[^3] bespricht dort die Community Bautipps, Fragen und Anregungen rund um das Gerät. Das dabei anleitende Prinzip ist der Open-Source-Gedanke hinsichtlich Wissen und Software, zu dem der kostengünstige Einkauf Hardware tritt. Beides zusammen kann (kann!) den Preis für eine einzelnes Gerät auf unter € 50 drücken. 


Kurz noch einmal die Funktionsweise: Ein Mikrocomputer (Arduino) in einem Gehäuse (der Box) erkennt per RFID berührungslos einen Gegenstand (Modell, Bild, Objekt, ...) der auf die Box gestellt wird. Der an diesem Gegenstand applizierte RFID-Chip übermittelt einen singulären Code, worauf der Rechner die dazu passende Sounddatei abspielt, die dann über die in der  Box eingebauten Lautsprecher hörbar wird. Die Maschine besitzt eine kleine externe Festplatte (Mikro-SD-Karte), auf der zunächst die Steuerung/Software der Box aufgespielt wird. Nachfolgend werden auf dieser SD-Karte auch die einzelnen Sprachdateien aufgespielt. Dadurch ist es möglich, über die Lautstärketasten der Box jeweils eine (interne) Sounddatei  mit einem bestimmten (externen) Chip zu verbinden. Weil die Paarung ‚Gegenstand plus Sprachdatei‘ nicht von der Box abhängt, ist die Anzahl und Art von damit erklärbaren Objekten potenziell unbeschränkt.

![Übersicht der Erzählomat-Einzelteile](erzaehlomat-doku-grafik/erzaehlomat-museumsbox-beispiel_220904_650px.jpg)


Das Ganze hat ein erhebliches didaktisches Potenzial für das Lernen am Modell, wie der Erfolg des Geräts, aber auch neuere Studien beweisen (Schade et al 2019). Ein Theater-Effekt setzt ein: Obwohl man weiß, dass es sich um eine Repräsentation handelt, wird die Informationen „als wirklich“ aufgenommen, weil „dort wirklich etwas steht und redet“. 

Um dieses Potenzial in Schule und Hochschule zu realisieren, haben wir diese Anleitung erstellt. 

Ein guter Einstieg in das ganze Feld ist dieser Thread:

**https://discourse.voss.earth/t/gibt-es-eine-anleitung-fuer-dummies/1837/7**

Bleiben dann auch noch nach diser Anleitung Fragen offen, ist die Community der beste Ansprechpartner:

**https://discourse.voss.earth/**

[^1]: Toniebox: https://tonies.com/de-de/ Ein kritischer Artikel zur Nutzung der Toniebox durch Eltern findet sich unter https://www.kweach.de/toniebox-wie-sinnvoll-ist-der-smarte-kinder-lautsprecher/
[^2]: https://museuminabox.org
[^3]: https://www.voss.earth/tonuino/

\pagebreak

# Vor dem Start: Übersicht, Informationen und Material
Der Zusammenbau von Box, Hardware und Software ist ein  Making-Prozess mit einem Zeitbedarf von etwa 4-6 Stunden. Die hohe Zeitschwankung ergibt sich aus der Möglichkeit, ein vorgefertigtes Chassis  zu verwenden (etwa einen Lautsprecher oder eine Holzbox) oder das Chassis selbst zu bauen und zu gestalten. 

![Einzelteile des Erzählomaten im Bild](erzaehlomat-doku-grafik/erzählomat-innenleben-foto_600px.jpg)

Der Zusammenbau benötigt keinen speziellen Arbeitsplatz, Zubehör und Werkzeuge werden nachfolgend aufgeführt. Von Zusammenbau bis Betrieb folgen diese Arbeitsabschnitte aufeinander:

1. Auflöten von Arduino und MP3-Player auf die Platine. Die Platine der "Leiterkartenpiraten" hat freundlicherweise die Lage dieser beiden Einzelteile bereitsaufgedruckt.
2. RFID-Chip und Tastenknöpfe werden per Kabel an die Platine angeschlossen
3. Die Box wird gebaut und mit einem Lautsprecher versehen. 
4. Der aufgelötete Arduino wird an den Rechner angeschlossen und die benötigte Software, zuerst die "Firmware", dann eventuelle Treiber, danach "Bibliotheken" werden aufgespielt
5. Die Platine mit dem "informierten" Arduino und der gesamten verbunden Hardware wird in der Box befestigt. Auf eine gute Zugänglichkeit zur Batterie und den Slot für die SD-Karte ist zu achten. Auf beides wird regelmäßig zugegriffen werden.
6. Die Batterie mus geladen und angeschlossen werden ( Stecker sind vorhanen = keine Verkabelung)
7. Die SD-Karte wird per Kartenhalter an den Rechner angeschlossen und mit den Soundfiles für die gewünschten Objekte befüllt. Danach wird sie in den Slot des MP3-Players gesteckt.
8. Noch "unverbundene" RFID-Chips werden über die Tastenknöpfe des Chassis mit den jeweiligen Soundfiles auf der SD-Karte verbunden.
7. Diese nun informierten Chips werden an den Exponaten befestigt

Der Erzählomat ist jetzt einsatzbereit.

Eine weitere Option ist, den Erzählomaten nicht mit Lautsprechern auszustatten, sondern mit Kopfhörern. Dies ist bislang zwar noch nicht in der Praxis erprobt, verändert aber weder Arbeitsweise noch Vorgehen.


## Wissensquellen

### Homepage und Forum
Alle nur denkbaren Fragen zum Zusammenbau und dem Betrieb des Erzählomaten finden sich natürlich auf der Homepage des Tonuino: **https://www.voss.earth/tonuino/**

Die Seite wird vom Gründer der Aktion, Thorsten Voss, stetig aktualisiert. Hier findet sich eine Bauteilliste, Hinweise zum Schaltplan und zur Firmware, Organisationstipps für die SD-Karte, ein FAQ und eine Fortlaufende Kommenarfunktion.

Einzelne Projekte, Probleme und Vorgehensweisen können im Forum des Projekts besprochen bzw. gesucht werden: **https://discourse.voss.earth/**

### Videos

Es gibt inzwischen etliche How-to-Videos auf Youtube, die man mit der Suche "tonuino anleitung" findet. Gut gefallen hat uns das Video des Youtube-Bastlers 'SmartHome yourself', nach dessen Anleitung die meisten unserer Boxen entstanden sind[^4].  Gleichzeitig noch einmal der Hinweis auf die stete Alterung solcher Videos, was etwa das Design der Platine oder der zum Projekt angebotenen Bausätze betrifft.

[^4]: https://www.youtube.com/watch?v=nSAZrJYT06o

### Fachartikel

Ein Artikel zum Tonuino-Projekt in der "Make": **https://www.heise.de/make/meldung/Tonuino-DIY-Musikbox-mit-RFID-Karten-und-Arduino-4155010.html**  
und in ifun.de, den Apple-News : **https://www.ifun.de/zum-selberbauen-kontaktlose-tonuino-musikbox-fuer-kinder-130007/**

Literatur zum fachdidaktischen Einsatz des Erzählomaten finden sich auch in Schaal/Brändle/Wilcke (2022): Making im Biologieunterricht (--> Literatur)

## Bauteil-Liste

Das Herz des Projekts sind die vier Bestandteile (1) Arduino Mini, (2) RFID-Erkennung, (3) MP3-Player und (4) Mikro-SD-Karte. Sie werden verkabelt und mit dem Lausprecher bzw. den Kopfhörerbuchsen verbunden. Dann benötigt das Setup noch Strom und alles zusammen muss in eine Box. Daraus ergibt sich diese Liste:

 1.  1x| Arduino Mini
 2.  1x| MP3-Player
 3.  1x| RFID-Empfänger
 4.  1x| Platine (für Positionen 1 & 2) 
 5.  1x| Mikro-SD Karte
 6.  1x| Batterie/ Powerbank
 7.  1x| Verbindungskabel Batterie-Arduino (USB Typ A --> USB Mini B)
 8.  8x| Jumper Wire Kabel 20 cm
 9.  3x| Steuerungsknöpfe ("Drucktaster") 
 10. 1x| Lautsprecher// wahlweise: Kopfhörerbuchsen (3x)
 11. 1x| Lautsprecherabdeckung PLUS 4 x Schlosschrauben zur Befestigung // wahlweise: 3 x Befestigungsmuttern für Kopfhörerbuchsen
 12. 8x| Schrumpfschläuche
 13. 4-6x| Kleine Schrauben für diverse Modulbefestigungen in der Box
 14. 1x| Chassis (=Box)
 15. 4x| Stuhlgleiter/ Filzkappen
 16. Set| Oberfläche Chassis: Schleifpapier, Lack, Farbe
 
## Einkauf und Preise

Alle Preis- und Bezugsangaben Stand September 2022. Preise gerundet. Alle Angaben & Angebote unterliegen stetem Wandel!  
Ein guter Online-Elektronik-Vertrieb ist Reichelt. Es gibt ein breites Angebot, solide Qualität und handelsübliche Rechnungen: www.reichelt.de  
Wer es besonders günstig mag, kauft via Amazon bei chinesischen Herstellern ein: www.amazon.de

 1. **Tonuino-Set: € 9,-** | Von AZDelivery. Enthält: Arduino Mini, MP3-Player, RFID-Modul, 10 RFID-Karten
 2. **Platine für Arduino & MP3-Player: € 10,-** | https://www.leiterkartenpiraten.de/produkt/tonuino-classic-platine/ Platine u. Buchsenbrücken
 3. **Mikro-SD Karte: € 4,-** | Intenso, 8 GB 
 4. **Batterie (Powerbank): € 17,-** | Amazon: Realpower Powerbank 10.000 mAh 
 5. **Verbindungskabel Batterie-Arduino: € 4,-** | Reichelt: (USB Typ A Stecker --> USB Mini B Stecker) 
 6. **Jumper Wire: € 4,-** | Reichelt: Kabel 20cm; "female-male"/"female-female" je 8 stk 
 7. **Schrumpfschläuche: € 2,-** | Reichelt: Befestigung Lötstellen an Platine
 8. **Steuerungsknöpfe: € 3,-** (Stück) | Amazon: Drucktaster- 24mm OEM Arcade Tasten Schalter"
 9. **(Entweder:) Lautsprecher: € 27,-** |Reichelt: Visaton FX10, 4Zoll, 10.16cm,Breitbänder 40W,4Ohm
 10. **(plus:) Lautsprechergitter: € 7,-** | Reichelt: Lautsprechergitter f.Breitbandlautspr. 40 W, 
 11. **(Oder mit:) Kopfhörerbuchsen: € 0.90** | Reichelt: Kopfhörer-Einbaubuchse 3,5 mm + Fixierschrauben
 12. **Box: €0 - €25,-** | Baumarkt/Internet: Sperrholz, Lautsprecherbox, Kiste, .... 
 13. **Schrauben: € 2,-** | Baumarkt: Holzschrauben f. Platine & RFID-Modul, Schlossschrauben f. Lautsprecher 
 14. **Beschläge u. Finish: € 20,-** |Baumarkt: Lack, Pinsel, Schleifpapier, Stuhlgleiter, ... 
 

## Werkzeuge

Das gesamte Projekt kann an einem Büroschreibtisch montiert werden. Nur (a) beim Setzen der Tastaturknöpfe fallen Späne (bohren, feilen) und (b) beim Lackieren des Chassis (schleifen, lackieren) müssen Oberflächen geschützt werden. Ein über die Arbeitsfläche gespanntes Packpapier bzw. ein größeres Bastelbrett sollte hier ausreichen.


  1. Lötkolben, Lötzinn, Lötpumpe (meist in Sets enthalten)
  2. Lötstation (Teilehalterung) bzw. Platinenhalter 
  3. Kleine Spitzzange mit Kneifabschnitt
  4. Bohrmaschine, Bohrer und (Rund-)Feile
  5. Kreuzschlitzschrauber (Befestigung Module in der Box)
  6. Feuerzeug (für Schrumpfschläuche)
  7. Finishing: Pinsel
  

\pagebreak
  
# Zusammenbau der Hardware

Der Prozess des Zusammenbaus beginnt mit "stecken und löten". Wer vorher noch nie gelötet hat, sollte mit Restmaterial vorher ein wenig üben. Gute Lötstellen zeichnen sich dabei durch die "drei Geh" aus: *gleichmäßig, glatt, glänzend*. Im Internet gibt es etliche How-to-Videos für Lötanfänger.

Grundsätzliches Vorgehen beim Löten ist, dass nicht das Lötzinn erhitzt werden soll, sondern das Bauteil so heiß gemacht wird, dass es das - ebenfalls erhitzte - Zinn ansaugt und dabei das Lötgut auch in die Platine fließt. Dafür muss die Lötspitze sauber sein und ausreichend heiß. Die Spitze des Lötkolbens wird auf das zu verlötende Bauteil gesetzt und nach einer kurzen Zeit (Gefühlssache!) wird das Lötzinn zugeführt, das damit ebenfalls flüssig wird und entlang des bereits heißen Bauteils einfließt. Nach einem Dutzend Versuchen mit anderen Drähten und Platinen entwickelt man für notwendige Dauer des Kontakts und der daraus folgenden Hitze ein Gefühl. Idealerweise dauern Aufsetzen, Erhitzen, Zinn zuführen und Lötkolben abheben weniger als eine halbe Minute. Sollte die Lötstelle verkorkst, d.h. unschön sein (Blasenbildung, Spalten, "kalte Lötung"), hilft die Lötpumpe das erneut erhitzte Lötzinn wieder zu entfernen.


## Zusammenstecken und verlöten 

Das Hardware-Angebot wandelt sich beständig. So bieten die Leiterkartenpiraten seit Frühjahr 2022 auch eine "All-in-one"-Platine an [^5]. Diese fast quadratische Platine hat fast alle Module (Arduino, MP3-Player, SD-Karte) schon aufgelötet und bietet dazu noch Kopfhörerbuchsen, eine Ladeanzeige, Erweiterungsports usw. an. Damit muss insgesamt weniger gelötet werden. Diese Anleitung aber beschreibt die (ältere, kleinere, gestreckt rechteckige) "Classic Platine" von etwa 4x12cm. 

**1)** Alle Buchsenbrücken werden als Abstandshalter bzw. Kabelverbindung auf die (Classic-)Platine gesetzt und rückseitig ("von unten") verlötet.  
Für eine gute spätere Schlüssigkeit empfiehlt es sich, schon jetzt den Arduino und MP3-Player aufzusetzen und so aufgesetzt die Kontakte der Buchsen in der Platine rückseitig zu verlöten.  
**2)** Der Arduino wird auf seine Buchsenbrücken der Platine gesetzt. Alle entstehenden Kontakte werden verlötet.  
**3)** Der MP3-Player wird auf seine Buchsenbrücken der Platine gesetzt. Alle entstehenden Kontakte werden verlötet.

[^5]: https://www.leiterkartenpiraten.de/category/anleitungen/all-in-one-platine/ 

## Verkabeln und fixieren

**4)** Das RFID-Modul wird mit Jumperkabeln an die Platine angeschlossen.  Alle entstehenden Kontakte werden verlötet.   
Es ist beim Festlöten der Jumperkabel am RFID-Modul darauf zu achten, wie das Modul später an der Box befestigt wird und wie also deswegen die Kabel an die Modulplatine herangeführt werden (von "unten" oder "oben").

**5)** Die Kabel für die Tastschalter werden an der Platine angelötet, aber NOCH NICHT mit den Tasten verbunden.   
Da die Tasten von außen in die Box eingeführt werden, werden  später die Verbindungkabel SPÄTER durch das Chassis geführt werden, dann werden die Taster angelötet und dann zurück in die Tastenlöcher geschoben

**6)** Die beiden ausgehenden Kabel für den Lautsprecher werden an der Platine festgesteckt.

**6a)** Soll der Erzählomat nicht mit einem Lautsprecher, sondern mit Kopfhörern ausgestattet werden, müssen an die beiden ausgehenden Kabel entsprechende Weichen angebracht werden. ((wie?? wo kaufen??))

## Das Chassis und seine Komponenten 

Die Bedienung des betriebsbereiten Geräts geschieht über drei Druckschalter (Tastenknöpfe). die sich an der Außenseite befinden. Dies sind die für Tasten "Start-Stop", "Lauter" und "Leiser". Neben der offensichtlichen Regulierung für die Wiedergabe der MP3-Files, kommen die Tasten auch zum Zug, wenn ein neuer RFID-Chip einem neuen Soundfile zugeordnet werden soll.

Selbstgebaute Chassis erfreuen sich großer Beliebtheit und werden in der Community von Voss.Erath zu Dutzenden vorgestellt: **https://discourse.voss.earth/**
Der Vorteil des Selbstbaus besteht in der größeren gestalterischen handwerklichen Freiheit und der guten Zugänglichkeit zu allen Bauteilen vor dem Zusammenbau. Die Nachteile sind der höhrere Aufwand an Material und Zeit, sowie das Risiko, dass bei einem unsachgemäßen bzw. nachlässigen Zusammenbau der Lautsprecher der Box scheppert
Der Vorteil eines bereits bestehenden Chassis (etwa einer Lautsprecherbox) ist das vorhandene - schepperfreie - Gesamtpaket aus stabiler Box und Lautsprecher. Das spart Zeit, Geld ( bei gebrauchtem Material etwa) und Aufwand. Zentraler Nachteil ist, dass man die Hardware in den Kasten hineinbauen muss und also weniger Raum zum Fixieren etwa de Platine hat. Allerdings gibt es dafür auch dafür sehr elegante Lösungen, wie das Projekt einer Studentin der PH Ludwigsburg, Lena-Marie Maisenhölder, zeigt:

![Erzählomat-Modell von Lena-Marie Maisenhölder; 2022](erzaehlomat-doku-grafik/maisenhölder-erzaehlomat_small.jpg) 

Hier wurde allerdings schon eine neue Platinenversion, die quadratische "#TonUINO All-In-One Plus Platine"-Platine der Leiterkartenpiraten, verbaut. Alle einzelnen Module sind dabei schon fest aufgelötet, aber leider kostet die Platine damit € 44,- .(https://www.leiterkartenpiraten.de/produkt/tonuino-all-in-one-plus-platine/).


## RFID-Chips: Nur Auslöser-Funktion

Die im Tonuino-Set mit enthaltenen RFID-Karten bzw. der im RFID-Modul enthaltene blaue Chip senden immer nur ein bestimmtes Signal und haben also nichts mit Soundfiles zu tun. Erst später, wenn die Box insgesamt zusammengebaut ist werden die einzelnen Chips(=Si9gnalgber) mit bestimmten Soundfiles auf der SD-Karte verbunden. 
Das bedeute aber im Umkehrschluss auch, dass ein Chip der auf einem bestimmten Objekt befestigt ist, auf _verschiedenen Boxen_ jeweils ein anderes Soundfile triggern kann.

## Soundfiles erstellen, bearbeiten und auf der SD-Karte speichern

Was das pädagogische Modell später über die Box verlauten lässt, muss zunächst als Soundfile aufgenommen werden. Die meisten Handys können inzwischen per kostenloser App wunderbare Aufnahmen machen. 

Danach müssen diese Soundfiles vom Handy auf den eignen Rechner übertragen und dort meist noch otimiert, d.h. geschnitten und bearbeitet werden. 

Die editierten Soundfiles dann weiter auf eine Mikro-SD-Karte aufzuspielen ist so einfach, wie Dateien in einem PC verschieben, d.h. das Ganze geschieht per Drag & Drop. Allerdings fordert die Software des Arduino, dass das Dateisystem der SD-Karte völlig klar aufgebaut wird. Es benötigt einen Ordner mit Steuerdaten, danach werden alle Soundfiles in jeweils neue Ordner gesteckt, die nur mit Zahlen benannt sein dürfen.

Zum Schluss wird die SD-Karte in den Slot des MP3-Players geschoben und die Zuordnung von Soundfile zu RFID-Chip Modell-Soundfile über die Drucktaster der Box vorgenommen.

Nach dieser schnellen, insgesamten Übersicht geht es jetzt in die Details:

\pagebreak

# Software und Soundfiles 

**Software für den Arduino**

Ist die Hardware zusammengebaut, muss der Arduino in zwei Schritten "informiert" werden. Zunächst muss die Firmware, also das Betriebssystem, des Mikrochips aufgespielt werden. Danach ist dieses System mit den entsprechenden "Bibliotheken" auszurüsten. Damit die Hardware des jeweilegen Rechners/Betriebssystems den Arduino  erkennt, benötigt es eventuell noch spezielle Treiber, die man aus dem Internet herunterladen kann.

Erfahrungsgemäß ist dieser Schritt ein wenig "tricky"; bei Problemen im Forum des Tonuino nachsehen oder unter "richtig googlen" in den Howtos.



## Firmware und "Bibliotheken" auf den Arduino aufspielen


**Software: Vorgehen im Schnelldurchgang:**

  - Arduino flashen:
  - Github repo (Tonuino) Zip herunterladen, öffnen - ? Sind alle Dateien da?
  - Tonuino.Ino in Sketch-Ordner laden; wird autom. gemacht
  - In Ordner auf "Sketch" gehen - Bibliothek einbinden - Bibliotheken verwalten - textfeld "df mini" - ist das installiert?  library "dc-buttons"? library "mrfc522" installiert? Wenn nicht, dann "installieren" klicken.
  - dann arduino anschließen
  - "werkzeuge" - "arduino nano" --> bootloader
  - seriellen port - video "com 9"
  - Sketch hochladen


**Software: Vorgehen Schritt für Schritt:**   

Um die Firmware zu kompilieren (also für den Arduino "verdaubar" zu machen)  und auf den Arduino aufzuspielen benötigt  man die Arduino IDE ("Integrated Development Enviroment" Eine Software-Entwicklungsumgebung, aka digitaler Werkzeugschrank). Diese kann auf arduino.cc (https://www.arduino.cc/en/Main/Software#) heruntergeladen werden.

Je nach Arduino benötigt es einen Treiber damit er via USB erkannt wird. Die meisten günstigen Arduino-Klone verwenden den CHG340G/CHG341G Chip. Auf der Herstellerseite des Chips wch.cn (http://wch.cn/download/CH341SER_ZIP.html) (Google Translate: https://translate.google.com/translate?hl=en&sl=auto&tl=de&u=http%3A%2F%2Fwch.cn%2Fdownload%2FCH341SER_ZIP.html) findet man den passenden Download für Windows, macOS oder Linux. Zunächst also den passenden Treiber für das Betriebssystem aussuchen und dann den Arduino via USB Kabel mit dem Rechner verbinden.

Nach der Installation müssen die notwendigen Bibliotheken installiert werden d.h. die "Software" für die Module des Erzählomaten muss heruntergealden werden.  Dies geschieht direkt in der IDE über den Pfad: Sketch -> Bibliothek einbinden -> Bibliotheken verwalten.

Für den TonUINO werden diese Bibliotheken gebraucht:

  - MFRC522
  - DFPlayer Mini Mp3 by Makuna
  - JC_Button
  
Nun muss aus dem der Tonuino-Community GitHub Repository[^6] der Sketch TonUINO.ino geöffnet werden. Auch dise gescheiht in der Arduino IDE.
[^6]: https://github.com/xfjx/TonUINO
Um den Sketch erfolgreich auf den Arduino übertragen zu können müssen noch ein paar letzte Einstellungen vorgenommen werden:

  - Werkzeuge -> Board : „Arduino Nano“
  - Werkzeuge -> Prozessor : „ATmega328P (Old Bootloader)
  - Werkzeuge -> Port : „/dev/cu.wchusbserial???“ (je nach Betriebssystem könnte es anders aussehen)
  
  Zuletzt dann den "Hochladen"-Button  drücken und die Firmware wird auf den Arduino geladen.
  
  **Fehler finden = Fehlermeldungen googlen**
  Der stete Schlupf zwischen den Versionen von Software, Hardware und Hersteller-Optimierungen kann in fast jedem Schritt der Software-Einrichtungen des Erzählomaten zu Fehlern oder Abbruch des Prozesses führen. Wer dann per Google nach der Lösung sucht, sollte **stets die Fehlermeldungen der Arduino-IDE kopieren und in die Google-Suche eintragen**. 



## Soundfiles erstellen und bearbeiten

Für die Aufnahme von Soundfiles reichen Smartphones  völlig aus. Größtes Problem ist meist der Hall in den großen Schulräumen. In einer Ecke aufgehängte Textilien (Vorhänge, Bettlaken schlucken diesen und sorgen für eine improvisierte Studioatmosphäre. Es lohnt sich, glkeich von Anfang an eine möglichst gut Aufnahme anzustreben, d.h. auch mehrere Aufnahmen zu machen. Die Überarbeitung per Spoftware kann echte Mängel nicht ausgleichen und die Überarbeitung erfordert oft detaillierte Kenntnisse der Software, die weder Lehrer noch SuS haben bzw. Zeit kosten. Weitere praktische Aufnahmetricks für Unterrichtssituationen findet man im Internet.

Über die Ausgabelautstärke der Soundfiles entscheiden prinzipiell vier Stationen in dieser Reihenfolge: Initiale Aufnahmequalität, digitale Überarbeitung, Software-Einstellungen auf dem Arduino, Lautsprechertasten.

Danach müssen die Soundfiles eigentlich immer noch geschnitten und bearbeitet werden. Audacity[^7] ist eine von Betriebssystemen unabhängige, freie Software, die für den Schnitt und die qualitative Verbesserung (Rauschunterdrückung, "Pumping") wärmstens empfohlen werden kann.


[^7]: https://www.audacityteam.org/download/

Nun müssen die abspielfertigen Soundfiles so umbenannt werden, dass sie durch die Software des Arduinos automatisch erkannt und abgespielt werden können. Dies geschieht über eine strikt numerische Benennung von Ordnern und Daten, damit die einzelnen Soundfiles später über die Tastenknöpfe des Erzählomaten einzelnen RFID-Chips zugeordnet werden können. 


## Soundfiles benennen und aufspielen

**Ordnerstruktur auf der SD-Karte**

Man kann auf der SD-Karte die Unterordner 01 bis 99 anlegen. In jeden dieser Ordner können dann bis zu 255 Dateien abgelegt werden. Die Dateinamen heißen damit entsprechend 001.mp3 bis 255.mp3.

Bitte weder bei den Ordnern noch bei Dateinamen Lücken lassen, denn damit kommt die Software nicht zurecht!

Zusätzlich gibt es noch die Ordner /mp3 und /advert. Hier werden einige Dateien für den Konfigurationsdialog abgelegt. Die Ordner findet man zusammen mit einer Liste in einem GitHub Repository (siehe Quellcode). 


![Screenshot der Dateistruktur auf der Micro-SD-Karte"](erzaehlomat-doku-grafik/dateistruktur-sd-karte.jpg)

Die Dateien in den jeweiligen Ordnern müssen dann, um automatisch abrufbar zu sein, disen Namenskonventionen folgen:  
  - Keine Leerzeichen in den Dateinamen
  - Jeder Name beginnt mit einer dreistelligen Nummer, wobei die Nummerierung mit 001 beginnt

![Beispielhafte Namengebung der Dateiuen in einem Ordner der SC-Karte. (Ordner hier noch vor dem Upload und daher lesbar beschriftet)](erzaehlomat-doku-grafik/mp3-taxonomie-erzaehlbox.jpg)

mp3-taxonomie-erzaehlbox.jpg)

**Wichtiger Hinweis! - SD-Karte sauber halten!**

Das DF-Player Mini Modul ist sehr zickig wenn es um die SD-Karte geht. Dort dürfen keine unnötigen Dateien herumliegen wie sie zum Beispiel von MacOS dort abgelegt werden (Spotlight und Co.). Besser geeignet ist also Linux oder Windows um die SD-Karte zu bespielen.

Unter MacOS kann man Notfalls versuchen mit folgendem Befehl aufzuräumen:

$ dot_clean /Volumes/SD-Karte



## Objekte, Box und Sounds

Final werden Objekt, Soundfil und Box verbunden. Dafür legt man zunächst einen bislang noch nicht verwendeten EFID-Chip auf den "Sweetspot" der Box. Die Softaresteuerung meldet sich mit einem freundlichen "Oh, eine Karte, die ich noch nicht kenne". Jetzt wird über die (durch die Maschine angesagte) Tastensteuerung dieser neue Chip einem einzelnen Soundfiole in einem Ordner auf der SD-Karte zugeordnet.

Dabei kennt die Software verschiedene Abspiel-Modi: Zufällig, alle nacheinander, nur eine Datei. Für den Unterrichtszwecke wird dann selbstredend die Möglichkeit "nur diese eine Datei" gewählt. Damit ist die Verbindung zwischen Chip und File hergestellt, das Objekt kann eingesetzt werden.

\pagebreak


# Einsatzmöglichkeiten im Unterricht

## Ebene eins, das Maker-Projekt: Zusammenbau der Box
 Making als gemeinsames Bastel hier der ZTusammenabu der Box. Ein klasdisches Projekt mit Lötarbeiten, Arbeiten mit Software und Aufnahmetechnik. Dazu die Erstllung von Figuren oder Artefakte, die auf die Box gestellt werden.

## Ebene zwei, die Wissens-Elaboration: Mit den richtigen Objekten die richtigen Geschichten erzählen

Zwei Schwerpunkte - Auswahl der Objekte und  Gestaltung der dazu beigestellten Informationen, die  notwendigerweise als GeschichtenAuswahl der Objekte für ein gewünschtes Wissensfeld. Entscheidung darüber, ob man Originale nimmt oder Modelle herstellt und wie diese beschaffen sind. 


**Arbeiten mit Modellen**
Upmeier zu Belzen, A. / Krüger, D. (2010): Modellkompetenz im Biologie-
unterricht. ZfDN 16, 41–57:

Modelle sind aus dem Biologieunterricht nicht wegzudenken: Sie dienen als Mittel, mit deren Hilfe die Schüler die biologische Welt erkunden und entdecken, neue Erkenntnisse über die Natur gewinnen und sich somit unbekannte Biologie erschließen.
(s.138)

Autorinnen und Autoren sehen Schülerinenn und Schüler vor dem Dilemma, dass sie ein Modell einerseits als exakte Replikation des Orignals erwarten und andererseits mit Modellen als Ideen konfrontiert werden, denen immanent die exaktheit fehlt. Außederm diskutieren die Autorinnen und Autoren potenzielle Missverständnisse bei SuS zwischen dem engen Modellbegriff im täglichen Leben und dem Modellbegriff in de Wissenschaft, der breiter aufgefasst wird und viel Repräsentationsformen zulässt.

In: Biologiedidaktische Forschung: Erträge für die Praxis - herausgegeben von Jorge Groß, Marcus Hammann, Philipp Schmiemann, Jörg Zabel
ISBN: 978-3-662-58442-2


### Objekte vs. Konzepte - ein Problemfeld
Die Funktionsweise des Erzählomaten wird ideal bedient, wenn kleine, handliche Objekte auf der Box landen und dann dort eine/ihre Geschichte erzählen. Für die Biologie, die Archäologie, Sprachen oder die Künste scheint es eher leichter zu sein, solche konkrete (Unterrichts-)Objekte zu finden, und zum Sprechen zu bringen. 

Wie aber kann oder soll der Erzählomat Konzepte transportieren, wie sie etwa die Musik, die Geisteswissenschaften oder die Mathematik kennt? Wie bringt man das Konzept "Oper" auf die Box, oder das Konzept "Sturm und Drang" oder "Infinitesimalrechnung"?

Für den ersten an der PH Ludwigsburg entstandenen Erzählomaten haben wir A4-Kartons mit Motiven beklebt, mit einem RFID-Chip ausgestattet und diese Bögen auf den Kasten gestellt. Thema war dabei das Konzept der Oper. 
Wir haben bislang vor allem herausgefunden, dass  man die Motivkarten deutlich und skizzenhaft anlegen soll. Sollen auch noch in de letzten Reihe grafische Impulse ankommen, müssen sie einfach, stark und klar sein. Keine kleinformatiken Grafiken, sondern lieber mit starkem Strich (Holzschnitt) und kräftigen Farben eher eine "Motivvignette" herstellen. Denn die eigntliche Information kommt über den Ton.

Konzepte sind immer ein Konglomerat aus einzelnen, kleineren Details und Sachverhalten. Es ist ein pädagogische Herausforderung, diese Sachverhalte für den Erzählomaten  zu isolieren, zu illustrieren und danach - im Ablauf des Unterrichts - sinnvoll und geordnet aufeinander (Besser: nacheinander) zu beziehen.


## Ebene drei, die didaktische Planung: Erzählomaten in Unterrichtssituationen

Der Fokus im Einsatz des Talk-O-Maten liegt auf der Interaktivität zwischen der Box und dem Lernenden im Sinne eines handlungsorientierten Unterrichts. Daher soll das Szenario des Frontalunterrichts vermieden werden. 

Gemäß dem Ansatz des Makings wäre es ideal wenn 3-4 Lernende als Gruppe mit einer Box interagieren. So lernen die Gruppenmitglieder von- und miteinander, der Fokus liegt dennoch weiterhin auf dem Talk-O-Maten. Lehrende sind eher als Mentor*innen zu sehen und könnten sich Schritt für Schritt aus dem Lernprozess der Lernenden zurückziehen bzw. im Hintergrund agieren. Am Beispiel des Prototyps “Der fliegende Holländer” wollen wir im Folgenden verschiedenen Szenarien exemplarisch skizzieren, wie eine Einbindung in den Fachunterricht aussehen könnte. In der praktischen Umsetzung müssten verschiedene Aspekte, wie Zielgruppe, Vorwissen, Zeitressourcen, Inhalte etc. bei der Konzeption berücksichtigt werden. 

### Interaktion mit dem Talk-O-Maten via Stationsarbeit

Da der pädagogische Lernansatz den Fokus auf die Lernenden legt, entscheiden auch diese, welche Gegenstände zu welcher Zeit auf die Box gelegt werden. Um eine gewissen Chronologie der Inhalte der Audiodateien zu gewährleisten, empfehlen wir, mit dem Startobjekte zu beginnen. Danach können die Lernenden frei nach Interesse und Neugierde wählen, welche Gegenstände auf die Box gelegt werden sollen. Die Box selbst gibt auditiv die nächsten möglichen Objekte (Lerngegenstände) vor. Folgt man einem dieser Wege, ist trotz der Wahlmöglichkeit eine Abfolge gewährleistet. Zur Visualisierung der Inhalte wurde die Abbildung 2 entworfen. Sie zeigt einen ersten Strukturentwurf und Überblick über die auditiven Inhalte zu den Objekten aus unserem Prototypen “Der fliegende Holländer”. Folgende Inhalte werden thematisiert bzw. folgende Objekte stehen zur Auswahl: Oper, Leitmotiv, WWV, die Charaktere Daland, Senta und der Holländer, die Handlung, die Einleitung, Ouvertüre, 1. Aufzug, 2. Aufzug und 3. Aufzug. Außerdem gibt es jeweils Start- (1+2) und Schluss-Elemente. Zu den fettgedruckten Lerngegenständen existieren bereits Audiofiles in einem Entwurfsstadium zur Simulation.
Eine methodische Idee ist die Einbindung des Talk-O-Maten in eine Art Stationsarbeit. Hier könnten mehrere Talk-O-Maten in die Unterrichtseinheit integriert werden. 

**Variante 1:**

Es würde sich anbieten, dass es je nach Größe der Schulklasse, einige Talk-O-Maten zur Verfügung gestellt werden und Schüler:innen an jeder Box etwas anderes erleben bzw. andere Aufgaben bearbeiten. Vorab festgelegte Gruppen könnten die einzelnen Stationen individuell bearbeiten. Außerdem könnte es an jeder Station einen Experten / eine Expertin für den Talk-O-Maten geben, der oder die für Fragen von Mitschüler*innen zur Verfügung steht. Nach der Stationsarbeit können alle Erlebnisse im Plenum besprochen werden. Übergeordnete Themen könnten die Stationen thematisch clustern, z.B. Charakterstation, Handlungsstation, Backgroundstation. An jeder Station würde es dazu thematisch passende Objekte geben. Somit wäre die räumliche Kopplung von Station und Inhalt im klassischen Setting der Stationsarbeit gegeben. 

**Variante 2:**

Die Stationsarbeit könnte auch neu gedacht werden, sodass vorher keine Gruppen eingeteilt sind und  gemeinsam an einer Ausgangsbox mit dem Startobjekt begonnen wird. Je nach Interesse können sich dann Gruppen an verschiedenen Stationen bilden. Ein Beispiel: Drei Schüler:innen nehmen das Angebot wahr, sich etwas über die Oper generell anzuhören, während drei weitere direkt zu den Hauptrollen der Oper weitergehen, da sie über die Oper bereits bescheid wissen. Mit diesem Verfahren teilen sich die Gruppen durch Ihren individuellen Lernstand selbst ein. Bei dieser Variante des Stationslernen, wäre der Inhalt nur an das Objekt, nicht an die Station gekoppelt. Jede*r kann mit seinem Objekt zum freien Ort seiner Wahl und sich dort mit Gleichgesinnten versammeln und gemeinsam hörend lernen. Klassisch könnte zur Ergebnissicherung bei beiden Varianten auch ein Quiz/Fragebogen zu jedem Objekt auszufüllen sein.

Beide Szenarien eignen sich gut für Schüler:innen die wenig Vorwissen im Bereich technisches Gestalten mitbringen und daher noch unsicher sind und mehr Instruktion benötigen. Diese Art der Einbindung in den Fachunterricht kann neugierig machen, den Talk-O-Maten verstehen zu wollen, ihn auseinanderzubauen oder Teile davon selbst herzustellen. Es eignet sich also gut, als Einstieg für die weitere Arbeit mit dem Talk-O-Maten und um zunächst die (technischen) Strukturen verstehen. Evtl. entwickeln Schüler:innen beim Erkunden des Talk-O-Maten schon Ideen, welche Inhalte so einer Box ebenfalls “verpackt” werden können. 

### Musikkonzepte über den Erzählomaten (ErzM) vermitteln

Dies ist leider eher ein konzeptuelles Fragment, das unsere Überlegungen zuur Arbeit des Erzählomaten darstellt, wenn es um Konzepte in der Musik geht:

Aufgelegt werden Bildkarten. ErzM muss daher evtl. einen Ständer für solche Karten besitzen.

1. Fragen/Musikschnipsel: produktorienterter Lerner, arbeitet sich ein.
2. Reihe von Boxen: Interaktive Erkundung; man läuft durch verschieden Stationen; Lernzirkel.
3. "Zeremonienmeister": 1 Box legt Karten im Verlauf auf. Es gibt Stationen, die man erkunden kann: 27 Karten mit Informationen. Zu jeder Karte gibt es einen Lernauftrag um Karten aufzubereiten.

Etwa eine UE von 4h --> Lehrkraft gestaltet Schlüsselszenen --> Verstärkte Lernanlässe; Arbeitsblätter; Aktivierung. Idealerweise: Karte wird eigenalktiv aufgelegt; Audioaufnahme startet; ErzM ist "Rundum-Sorglos-Paket"

+ Objekte werden erstellt: Studierende gestalten Unterrichtsbezogenes Material; bauen danach Artefakte 
+  Musiklehrer macht Gruppen; diese setzen sich mit interaktivem Material auseinander und aktivieren RFID-Chip 


1. Material (in der Box) ist nicht selbsterklärend, sondern muss weiter erklärt werden, "Mosaiksteine" nicht "Bild".
2. Arbeit mit Material muss mehr umfassen, als nur auflegen & zuhören. Frage ist, wie SuS zu "Material bearbeiten" kommen.
3. Grenzen zwischen hören und machen müssen aufgebrochen/fließend werden. RFID-Chips werden selbst geordnet, werden "programmiert", werden angereichert, indem SuS Material dazu bauen: Bilder malen, Gedanken aufschreiben, …


### Neue Möglichkeiten der Box durch Ausbau/Veränderung von Soft- und Hardware

Die Software des Erzählomaten kann auf eine "Wenn-Dann"-Logik erweitert werden, die Quizfragen möglich macht und der Box also eine aktivere Rolle zuweist, als nur Abspielinstrument zu sein. Die Universität Stuttgart hat damit experimentiert, dafür muss allerdings sowohl Soft- wie Hardware der Box erweitert werden. Kontakt & Fragen: 
Jan Vanvinkenroye - Uni Stgt.

\pagebreak

# Hilfen, Hinweise, Troubleshooting

Der Teufel steckt stets im Detail. Bei selbst gebauter Technik und Open Source-Software entstehen diese Details vor allem durch die subtilen aber stetigen Veränderungen von Soft- und Hardware, die upgedatet, erneuert, verbessert wird . Daraus ergeben sich leicht voneinander abweichende Prozesse oder neue Vorgehensweisen, die eventuell nicht mehr dokumentiert sind bzw. zu noch nicht dokumentierten Problemen führen. 

## Das Forum  / Richtig googlen

Richtig zu googlen ist definitiv ein 21st-Century-Skill. Wichtig ist: Viele Worte, viele Details in die Suchmaske eintragen. Bei Fehlermeldungen aus der Software (imaginäres Bsp:"Port 23 Output 5  list 000 000") immer die ganze originale  Fehlermedlung kopieren, eingeben und suchen.

## Tonuino automatisch bei längerer Inaktivität abschalten

Die separate Stromversorgung  bedeutet auch, das man sie nach dem Unterricht wieder abschalten mus,was leicht vergessen wird. Dieses Video zeigt eine remedur, die allerdings auch wieder in neuen Basteleien endet ...

## Stromversorgung: Mobil oder stabil?

Powerbanks sind wartungsintensiv und können sich abschalte. Stromkabel liefern zuverlässig, benötigen aber eine Steckdose, werden also immobiler, auch muss dann im Erzählomaten noch ein Transformator eingebaut werden

## Kopfhörer statt Lautsprecher 

Sollen mehrere Boxen in einem Unterrichtsraum arbeiten, kommt es notwendigerweise zu Klangbrei. Abhilfe schaffen könnten Boxen, die statt Lautsprechern Kopfhörerbuchsen anbieten.

![Situationsskizze "Erzählomat mit Kopfhörern"](erzaehlomat-doku-grafik/situation-kopfhoerer-talko.jpg)

Denkbar wären dabei 4-6 Anschlüsse, die dann mit mehreren Boxen Stationenarbeit erlauben. 
In der offenen Web-Community sind solche Kopfhörer-Lösungen bislang nicht zu finden. Rein technisch wären sie aber sehr leicht umzusetzen. Charmant ist außerdem, dass der fehlende Lautsprecher ein extrem flaches Design der Box zulassen würde. Dabei müssten Abmessungen von ca. 22 x 15 x 3,5 cm gut ausreichen, um übliche Modelle darauf zu platzieren. Der Nachteil wäre, dass die bislang alleine arbeitende Box, nun zwingend Zubehör benötigt.


\pagebreak

\pagebreak

# Literatur & Quellen {-}
\small
\sf
\begin{spacing}{1}
\parskip=2pt
\parindent=-7pt

 Peschel, Markus (Hrsg.): KINDER LERNEN ZUKUNFT - Didaktik der Lernkulturen. HG: Grundschulverband e. V. Ffm. ISBN: 978-3-941649-32-3 / Best. -Nr. 1117 (Beiträge zur Reform der Grundschule, Band 153) Bestelladresse: info@grundschulverband.de bzw. direkt online unter
www.grundschulverband.de --> Shop  → Buchreihe

Schaal/Brändle/Wilcke (2022): Making im Biologieunterricht -  Naturwissenschaftliches Lernen mit Kreativität und Technik verbinden. In: Unterricht Biologie, Nr. 473 | 2022. Hannover: Friedrich Verlag. S. 44-47

Schade, B. L., Dietz, C. T., Smith, O. C., & Gibbs, T. (2019). Evaluating Museum in a Box for the London Postal Museum. Retrieved from
https://digitalcommons.wpi.edu/iqp-all/5441

Upmaier zu Belzen, A (2013): Unterrichten mit Modellen. In: H. Gropengießer, U. Harms & U. Kattmann (Hgg.) Fachdidaktik Biologie (S. 3325-334) Halbergmoos: Aulis 2013 Fachdidaktik Biologie

