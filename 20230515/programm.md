# DOM (Document Object Model)
DOM, was ist das? <br/>
Eine Schnittstelle, über die JavaScript alle Elemente eines HTML Dokuments verändern kann.<br/>
https://www.w3schools.com/js/js_htmldom.asp<br/>
Noch etwas tiefer: https://eloquentjavascript.net/14_dom.html<br/>

## Ein Beispiel
Mit JavaScript Attribute eines Elements verändern:
Erstelle im HTML ein Element mit der ID #element und style es über CSS. Positioniere es absolut.
```html
<div id="element"></div>
```
im head einbinden:
```html
<style>
    #element{
        position: absolute;
        top: 200px;
        left: 0px;
    }
<style>
```
Im body:
```html
<button  onclick="moveEl()">Klick Mich!</button>


```
Verändere die Position des Elements, im script.js
```js
let n = 0; /*schlüsselwort let und variablenname. zuweisung des werts von rechts nach links */
function moveEl() {
    n++;
    document.getElementById("element").style.left = n + "px";
}
```
Du greifst nun über die DOM Schnittstelle auf das Attribut left zu.<br/>
W3C, Zugriff auf Style Properties: https://www.w3schools.com/jsref/prop_style_aligncontent.asp<br/><br/>

## Ein zweites Beispiel
<a href="JSIntro.zip" target="_blank">Elemente mit JavaScript erzeugen, Gerüst laden </a> :round_pushpin:

## JS Cheat Sheet 
https://eparraaravena.github.io/clase-p5-1/referencias.html

## Try
```js
/*--- Attribute verändern ---*/
//https://www.w3schools.com/jsref/dom_obj_style.asp

/*----alle Elemente mit der Klasse random verändern---*/
//https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementsByName

/*----durch NodeList loopen----*/
//https://developer.mozilla.org/en-US/docs/Web/API/NodeList

/*--- Elemente löschen ---*/
//https://developer.mozilla.org/en-US/docs/Web/API/Element/remove



```

## HTML Events, Event Listener 
https://www.w3schools.com/jsref/met_element_addeventlistener.asp <br/>
Statt dass du im HTML über das `onclick` Attribut das Klick Event abfängst, kannst du das über JS machen. Wenn du keinen direkten Zugriff auf das HTML hast – wie es in einer Browser Extension der Fall ist – ist das die Lösung.

```js
element=document.querySelector("button"); //https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelector
element.addEventListener("click", moveEl);

```

## Zugriff auf API, Bilder austauschen
```js
/*
* replace img with some random cat img from unsplash
* @el img node
* 
*/
function replaceImage(el) {
  let stichwort = "cat"
  
  let URL = "https://source.unsplash.com/random/?" + stichwort;
  el.setAttribute("src", URL);
}

```
<a href="randomImgApi.zip" target="_blank">Boilerplate Wörter mit Bildern tauschen </a> :round_pushpin:

## Boilerplate Website Scrambler 
<a href="BoilerplateScrambler.zip" target="_blank">Gerüst laden</a> :round_pushpin:

## Ressourcen
* https://extensionworkshop.com/
* https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions
* https://github.com/mdn/webextensions-examples

