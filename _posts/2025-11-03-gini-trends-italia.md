---
layout: post
title: "Airbnb: il mercato si concentra, ma Roma è un'eccezione"
date: 2025-11-03
author: "Bernardo & Martina"
tags: [italia, inequality]
categories: [italiano]
excerpt: Come è cambiato e come sta cambiando il mercato degli Airbnb
---

Come abbiamo osservato in un [post precedente](https://bernomone.github.io/citybreaking/italiano/2025/10/19/gini-italia.html) la distribuzione degli appartamenti di Airbnb in alcune delle maggiori città italiane è concentrata nelle mani di pochi host che ne possiedono molti, almeno in tempi recenti.
Volendo approfondire la questione, ci siamo chiesti se questa situazione sia così da molto e come è cambiata nel tempo (per lo meno da quando riusciamo ad osservare grazie ai dati raccolti da [Inside Airbnb](https://insideairbnb.com/get-the-data/)).

# L'indice di Gini nel tempo

Come abbiamo precedentemente spiegato, l'[indice (o coefficiente) di Gini](https://it.wikipedia.org/wiki/Coefficiente_di_Gini) misura la diseguaglianza di ricchezza di una popolazione e può essere utilizzato per misurare quanto le proprietà siano o meno concentrate nelle mani di pochi host. Un indice vicino a 0 indicherebbe che tutti gli host possiedono lo stesso numero di proprietà, ed il caso estremo di un indice pari a 1 indicherebbe che un solo host possiede tutte le proprietà. 
Il suo andamento nel tempo ci può dare un'indicazione di come il mercato stia cambiando: se tanti piccoli proprietari stanno dominando sempre di più il mercato ci aspettiamo che questo decresca; viceversa, se sta crescendo allora sono probabilmente agenzie e gruppi di case vacanze ad aumentare di peso.

![Gini index trends for some Italian cities. The Gini index is decreasing only in the city of Rome.]({{ '/assets/post_gini_trends_gini.png' | relative_url }})

Come vediamo dalla figura, il secondo scenario vale per 5 delle 6 città osservate, con l'unica eccezione della città di Roma.
Nelle altre città però si osserva una crescita dell'indice di Gini. Cosa significa più concretamente?

# Alcuni numeri più semplici

Volendo misurare qualcosa di più interpretabile dell'indice di Gini possiamo vedere quante proprietà appartengono a host che ne hanno 1 sola e come questo numero è variato dal primo all'ultimo campione di dati in nostro possesso. Ci aspettiamo che siano queste le proprietà che rientrano in quella che era l'idea originale di Airbnb: aggiungere offerta sul mercato degli alloggi temporanei, mettendo a disposizione proprietà "in eccesso" (stanze o appartamenti inutilizzati) di piccoli proprietari. 

Nella tabella seguente si può vedere come la percentuale di proprietà che appartengono a questa categoria fosse oramai già minoritaria ad inizio 2024 ed è diminuita in un anno e mezzo circa. Ad esempio, nella città di Bologna questa percentuale è diminuita di 5 punti, mentre a Milano addirittura di 8 (Nota: nella tabella usiamo il termine inglese "listing" per indicare una proprietà in affitto).

| City     |   Num. of listings (Feb 2024) |   % 1-listing hosts (Feb 2024) |   Num. of listings  (Jun 2025) |   % 1-listing hosts (Jun 2025) |
|:---------|----------------------------:|------------------------------------------:|----------------------------:|------------------------------------------:|
| Bologna  |                        4491 |                                        39 |                        4555 |                                        34 |
| Florence |                       11172 |                                        33 |                       13043 |                                        30 |
| Lecce    |                        2047 |                                        37 |                        2213 |                                        35 |
| Milan    |                       22106 |                                        45 |                       22540 |                                        37 |
| Naples   |                        9943 |                                        38 |                       10669 |                                        34 |
| Palermo  |                        6723 |                                        39 |                        7600 |                                        37 |
| Rome     |                       30318 |                                        38 |                       36309 |                                        40 |

Un altro spunto di riflessione interessante viene dal numero totale di proprietà nei due periodi: non si osservano infatti variazioni significative. Il quadro che questo sembra suggerire è che, nell'arco di tempo che va da inizio 2024 alla metà del 2025, non ci siano state espansioni o contrazioni dell'offerta ma solo accentramento verso i grandi host.

Roma è di nuovo l'unica città che fa eccezione: nello stesso periodo il numero totale delle proprietà è aumentato di circa 6000 unità, e la percentuale di proprietà nelle mani di host con una sola proprietà è aumentata di 2 punti. Non abbiamo una spiegazione di questa particolarità al momento, voi che ne pensate? Alla prossima!

## Dati
I dati presentati in questo post, con i conteggi di alloggi Airbnb per ogni host in ogni mandata di scraping sono presenti [qui](https://github.com/bernomone/citybreaking/tree/main/data/airbnb-counts-per-host-time-series/).