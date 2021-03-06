# Beispiel Anwendung "Training Fellow"

Die Beispielanwendung "Training Fellow" wird im Buch "Microservices mit Go" des Rheinwerk Verlags beschrieben. Sie soll Schulungsanbieter bei der Schulungsbuchung, -vorbereitung und -durchführung unterstützen und vor Allem Ansätze für die Umsetzungen von Microservices in Go aufzeigen.

https://www.rheinwerk-verlag.de/microservices-mit-go-konzepte-werkzeuge-best-practices/

Der aktuelle Stand befinden sich immer unter: https://github.com/SourceFellows/trainingfellow

## Die Anwendung

Eine ausführliche Beschreibung der Anwendung befindet sich im Buch. Hier nur kurz die Domain Story der Anwendung:

![Domain Story der Anwendung](Training-Fellow.png)

## Start der Anwendung

Benötigt wird [Docker-Compose](https://docs.docker.com/compose/install/) und [Docker](https://www.docker.com/).

Nach einer eventuell nötigen Installation und konfiguration kann die komplette Anwendung über Docker-Compose mit folgendem Kommando gestartet werden:

```
docker-compose up
```

Daraufhin werden die Docker Container für die folgenden Services gestartet:

* [Registrierungs-Service](registrierung)

* [Vorbereitungs-Service](vorbereitung)

* NATS-Server

* MongoDB

* Mongo-Express

## Test der Anwendung

Testen kann man die Anwendung entweder über den [Browser](https://localhost:8443/registrierung) oder über den enthaltenen [Registrierungs-Client](registrierungclient). Alternativ können Sie auch HTTP-Request direkt aus der IDE starten. Hierzu ist für VSCode die [Registrierung-request.http](registrierung/Registrierung-request.http) Datei enthalten. Benötigt wird hierzu die Extension [humao.rest-client](https://marketplace.visualstudio.com/items?itemName=humao.rest-client).

### HTML-Formular

Erreichbar ist die Anwendung über https://localhost:8443/registrierung.

![HTML Formular der Anwendung](Registrierungsformular.png)

### Sicht auf MongoDB

Möchten Sie in die MongoDB schauen was gespeichert wurde, erreichen Sie diese unter http://localhost:8081.

![Ansicht in Mongo-Express](MongoExpress.png)

### Metriken der Anwendung

Die Prometheus-Metriken können unter http://localhost:9090/metrics abgerufen werden.


