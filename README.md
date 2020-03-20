# E-Edu
E-Edu ist ein von [The Morpheus Tutorials](https://the-morpheus.de/) initiierte Herausforderung für den [bundesweiten Hackathon WirVsVirus](https://wirvsvirushackathon.org/). Ziel ist es, innerhalb von 48 Stunden ein open-source E-Learning-System für Schüler:innen in Deutschland zu entwickeln, um Aufgaben und Unterrichtsinhalte zu vermitteln. Anlass für diesen Hackathon und damit auch die Herausforderung ist die [COVID-19-Pandemie](https://de.wikipedia.org/wiki/COVID-19-Pandemie) und die eingeschränkte Unterrichtsmöglichkeit. 

Weitere Informationen zum Hackathon und dem Ablauf muss der [offiziellen Veranstalter-Internetseite](https://wirvsvirushackathon.org/) entnommen werden.

## Ziel
Das Ziel für den 48-stündigen Hackathon ist es, einen [Prototypen](https://de.wikipedia.org/wiki/Minimum_Viable_Product) von E-Edu zu entwickeln und zu veröffentlichen.  

## Dokumentation und Software-Design
Die Dokumentation des Software-Designs und für den Entwurf relevante Informationen sind in [dieses Repository](https://github.com/E-Edu/draft-documents) ausgelagert bzw. auf den GitHub-Wikis veröffentlicht.

## Contribution Guidelines
Die Entwicklung des E-Learning-Systems unterliegt immer den [Konventionen](https://github.com/E-Edu/general/blob/master/guides/conventions.md). So hat auch jeder Entwickler sich an diese zu halten und sich nach neuen Versionen zu informieren.

## Deployment
Da der Prototyp erstmal keine große CI-Pipeline benötigt, wird der Build über [GitHub-Actions](https://github.com/features/actions) durchgeführt. Das Front- und Backend wird auf den Servern von [The Morpheus Tutorials](https://the-morpheus.de/) gestartet und öffentlich  zugänglich gemacht. Um dies zu ermöglichen, wird die jeweilige Software [dockerized](https://www.docker.com/).
Für den Prototypen ist die Domain `e-edu.the-morpheus.de` vorgesehen.
