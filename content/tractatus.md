---
title: "Tractatus"
date: 2021-01-04T14:31:42+01:00
draft: false
---

Der *Tractatus logico-philosophicus* gilt als das Hauptwerk des deutschen Philosophen Ludwig Wittgenstein (1889-1951).

Im Rahmen eines Wochenendprojekts habe ich [eine Website aufgesetzt](https://tractatus.baneland.de/de?ref=jakoubek-page), auf der der *Tractatus* satzweise veröffentlicht ist. Der Text des Tractatus ist frei verfügbar - diesen zusammenzutragen war der kleinste Teil.

Es ging mir hierbei darum, auf einer Website Inhalt darzustellen, der im verwendeten CMS *nicht* eingespeist ist. Statt dessen greift das CMS über einen API-Aufruf auf die Datenbank zu, in der der Text steht.

Zusätzlich gibt es noch eine "interaktive" Komponente: jeden Tag wird ein weiterer Satz des Tractatus (in numerischer Reihenfolge) "abgeholt" und auf Twitter veröffentlicht ([deutsch](https://twitter.com/tractatusDE), [englisch](https://twitter.com/tractatusEN)). Die bereits veröffentlichten Sätze haben auf der Website dann einen entsprechenden Retweet-Link.

## Stack

Folgende Tools kamen dabei zum Einsatz:

- als CMS: [Kirby CMS](https://getkirby.com/)
- als Datenbank: [Ninox](/ninox)
- zur Veröffentlichung auf Twitter: [Integromat](https://www.integromat.com/en/)
