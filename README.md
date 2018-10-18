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

### Task 1
_Ein Tank soll über drei an verschiedenen Orten angebrachten Schaltern S1, S2, S3 entleert werden können. Das Ventil V5 zum Entleeren soll dabei von jedem Schalter ein und ausgeschaltet werden können (Funktionsweise wie bei einer Kreuzschaltung in der Elektrik, Kreuzschaltung = Wechselschaltung mit drei Schaltern)._  

_Das Programm soll in einen zyklischen Task mit einer Zykluszeit von 400ms eingebettet werden._

### Programm testen
Um das Programm zu testen muss man sich mit einem Gerät verbinden. Da wir keines besitzen, wird nun eine Simulation erstellt.  
-> "Online/Simulation"  
Anschließend "Online/einloggen" (ALT+F8)  
Alternativ kann man für's einloggen auch den Button mit dem Zahnrad verwenden. Nachdem man eingeloggt ist, kann man über den Playbutton (F5) das Programm starten.  

#### Programmänderungen zur Laufzeit
In diesem Programm kann man nun einen Schalter ein/ausschalten in dem man den Boolean Wert ändert.  
Bei den Programmen ist es so, dass man zuerst den Variablen einen vorbereiteten Wert gibt. Das macht man, damit man mehrere Änderungen gleichzeitig machen kann. (Die Laufzeit der Tasks sind nur ein paar Millisekunden)  
<div align="center">
    <img src="images/vordefWert.PNG" alt="Anwendungsfenster" width="90%" align="center" style="border: solid 1px black;" />
</div>  

In diesem Fall ändere ich den Wert eines Schalters von False auf True. Um diese __Änderungen wirksam__ zu machen klickt man mit der rechten Maustaste auf "Application" und wählt __"Alle Werte von ... schreiben"__.  

<div align="center">
    <img src="images/anwendungsfenster2.png" alt="Anwendungsfenster" align="center" style="border: solid 1px black;" />
</div>  
Daraufhin ändern sich die Werte und das Ventil5 wird auf True gesetzt (aufgemacht).  
<div align="center">
    <img src="images/erg1.png" alt="Anwendungsfenster" width="90%" align="center" style="border: solid 1px black;" />
</div>