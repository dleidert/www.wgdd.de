---
title: N54L - Lüftertausch
date: '2013-06-27T02:17:00.002+02:00'
category:
- hardware
tags:
- hardware
- n54l
- microserver
last_modified_at: '2015-02-11T21:21:09.156+01:00'
redirect_from:
- /2013/06/n54l-luftertausch.html
---

Nachdem ich mich im Vorfeld bereits [belesen] hatte, erwartete ich erschwerte
Bedingungen, den im N54L verbauten Gehäuselüfter gegen einen [Scythe Slip
Stream Gehäuselüfter 120mm][SSSGL] mit 800&nbsp;RPM und 11&nbsp;dB für ca.
*9&nbsp;EUR* (*SY1225SL12L*) zu tauschen.

[belesen]: http://www.silentpcreview.com/article1193-page7.html
[SSSGL]: http://www.scythe-eu.com/produkte/luefter/slip-stream-120.html

Die erste "Überraschung" erwartete mich nach dem Auspacken des neuen Lüfters:
statt des erwarteten 4-Pin-Anschlusses war da nur ein 3-Pin-Anschluss sowie ein
Adapterkabel zum Anschluss des Lüfters an einen 12&nbsp;V MOLEX-Stecker. Der
Gehäuselüfter im N54L steckt jedoch mit einem 4-Pin-Anschluss am Mainboard. Um
es vorweg zu nehmen: Der o.g. Scythe-Lüfter ist kein [PWM-Modell] und verfügt
damit nicht über den vierten Anschluss. Positiv ist, das ich auch gar nicht
erst die Anschlüsse am 3-Pin-Stecker tauschen musste und dieser auch sehr gut
auf dem Board befestigt werden kann ... sofern man über eine Verlängerung
verfügt! Diese war glücklicherweise noch vorhanden. Sogar ein Regelmodul von
Zalman fand sich noch in den Überresten älterer PCs - wurde jetzt aber nicht
verbaut :)

[PWM-Modell]: http://www.scythe-eu.com/produkte/luefter/slip-stream-120-pwm.html

So bin ich vorgegangen um den alten Lüfter zu entfernen:

1. N54L ausschalten und Stromversorgung trennen

1. Fronttür des N54L öffnen - am Anschlag die Tür leicht anheben und so aus
ihrer Verankerung befreien und vollständig abnehmen

1. Kopfplatte des N54L abnehmen; Schraube an der Rückseite lösen
([Handbuch](http://bizsupport2.austin.hp.com/bc/docs/support/SupportManual/c02516488/c02516488.pdf
"HP ProLiant MicroServer Benutzerhandbuch"){: type="application/pdf"
hreflang="de"}); Platte zunächst nach vorne ziehen und dann leicht anheben;
Blick auf den Gehäuselüfter wird freigegeben

1. Kabel des Lüfters suchen - verläuft links neben Einschubschacht für
optisches Laufwerk und dann am linken Gehäuserand bis zum Mainboard, wo der
Stecker ca. 2,5&nbsp;cm neben dem USB-Anschluss auf dem Mainboard steckt - mit
insg. 3x Kabelbindern befestigt

1. Kabelbinder entlang des Lüfterkabels mit Seitenschneider entfernen

1. Anschluss des Lüfters vorsichtig mit Telefonzange und Fingern vom Mainboard
abziehen (ging etwas schwer)

1. Clip auf der rechten Gehäuseseite öffnen (dagegen drücken), Lüfterkabel
entfernen und Clip wieder schließen

1. Lüfterkabel vorsichtig durch die Schächte zum Gehäuselüfter zurückziehen

1. 4&nbsp;Schrauben des Lüfters am hinteren Gehäuse mit dem Torx-Schlüssel
(Servertür) lösen und entfernen

1. vorsichtig den Lüfter entlang den Schienen nach oben ziehen - dabei habe ich
die Kabel von den Festplattenplattenschächten mit einem Lineal vom Lüftergitter
ferngehalten, da diese sonst in das Gitter ragten

1. Lüfter entnehmen

1. Befestigung des Lüftergitters lösen, indem die Stifte mit einem spitzen
Gegenstand (Telefonzange) nach außen gedrückt und dann die Befestigung selbst
entfernt wird

Entgegen meiner Erwartung hatte der Scythe-Lüfter die richtige Steckerbelegung
für das HP-Board (Pin&nbsp;4: yellow, Pin&nbsp;3: red, Pin&nbsp;2: schwarz -
Pin&nbsp;1: "Control" wird nicht belegt). Dementsprechend musste ich gar nichts
weiter tun. Laut
[dieser](http://www.allpinouts.org/index.php/Motherboard_%28CPU%29_4_Pin_Fan)
Webseite kann der 3-Pin-Stecker einfach befestigt werden. Allerdings bleibt im
N54L auf dem Board der Pin&nbsp;1 (der hinterste) frei. Und so, um den neuen
Scythe Lüfter einzubauen:

1. passende Verlängerung (3-Pin auf 3-Pin) heraussuchen und an dem Stecker, der
auf dem Mainboard befestigt werden soll, die linke Führungsfeder mit einem
Teppichmesser abschneiden

1. Verlängerung mit Lüfter verbinden

1. (Testbetrieb durch Anschließen des Lüfters am Mainboard und kurzzeitiges
Einschalten des Servers)

1. Lüftergitter am Scythe-Lüfter anbringen, Stifte zum Schluss wieder
einschieben und das Lüftergitter befestigen

1. Lüfter langsam entlang der Schienen einschieben (dabei wieder die Kabel vom
Lüftergitter fernhalten)

1. Lüfter mit den vier Torx-Schrauben befestigen

1. Kabel entlang Einschubschacht für optisches Laufwerk verlegen; in Clip auf
der linken Gehäuseseite befestigen

1. 3-Pin-Stecker auf dem Mainboard befestigen (der hinterste Pin für PWM bleibt
unbelegt) - dank des Entfernens der Feder passt der Stecker :)

1. Kabellage noch einmal prüfen und dann Lüftungskabel mit Kabelbindern an den
drei originalen Stellen wieder befestigen

1. Kopfplatte anbringen und mit Schraube an der Rückseite befestigen

1. Tür einhängen und schließen

Nach dem Verbinden der Stromversorgung lief der Server beim Einschalten wieder
an. Der Scythe-Lüfter ist hörbar leiser als der original verbaute. Das ist sehr
gut. Aber für mich könnte der N54L dennoch eine Spur leiser werden.

*[PWM]: Pulsweitenmodulation

<!-- {: type="application/pdf" hreflang="de"} -->


<!-- vim: set tw=79 ts=2 sw=2 ai si et: -->
