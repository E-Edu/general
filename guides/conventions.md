# Konvention

## Branches
Alle Branches müssen folgend benannt werden:
* `master`
* `experimental`
* `issue/ISSUE-ID ISSUE-TITLE`

### Experimental
In den Experimental Branch dürfen nur Branches mit dem Namen `issue/ISSUE-ID` oder User Branches gemerged werden. Den Heads ist es auch bei dem Verbessern von z.B. Rechtschreibfehlern ohne Issue auf *experimental* zu pushen. Dieser Umstand sollte aber so selten wie möglich stattfinden.

### Master Branch
Es ist nichts direkt in den Master Branch zu commiten. Es darf nur der Experimental Branch in den Master Branch gemerged werden. Außnahmen dazu sind *Hotfixes*.

#### Hotfixes
Hotfixes sind Fehlern vorbehalten, welche so gravierend sind, dass diese schnell und gezielt behoben werden müssen. Hotfixes müssen als Commit Message Titel `hotfix: TITEL`  haben.

## Commit Messages
Commit Messages müssen folgendem Template entsprechen: `TITEL (#ISSUE-ID)`.
- Commit Messages müssen als Titel eine kurze und **sinnvolle** Beschreibung enthalten, d.h. etwas einfaches wie "*bug fix*" ist unakzeptabel. Zudem sind besondere Zeichen wie `;:<>-+[]()` usw. unakzeptabel
- Commit Messages müssen in Englisch und im Past Tense verfasst werden
- Genauere Beschreibungen sind akzeptabel, solange diese nicht in der Titelzeile der Commit Message sind
- Sollte der Commit ohne Issue erfolgen, darf diese weg gelassen werden.
- Ausnahmen sind Hotfixes. Mehr dazu bei Hotfixes.

Bei Merges muss der Commit Message Titel `merge from SOURCE to DESTINATION (#PR-ID)` und der Inhalt der Titel der Pull Request sein.

## Pull Requests

### Titel
Titel der assoziierten Issue *oder* eine kurze Beschreibung, wenn keine Issue existiert.

### Inhalt
In der Pull Request müssen alle Felder des Templates sinnvoll ausgefüllt werden. Falls dies nicht der Fall ist wird die Pull Request geschlossen und mit dem Label *malformed* getagged.  Sie kann, nachdem sie korrigiert wurde, jederzeit wiedereröffnet werden. Als Hilfsmittel zur Lösung kann hier auch "Squash commits" genutzt werden.

## Issues

### Titel
Der Titel einer Issue soll eine *sehr* knappe Zusammenfassung des Inhalts sein und darf keine Sonderzeichen wie z.B. `[]()\/;+-*` enthalten. Die einzige Ausnahme dazu ist `:`.

### Inhalt
Eine Issue hat einem der gegebenen Issue Templates zu entsprechen (zur Zeit *feature_request.md* und *bug_report.md*). Felder die keine neuen oder sinnigen Informationen zur Issue hinzufügen, dürfen entfernt werden. Falls dies nicht der Fall ist wird die Issue geschlossen und mit dem Label *malformed* getagged. Sie kann, nachdem sie korrigiert wurde, jederzeit wiedereröffnet werden. 

# Code Style
Allgemein lässt sich sagen, dass in Englisch programmiert wird, sprich alle Variablen Namen und Kommentare sind in Englisch zu verfassen.

### Python

#### Coding Convention
Grundsätzlich ist sich an [PEP 8](https://www.python.org/dev/peps/pep-0008/) zu halten, mit einigen folgenden Ausnahmen, die aber in der Anzahl ihrer gering zu halten sind.
- Als Autoformatter wird der Integrierte von [PyCharm](https://www.jetbrains.com/pycharm/) empfohlen, als Alternative hierfür kann aber auch [black](https://github.com/python/black) benutzt werden. Ggf. schlägt PyCharm aber black.
	- Spezifikationen
		- Line Length: 120
		- Unnötige (leere) Zeilen sind zu entfernen
 		- Variablen und Funktionen Naming Convention
Grundsätzlich ist sich hier an alles zu halten was in [diesem](https://dev.to/somedood/a-grammar-based-naming-convention-13jf) dev.to geschrieben wurde, mit der Ausnahme, dass Funktionen natürlich mittels *snake_case* benannt werden und Variablen vom Typen *bool* nicht den Prefix *is-* haben müssen.
	- Ausnahmen (müssen z.B. mittels `# noinspection PyPep8Naming` und einer Erklärung darüber angemerkt werden)
		- Wenn Klassen als Variable gespeichert werden, z.B. `self.Session: sessionmake = sessionmaker(...)`

# Ausnahmen dieser Regelungen
Diese Regelungen beziehen sich aktuell nur auf die Repositories, in welchen aktiv Entwicklung geschieht. Beispiele, für von den Regelungen ausgenommenen Repositories, sind `backend`, `frontend` und `graphics`.

# Anders, Verbesserungen & Änderungen
- Falls es einen Umstand gibt, welcher hier nicht klar definiert ist, muss das mit dem korrekten Backend Head abgesprochen werden, und wird ggf. hier eingefügt.
- Verbesserungsvorschläge sind wilkommen
- Bei Änderungen sind schon Geschehene Pull Requests etc. nicht zu verändern.

## Versionierung der Conventions
Die Versionsnummer besteht aus zwei von einem Punkt getrennten positiven natürlichen Zahlen, bei welchen die Zweite inkrementiert wird, wenn ein Punkt näher bzw. klarer ausgeführt wird oder ein Rechtschreib- oder Grammatikfehler verbessert wird. Die erste Zahl wird ausschließlich bei einer inhaltlichen Veränderung, dem Hinzukommen oder Entfernen einer Regelung inkrementiert, wobei die zweite Zahl wieder auf Null gesetzt wird.

# Version
3.0 by [mieasy](https://github.com/mieasy) originally published on [cryptic-game](https://github.com/cryptic-game/cryptic/blob/master/conventions.md)
