# syt5-gk911-industrielle-programmierung

## Einleitung
In diesem Repository wird die Aufgabendurchführung der Ersten Aufgabe "Tankentleerung" dokumentiert.

## Vorraussetzung
- CodeSys 3.5

## Aufgabenstellung
Die Aufgabenstellung ist auf E-Learning

## Arbeitsschritte
### Neues Projekt erstellen 
In CodeSys wird als erster Schritt ein neues Standardprojekt erstellt. Als Gerät wird __"CODESYS Control Win V3"__ ausgewählt. Dieses ist eine sogenannte Software Solution und rennt daher nur virtuell auf der Maschine. Als Programmiersprache wird für den ersten Task __"Funktionsbausteine"__ ausgewählt.  

Nun wird man mit einer neuen Arbeitsumgebung konfrontiert. Diese sieht so aus:  
<div align="center">
    <img src="images/anwendungsfenster.png" alt="Anwendungsfenster" width="50%" align="center" style="border: solid 1px black;" />
</div>  
  
Was hier markiert ist sind folgende Dinge:  
- PLC_PRG ... steht für ein Programm  
- Programme laufen nur, wenn man sie in einem Task, hier MainTask, aufruft.

### Tasks
Tasks sind Dinge, die von der Hardware dann ausgeführt werden. Diese rufen Programme auf.  
Tasks können zyklisch immer wieder aufgerufen werden, solange die Hardware eingeschalten ist/Strom hat.  

In einem Task können beliebig viele Programme aufgerufen werden, allerdings muss man bedenken, dass, sobald die Zyklus-Zeit abgelaufen ist, der Task wieder von vorne beginnt. Daher kann es sein, dass Programme, die erst ziemlich spät im Task vorkommen, gar nicht aufgerufen werden.  

Programme kann man zu Tasks __hinzufügen__ entweder per Drag-and-Drop oder, indem man im Task auf den Button __"Aufruf hinzufügen"__ drückt.

<div align="center">
    <img src="images/maintask.png" alt="Anwendungsfenster" width="90%" align="center" style="border: solid 1px black;" />
</div>  

### Neue Programme hinzufügen
Um ein neues Programm zu Erstellen klickt man mit der rechten Maustaste auf __"Application"__, __"Neues Objekt"__, __"POU"__.  
Im nächsten Fenster wählt man den Bulletpoint "Programm" und die gewünschte Programmiersprache aus.  

#### Variablen
Variablen können im Programm über den Baustein "Zuweisung" erstellt werden. Wenn man dort dann einen Variablennamen angibt, den es noch nicht gibt, wird man dann gleich gefragt ob man eine neue Variable hinzufügen möchte.  

Alternativ kann man das natürlich auch gleich im Code machen, was schneller geht. Man kann diesen Variablen auch einen Initialisierungswert geben.  

<div align="center">
    <img src="images/variablen.png" alt="Anwendungsfenster" width="90%" align="center" style="border: solid 1px black;" />
</div>  