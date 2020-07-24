# ProgrammierenSpiel
Hanna Hügler Ageguesser

Hier beschreibe ich, was dieses großartige Projekt tut. Weshalb es gebaut wurde. Welche Inspirationen und vorhandenen Quellen eingeflossen sind, und für wen es gemacht wurde. Ein Screenshot macht sich hier auch immer gut.

Usage / Benutzung

Man benötigt einen Web-Server(http-serveer auf terminal).
Hier beschreibe ich, wie man mein großartiges Projekt benutzen kann. Was ich tun muss um es zum Laufen zu bekommen (downloaden? welcher Browser? etc.). Wie ich es steuern kann. Was (noch) nicht richtig funktioniert und weshalb.

Structure / Aufbau

Datensatz:
Die Bilder sind mit dem zugehörigem Alter in einem Array abgespeichert

alcVol: der Alkoholgehalt (Property)
amount: die Menge (Property, Standardwert: 500ml)
Person: Eine Klasse um eine Person in Code abzubilden. Enthält typische Eigenschaften und Methoden von Menschen, um mit Bier zu interagieren:

drinkBeer(beer): trinkt ein Bier, welches als Parameter übergeben wird und vom Typ / Klasse "Beer" sein muss (Funktion)
isDrunk: gibt an ob eine Person betrunken ist (Property, Boolean)
Zentrale Funktionen (die nicht zu Klassen gehören) folgen dem selben Muster, werden aber meist etwas ausführlicher beschrieben:

haveParty(persons[], interval): Eine Funktion die ein Array von Personen entgegennimmt, und diese dann im angegebenen Intervall Bier trinken lässt. Nach jedem Durchlauf durch das Biertrinken (durch Aufruf von drinkBeer mit einem neu erzeugten Bier-Objekt) wird überprüft, ob die Anzahl der betrunkenen Personen größer 0 ist. Wenn dies eintritt, wird das Intervall bei jedem Durchlauf auf die doppelte Länge verlängert. Die Funktion endet in ihrer Ausführung dann wenn alle Personen isDrunk = true zurückgeben, oder wenn das Interval größer als 1 Stunde wird. Wird die Funktion mit nur einer Person im Array aufgerufen, wird eine Warnmeldung ausgegeben, um versehentliches Trinken alleine zu vermeiden.

(Achtung: Hier werden nur Funktionen beschrieben, die eine zentrale Rolle einnehmen.)

Nach der Beschreibung der elementaren Bestandteile wird aus der Vogelperspektive nochmals beschrieben, welche Gesamtzustände euer System durchlaufen kann. In diesem Fall würde der User zunächst 0 bis n Personen erzeugen, und diese mit haveParty() zum Bier trinken bringen. Dabei wird innerhalb von haveParty nacheinander für jede Person drinkBeer() aufgerufen, unter Benutzung von neuen Bier-Objekten. Nach Ende der Party muss das Programm neu gestartet werden um die Zustände zurückzusetzen.

(Achtung, dieser Teil liest sich jetzt sehr ähnlich zur Funktionsbeschreibung von haveParty - das liegt daran dass es im Beispiel nur eine zentrale Funktion gibt. Ihr habt aber mehrere die zusammenspielen!).

Future Work

Was noch fehlt, und was die nächsten Schritte wären um es ggf. umzusetzen:

- Erweitern des Datensatz um Blder mit dem zugehörigem Alter
- Zeitlicher ablauf, so dass direkt beim Laden des Bilds API aufgerufen wird
