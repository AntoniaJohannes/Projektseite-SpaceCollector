# Projektseite: SpaceCollector

## Inhaltsverzeichnis

[1. Einleitung](#1)

[2. Spielprinzip](#2)

[3. Gesamtcode und Codeinhaltsverzeichnis](#3)

[4. Das Spielfeld](#4)

[5. Spielfiguren und Steuerung](#5)

[5.1 Spielfiguren](#5.1)

[5.2 Steuerung](#5.2)

[6. Coins](#6)

[6.1 Die verschiedenen Coins](#6.1)

[6.1.1 Der Bronzene Coin](#6.1.1)

[6.1.2 Der Silberne Coin](#6.1.2)

[6.1.3 Der Goldene Coin](#6.1.3)

[6.1.4 Der BadCoin](#6.1.4)

[6.2 Das Sammeln der Coins](#6.2)

[7. Hindernisse](#7)

[7.1 Die Sonne](#7.1)

[7.1.1 Kollision und Punktverlust](#7.1.1)

[7.1.2 Das Münzenproblem](#7.1.2)

[7.2 Die Raumschiffe](#7.2)

[7.2.1 Die Flugroute](#7.2.1)

[7.2.2 Kollision und Punktverlust](#7.2.2)

[8. Spielende](#8.)

[8.1 Die WinningCoins](#8.1)

[8.2 Dem Gegner zuvorkommen](#8.2)

[8.2.1 Einsammeln des gegnerischen WinningCoins](#8.2.1)

[8.2.2 Geschenkte Coins](#8.2.2)

[8.3 Einsammeln des eigenen WinningCoins](#8.3)




## Einleitung<a name="1"></a>

"SpaceCollector" ist ein Spiel, welches wir während des Informatikunterrichts im 12. Jahrgang entwickelt und programmiert haben. Hierbei haben wir die Plattform [studio.code.org](https://studio.code.org/) genutzt, welche die Codesprache in einfachen Bausteinen darstellt und so das Programmieren ohne Vorkenntnisse erheblich erleichtert. Dies war für uns das ausschlaggebene Argument, diese Plattform zu wählen, da wir beide im Informatikunterricht das erste Mal mit Programmiersprachen in Kontakt waren. Eingearbeitet haben wir uns mit dem [Tutorial](https://studio.code.org/s/csd3-2019), welches wir auf der[Website](https://studio.code.org/) vorfanden.

Nachdem wir verschiedene Spielmodelle in Erwägung gezogen hatten, entschieden wir uns für ein Spiel des Collectorgenres. Nach dem Progammieren eines [simplen Spiels](https://studio.code.org/projects/gamelab/EnadgHkFPFnDpVfr0FkQonvOLRhZsmTOVeFaQ5JREJw) ohne weitere Funktionen war es ein Leichtes, das Grundspiel zu entwickeln. Die anschließende Weiterentwicklung war der Hauptbestandteil der Informatikstunden.
Im folgenden Text werden wir unser Spiel erklären und auf Herausforderungen und Schwierigkeiten während des Prozesses eingehen. Wenn Codezeilen für Spieler 1 und Spieler 2 aus Übersichtsgründen im Code zwar in getrennten Funktionen geschrieben wurden, sich aber außer in der Bezeichnung nicht unterscheiden, werden wir aus Platzgründen exemplarisch den Code für Spieler 1 verwenden. Es ist dann davon auszugehen, dass der Code von Spieler 2 diesem entspricht.

## Spielprinzip<a name="2"></a>

Bei "SpaceCollector" konkurrieren zwei Aliens im [All](#4) um verschiedene [Coins](#6). Im Hintergrund funkeln Sterne, um das [All](#4) darzustellen. Die [Coins](#6) werden durch simples Berühren [eingesammelt](6.2). Ziel des Spiels ist es, [Coins](#6) im Wert von 30 Punkten einzusammeln, um so den [finalen Coin](#8.1) erscheinen zu lassen.
Zu Beginn des Spiels erscheint Spieler 1 in der oberen linken Ecke, Spieler 2 in der unteren rechten Ecke. Die [Sonne](#7.1) ist als zentrales [Hindernis](#7) im Zentrum, darum herum fliegen zwei [Raumschiffe](#7.2). Diese beginnen in der unteren linken Ecke bzw. in der oberen rechten Ecke des Spielfelds, also in den Ecken, wo die Spieler sich zu Anfang nicht befinden.

![Ausgangssituation](https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/Spawn.PNG)

Ausgangssituation beim Start des Spiels

## Gesamtcode und Codeinhaltsverzeichnis<a name="3"></a>

Unser Code besteht aus einer [Hauptfunktion](#Hauptfunktion), die das Spiel ausführt, und mehreren Unterfunktionen, die einzelne Bestandteile und Mechaniken des Spiels definieren. Um den Überblick zu wahren, sind alle mit einem charakteristischen Namen bezeichnet worden und in derselben Reihenfolge angeordnet, wie sie in der [Hauptfunktion](#Hauptfunktion) aufgelistet sind. In den obersten Codezeilen haben wir außerdem ein kleines Inhaltsverzeichnis eingefügt.

<a name="Hauptfunktion"></a>
![Inhaltsverzeichnis](https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/Code%20Inhaltsverzeichnis.PNG)

![Hauptfunktion](https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/Gesamter%20Code.PNG)

## Das Spielfeld<a name="4"></a>

Das Spiel findet, wie der Name schon andeutet, im [All](#4) statt. Der schwarze Hintergrund soll das [All](#4) darstellen, während die gelben Punkte, die ständig die Position wechseln, funkelnde Sterne sein sollen. 

![Setup](https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/Hintergrund%20Code.PNG)

Um das Allthema aufrechtzuerhalten, werden die [Spielfiguren](#5) durch verschiedenfarbige Aliens dargestellt und die [Hindernisse](#7) durch eine [Sonne](#7.1) und [Raumschiffe](#7.2) verkörpert.

## Spielfiguren und Steuerung<a name="5"></a>

### Die Spielfiguren<a name="5.1"></a>
Das Spiel wird von zwei Spielern gegeneinander gespielt. Spieler 1 steuert den grünen Alien, Spieler 2 den pinken Alien. Die Sprites für die [Spielfiguren](#5.1) waren bei der [Website](https://studio.code.org/home) bereits vorgefertigt und standen uns zur Verfügung.

<img src="https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/Player1.jpeg" alt="image" width="100"><img src="https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/Player2.jpeg" alt="image" width="100">

### Steuerung<a name="5.2"></a>
Spieler 1 steuert die [Spielfigur](#5.1) mit den Tasten WASD, Spieler 2 mit den Pfeiltasten, wobei sich die Animation für links und rechts so verändert, als wenn die [Spielfigur](#5.1) nach links bzw. rechts laufen würde.

<img src="https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/Player1L.jpeg" alt="image" width="100"><img src="https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/Player1R.jpeg" alt="image" width="100">

Sprites für links bzw. rechts bei Spieler 1.


<img src="https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/Player2L.jpeg" alt="image" width="100"><img src="https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/Player2R.jpeg" alt="image" width="100">

Sprites für links bzw. rechts bei Spieler 2.


![Keys1](https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/Keys%201.PNG)

Code für die [Steuerung](#5.2) bei Spieler 1. Die Sprites für links und rechts werden zusammen mit der Geschwindigkeit geändert. Durch Gedrückthalten der Tasten wird man in die entsprechende Richtung immer schneller, die [Spielfigur](#5.1) beschleunigt. Dies wird durch das Verlassen des [Spielfelds](#4) nicht beeinträchtigt. Es gibt keine Maximalgeschwindigkeit. Man hört augenblicklich auf, sich in eine Richtung zu bewegen, wenn man den Knopf loslässt. Es ist durch gleichzeitiges Drücken von zwei Tasten möglich, die [Spielfigur](#5.1) schräg über das [Spielfeld](#4) zu bewegen. Die if-Schleifen zur Zurücksetzung des Sprites und der Geschwindigkeit war nötig, da sonst die Darstellung der [Spielfiguren](#5.1) nicht mit der Bewegungsrichtung übereingestimmt hätten.


Wenn der Sprite z.B. das [Spielfeld](#4) auf der linken Seite verlässt, erscheint er auf derselben Höhe auf der rechten Seite. Dasselbe gilt für die andere Richtung sowie den oberen und unteren Rand. Dieses Prinzip haben wir von dem bekannten Handyspiel "Doodle Jump" übernommen. Wir entschieden uns dafür, da sonst die [Spielfiguren](#5.1), einmal außerhalb des [Spielfelds](#4), nicht mehr sichtbar sind und nur schwer wieder in den sichtbaren Bereich zu navigieren sind. 

![Edges](https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/Edge.PNG)

Der Code zum Erscheinen auf der jeweils anderen Seite des [Spielfelds](#4) bei Verlassen des [Spielfelds](#4) auf einer beliebigen Seite.


## Coins<a name="6"></a>

### Die verschiedenen Coins<a name="6.1"></a>

In "SpaceCollector" gibt es vier verschiedene Arten von [Coins](#6). Diese haben die Wertigkeiten +1, +2, +5 sowie -1. Die unterschiedlichen Wertigkeiten werden durch uterschiedliche Farben und Kennzeichnungen eindeutig gezeigt.

#### Der Bronzene Coin<a name="6.1.1"></a>

<img src="https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/C1.jpeg" alt="image" width="100">

![C1 Eigenschaften](https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/C1%20Eigenschaften.PNG)

Der Bronzene Coin gibt +1 Punkt. Er erscheint zu Beginn des Spiels an einem zufälligen Punkt auf dem [Spielfeld](#4). 

#### Der Silberne Coin<a name="6.1.2"></a>

<img src="https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/C2.jpeg" alt="image" width="100">

![C2 Eigenschaften](https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/C2%20Eigenschaften.PNG)

Der Silberne Coin gibt +2 Punkte. Er erscheint zu Beginn ebenfalls an einem zufälligen Punkt auf dem [Spielfeld](#4).

#### Der Goldene Coin<a name="6.1.3"></a>

<img src="https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/C5.jpeg" alt="image" width="100">

![C5 Eigenschaften](https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/C5%20Eigenschaften.PNG)

Der Goldene Coin ist der beste [Coin](#6). Er gibt +5 Punkte. Auch dieser [Coin](#6) erscheint zu Beginn an einem zufälligen Punkt innerhalb des [Spielfelds](#4).

#### Der BadCoin<a name="6.1.4"></a>

<img src="https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/BadC.jpeg" alt="image" width="100">

![BC Eigesnschaften](https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/BC%20Eigenschaften.PNG)

Entgegen seiner goldenen Farbe gibt dieser [Coin](#6) keine Punkte. Im Gegenteil, dieser [Coin](#6) gibt -1 Punkt und wird im Code deshalb als "badcoin" bezeichnet. Dieser [Coin](#6) verhält sich wie alle anderen [Coins](#6) auch und erscheint zu Beginn an einem zufälligen Ort. 

### Das Sammeln der Coins<a name="6.2"></a>

Die [Coins](#6) werden durch Berühren mit dem [Spielcharakter](5.1) eingesammmelt und erscheinen an einem zufälligen Ort erneut auf dem [Spielfeld](#4). Gleichzeitig werden dem Coincounter des Spielers, der den [Coin](#6) eingesammelt hat, der entsprechende Wert des [Coins](#6) gutgeschrieben.
Wie dem oben gezeigten Code zu entnehmen ist, sind die Collider aller [Coins](#6) auf "circle" gesetzt. Dies dient zur exakteren Darstellung des Einsammelns der [Coins](#6), da sonst auch "Nah-Dran-Vorbeilaufen" als Einsammeln gilt.

![Collecting](https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/Collecting.PNG)

Um Minuspunkte zu verhindern, wird beim Einsammeln eines [Badcoins](#6.1.4), während man 0 Punkte hat, der eigene Coincounter auf 0 festgesetzt, ohne Punkte abzuziehen. 
Die Anzahl gesammelter [Coins](#6) kann am oberen Rand des [Spielfelds](#6) dem Coincounter entnommen werden.

![Coincounter Spielfeld](https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/Coincounter.png)

![Coincounter Variablen](https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/Coincounter%20Variablen.PNG)

![Coincounter Code](https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/Coincounter%20Anzeige%20Code.PNG)


## Hindernisse<a name="7"></a>
Die [Hindernisse](#7) in "SpaceCollector" sollen das Spielerlebnis spannender gestalten, indem sie die Spieler beim [Sammeln der Coins](#6.2) behindern. In "SpaceCollector" gibt es drei [Hindernisse](#7): Eine [Sonne](#7.1) in der Mitte des [Spielfelds](#4) sowie zwei [Raumschiffe](#7.2).

### Die Sonne<a name="7.1"></a>

<img src="https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/H1.jpeg" alt="image" width="100"><img src="https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/Sonne%202.PNG" alt="image" width="100">

![Sonne Code](https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/Sonne%20Eigenschaften.PNG)

Die [Sonne](#7.1) ist im Zentrum des [Spielfelds](#4). Die wechselnde Animation am Rand der [Sonne](#7.1) soll sie ein wenig gefährlicher aussehen lassen, ebenso wie die wechselnde Augenfarbe. 

#### Kollision und Punktverlust<a name="7.1.1"></a>

Bei Kontakt mit der [Sonne](#7.1) verlieren die [Spieler](#5.1) 3 Punkte. Damit ist die [Sonne](#7.1) das gefährlichste [Hindernis](#7) im Spiel. Um permanenten Kontakt mit der [Sonne](#7.1) und somit permanenten Punktverlust zu verhindern, prallen die [Spieler](#5.1) bei Kontakt von der [Sonne](#7.1) ab.

![Kollision Sonne](https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/Sonne%20Kollision.PNG)<a name="0"></a>

Die Stärke des Abprallens haben wir von vornherein in den Eigenschaften der Sprites der [Spielfiguren](#5.1) festgelegt. Dies kann dem [obigen Code](#0) unter "bounciness" entnommen werden.
Wie dem Code zu entnehmen ist, wird bei der Kollision geprüft, wie viele Punkte der [Spieler](#5.1) hat. Sollten es mehr als 0 sein (bzw. weniger als 100, wir gehen davon aus, dass niemand je 100 [Coins](#6) sammelt), so verliert er die besagten 3 Punkte. Sollte der Punktestand des [Spielers](#5.1) so niedrig sein, dass er nach der Kollision auf 0 oder weniger Punkte abrutscht, wird er an seinen Anfangspunkt zurückgesetzt, im Beispiel von Spieler 1 an die Koordinaten 50/50, und der Punktestand wird auf 0 gestellt. Dies haben wir als kleine Strafe gedacht, um die Spieler bei niedrigem Punktestand zu besonders vorsichtigem Spielen zu bewegen.  

#### Das Münzenproblem<a name="7.1.2"></a>
Nachdem wir die [Sonne](#7.1) als [Hindernis](#7) eingeführt hatten, fiel uns schnell ein schwerwiegendes Problem auf: Die [Coins](#6) konnten hinter der [Sonne](#7.1) erscheinen und so für die [Spieler](5.1) unnereichbar sein. Um dies zu verhindern, haben wir eine [weitere Funktion](#0.1) programmiert, die prüft, ob die [Coins](#6) an ihrem Erscheinungsort die [Sonne](#7.1) berühren. Sollte dies der Fall sein, erscheinen sie einfach an einem neuen Ort auf dem [Spielfeld](#4). Dabei werden selbstverständlich keinem [Spieler](#5.1) Punkte angerechnet, obwohl die [Coins](#6) die Position wechseln.

![Keine Coins hinter der Sonne Code](https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/Hidingcoins.PNG)<a name="0.1"></a>

### Die Raumschiffe<a name="7.2"></a>

In "SpaceCollector" gibt es zusätzlich zu der [Sonne](#7.1) zwei weitere, sich bewegende [Hindernisse](#7) in Gestalt von zwei identisch aussehenden [Raumschiffen](#7.2).

<img src="https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/H2.jpeg" alt="image" width="100">

#### Die Flugroute<a name="7.2.1"></a>

Die [Raumschiffe](#7.2) fliegen in Form eines Vierecks im Uhrzeigersinn um die [Sonne](#7.1) herum. Dabei startet ein [Raumschiff](#7.2) oben rechts, das andere unten links.

![ME Eigenschaften](https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/ME%20Eigenschaften.PNG)

Die Route der [Raumschiffe](#7.2) wird durch if-Schleifen, die die Position der [Raumschiffe](#7.2) überprüfen, und velocityX- bzw. velocityY- Befehle, die die Geschwindigkeit der [Raumschiffe](#7.2) in eine Richtung steuern, definiert. Der Code sieht bei beiden [Raumschiffen](#7.2) gleich aus, aufgrund der unterschiedlichen Startpunkte unterscheidet sich allerdings die Reihenfolge der einzelnen if-Schleifen.

![ME1 Route](https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/ME1%20Route.PNG)

Code für das [Raumschiff](#7.2), das unten links startet. Die Bezeichnung für die [Raumschiffe](#7.2) im Code sind "me1" und "me2" für "Moving Enemy 1/2".

![ME2 Route](https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/ME2%20Route.PNG)

Code für das [Raumschiff](#7.2), das oben rechts startet.

Um die Flugrichtungen realistischer darzustellen, benutzen wir vier verschiedene Sprites für die [Raumschiffe](#7.2). Je nach Richtungswechsel wird der Sprite gleichzeitig mit der Geschwindigkeit geändert.

<img src="https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/H2.jpeg" alt="image" width="100"><img src="https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/H2R.jpeg" alt="image" width="100">
<img src="https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/H2L.jpeg" alt="image" width="100">
<img src="https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/H2U.jpeg" alt="image" width="100">

#### Kollision und Punktverlust<a name="7.2.2"></a>

Bei Kontakt mit den [Raumschiffen](#7.2) werden den [Spielern](#5.1) 2 Punkte abgezogen. Auch hier prallen die [Spieler](#5.1) beim Kontakt ab, um einen massiven Punktverlust zu unterbinden. Allerdings stellen die [Raumschiffe](#7.2) insofern ein gefährliches [Hindernis](#7) dar, als dass sie die [Spieler](#5.1) auf ihrer [Flugroute](#7.2.1) vor sich her schieben können. Dies ist durchaus beabsichtigt.

![Kollision mit Raumschiff](https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/Kollision%20Raumschiff.PNG)![Kollision mit Raumschiff 2](https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/Kollision%20Raumschiff%202.PNG)

Wie bei der [Sonne](#7.1) wird auch bei den Raumschiffkollisionen geprüft, ob [die Spieler](#5.1) mit der Kollsion auf 0 Punkte oder weniger fallen. Sollte dies der Fall sein, wird auch hier der [Spieler](#5.1) wieder auf seinen Anfangspunkt zurückgesetzt.

Das [Münzenproblem](#7.1.1) tritt bei den [Raumschiffen](#7.2) nicht auf, da sie sich bewegen. Würden wir eine ähnliche Schleife wie bei der [Sonne](#7.1) einführen, würden die [Coins](#6) ständig ihre Position wechseln, ohne dass die [Spieler](#5.1) sie [einsammeln](#6.2). Dies würde das Spiel stark beeinflussen.
Stattdessen fliegen die [Raumschiffe](#7.2) über die [Coins](#6) herüber. Dadurch sind sie nur kurzzeitig blockiert, können aber weiterhin problemlos eingesammelt werden, nachdem das [Raumschiff](#7.2) weitergeflogen ist. Dass die [Raumschiffe](#7.2) über die [Coins](#6) herüber und nicht unter durch fliegen, liegt an der Reihenfolge, in der wir die Sprites eingeführt haben. Im Code ganz oben haben wir die verschiedenen Sprites alle eingeführt und dabei die [Coins](#6) zuerst genannt. Bei dieser Codesprache überdeckt immer der zuletzt genannte Sprite sämtliche vorher genannten. Somit mussten wir nur die [Raumschiffe](#7.2) nach den [Coins](#6) einführen, um diese Darstellung realisieren zu können. Dies ist unserem [Codeinhaltsverzeichnis](#3) vom Anfang zu entnehmen.

![Coins vor Hindernissen](https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/Coins%20vor%20Obstacles.PNG)


## Spielende<a name="8"></a>

### Die WinningCoins erscheinen<a name="8.1"></a>

Sollte es einem [Spieler](#5.1) gelingen, 30 Punkte zu sammeln, so erscheint ein Coin in seiner Farbe, der sogenannte [WinningCoin](#8.1) auf dem [Spielfeld](#4).  

<img src="https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/WC1.jpeg" alt="image" width="100"><img src="https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/WC2.jpeg" alt="image" width="100">

Diese sind zusammen mit allen anderen Sprites zu Beginn eingeführt worden, allerdings waren sie die ganze Zeit unsichtbar.

![WC1 Eigenschaften](https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/WC1%20Eigenschaften.PNG)

Zu dem Zeitpunkt, an welchem ein [Spieler](#5.1) 30 Punkte sammelt, wird sein [WinningCoin](#8.1) sichtbar und er kann ihn einsammeln. 

![WC1 erscheint](https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/WC1%20erscheint.PNG)<a name="0.2"></a>

### Dem Gegner zuvorkommen<a name="8.2"></a>

#### Einsammeln des gegnerischen WinningCoins<a name="8.2.1"></a>

Allerdings kann auch der Gegner den [WinningCoin](#8.1) einsammeln. Gelingt es dem anderen [Spieler](#5.1), den WinningCoin seinem Gegner wegzuschnappen, verhindert er so den [Sieg](#8.3) zu diesem Zeitpunkt. Denn dadurch wird der Coincounter des [Spielers](#5.1), der zuvor noch 30 Punkte hatte, auf 20 zurückgesetzt. Dadurch verschwindet auch der [WinningCoin](#8.1), wie in dem [obigen Code](0.2) vorgesehen. Damit man sich nicht merken kann, wo der [WinningCoin](#8.1) vorher war, wird dieser außerdem auf eine andere zufällige Position gesetzt. 

![Hiding WC1](https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/Hiding%20WC1.PNG)

#### Geschenkte Punkte<a name="8.2.2"></a>

Mit [dieser Spielmechanik](#8.2) hatten wir zwar eine Chance für den gegnerischen [Spieler](#5.1), den anderen [Spieler](#5.1) zu behindern und sich selbst noch eine realistische Gewinnchance zu verschaffen, allerdings stießen wir an dieser Stelle ebenfalls auf ein massives Problem. Dieses bestand im Wesentlichen aus der Tatsache, dass die [WinningCoins](#8.1) zwar für die [Spieler](#5.1) unsichtbar waren, nichtsdestotrotz befanden sie sich auf dem [Spielfeld](#4). Dies führte mit dem ursprünglichen Code dazu, dass die [Spieler](#5.1) während des Spiels unwissend den [WinningCoin](#8.1) des Gegners einsammelten und ihm so 20 Punkte schenkten. Dies war natürlich nicht gewollt. Zudem wurde bei jeder ungewollten Berührung des gegnerischen [WinningCoins](#8.1) der Coincounter auf 20 zurückgesetzt, wodurch es nahezu unmöglich war, die Marke von 30 Punkten zu erreichen.

Dieses Problem konnte durch eine weitere Prämisse für die Zurücksetzung gelöst werden. Für diese vermeintlich einfache Lösung war jedoch eine Menge Gehirnschmalz und Analyse der Spielmechaniken notwendig. 

Anstatt nur auf Berührung mit dem [WinningCoin](#8.1) des Gegners zu prüfen, muss zusätzlich zur Brührung auch der [WinningCoin](#8.1) sichtbar sein. Denn nur dann soll auch der Coincounter des Gegners auf 20 heruntergesetzt werden. 

![Zusatzprämisse](https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/Zusatz.PNG)

### Einsammeln des eigenen WinningCoins<a name="8.3"></a>

Schafft es ein [Spieler](#5.1), den eigenen [WinningCoin](#8.1) einzusammeln, so endet damit das Spiel und es erscheint der sogenannte WinningScreen.

<img src="https://github.com/AntoniaJohannes/Stundenprotokoll/blob/master/Bildschirmfoto%20Player%201%20wins%20.jpeg" alt="image" width="200">  <img src="https://github.com/AntoniaJohannes/Stundenprotokoll/blob/master/Bildschirmfoto%20Player%202%20wins.jpeg" alt="image" width="200"> 

Dazu wird bei Einsammeln des eigenen [WinningCoins](#8.1) ein neuer Hintergrund in hellblauer Farbe eingefügt. Zudem verschwinden alle [Spieler](#5.1), [Coins](#6), [Hindernisse](#7) und alles andere, was sich noch vorher auf dem [Spielfeld](#4) befand.

![Alles verschwindet](https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/Endbildschirm%20Code.PNG)

Desweiteren wird die [Steuerung](#5.2) beider [Spieler](#5.1) außer Kraft gesetzt, da der WinningScreen nur so lange erscheint, wie der Gewinner seinen [WinningCoin](#8.1) berührt. Um das Verschwinden des WinningScreens zu verhindern, haben wir deshalb die [Steuerung](#5.2) ausgeschaltet.

![No Keys](https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/No%20Keys.PNG)

Gleichzeitig erscheint die Medaille und der WinnerIcon des Gewinners. Dies ist ein weiterer Sprite der [Spielfigur](#5.1). Hinzu kommen die Textausgaben "Congratulations!" und "Player 1/2 Wins". 

![WinningIcons](https://github.com/AntoniaJohannes/Projektseite-SpaceCollector/blob/master/Winning%20Icon%20Code.PNG)

Dies ist das Ende des Spiels. Nun kann es von neuem gestartet werden.
