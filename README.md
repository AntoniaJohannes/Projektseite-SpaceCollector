# Projektseite: SpaceCollector

## Inhaltsverzeichnis

[ Einleitung](#)

[ Spielprinzip](#)

[ Spielfiguren und Steuerung](#)

[ Spielfiguren](#)

[ Steuerung](#)

[ Coins](#)

[ Die verschiedenen Coins](#)

[ Das Sammeln der Coins](#)

[ Hindernisse](#)

[ Die Sonne](#)

[ Die Raumschiffe](#)

[ Spielende](#)

[ Die WinningCoins](#)

[ Einsammeln des gegnerischen WinningCoins](#)

[ Einsammeln des eigenen WinningCoins](#)



## Einleitung<a name=""></a>
SpaceCollector ist ein Spiel, welches wir während des Informatikunterrichts im 12. Jahrgang entwickelt und programmiert haben. Hierbei haben wir die Plattform studio.code.org genutzt, welche die Codesprache in einfachen Bausteinen darstellt und so das Programmieren ohne Vorkenntnisse erheblich erleichtert. Dies war für uns das ausschlaggebene Argument, diese Plattform zu wählen, da wir beide im Informatikunterricht das erste Mal mit Programmiersprachen in Kontakt waren. Nachdem wir verschiedene Spielmodelle in Erwägung gezogen hatten, entschieden wir uns ein Spiel des Collectorgenres. Nach dem Progammieren eines simplen Spiels ohne weitere Funktionen war es ein leichtes, das Grundspiel zu entwickeln. Die anschließende Weiterentwicklung war der Hauptbestandteil der Informatikstunden.
Im folgenden Text werden wir unser Spiel erklären und auf Herausforderungen und Schwierigkeiten während des Prozesses eingehen. Wenn Codezeilen für Spieler 1 und Spieler 2 aus Übersichtsgründen im Code zwar in getrennten Funktionen geschrieben wurden, sich aber außer in der Bezeichnung nicht unterscheiden, werden wir aus Platzgründen exemplarisch den Code für Spieler 1 verwenden. Es ist dann davon auszugehen, dass der Code von Spieler 2 diesem entspricht.

## Spielprinzip<a name=""></a>
Bei SpaceCollector konkurrieren zwei Aliens im All um verschiedene Coins. Im Hintergrund funkeln Sterne, um das All darzustellen. Die Coins werden durch simples Berühren eingesammelt. Ziel des Spiels ist es, Coins im Wert von 30 Punkten einzusammeln, um so den finalen Coin erscheinen zu lassen.
Zu Beginn des Spiels erscheint Spieler 1 in der oberen linken Ecke, Spieler 2 in der unteren rechten Ecke. Die Sonne ist als zentrales Hindernis im Zentrum, darum herum fliegen zwei Raumschiffe. Diese beginnen in der unteren linken Ecke bzw. in der oberen rechten Ecke des Spielfelds, also in den Ecken, wo die Spieler sich zu Anfang nicht befinden.

![Ausgangssituation](https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/Spawn.PNG)

Ausgangssituation beim Start des Spiels

## Spielfiguren und Steuerung<a name=""></a>

### Die Spielfiguren<a name=""></a>
Das Spiel wird von zwei Spielern gegeneinander gespielt. Spieler 1 steuert den grünen Alien, Spieler 2 den pinken Alien. Die Sprites für die Spielfiguren waren bei der Website bereits vorgefertigt und standen uns zur Verfügung.

<img src="https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/Player1.jpeg" alt="image" width="100"><img src="https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/Player2.jpeg" alt="image" width="100">

### Steuerung<a name=""></a>
Spieler 1 steuert die Spielfigur mit den Tasten WASD, Spieler 2 mit den Pfeiltasten, wobei sich die Animation für links und rechts so verändert, als wenn die Spielfigur nach links bzw. rechts laufen würde.

<img src="https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/Player1L.jpeg" alt="image" width="100"><img src="https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/Player1R.jpeg" alt="image" width="100">

Sprites für links bzw. rechts bei Spieler 1.


<img src="https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/Player2L.jpeg" alt="image" width="100"><img src="https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/Player2R.jpeg" alt="image" width="100">

Sprites für links bzw. rechts bei Spieler 2.


![Keys1](https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/Keys%201.PNG)

Code für die Steuerung bei Spieler 1. Die Sprites für links und rechts werden zusammen mit der Geschwindigkeit gewechselt. Durch Gedrückthalten der Tasten wird man in die entsprechende Richtung immer schneller, die Spielfigur bescheleunigt. Dies wird durch das Verlassen des Spielfelds nicht beeinträchtigt. Es gibt keine Maximalgeschwindigkeit. Man hört augenblicklich auf, sich in eine Richtung zu bewegen, wenn man den Knopf loslässt. Es ist durch gleichzeitiges Drücken von zwei Tasten möglich, sich schräg über das Spielfeld zu bewegen. Die if-Schleife zur Zurücksetzung des Sprites und der Geschwindigkeit war nötig, da sonst die Sprites nicht mit der Bewegungsrichtung übereingestimmt hätten.


Es ist möglich, am linken Spielfeldrand das Spielfeld zu verlassen und auf der rechten Seite zu erscheinen. Dasselbe gilt für die andere Richtung sowie den oberen und unteren Rand. Dieses Prinzip haben wir von dem Handyspiel "Doodle Jump" übernommen. Wir entschieden uns dafür, da sonst die Spielfiguren, einmal außerhalb des Spielfelds, nicht mehr sichtbar sind und nur schwer wieder in den sichtbaren Bereich zu navigieren sind. 

![Edges](https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/Edge.PNG)

Der Code zum Erscheinen auf der jeweils anderen Seite des Spielfelds bei Verlassen des Spielfelds auf einer beliebigen Seite.


## Coins<a name=""></a>

### Die verschiedenen Coins<a name=""></a>

In "SpaceCollector" gibt es vier verschiedene Arten von Coins. Diese haben die Wertigkeiten 1, 2, 5 sowie -1. Die unterschiedlichen Wertigkeiten werden durch uterschiedliche Farben und Kennzeichnungen eindeutig gezeigt.

#### Der Bronzene Coin

<img src="https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/C1.jpeg" alt="image" width="100">

![C1 Eigenschaften](https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/C1%20Eigenschaften.PNG)

Der Bronzene Coin gibt +1 Punkte. Er erscheint zu Beginn des Spiels an einem zufälligen Punkt auf dem Spielfeld. 

#### Der Silberne Coin

<img src="https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/C2.jpeg" alt="image" width="100">

![C2 Eigenschaften](https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/C2%20Eigenschaften.PNG)

Der Silberne Coin gibt +2 Punkte. Er erscheint zu Beginn ebenfalls an einem zufälligen Punkt auf dem Spielfeld.

#### Der Goldene Coin

<img src="https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/C5.jpeg" alt="image" width="100">

![C5 Eigenschaften](https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/C5%20Eigenschaften.PNG)

Der Goldene Coin ist der beste Coin. Er gibt +5 Punkte. Auch dieser Coin erscheint zu Beginn an einem zufälligen Punkt innerhalb des Spielfelds.

#### Der Coin mit dem rotem Kreis

<img src="https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/BadC.jpeg" alt="image" width="100">

![BC Eigesnschaften](https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/BC%20Eigenschaften.PNG)

Entgegen seiner goldenen Farbe gibt dieser Coin keine Punkte. Im Gegenteil, dieser Coin gibt -1 Punkt und wird im Code deshalb als "badcoin" bezeichnet. Dieser Coin verhält sich wie alle anderen Coins auch und erscheint zu Beginn an einem zufälligen Ort. 

### Das Sammeln der Coins<a name=""></a>

Die Coins werden durch Berühren mit dem Spielcharakter eingesammmelt und erscheinen an einem zufälligen Ort erneut auf dem Spielfeld. Gleichzeitig werden dem Coincounter des Spielers, der den Coin eingesammelt hat, der entsprechende Wert des Coins gutgeschrieben.
Wie dem oben gezeigten Code zu entnehmen ist, sind die Collider aller Coins auf "circle" gesetzt. Dies dient zur exakteren Darstellung des Einsammelns der Coins, da sonst auch "Nah-Dran-Vorbeilaufen" als Einsammeln gilt.

![Collecting](https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/Collecting.PNG)

Um Minuspunkte zu verhindern, wird beim Einsammeln eines Badcoins, während man 0 Punkte hat, der eigene Coincounter auf 0 gesetzt. 
Die Anzahl gesammelter Coins kann am oberen Rand des Spielfelds dem Coincounter entnommen werden.

![Coincounter Spielfeld](https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/Coincounter.png)

![Coincounter Variablen](https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/Coincounter%20Variablen.PNG)

![Coincounter Code](https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/Coincounter%20Anzeige%20Code.PNG)



## Hindernisse<a name=""></a>
Die Hindernisse in SpaceCollector sollen das Spielerlebnis spannender gestalten, indem sie die Spieler beim Sammeln der Coins behindern. In SpaceCollector gibt es drei Hindernisse: Eine Sonne in der Mitte des Spielfelds sowie zwei Raumschiffe.

### Die Sonne<a name=""></a>

<img src="https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/H1.jpeg" alt="image" width="100"><img src="https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/Sonne%202.PNG" alt="image" width="100">

![Sonne Code](https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/Sonne%20Eigenschaften.PNG)

Die Sonne ist im Zentrum des Spielfelds. Die wechselnde Animation am Rand der Sonne soll sie ein wenig gefährlicher aussehen lassen, ebenso wie die Augen. 

#### Kollision und Punktverlust

Bei Kontakt mit der Sonne verlieren die Spieler 3 Punkte. Damit ist die Sonne das gefährlichste Hindernis im Spiel. Um permanenten Kontakt mit der Sonne und somit permanenten Punktverlust zu verhindern, prallen die Spieler bei Kontakt von der Sonne ab.
Die Stärke des Abprallens haben wir von vornherein in den Eigenschaften der Sprites der Spielfiguren festgelegt. Dies kann dem obigen Code unter "bounciness" entnommen werden.

![Kollision Sonne](https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/Sonne%20Kollision.PNG)

Wie dem Code zu entnehmen ist, wird bei der Kollision geprüft, wie viele Punkte der Spieler hat. Sollten es mehr als 0 sein (bzw. weniger als 100, wir gehen davon aus, dass niemand je 100 Coins sammelt), so verliert er die besagten 3 Punkte. Sollten der Punktestand des Spielers so niedrig sein, dass er nach der Kollision auf 0 oder weniger Punkte abrutscht, wird er an seinen Anfangspunkt zurückgesetzt, im Beispiel von Spieler 1 an die Koordinaten 50/50. Dies haben wir als kleine Strafe gedacht, um die Spieler bei niedrigem Punktestand zu besonders vorsichtigem Spielen zu bewegen.  

#### Das Münzenproblem

Nachdem wir die Sonne als Hindernis eingeführt hatten, fiel uns schnell ein schwerwiegendes Problem auf: Die Münzen konnten hinter der Sonne erscheinen und so für die Spieler unnereichbar sein. Um dies zu verhindern, haben wir eine weitere Funktion programmiert, die prüft, ob die Coins an ihrem Erscheinungsort die Sonne berühren. Sollte dies der Fall sein, erscheinen sie einfach an einem neuen Ort auf dem Spielfeld. Dabei werden selbstverständlich keinem Spieler Punkte angerechnet, obwohl die Coins ja die Position wechseln.

![Keine Coins hinter der Sonne Code](https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/Hidingcoins.PNG)

### Die Raumschiffe<a name=""></a>

In SpaceCollector gibt es zusätzlich zu der Sonne zwei weitere, sich bewegende Hindernisse in Gestalt von zwei identisch aussehenden Raumschiffen.

<img src="https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/H2.jpeg" alt="image" width="100">

#### Die Flugroute

Die Raumschiffe fliegen um die Sonne in Form eines Vierecks im Uhrzeigersinn um die Sonne herum. Dabei startet ein Raumschiff oben rechts, das andere unten links.

![ME Eigenschaften](https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/ME%20Eigenschaften.PNG)

Die Route der Raumschiffe wird durch if-Schleifen, die die Position der Raumschiffe überprüfen, und velocityX- bzw. velocityY- Befehle, die die Geschwindigkeit der Raumschiffe in eine Richtung steuern, definiert. Der Code sieht bei beiden Raumschiffen gleich aus, aufgrund der unterschiedlichen Startpunkte unterscheidet sich allerdings die Reihenfolge der einzelnen if-Schleifen.

![ME1 Route](https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/ME1%20Route.PNG)

Code für das Raumschiff, das oben rechts startet. Die Bezeichnung für die Raumschiffe im Code sind "me1" und "me2" für "Moving Enemy 1/2".

![ME2 Route](https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/ME1%20Route.PNG)

Code für das Raumschiff, das unten links startet.

Um die Flugrichtungen relaistischer darzustellen, benutzen wir vier verschiedene Sprites für die Raumschiffe. Je nach Richtungswechsel wird der Sprite gleichzeitig mit der Geschwindigkeit geändert.

<img src="https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/H2.jpeg" alt="image" width="100"><img src="https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/H2R.jpeg" alt="image" width="100">
<img src="https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/H2L.jpeg" alt="image" width="100">
<img src="https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/H2U.jpeg" alt="image" width="100">

#### Die Kollision

Bei Kontakt mit den Raumschiffen werden den Spielern 2 Punkte abgezogen. Auch hier prallen die Spieler beim Kontakt ab, um den massiven Punktverlust zu unterbinden. Allerdings stellen die Raumschiffe insofern ein gefährliches Hindernis dar, als dass sie die Spieler auf ihrer Flugroute vor sich her schieben können. Dies ist durchaus beabsichtigt.

![Kollision mit Raumschiff](https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/Kollision%20Raumschiff.PNG)![Kollision mit Raumschiff 2](https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/Kollision%20Raumschiff%202.PNG)

Wie bei der Sonne wird auch bei den Raumschiffkollisionen geprüft, ob die Spieler mit der Kollsion auf 0 Punkte fallen. Sollte dies der Fall sein, wird auch hier der Spieler wieder auf seinen Anfangspunkt zurückgesetzt.

Das Münzenproblem tritt bei den Raumschiffen nicht auf, da sie sich bewegen. Würden wir eine ähnliche Schleife wie bei der Sonne einführen, würden die Coins ständig ihre Position wechseln, ohne dass die Spieler sie einsammeln. Dies würde das Spiel stark beeinflussen.
Stattdessen fliegen die Raumschiffe über die Coins herüber. Dadurch sind sie nur kurzzeitig blockiert, können aber weiterhin problemlos eingesammelt werden, nachdem das Raumschiff weitergeflogen ist. Dass die Raumschiffe über die Coins herüber und nicht unter durch fliegen, liegt an der Reihenfolge, in der wir die Sprites eingeführt haben. Im Code ganz oben haben wir die verschiedenen Sprites alle eingeführt und dabei die Coins zuerst genannt. Bei dieser Codesprache überdeckt immer der zuletzt genannte Sprite sämtliche vorher genannten. Somit mussten wir nur die Raumschiffe nach den Coins einführen, um diese Darstellung realisieren zu können. Dies ist unserem Code Inhaltsverzeichnis vom Anfang zu entnehmen.

![Coins vor Hindernissen](https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/Coins%20vor%20Obstacles.PNG)


## Spielende<a name=""></a>

### Die WinningCoins erscheinen<a name=""></a>
Sollte es einem Spieler gelingen, 30 Coins zu sammeln, so erscheint ein Coin in seiner Farbe auf dem Spielfeld.  

<img src="https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/WC1.jpeg" alt="image" width="100"><img src="https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/WC2.jpeg" alt="image" width="100">

Diese sind zusammen mit allen anderen Sprites zu Beginn eingeführt worden, allerdings waren sie die ganze Zeit unsichtbar.

![WC1 Eigenschaften](https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/WC1%20Eigenschaften.PNG)

Zu dem Zeitpunkt, an welchem der Spieler 30 Punkte sammelt, wird sein WinningCoin sichtbar und er kann ihn einsammeln. 

![WC1 erscheint](https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/WC1%20erscheint.PNG)

### Einsammeln des gegnerischen WinningCoins<a name=""></a>

Allerdings kann auch der Gegner den WinningCoin einsammeln. Gelingt es dem anderen Spieler, den WinningCoin seinem Gegner wegzuschnappen, verhindert er so den Sieg zu diesem Zeitpunkt. Denn dadurch wird der Coincounter des Spielers, der zuvor noch 30 Punkte hatte, auf 20 zurückgesetzt. Dadurch verschwindet auch der WinningCoin, wie in dem obigen Code vorgesehen. Damit man sich nicht merken kann, wo der WinningCoin vorher war, wird dieser außerdem auf eine andere zufällige Position gesetzt. 

![Hiding WC1](https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/Hiding%20WC1.PNG)

### Einsammeln des eigenen WinningCoins<a name=""></a>

Schafft es ein Spieler, den eigenen WinningCoin einzusammeln, so endet damit das Spiel und es erscheint der sogenannte WinningScreen.

<img src="https://github.com/AntoniaJohannes/Stundenprotokoll/blob/master/Bildschirmfoto%20Player%201%20wins%20.jpeg" alt="image" width="200">  <img src="https://github.com/AntoniaJohannes/Stundenprotokoll/blob/master/Bildschirmfoto%20Player%202%20wins.jpeg" alt="image" width="200"> 

Dazu wird bei Einsammeln des eigenen WinningCoins ein neuer Hintergrund in hellblauer Farbe eingefügt. Zudem verschwinden alle Spieler, Coins, Hindernisse und alles andere, was sich noch vorher auf dem Feld befand.

![Alles verschwindet](https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/Endbildschirm%20Code.PNG)

Desweiteren wird die Steuerung beider Spieler außer Kraft gesetzt, da der WinningScreen nur so lange erscheint, wie der Gewinner seinen WinningCoin berührt. Um das Verschwinden des WinningScreens zu verhindern, haben wir deshalb die Steuerung ausgeschaltet.

![No Keys](https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/No%20Keys.PNG)

Gleichzeitig erscheint die Medaille und der WinnerIcon des Gewinners. Dies ist ein weiterer Sprite der Spielfigur. Hinzu kommen die Textausgaben "Congratulations!" und "Player 1/2 Wins". 

![WinningIcons](https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/Winning%20Icon%20Code.PNG)


