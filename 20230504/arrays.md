# Arrays
Viele verschiedene Variablen in einem Sketch zu verwalten wird schnell unübersichtlich. Betrachte den Code in diesem Beispiel: <br/> https://editor.p5js.org/hzuellig/sketches/D8JJrHjhF <br/> 
Ein Array ist dazu da, inhaltlich zusammen gehörenden Variablen gemeinsam zu verwalten. <br/> 
Definition: eine bestimmte Anzahl Daten-Elemente, welche unter dem gleichen Namen abgespeichert sind.z.Bsp.<br/> 
> Gebäude der Bahnhofstrasse   <br/> 
> Bahnhofstrasse = Name des Arrays  <br/> 
> Gebäude = Daten-Elemente im Array  <br/> 
> Sprüngli <br/> 
> Credit Suisse <br/> 
> Globus <br/> 
> Um die Gebäude zu finden, braucht es eine Nummerierung (Index) <br/> 
> Die Indexe eines Arrays beginnen bei 0. Über Arrayname und Indexnummer in eckiger Klammer wird ein Element initialisiert:<br/> 
> `let Bahnhofstrasse = new Array();`<br/> 
> `Bahnhofstrasse [0] = 'Sprüngli'` <br/> 
> `Bahnhofstrasse [1] = 'UBS'`<br/> 
> `Bahnhofstrasse [2] = 'H&M'`<br/> 
> etc.<br/> 
> Über Arrayname und Indexnummer kann auf diesen Wert wieder zugegriffen werden.<br/> 
> `Bahnhofstrasse [0]`<br/> 
> enthält den Wert 'Sprüngli'. <br/> 


## Beispiel Arrays
Jeder Eintrag, welcher in einem Array gespeichert ist, wird typischerweise als Element bezeichnet und hat einen Index, der seine Position definiert. Das erste Element innerhalb eines Arrays hat den Index 0, das zweite hat den Index 1 und so weiter; das letzte Element hat den Index gleich der Anzahl aller Elemente minus 1. Wir können beispielsweise eine Farbpalette innerhalb eines Arrays speichern:<br/> 
`let colors = [ "#FF0000", "#FFC000", "#E0FF00", "#7EFF00", "#21FF00" ];`<br/> 
Ein Array kann in jedem Eintrag Zahlen, Strings (=Buchstaben), oder auch ein weiteres Array enthalten.<br/> 
Um die Anzahl der Element in einem Array herauszufinden, gibt es die Eigenschaft `length`, welches die Länge des Arrays als Zahl zurückgibt. Probiert mal: `console.log(colors.length);` auszugeben. 

## Durch ein Array "loopen"
Sobald man die Länge eines Arrays kennt, kann man mit einer for Schleife alle Elemente einer Liste mit nur wenigen Zeilen Code auslesen. <br/> 
<a href="https://editor.p5js.org/hzuellig/sketches/oUWHXXH1_" target="_blank">Beispiel</a>
<br/> <br/> 
<a href="https://thecodingtrain.com/tracks/code-programming-with-p5-js/code/7-arrays/1-arrays" target="_blank">Daniel Shiffman erklärt Arrays </a> 



## Übung 
Erstelle eine 'lebendige Linie', welche die letzten 100 Mauspositionen darstellt. Speichere dafür die Mausposition in zwei Arrays, eines für die x Position, eines für die y Position. 
Alternative, speichere die Mausposition in einem zweidimensionalen Array. 
<br/> 
Erweiterung: Stelle die Linienabschnitte unterschiedlich dar, je nach Länge des Abschnitts oder je nach Position im Array.  <br/> 
Erweiterung: Lass ein Objekt entlang der Linie fahren.  <br/> 

<a href="https://editor.p5js.org/hzuellig/sketches/ZsUJ7HTLw" target="_blank">Hint</a>