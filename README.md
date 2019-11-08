# Projektseite: SpaceCollector

## Einleitung
SpaceCollector ist ein Spiel, welches wir während des Informatikunterrichts im 12. Jahrgang entwickelt und programmiert haben. Hierbei haben wir die Plattform studio.code.org genutzt, welche die Codesprache in einfachen Bausteinen darstellt und so das Programmieren ohne Vorkenntnisse erheblich erleichtert. Dies war für uns das ausschlaggebene Argument, diese Plattform zu wählen, da wir beide im Informatikunterricht das erste Mal mit Programmiersprachen in Kontakt waren. Nachdem wir verschiedene Spielmodelle in Erwägung gezogen hatten, entschieden wir uns ein Spiel des Collectorgenres. Nach dem Progammieren eines simplen Spiels ohne weitere Funktionen war es ein leichtes, das Grundspiel zu entwickeln. Die anschließende Weiterentwicklung war der Hauptbestandteil der Informatikstunden.
Im folgenden Text werden wir unser Spiel erklären und auf Herausforderungen und Schwierigkeiten während des Prozesses eingehen.

## Spielprinzip
Bei SpaceCollector konkurrieren zwei Aliens im All um verschiedene Coins. Im Hintergrund funkeln Sterne, um das All darzustellen. Die Coins werden durch simples Berühren eingesammelt. 

## Spielfiguren und Steuerung
Das Spiel wird von zwei Spielern gegeneinander gespielt. Spieler 1 steuert den grünen Alien, Spieler 2 den pinken Alien.

<img src="https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/Player1.jpeg" alt="image" width="100">

<img src="https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/Player2.jpeg" alt="image" width="100">

Spieler 1 steuert die Spielfigur mit den Tasten WASD, Spieler 2 mit den Pfeiltasten, wobei sich die Animation für links und rechts so verändert, als wenn die Spielfigur nach links bzw. rechts laufen würde.

<img src="https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/Player1L.jpeg" alt="image" width="100">

<img src="https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/Player1R.jpeg" alt="image" width="100">

<img src="https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/Player2L.jpeg" alt="image" width="100">

<img src="https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/Player2R.jpeg" alt="image" width="100">

Bilder Code Steuerung

Es ist möglich, am linken Spielfeldrand das Spielfeld zu verlassen und auf der rechten Seite zu erscheinen. Dasselbe gilt für die andere Richtung sowie den oberen und unteren Rand. Dieses Prinzip haben wir von dem Handyspiel "Doodle Jump" übernommen. Wir entschieden uns dafür, da sonst die Spielfiguren, einmal außerhalb des Spielfelds, nicht mehr sichtbar sind und nur schwer wieder in den sichtbaren Bereich zu navigieren sind. 

## Coins
In "SpaceCollector" gibt es vier verschiedene Arten von Coins. Diese haben die Wertigkeiten 1, 2, 5 sowie -1. Die unterschiedlichen Wertigkeiten werden durch uterschiedliche Farben und Kennzeichnungen eindeutig gezeigt.


<img src="https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/C1.jpeg" alt="image" width="100">

<img src="https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/C2.jpeg" alt="image" width="100">

<img src="https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/C5.jpeg" alt="image" width="100">

<img src="https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/BadC.jpeg" alt="image" width="100">

Die Coins werden durch Berühren mit dem Spielcharakter eingesammmelt und erscheinen an einem zufälligen Ort erneut auf dem Spielfeld. Die Anzahl gesammelter Coins kann am oberen Rand des Spielfelds dem Coincounter entnommen werden.

Bild Coincounter
<img src="https://github.com/BohrisNaturalisRettner/ToDo/blob/master/GreenSHield.png" alt="image" width="100">

Bei 30 gesammelten Münzen erscheint irgendwo ein großer, blinkender Coin in der Farbe des Charakters.


<img src="https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/WC1.jpeg" alt="image" width="100">

<img src="https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/WC2.jpeg" alt="image" width="100">

Wenn dieser Coin vom Charakter eingesammelt wird, hat dieser Spieler gewonnen. Wird dieser Coin jedoch vom Gegner eingesammelt, so wird der Coincounter auf 20 zurückgesetzt, sodass auch der andere Spieler noch eine Chance hat, das Spiel zu gewinnen. 

## Hindernisse
Die Hindernisse in SpaceCollector sollen das Spielerlebnis spannender gestalten, indem sie die Spieler beim Sammeln der Coins behindern. In SpaceCollector gibt es drei Hindernisse: Eine Sonne in der Mitte des Spielfelds sowie zwei Raumschiffe, die in einem Viereck im Uhrzeigersinn um die Sonne herumfliegen.

<img src="https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/H1.jpeg" alt="image" width="100">

<img src="https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/H2.jpeg" alt="image" width="100">

Bei den Raumschiffen haben wir verschiedene Spriteanimationen genutzt, um die Flugrichtung realistisch darzustellen.

<img src="https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/H2.jpeg" alt="image" width="100"><img src="https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/H2R.jpeg" alt="image" width="100">
<img src="https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/H2L.jpeg" alt="image" width="100">
<img src="https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/H2U.jpeg" alt="image" width="100">

Bei Berühren der Raumschiffe werden 2 Coins abgezogen, bei Berühren der Sonne 3 Coins. Dabei prallen die Spielfiguren von dem Hindernissen ab, damit kein permanenter Kontakt und somit permanenter Coinverlust möglich ist.

Bilder Code

Sollte man durch den Hinderniskontakt auf 0 oder weniger Coins zurückgesetzt werden, wird die Spielfigur auf den Spawn zurückgesetzt und der Coincounter auf 0 gestellt, damit keine Minuspunkte möglich sind.

Bild Code



## Der Endbildschirm
Sollte es einem Spieler gelingen, den eigenen WinningCoin einzusammeln, verschwindet das Spielfeld mit sämtlichen Spielfiguren, Münzen und Hindernissen und es erscheint der Endbildschirm. Dieser zeigt die Spielfigur des Gewinners in Siegerpose neben einer Goldmedaille auf hellblauem Grund. Dazu kommen die Textausgaben "Congratulations" und "Player 1 Wins" bzw. Player 2 Wins". 

Bilder WinningScreens
<img src="https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/M.jpeg" alt="image" width="100">
<img src="https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/Player1W.jpeg" alt="image" width="100">
<img src="https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/Player2W.jpeg" alt="image" width="100">

Dies ist das Ende des Spiels.
