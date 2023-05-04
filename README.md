# sidekick-documentation

Aktueller Stand, zunächst aufgeteilt auf die folgenden 4 Repos:
1. https://github.com/Menersar/sidekick-gui
2. https://github.com/Menersar/sidekick-desktop
3. https://github.com/Menersar/sidekick-modules
4. https://github.com/Menersar/sidekick-extension-creator

- Um das selber zu testen, müsste man erstmal alle 4 in einen Ordner clonen oder downloaden.
- Dann braucht man auf jeden Fall Node v16 und Yarn 
(diese Vorbereitung hatte ich in https://github.com/Menersar/scratch-extensions-2#1-entwicklungsumgebung-vorbereiten- zum Großteil zusammengefasst).
- Im `1.` Repo sollte man dann `yarn install` ausführen, danach ist die GUI über `yarn start` ausführbar (wenn es fertig geladen hat, unter http://localhost:8601/ einsehbar).

<br/>

`2.` ist das Repo der aktuellen Offline-Version der GUI. Um sie zu starten müssten eigentlich lediglich die gleichen Befehle wie für 1. ausgeführt werden.

<br/>

`3.` beinhaltet nur die benötigten Module.

<br/>

`4.` ermöglicht das Erstellen und Builden von Erweiterungen (dabei habe ich mich etwas an dieser Anleitung orientiert: https://doc.codingclip.com/developer/basic).
- Zunächst sollten mit `yarn install` die Projekt-Dependencies installiert werden.
- In die Datei `sidekick-extension-creator/info.json` werden die grundlegenden Information der Extension angegeben.
- In `sidekick-extension-creator/index.js` werden die Blöcke der Extension angegeben und deren Funktionen implementiert.
- Im Ordner `sidekick-extension-creator/locales` können die Block-Texte in verschiedenen Sprachen abgelegt werden.
- `sidekick-extension-creator/assets` dient zum Speichern der Ressourcen des Plugins (hier z. B. das Icon und der Hintergrund der Erweiterung).
→ Mit diesen Dateien kann dann die Erweiterung gebuildet werden <br/>
(in den Ordner `sidekick-extension-creator/dist`) mit dem Befehlt `yarn run build`.

<br/>
<br/>

Die die in `4.` erstellte Datei kann dann über die Anwendung geladen werden.
- Dazu sollte die Anwendung aus 1. oder 2. gestartet sein.
- Danach auf den `Add Extension`-Button (links unten) klicken.
- Auf den Upload-Button klicken und die exportierte Datei (über `4.`) auswählen.
- Sobald die Extension in der Extension-Bibliothek erscheint, die Erweiterung mit einem Klick aktivieren (über den kleinen Regler im Kasten der Erweiterung).
- Danach auf den Back-Button (links oben) gehen und eine auftretende Meldung bestätigen.

Die Blöcke der Erweiterung sollten nun in der entsprechend spezifizierten Kategorie auftauchen und (entsprechend der implementierten Funktionen) bedienbar sein.
(Als Beispiel habe ich im Repo `4.` eine Umsetzung von 2 Blöcken mit unterschiedlichen `Hello World`-Rückgaben hochgeladen).

<br/>

#### Beispiel-Blöcke in der Anwendung:
![Screenshot 2023-05-04 104224](https://user-images.githubusercontent.com/48289383/236154466-3c3976ed-84ca-45db-ab3d-6e80b468c616.png)
