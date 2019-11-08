# Projektseite: SpaceCollector

## Inhaltsverzeichnis

[1. Einleitung](#1)

[2. Spielprinzip](#2)

[3. Spielfiguren und Steuerung](#3)

[3.1 Spielfiguren](#4)

[3.2 Steuerung](#5)

[4. Coins](#6)

[4.1 Die verschiedenen Coins](#7)

[4.2 Das Sammeln der Coins](#8)

[5. Hindernisse](#9)



## Einleitung<a name="1"></a>
SpaceCollector ist ein Spiel, welches wir während des Informatikunterrichts im 12. Jahrgang entwickelt und programmiert haben. Hierbei haben wir die Plattform studio.code.org genutzt, welche die Codesprache in einfachen Bausteinen darstellt und so das Programmieren ohne Vorkenntnisse erheblich erleichtert. Dies war für uns das ausschlaggebene Argument, diese Plattform zu wählen, da wir beide im Informatikunterricht das erste Mal mit Programmiersprachen in Kontakt waren. Nachdem wir verschiedene Spielmodelle in Erwägung gezogen hatten, entschieden wir uns ein Spiel des Collectorgenres. Nach dem Progammieren eines simplen Spiels ohne weitere Funktionen war es ein leichtes, das Grundspiel zu entwickeln. Die anschließende Weiterentwicklung war der Hauptbestandteil der Informatikstunden.
Im folgenden Text werden wir unser Spiel erklären und auf Herausforderungen und Schwierigkeiten während des Prozesses eingehen. Wenn Codezeilen für Spieler 1 und Spieler 2 aus Übersichtsgründen im Code zwar in getrennten Funktionen geschrieben wurden, sich aber außer in der Bezeichnung nicht unterscheiden, werden wir aus Platzgründen exemplarisch den Code für Spieler 1 verwenden. Es ist dann davon auszugehen, dass der Code von Spieler 2 diesem entspricht.

## Spielprinzip<a name="2"></a>
Bei SpaceCollector konkurrieren zwei Aliens im All um verschiedene Coins. Im Hintergrund funkeln Sterne, um das All darzustellen. Die Coins werden durch simples Berühren eingesammelt. Ziel des Spiels ist es, Coins im Wert von 30 Punkten einzusammeln, um so den finalen Coin erscheinen zu lassen.
Zu Beginn des Spiels erscheint Spieler 1 in der oberen linken Ecke, Spieler 2 in der unteren rechten Ecke. Die Sonne ist als zentrales Hindernis im Zentrum, darum herum fliegen zwei Raumschiffe. Diese beginnen in der unteren linken Ecke bzw. in der oberen rechten Ecke des Spielfelds, also in den Ecken, wo die Spieler sich zu Anfang nicht befinden.

![Ausgangssituation](https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/Ausgangssituation.PNG)

Ausgangssituation beim Start des Spiels

## Spielfiguren und Steuerung<a name="3"></a>

### Die Spielfiguren<a name="4"></a>
Das Spiel wird von zwei Spielern gegeneinander gespielt. Spieler 1 steuert den grünen Alien, Spieler 2 den pinken Alien. Die Sprites für die Spielfiguren waren bei der Website bereits vorgefertigt und standen uns zur Verfügung.

<img src="https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/Player1.jpeg" alt="image" width="100"><img src="https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/Player2.jpeg" alt="image" width="100">

### Steuerung<a name="5"></a>
Spieler 1 steuert die Spielfigur mit den Tasten WASD, Spieler 2 mit den Pfeiltasten, wobei sich die Animation für links und rechts so verändert, als wenn die Spielfigur nach links bzw. rechts laufen würde.

<img src="https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/Player1L.jpeg" alt="image" width="100"><img src="https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/Player1R.jpeg" alt="image" width="100">

Sprites für links bzw. rechts bei Spieler 1.

![Keys1](https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/Keys%201.PNG)

Code für die Steuerung bei Spieler 1. Die Sprites für links und rechts werden zusammen mit der Geschwindigkeit gewechselt. Die if-Schleife zur Zurücksetzung des Sprites und der Geschwindigkeit war nötig, da sonst die Sprites nicht mit der Bewegungsrichtung übereingestimmt hätten.

<img src="https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/Player2L.jpeg" alt="image" width="100"><img src="https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/Player2R.jpeg" alt="image" width="100">

Sprites für links bzw. rechts bei Spieler 2.

![Keys2](https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/Keys%202.PNG)

Code für die Steuerung bei Spieler 2. Hier gilt dasselbe wie bei Spieler 1.

Es ist möglich, am linken Spielfeldrand das Spielfeld zu verlassen und auf der rechten Seite zu erscheinen. Dasselbe gilt für die andere Richtung sowie den oberen und unteren Rand. Dieses Prinzip haben wir von dem Handyspiel "Doodle Jump" übernommen. Wir entschieden uns dafür, da sonst die Spielfiguren, einmal außerhalb des Spielfelds, nicht mehr sichtbar sind und nur schwer wieder in den sichtbaren Bereich zu navigieren sind. 

![Edges](https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/Edges.PNG)

Der Code zum Erscheinen auf der jeweils anderen Seite des Spielfelds bei Verlassen des Spielfelds auf einer beliebigen Seite. Dies ist der Code für Spieler 1, derselbe Code gilt für Spieler 2, welcher sich lediglich durch die Bezeichnungen des Sprites unterscheiden.


## Coins<a name="6"></a>

### Die verschiedenen Coins<a name="7"></a>

In "SpaceCollector" gibt es vier verschiedene Arten von Coins. Diese haben die Wertigkeiten 1, 2, 5 sowie -1. Die unterschiedlichen Wertigkeiten werden durch uterschiedliche Farben und Kennzeichnungen eindeutig gezeigt.

#### Der Bronzene Coin

<img src="https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/C1.jpeg" alt="image" width="100">

![C1 Eigenschaften](https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/C1%20Eigenschaften.PNG)

Der Bronzene Coin gibt +1 Coins. Er erscheint zu Beginn des Spiels an einem zufälligen Punkt auf dem Spielfeld. 

#### Der Silberne Coin

<img src="https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/C2.jpeg" alt="image" width="100">

![C2 Eigenschaften](https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/C2%20Eigenschaften.PNG)

Der Silberne Coin gibt +2 Coins. Er erscheint zu Beginn ebenfalls an einem zufälligen Punkt auf dem Spielfeld.

#### Der Goldene Coin

<img src="https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/C5.jpeg" alt="image" width="100">

![C5 Eigenschaften](https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/C5%20Eigenschaften.PNG)

Der Goldene Coin ist der beste Coin. Er gibt +5 Coins. Auch dieser Coin erscheint zu Beginn an einem zufälligen Punkt innerhalb des Spielfelds.

#### Der Coin mit dem rotem Kreis

<img src="https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/BadC.jpeg" alt="image" width="100">

![BC Eigesnschaften](https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/BC%20Eigenschaften.PNG)

Entgegen seiner goldenen Farbe gibt dieser Coin keine Punkte. Im Gegenteil, dieser Coin gibt -1 Coin. Dieser Coin verhält sich wie alle anderen Coins auch und erscheint zu Beginn an einem zufälligen Ort. 

### Das Sammeln der Coins<a name="8"></a>

Die Coins werden durch Berühren mit dem Spielcharakter eingesammmelt und erscheinen an einem zufälligen Ort erneut auf dem Spielfeld. Gleichzeitig werden dem Coincounter des Spielers, der den Coin eingesammelt hat, der entsprechende Wert des Coins gutgeschrieben.

![Collecting](https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/Collecting.PNG)

Die Anzahl gesammelter Coins kann am oberen Rand des Spielfelds dem Coincounter entnommen werden.

![Coincounter Spielfeld](https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/Coincounter.png)

![Coincounter Variablen](https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/Coincounter%20Variablen.PNG)

![Coincounter Code](https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/Coincounter%20Anzeige%20Code.PNG)



## Hindernisse<a name="9"></a>
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










Bei 30 gesammelten Münzen erscheint irgendwo ein großer, blinkender Coin in der Farbe des Charakters.


<img src="https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/WC1.jpeg" alt="image" width="100">

<img src="https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/WC2.jpeg" alt="image" width="100">

Wenn dieser Coin vom Charakter eingesammelt wird, hat dieser Spieler gewonnen. Wird dieser Coin jedoch vom Gegner eingesammelt, so wird der Coincounter auf 20 zurückgesetzt, sodass auch der andere Spieler noch eine Chance hat, das Spiel zu gewinnen. 

