---
layout: post
title: "Scambi di Airbnb a Firenze"
date: 2025-12-04
author: "Bernardo & Martina"
tags: [italia, exchange]
categories: [italiano]
excerpt: Come individuare scambi di Bnb tra host
---

La popolazione degli host su Airbnb si può grossolanamente dividere in categorie basate su quanti listing possiedono. Host molto "grandi", ossia con molti listing nel proprio account, sono presenti in [molte città contemporaneamente](https://bernomone.github.io/citybreaking/italiano/2025/11/22/presenza-in-loco.html) e stanno guadagnando [fette di mercato sempre maggiori](https://bernomone.github.io/citybreaking/italiano/2025/11/03/gini-trends-italia.html) (eccetto Roma).

L'accentramento del mercato avviene in molte delle città che abbiamo osservato in post precedenti, senza un sostanziale aumento del numero di listing. Questo può essere spiegato in due modi:

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

Le seguente tabella riporta i passaggi di proprietà individuati per Firenze nello snapshot di Giugno 2025.

| Previous Listing Name                            | Previous Host Name   | New Listing Name                                 | New Host Name                |
|:-------------------------------------------------|:---------------------|:-------------------------------------------------|:-----------------------------|
| Leoni Bargello Apartment by Mamo Florence        | Claudio              | Leoni Bargello Apartment by Mamo Florence        | Mamo                         |
| Santo Stefano Apartment by Mamo Florence         | Alvise               | Santo Stefano Apartment by Mamo Florence         | Mamo                         |
| Beautiful Apartment Next Duomo                   | Rachelle Khriseth    | Cozy & Charming Florentine Hideaway by Oteego    | Sea N' Rent                  |
| Noa, Deluxe flat in city center                  | Francesco            | Maison - Luxury and Design Three-Room Apartment  | Florence Charming Apartments |
| Cosy and Charming Apartment in Heart of Florence | Nicolò               | Cosy and Charming Apartment in Heart of Florence | Tommaso                      |
| Giacomini Suites (Free Wifi)                     | Edoardo              | Appartamento con 2 bagni privati                 | Roberto                      |
| A Romantic studio                                | Edo & Rita           | Sweet Florence close to Bargello 1               | Nikolozi                     |
| Flat Dona- Santo Spirito neighbourhood           | Margherita           | Flat Dona- Santo Spirito neighbourhood           | Marco                        |
| Maggio Boutique Apartment MBA Pitti Palace     | Beatrice             | MBA Maggio Boutique Apartment Pitti Palace     | Tommaso                      |
| Spacious flat in the historic centre of Florence | Francesca            | Spacious flat in the historic centre of Florence | Gianrocco                    |

Si può vedere come in molti casi il numero identificativo del listing non cambia, ma cambia solo il nome (leggermente) e il proprietario.
Particolarmente interessante è il caso dei due listing "acquisiti" dall'account [Mamo](https://www.airbnb.it/rooms/33062988). Ci sono molti casi come quelli riportati in tabella nei dati: un host molto piccolo che possiede un listing dal nome che riporta "by Mamo Florence" cede il suo listing all'account Mamo.
Possiamo ipotizzare che questi host lavorassero già per la catena Mamo come gestori, e che poi Mamo abbia deciso di accentrare i listing sotto l'account principale. 


Avendo le coordinate, possiamo mappare dove si trovano i listing nuovi emersi nello snapshot di Giugno 2025: 

<iframe src='{{ "/assets/new_listings_map_20250601.html" | relative_url }}' width='120%' height='800px' frameborder='0' alt=""></iframe>

I punti rossi sulla mappa rappresentano i listing che abbiamo identificato come passaggi di proprietario, mentre quelli blu sono i listing completamente nuovi. Possiamo vedere a colpo d'occhio che i listing rossi non sono la maggioranza, seppur siano un 13% del totale. Questa percentuale varia se dividiamo gli host in base al numero di listing già posseduti:

- Solo 1 listing: 6.61%
- Da 2 a 5 listing: 11.64%
- Da 5 a 50 listing: 9.84%
- Più di 50 listing: 23.95%

Com'è ragionevole aspettarsi, questo genere di passaggio viene fatto con più frequenza da host grandi che hanno abbastanza risorse per acquisire un listing già avviato e quindi più costoso da rilevare.

## Dati
I dati presentati in questo post, con la categorizzazione dei nuovi Airbnb e la loro posizione geografica si trovano [qui](https://github.com/bernomone/citybreaking/tree/main/data/airbnb-new-listing-status/).
