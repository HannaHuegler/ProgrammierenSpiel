# ProgrammierenSpiel
Hanna Hügler Ageguesser

In dem Spiel werden der Reihe nach Bilder angezeigt. Der Benutzer muss dann ein Alter raten und dieses eingeben. Dannach läuft die API darüber und rät ebenfalls. Es wird dann die Differenz zwischen geratenem und realem Alter angezeigt und dadurch ein Score ermittelt. 
![Bildtext](doku/API.jpg "Bildtitel")
Die API die ich verwendet habe ist die face detect-age von Cloudmersive.


Usage / Benutzung

Man benötigt einen Web-Server(http-server auf terminal). 
- Benutzer muss das Alter eingeben diese wird ihm dann angezeigt
- Dannach auf denn Play against API Button klicken
- es wird ein Countdown angezeigt wie lang die API ungefähr noch braucht bis dass Ergebnis angezeigt wird
- Das reale Alter, das geratene Alter der API, die Differenzen zum geratenen und realen und dem realen und geratenen der API wird angezeigt
- Das Scoring wird angezeigt. Das funktioniert be mir allerdings noch nicht bei dem Score kommt immer  [object HTMLDivElement] heraus
- Zuletzt muss der Benutzer auf Lade neuse Bild drücken um das nächste Bild zu sehen


Structure / Aufbau

Datensatz: Die Bilder sind mit dem zugehörigem Alter in einem Array abgespeichert 
    name: Name der Bilddatei
    age: Alter der Person
inputage: Alter das der Benutzer geraten hat
timeleft: Zeit für Countdown der herunter zählt
myImage: zieht sich das jetzige Bild heraus
myCanvas: Zeichenfläche für HTML 
blob: Datensatz chunk, hält Daten
apiinput: Alter das die API geraten hat
yourcount: Differenz zwischen Benutzer geratenem Alter und realem Alter 
apicount: Differenz zwischen API geratenem Alter und realem Alter
yourscore: Score vom Benutzer im Vergleich zum relen Alter
apiscore: Score von API im vergleich zum realen Alter
score: Score der aus apiscore und yourscore berechnet wird mir wird aber immer:[object HTMLDivElement] angezeigt

ctx.drawImage(myImage, 0, 0, 800, 800 * myImage.height / myImage.width): Bildausschnit über den API läuft(ganzes Bild)

apiinput = result.data.PeopleWithAge[0]["Age"] : zieht das Alter mit direkter Angabe aus dem Array damit dieses dann angezeigt werden kann




Der Benutzer rät ein Alter das ihm auch angezeigt wird. Dannach wird das Bild in die Rohdaten zerlegt diese werden dann zu einem Blob gemacht. Diese Daten werden in die API geschickt, die diese dann ausliest und unter anderem das von ihr bestimmte Alter ausgibt. Dieses wird dann mit apiinput festgelegt um damit weiter zu rechnen. 
Zuerst wird die Differenz von dem echen und benutzer Alter berechnet mit: positiveyourcount wird die Differenz festgelegt und ausgegeben.
Dann wird die Differenz von API und realem Alter berechnet und mit apipositiveyourcount festgelegt und ausgegeben.
Scoring
Wenn Benutzer oder API genau das richtige Alter erraten und die Differenz somit 0 beträgt, wird der eigene score auf 10 gesetzt und die beiden werden je nach dem voneinander abgezogen.

Wenn Benutzer oder API eine höhere Differenz als Null haben wird die jeweilige Differenz von 10 abgezogen und so der Score festgelegt.

Dannach kann auf Lade neues Bild geklickt werden, um zum nächsten Bild zu kommen, der Counter wird dann hochgezäht um so zum nächsten Bild im Array zu gelangen. Das ganze ist mit einer setTimeout Funktion versehen um damit das neuladen des Bildes zu verzögern.



Future Work

- Erweitern des Datensatz um Blder mit dem zugehörigem Alter
- Zeitlicher ablauf, so dass direkt beim Laden des Bilds API aufgerufen wird
- Score jede Runde addieren
