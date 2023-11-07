Angabe: P:\\ento\\imc4bk1\\01_lightsOn

In HTML-Tags werden JavaScript-Funktionen oft mit sog. Ereignishandlern aufgerufen. Hier z.B. onclick
Events: siehe [JavaScript Events (w3schools.com)](https://www.w3schools.com/js/js_events.asp)

```js
<a href="#" onclick="myClick(1,1)">
```

Hier wird bei Klick auf das jeweilige Element (image bzw. eigentlich auf den Link) die Funktion myClick aufgerufen. Diese erhält 2 Parameter: spalte,zeile

Einstellungen:
globale Variablen

```js
var maxZeile = 5
var maxSpalte = 5;
```

`myClick` ist in jedem Link rund um die Images definiert mit einer anderen Zeilen- und Spaltennummer als Parameter. 

```js
//hier gilt JS-Syntax
function myClick(spalte,zeile) {
	//alert("myClick");
	console.log(spalte+" "+zeile);
	//Welches Bild?
   toggleImage(zeile, spalte);
   //Bild oben
   var oben = zeile - 1;
   var unten = zeile + 1;
   var links = spalte - 1;
   var rechts = spalte + 1;
   //if (oben>0) 
      toggleImage(oben, spalte);
   //if (unten<6) 
      toggleImage(unten, spalte);
   //if (links>0) 
      toggleImage(zeile, links);
   //if (rechts < 6) 
      toggleImage(zeile, rechts);
   
}
```

Um den Code für das Ändern des Bildes nicht 5 mal redundant zu haben, wird dieser in der Funktion` toggleImage` eingefügt. Wiederum mit Parametern `zeile`, `spalte` (diesmal vertauscht)

```js
function toggleImage(zeile, spalte) {
   //Am Beginn brechen wir die Funktion mit return false ab, falls ein Parameter
   //nicht im gültigen Bereich ist.
   if (zeile < 1 || spalte < 1 || zeile > maxZeile || spalte > maxSpalte ) return false;
   var bildid = "bild"+spalte+zeile;
	var bild = document.getElementById(bildid);
	console.log(bild);
	if (bild.src.indexOf('off.gif') >= 0) {
      //off.gif gefunden
      bild.src = "images/on.gif";
   } else {
      bild.src = "images/off.gif";
   }
}

```

   Um die Schritte mit zu zählen und den entsprechenden Seitenbereich damit zu befüllen fügen wir am Ende unserer Funktion `myClick` folgenden Code ein:
   
  ```js
schritte++;
counter.innerHTML = "<b>"+schritte+"</b>";
```

Schlussendlich müssen wir noch in einer eigenen Reset-Funktion alles wieder zurücksetzen (Grafiken und Zähler):

```js
function reset() {
	schritte = 0;
	counter.innerHTML = schritte;
	for (var zeile = 1;zeile <= maxZeile; zeile++) {
		for (var spalte = 1;spalte <= maxSpalte; spalte++) {
			var bildid = "bild"+spalte+zeile;
			var bild = document.getElementById(bildid);
			bild.src = "images/off.gif";
		}
	}
}
```
