---
layout: post
title: "Compravendita di Bnb"
date: 2025-12-04
author: "Bernardo & Martina"
tags: [italia, buying and selling]
categories: [italiano]
excerpt: Individuare scambi di Bnb tra host
---

La popolazione degli host su Airbnb si può grossolanamente dividere in categorie basate su quanti listing possiedono. Host molto "grandi", ossia con molti listing nel proprio account, sono presenti in [molte città contemporaneamente](https://bernomone.github.io/citybreaking/italiano/2025/11/22/presenza-in-loco.html) e stanno guadagnando [fette di mercato sempre maggiori](https://bernomone.github.io/citybreaking/italiano/2025/11/03/gini-trends-italia.html) (escludendo Roma).

L'accentramento del mercato avviene in molte delle città che abbiamo osservato in post precedenti, senza un sostianziale aumento del numero di listing. Questo può essere spiegato in due modi:

1. Host più piccoli chiudono le loro attività essendo più deboli sul mercato e al contempo host più grandi si espandono creando nuovi listing. Le chiusure dei più piccoli e le aperture dei più grandi si bilanciano in numero.
2. Host più piccoli vendono i loro listing a host più grandi, non facendo variare il numero complessivo di listing. La cessione di listing non è supportata nativamente da Airbnb e gli host devono ricorrere a delle [strategie](https://community.withairbnb.com/t5/Help-with-your-business/Selling-my-Airbnb/td-p/1967210#:~:text=Unfortunately%2C%20Airbnb%20does%20not%20allow,the%20property%20on%20your%20account.) per far sì che il nuovo proprietario mantenga le informazioni (e la reputazione) del listing a passaggio avvenuto.

Questi due fenomeni non sono esclusivi e, in questo post, proveremo a capire come individuare quando un nuovo listing appartiene a una di queste due categorie.

## Individuare Passaggi di Listing

Individuare un nuovo listing apparso sul mercato è relativamente semplice: basta considerare tutti i listing che sono apparsi per la prima volta in uno snapshot di dati e non erano in quelli precedenti. 

Come si può riconoscere se un listing apparso per la prima volta esisteva già ed era precedentemente nelle mani di un altro host? Non esiste un modo semplice, noi abbiamo definito le seguenti regole:

* Consideriamo solo interi appartamenti
* Le coordinate del listing nuovo sono esattamente le stesse di uno che ha precedentemente chiuso
* Il numero di stanze e bagni del listing nuovo sono esattamente le stesse di quello chiuso che ha le sue stesse coordinate

Nonostante queste regole possano inevitabilmente condurre a degli errori, sia di falsi positivi (nuovi listing erroneamente identificati come passaggi di proprietà) che di falsi negativi (passaggi non individuati), dei controlli a campione ci hanno convinto che la strategia adottata è tuttosommato ragionevole.

Le seguente tabella riporta i passaggi di prorietà indivudati per Firenze nello snapshot di Giugno 2025.

|   Previous Listing ID | Previous Listing Name                            | Previous Host Name           |   Previous Host Listings Count |      New Listing ID | New Listing Name                                 | New Host Name      |   New Host Listings Count |
|----------------------:|:-------------------------------------------------|:-----------------------------|-------------------------------:|--------------------:|:-------------------------------------------------|:-------------------|--------------------------:|
|   1079604502176186210 | Ponte Vecchio & Uffizi Lovely Apartment          | Welcome To Our Holiday Homes |                            589 | 1383936940171769137 | Ponte Vecchio & Signoria Charming Flat           | Francesco          |                       612 |
|              53773844 | Mosse Leopolda Apartment by Mamo Florence        | Alessandro                   |                              1 |            53773844 | Mosse Leopolda Apartment by Mamo Florence        | Mamo               |                       201 |
|              45947494 | Mosse Teatro Apartment by Mamo Florence          | Enrico                       |                              1 |            45947494 | Mosse Teatro Apartment by Mamo Florence          | Mamo               |                       201 |
|    670867611138389208 | Florence By Frances | Heart                      | Massimo                      |                              2 | 1421676297416015954 | Costa San Giorgio with unique view               | ApartmentsFlorence |                        57 |
|    838898740492670422 | Sanzanobi typical Florence Apartment             | Otello                       |                             31 |  838898740492670422 | Sanzanobi typical Florentine-style apartment     | Esthel             |                        22 |
|    660660352431563338 | Finestra sull'Arno Atto V                        | Anna Maria                   |                              5 | 1425403589330510292 | View on Arno V (walking distance to city center) | Gianni             |                        20 |
|   1186684027160469825 | Giacomini Suites (Free Wifi)                     | Edoardo                      |                             22 | 1429693495006105522 | Appartamento con 2 bagni privati                 | Roberto            |                        17 |
|   1137470152649286967 | [5 Minutes Hospital Careggi] Wonderful           | Alessio                      |                             47 | 1137470152649286967 | [5 Minutes Hospital Careggi] Wonderful           | Claudio            |                         2 |
|   1262939271839382474 | Chic Mamma Glow Suite                            | Sergio                       |                              4 | 1409181641324582364 | Casa Ale - Dolcevita Holiday                     | Tommaso            |                         2 |
|   1262882362186221738 | Galileo's House [Wi-Fi Netflix, vicino a tutto ] | Sandro                       |                             11 | 1262882362186221738 | Galileo's House [Wi-Fi Netflix, vicino a tutto ] | Paola              |                         1 |

Si può vedere come in molti casi il numero identificativo del listing non cambia, ma cambia solo il nome (leggermente) e il proprietario.
Particolarmente interessante è il caso dei due listing "acquisiti" dall'account [Mamo](https://www.airbnb.it/rooms/33062988). Ci sono molti casi come quelli riportati in tabella nei dati: un host molto piccolo che possiede un listing dal nome che riporta "by Mamo Florence" cede il suo listing all'account Mamo.
Possiamo ipotizzare che questi host lavorassero già per la catena Mamo, gestendo pochi appartamenti, e abbiano infine ceduto la gestione al franchise principale.


## Dati
