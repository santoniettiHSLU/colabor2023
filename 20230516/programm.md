# Browser Extension
Eine Browser Erweiterung ist eine einfache Sammlung von Dateien, die das Aussehen und Verhalten des Browsers verändern. Sie können Elemente der Benutzeroberfläche hinzufügen, Inhalte ändern oder Hintergrundaufgaben ausführen, die das Surfen verbessern. <br/>
Über JavaScript Extension APIs können zusätzliche Informationen abgerufen und Aufgaben ausgeführt werden, die auf einer Web Applikation nicht zur Verfügung stehen. So kann zum Beispiel abgefragt werden, welche Tabs aktuell offen sind oder es kann automatisiert ein Screenshot erstellt werden, sobald der Content in einem neuen Tab geladen ist. <br/>
https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions <br/>
Die Technologie für Erweiterungen in Firefox ist weitgehend kompatibel mit der Erweiterungs-API, die von Chromium-basierten Browsern (wie Google Chrome, Microsoft Edge, Opera, Vivaldi) unterstützt wird. In den meisten Fällen laufen Erweiterungen, die für Chromium-basierte Browser geschrieben wurden, mit nur wenigen Änderungen in Firefox. <br/>

## Anatomie einer Browser Extension
|Bestandteil|Aufgabe | 
--- | --- | 
manifest.json| Dies ist die einzige Datei, die in jeder Erweiterung vorhanden sein muss. Sie enthält grundlegende Metadaten wie den Namen, die Version und die erforderlichen Berechtigungen. Außerdem enthält sie Verweise auf andere Dateien in der Erweiterung. | 
User Interface| Du kannst Symbolleistenschaltflächen, Menüoptionen und - nur in Firefox - Seitenleisten hinzufügen, um zusätzliche Inhalte anzuzeigen. Verwalte das Verhalten von Tabs und erstellen Sie Popup-Fenster, die auf Benutzerereignisse reagieren. | 
Content Scripts| Content Scripts sind von der Erweiterung bereitgestellte Skripte, die im Kontext einer Webseite ausgeführt werden. Ändere den Inhalt von Webseiten. Entferne Elemente, füge neuen Content hinzu.| 
Background Scripts| Erweiterungen müssen oft auf Ereignisse im Browser reagieren, die unabhängig von der Lebensdauer einer bestimmten Webseite oder eines Browserfensters auftreten. Dafür sind Background Scripts gedacht. Sie haben Zugriff auf die ganze JavaScript Extension API, aber nicht auf den Content einer Seite.| 

<img src="anatomy.png" width="600"/> <br/>


## First Extension
Image Replacer
```js
{
    "manifest_version": 2,
    "name": "ImageReplacer",
    "version": "0.1",
    "content_scripts": [{
        "matches": [
            "<all_urls>"
        ],
        "js": ["replace.js"]
    }],
    "icons": {
        "48": "icons/beast48.png",
        "96": "icons/beast96.png"
      },
    "browser_action": {
        "default_icon": "icons/beast96.png"
    }
}
```
Was bedeuten die <a href="https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/manifest.json" target="_blank">Einträge im manifest.json</a>? 
|Eintrag|Erklärung | 
--- | --- | 
manifest_version |  Dieser Schlüssel gibt die von dieser Erweiterung verwendete Version von manifest.json an (2 oder 3). Beachte, viele Tutorials verwenden noch die Version 2 zu 3 gibt es weniger.  | 
name |  Name der Erweiterung. Dieser wird verwendet, um die Erweiterung in der Benutzeroberfläche des Browsers und auf Websites wie addons.mozilla.org zu identifizieren. Es empfiehlt sich, den Namen so kurz zu halten, dass er in der Benutzeroberfläche angezeigt werden kann. Google Chrome und Microsoft Edge beschränken die Länge des Namens auf 45 Zeichen.  | 
version |  Die Versionszeichenfolge besteht aus 1 bis 4 Zahlen, die durch Punkte getrennt sind, beachte, hier handelt es sich um die Version deiner spezifischen Erweiterung, nicht um die Version des manifests.  | 
content_scripts |  Weist den Browser an, Inhaltsskripte (JS, CSS) in Webseiten zu laden, deren URL einem bestimmten Muster (matches) entspricht. <a href="https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/manifest.json/content_scripts" target="_blank"> Detail</a> | 
icons |  Der Icons Eintrag gibt Icons für deine Erweiterung an. Diese Icons werden verwendet, um die Erweiterung in Komponenten wie dem Add-ons Manager darzustellen.  | 
browser_action |  Eine Browseraktion ist eine Schaltfläche, die Ihre Erweiterung der Symbolleiste des Browsers hinzufügt. Die Schaltfläche hat ein Symbol und kann optional ein Popup haben, dessen Inhalt mit HTML, CSS und JavaScript festgelegt wird. Dieser Schlüssel wird in Manifest V3-Erweiterungen durch action ersetzt.| 


### Lokales Testing
Testing in Firefox `about:debugging#/runtime/this-firefox` aufrufen.
Load Temporary Add-On auswählen und `manifest.json` öffnen. <br/>
Oder über Node: https://extensionworkshop.com/documentation/develop/getting-started-with-web-ext/


### Debugging 
* Debugging von Content Skripts: über Webdeveloper Tools.
* Debugging von Background Skripts: über `about:debugging#/runtime/this-firefox` und dann `inspect` bei der jeweiligen Extension

## Second Extension
* JavaScript Object Notation
* Kommunikation zwischen content und background Scripts
* Bolierplate Store Mouse Positions

## Examples, Tutorials
* https://www.youtube.com/watch?v=Q3AQ5D2QFwc (Einfaches Tutorial, das zeigt, wie über ein Pop-Up eine CSS Property gesetzt und im Storage gespeichert/geladen wird)
* https://github.com/mdn/webextensions-examples/ Github Repo mit vielen Beispielen
* https://extensionworkshop.com Workshops von Building bis Deploying


