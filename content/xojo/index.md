---
title: "Xojo"
date: 2021-01-03T12:48:34+01:00
draft: false
syntax: true
---

Xojo ist eine integrierte Entwicklungsumgebung und Programmiersprache.

### Plattformübergreifend

Xojo ist plattformübergreifend, und das im doppelten Sinne: die Entwicklungsumgebung ist für Windows und OSX (sowie eher experimentell für Linux) verfügbar. Außerdem können von jedem System aus auch die Builds für alle Zielbetriebssysteme erzeugt werden.

### Desktop und Web

Mit Xojo konnten schon immer Desktop-Anwendungen erzeugt werden. Seit einigen Jahren ist es auch möglich, Web-Anwendungen umzusetzen.
Außerdem können Apps für iOS sowie seit neuestem Anwendungen für den Raspberry Pi geschrieben werden.

### Die Programmiersprache

Die Xojo-Programmiersprache ist ein BASIC-Dialekt. Das ist zugegebenermaßen wenig spektakulär, erlaubt dem Entwickler aber schnelle Ergebnisse. Eine starke Ähnlichkeit mit Visual Basic ist nicht von der Hand zu weisen:

{{< highlight bas >}}
Dim t As TextOutputStream
Dim f As FolderItem
f = GetSaveFolderItem("", "CreateExample.txt")
If f <> Nil Then
    t = TextOutputStream.Create(f)
    t.WriteLine(TextField1.Text)
    t.Close
End If
{{< / highlight >}}

### Datenbanken

Als integrierte Standarddatenbank unterstützt Xojo SQLite. Das eignet sich ideal für kleine Testumgebungen oder als "Lern-Anwendung", aber auch für die lokale Speicherung von Konfigurations- oder Programmdaten.

Darüber hinaus kann auf jede ODBC-fähige Datenbank sowie direkt auf MySQL, PostgreSQL, Oracle und Microsoft SQL Server zugegriffen werden.

### Lizenzen

Xojo ist eine kommerzielle Software mit einsteigerfreundlichem Modus: die Software kann beliebig lange kostenlos zur Entwicklung genutzt werden – allerdings können die Programme dann **nicht** kompiliert werden. Um jedoch Builds, also ein kompiliertes Programm, zu erzeugen, muss der Entwickler eine Lizenz erwerben.

Für die Lizenzen ist ein einmaliger Kaufpreis sowie eine günstige jährliche Wartungspauschale zu bezahlen. Die Preise werden auf der Xojo-Website in USD angegeben.

Darüber hinaus fallen keine weiteren Kosten an, vor allem auch keine für Runtime-Umgebungen bei den Nutzern der erstellten Programme (wie man das von Microsoft Access oder FileMaker kennt).

Es gibt verschiedene Lizenzstufen:

#### Single Desktop

Die Einsteigerlizenz: je gewünschtes Zielsystem (Windows, OSX, Linux/Raspberry Pi) 99 USD. Web und iOS nicht möglich.

#### Desktop/Web/iOS

Wer **nur** für den Desktop oder **nur** Web-Anwendungen oder **nur** iOS-Apps entwickeln möchte, kann eine plattform-spezifische Lizenz für 299 USD erwerben.

#### Pro

Die Pro-Lizenz erlaubt die Entwicklung von Anwendungen für **jedes** Zielsystem und wird von Xojo auch ganz klar als das gewünschte Standard-Produkt positioniert. Die Lizenz kostet 699 USD.

#### Enterprise

Es gibt noch eine Enterprise-Lizenz für 1.999 USD. Diese beinhaltet Schulungsangebote.

### Release-Politik

Xojo veröffentlicht alle drei Monate eine aktualisierte Version. Die Versionen tragen immer den Namen "Jahr + r + laufende Nummer im aktuellen Jahr" (Beispiel: 2016r4).

### Links

- [Xojo-Website](http://www.xojo.com/)
- [Xojo-Lizenzen](https://www.xojo.com/store/)
- [Wikipedia-Eintrag zu Xojo](https://de.wikipedia.org/wiki/Xojo)
