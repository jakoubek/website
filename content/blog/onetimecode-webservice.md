---
title: "Onetimecode-Webservice"
date: 2021-01-10T11:10:11+01:00
tags: ['API', 'Webservice', 'Onetimecode']
draft: false
syntax: true
---

Für verschiedene Zwecke benötige ich regelmäßig {{< rawhtml >}}<mark>eindeutige IDs</mark>{{< /rawhtml >}} in verschiedenen Formaten. Ich habe dazu einen Webservice aufgesetzt, der über eine einfache [API](../was-ist-eine-api) verschiedene IDs zurückgibt. Das erspart mir, diese ID-Generierung jedesmal wieder neu implementieren zu müssen. Außerdem kann ich so jederzeit von Automatisierungsplattformen (z.B. Zapier, Integromat) aus auf *meine* IDs zugreifen. Dienste dieser Art haben zusätzlich zu den normalen Integrationen auch immer eine "neutrale" HTTP-Funktion. Darüber kann man beliebige HTTP-Requests ausführen und das Ergebnis entgegennehmen.

## Unterstützte ID-Formate

- numerisch (z.B. `378134`)
- alphanumerisch (z.B. `jM9LK3`)
- UUID (z.B. `f4b7a8d3-4edf-4a30-991b-ebf99f493c86`)
- KSUID (z.B. `1msEhq2gU30WRD613L9X95xMAgd`)

## Webservice und Endpunkte

Der Webservice hat die Adresse https://api.onetimecode.net. Es werden ausschließlich `GET`-Requests entgegengenommen.

Das Ergebnis ist ein JSON-Objekt mit dem einzigen Schlüssel `result` und der jeweiligen ID als Wert:

```json
{"result":526766}
```

Folgende Endpunkte gibt es:

- /number
- /alphanumeric
- /uuid
- /ksuid

Wenn man anstatt einer JSON-Antwort eine reine Textantwort bekommen möchte (z.B. für die Integration in ein Shell-Skript), kann man an den Endpunkt die Endung `.txt` anhängen:

- /number.txt
- /alphanumeric.txt
- /uuid.txt
- /ksuid.txt

### Weitere Parameter

#### length

Die Endpunkte `/number` und `/alphanumeric` können optional den Query-Parameter `length` haben. Die Standardlänge ist immer sechs Zeichen.

- /number?length=4
- /alphanumeric?length=16

#### min/max

Der Endpunkt `/number` versteht optional auch die beiden Query-Parameter `min` und `max`. Sind diese Parameter gegeben, überschreiben diese einen ggf. übergebenen `length`-Parameter. Die zurückgegebene Nummer ist dann eine im Bereich zwischen `min` und `max`.

- /number?min=100&max=200

#### withoutdashes

Der Endpunkt `/uuid` versteht optional den Query-Parameter `withoutdashes=true`. Die zurückgegebene UUID hat dann *keine* Bindestriche als Trennzeichen.
