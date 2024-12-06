---
title: "Good practices - german version"
header:
  image: /assets/images/unit_images/u08/header.png
  image_description: "loop"
  caption: "Photo by [Christopher Kuszajewski](https://pixabay.com/de/users/kuszapro-369349/?utm_source=link-attribution&amp;utm_medium=referral&amp;utm_campaign=image&amp;utm_content=583537) [from Pixabay](https://pixabay.com/de/?utm_source=link-attribution&amp;utm_medium=referral&amp;utm_campaign=image&amp;utm_content=583537)"
---

Im aller ersten Kapitel hieß es:

*“the functional appearance of the interpreter, which in my experience has struck fear into the heart of so many an undergraduate, stays true to the very nature of the software – a blank statistical canvas that can be used for any number of tasks”*- Tilman M. Davies, The book of R "

Diese leere Leinwand, die darauf wartet, bemalt zu werden, kann einschüchternd wirken. 
Menschen neigen dazu, direkt loslegen zu wollen: Daten laden, ein paar Befehle ausprobieren, und dann stecken sie fest. In diesem Guide möchten wir euch durch die Schritte führen, die euch helfen, eine strukturierte und methodische Arbeitsweise zu entwickeln – von der leeren Leinwand hin zum fertigen Meisterwerk eurer Analyse.

Natürlich ist jede/r Künstler/in anders - dementsprechend ist der folgende Ablauf nur ein Vorschlag. 

# Schritt 1: Das Problem verstehen und Schritte planen

*Bevor man ein Portrait malt, muss man wissen, was man zeichnen möchte.*

Der erste und wichtigste Schritt ist das Verstehen des Problems und das Festlegen der notwendigen Schritte. Dazu braucht ihr theoretisch nicht einmal R zu öffnen – ein Blatt Papier oder ein Whiteboard reicht aus.

<details>
<summary>Arbeit am Beispiel </summary>
    Stellt euch vor, ihr untersucht, wie sich die Landnutzung auf das Mikroklima auswirkt. Eine erste Forschungsfrage könnte sein:
    Wie unterscheidet sich die Lufttemperatur (10 cm über dem Boden) zwischen zwei verschiedenen Landnutzungstypen?
</details

Macht euch z.B. eine Flowchart oder Ähnliches zur Übersicht.

Stellt euch folgende Fragen:

1.1 Was ist das Objekt der Untersuchung?  
1.2 Welchen Effekt wollt ihr testen?  
1.3 Welche Variablen habt ihr und welche Datentypen sollten sie haben ?  
1.4 Welche Aspekte könnt ihr analysieren?  
1.5 Gibt es weitere Einflussfaktoren?  

Anhand dieser Fragen könnt ihr, unabhängig davon ob ihr den klassischen frequentistischen, den bayesianischen Ansatz der Statistik oder machinelles Lernen nutzen wollt oder "nur" etwas darstellen wollt die verschiedenen Optionen evaluieren. 
In diesem Kurs werden wir auf dem Level deskriptiver Statistik und einfacher klassischer statistischer Tests bleiben. Gute Entscheidungshilfen zu klassischer statistik findet ihr zB hier [here](https://www.biostathandbook.com/). Dabei können die Angaben von Datentyp und ggf. confounding Variablen helfen, passende Analysen zu suchen oder die Methodik vergleichbarer Studien durchlesen.


# Schritt 2:  Projekt aufbauen, Rohdaten überprüfen und ausbessern

*Legt eure Farbpalette und Pinsel bereit*

2.1 Nutzt am besten euer [template](/moer-bsc-base-r/unit10/unit10-assignment03.html) für eure Ordnerstruktur, die README file und für euer Script.
2.2 Ladet die Rohdaten herunter. Haltet dabei wichtige Informationen und Metadaten in der README file fest.
    Woher kommen die Daten? Wann habt ihr diese erhalten? Was steckt drin? Wie viele Messpunkte beinhalten sie? etc.
2.3 Lest die Daten ein und überprüft via **str()**, ob sie den gewünschten Datentyp (s. 1.4) haben.
2.4 Führt einen Rohdaten-Check aus. Nützliche Funktionen dafür sind z.B. **summary**, **length()**, **unique()** und **tapply**, falls ihr gruppierende Faktoren habt. 
2.5 Die Daten graphisch darzustellen kann auch hilfreich sein, insb. bei räumlich- und zeitlich strukturierten Daten.
2.6 Falls euer Test in 2.4 Probleme aufgezeigt hat, könnt ihr diese nun im Script verbessern. Ändert nie die Rohdaten selbst! 
2.7 Protokolliert die Änderungen, die sich dadurch auf eure Daten ergeben.

# Schritt 3:  Daten aufbereiten

*Skizziert eure Umrisse*

Ihr wisst nun, wie eure Daten aussehen. die zwei Fragen, die man sich jetzt (erneut) stellen kann sind:

3.1 Was ist meine Untersuchungseinheit?
3.2 In welcher Struktur müssen die Daten vorliegen, damit ihr die gewählte Analyse durchgeführt werden kann?  

Letzteres könnt ihr z.B. feststellen in dem ihr die Hilfe der Funktion abfragt und die Argumente durchlest, und/oder die Beispiele durchgeht. Alternativ gibt es auch häufig sog. vignettes und/oder handbooks, die die Funktionsweisen und Hintergründe genauer erläutern.  
Ihr könnt es  wieder der in Schritt 1 erstellten Skizze verdeutlichen, wie die Struktur eurer Rohdaten aussieht, und wie die Struktur aussehen muss, die ihr später für die Analyse braucht. Daraus ergeben sich die notwendigen Funktionen zur Datentransformation. 

# Schritt 4:  Script erstellen und überprüfen

*Füllt eure Skizze aus, verbessert Stellen so lange, bis das Bild sowohl im Gesamteindruck als auch im Detail den Anprüchen genügt*

4.1 Die notwendigen Schritte zur Datentransformation und Analyse habt ihr in den vorherigen Schritten herausgearbeitet. Nun sucht euch die passenden Funktionen zusammen - ob aus diesem Handbook, Hardcover Lehrbüchern oder der weiten Welt des Internets ist egal
4.2 Prüft immer nach, ob das Resultat einer Funktion - egal ob sie zur Datentransformation, Analyse oder Darstellung verwendet wurde - stimmig ist. Stimmt nach Transformationen die Anzahl wer Einzelwerte mit dem überein, was logisch erscheint? Sind Daten verloren gegangen? Stimmen die Ergebnisse von Berechnungen? Prüft es zur Not händisch nach, Macht die Darstellung Sinn? Wenn ihr solche Fragen sicher mit ja beantworten könnt, Gratulation, ihr habt das Kursziel erreicht.  
 