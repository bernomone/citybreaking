---
layout: post
title: Ma gli host maggiori in una città, stanno solo lì?
date: 2025-11-22
author: "Bernardo & Martina"
tags: [italia, inequality]
categories: [italiano]
excerpt: Vediamo quanto sono grossi (globalmente) gli host più grossi
---

Nel [post sulla quantità di proprietà per host in varie città italiane](https://bernomone.github.io/citybreaking/italiano/2025/10/19/gini-italia.html) abbiamo visto che ovunque esistono host, molto probabilmente agenzie, che posseggono molte case vacanza. Qui ci chiediamo due cose
* che fetta di mercato hanno i grossi host di ogni città _in quella città_;
* che sovrapposizione c'è, in termini di proprietà dello stesso host, tra coppie di città

Come prima consideriamo i dati di Milano, Roma, Napoli, Lecce, Palermo, Bologna, Venezia e Firenze - sono le città di cui Inside Airbnb fornisce dati e che sono abbastanza grandi e "turistiche" (Lecce e Palermo si trovano nei file delle rispettive regioni). Inside Airbnb fa uno scraping regolare dei dati da Airbnb e noi, come prima, prendiamo i dati dell'ultima mandata disponibile - per diverse città è la stessa del precedente post ma per alcune abbiamo l'aggiornamento; si tratta comunque di date dell'estate 2025.

Un host può avere proprietà ovunque, in linea di principio. Ci interessa capire come sons diffusi gli host sul territorio, in termini di dove affittano.

Se per ogni città isoliamo gli host unici e contiamo quanti esistono in ciascuna altra città, possiamo tirare fuori la _heatmap_ qui sotto:

![Una heatmap della % di host che esistono in ciascuna coppia di città, i numeri vanno dal 0.41% della coppia Roma-Milano allo 0.03% della coppia Napoli-Bologna.]({{ '/assets/hosts_overlap.jpg' | relative_url }})

Praticamente, i numeri illustrati mostrano la percentuale di host che è mutua tra due città, ovvero che esiste in entrambe. Per esempio, Milano ha 10691 host, Roma ne ha 20523; di questi, 127 esistono (hanno proprietà) in entrambe le città quindi la percentuale sul totale degli host tra di loro è 0.41%. 

Osserviamo che è vero che i numeri sono molo piccoli, ma sono anche parecchio vari, cioè la forbice (dal minimo 0.03% di Napoli-Bologna al massimo 0.41% di Roma-Milano) è parecchio ampia! Più host mutui significa molto probabilmente più penetrazione di grossi gruppi - se i 127 host mutui tra Roma e Milano aumentano vedremo più proprietà in mano alle stesse entità. Ma per ora, appunto, sembra che generalmente i grossi gruppi non hanno una grnde sovrapposizione con altri.
Attenzione però: noi abbiamo solo i dati di queste 8 città, non tutto il paese (o il globo) - quindi possiamo vedere solo la sovrapposizione tra queste, ma è altamente possible che la faccenda sia più variegata localmente, per esempio è possibile che i grossi gruppi di Firenze siano anche quelli di, diciamo, Pisa o Livorno. Non abbiamo modo di verificarlo, ma a livello nazionale non c'è grossa sovrapposizione e il numero relativamente alto di Roma e Milano può essere dovuto alla natura delle due città, rispettivamente la capitale politica e quella economica del paese. Come per tutto il resto, espanderemo le indagini ad altri paesi.

# Fette di mercato

Ma se guardiamo agli host singolarmente, che fetta di mercato (percentuale di proprietà) hanno quelli più grossi di ogni città in quella città? Abbiamo visto sopra che la sovrapposizione degli host tra città è generalmente scarsa, ma ci sono host grossi che sono anche molto diffusi sul territorio?