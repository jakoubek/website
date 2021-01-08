---
title: "FERAG-String erzeugen"
description: "Ich zeige Ihnen, wie leicht Sie mit Hilfe meiner Open-Source-Bibliothek feragstring selbst eine FERAG-String-Datei aus Ihren Logistikdaten erzeugen können."
date: 2021-01-03T12:48:47+01:00
tags: ['FERAG', 'Go']
draft: false
syntax: true
---

Für den Versand in Ihrer Druckereilogistik benötigen Sie einen FERAG-String zur Ansteuerung Ihrer FERAG-Versandanlage? Ich zeige Ihnen, wie leicht Sie mit Hilfe meiner Open-Source-Bibliothek **feragstring** selbst eine FERAG-String-Datei aus Ihren Logistikdaten erzeugen können.

Die Bibliothek zur Erzeugung eines FERAG-Strings ([auf Github verfügbar](https://github.com/jakoubek/feragstring)) ist in **Go** geschrieben. Außer Grundkenntnissen in Go und Ihren produktionsrelevanten Daten benötigen Sie nichts, um sofort selbst einen FERAG-String zu erzeugen.

Sie können mit Hilfe dieser Bibliothek ein Programm erzeugen, das aus Ihren produktionsrelevanten Daten (z.B. aus einer CSV-Datei oder per direktem Zugriff auf eine Datenbank) einen FERAG-String erzeugt.

Diese Bibliothek wird erfolgreich bei mehreren Zeitungsverlagen zur Erzeugung von FERAG-String-Dateien eingesetzt.

## Installation

```
go get -u github.com/jakoubek/feragstring
```

## Beispiel

```go
// create a FERAG string object
fs := feragstring.NewFeragString()
fs.SetTitleName("EDITION1")

// set title parameters
fs.TitleInfo.SetPrintObjectName("EDITION1A")
fs.TitleInfo.SetPublicationDate("2020-05-31")
fs.TitleInfo.SetCountryCode("13")
fs.TitleInfo.SetPrintObjectColor("00000000")

// add a product
pr1 := feragstring.NewProductReference()
pr1.SetProductName("MAIN")
pr1.SetCopiesAssigned(25000)
pr1.SetSupervision(1)
pr1.SetOverlap(5)
mp := feragstring.NewMissingParameter(1, 1)
pr1.SetMissingParameter(mp)
pr1.SetIssueReference("MAIN01")
fs.AddProductReference(pr1)

// add a route
rt := feragstring.NewRoute()
rt.SetRouteName("ROUTE001")
rt.SetRouteCode(fs.NextRouteCode())
rt.SetRampNumber(0)
rt.SetCopiesInRoute(1500)
rt.SetLimit(1)
rt.SetMaxStack(13)
rt.SetStandard(40)
rt.SetParameterN(4)
rt.SetMaxBundle(40)
rt.SetTopsheetMarker(5)
rt.SetEaMarker(0)
rt.SetTopsheetTemplateDirectory(20)
rt.AddProductReferenceNumber(1)
fs.AddRoute(rt)

// get the FERAG string (the write it to a file...) 
feragString := fs.PrintOut()
```

Das aufgeführte Code-Beispiel würde folgenden FERAG-String erzeugen:

```
%2440+93EDITION1A   +40EDITION1+95200531+9713+9400000000!
%2450+4101+42MAIN                          +5501+350000+0200025000+3600000+4401+4505+9910100+99102000000+99105000100000001+99195MAIN01  !
%2401+11ROUTE001     +7900001+2500+23001500!
%2402+11ROUTE001     +300001+310013+320040+330004+340040+350000+595+690+56020+4101!
%2406+11ROUTE001     !
%2441+40EDITION1!
```

---

## Sie benötigen Unterstützung?

**Sie benötigen Unterstützung bei der Nutzung meiner Bibliothek oder haben Interesse an einer maßgeschneiderten Server-Anwendung, um aus Ihren Logistikdaten einen FERAG-String zu erzeugen?**

{{< kontakt >}}
