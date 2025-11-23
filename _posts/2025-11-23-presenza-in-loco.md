---
layout: post
title: Ma gli host maggiori in una città, stanno solo lì?
date: 2025-11-22
author: "Bernardo & Martina"
tags: [italia, inequality]
categories: [italiano]
excerpt: Vediamo quanto sono grossi (globalmente) gli host più grossi
---

Nel [post sulla quantità di proprietà per host in varie città italiane](https://bernomone.github.io/citybreaking/italiano/2025/10/19/gini-italia.html) abbiamo visto che ovunque esistono host che posseggono molti alloggi vacanza e che molto probabilmente sono agenzie. Qui ci chiediamo due cose:
* quanto estesi sono i grossi host _in quella città_ rispetto alla totalità dei propri listing
* che sovrapposizione c'è tra coppie di città in termini di host comuni

Come prima consideriamo i dati di Milano, Roma, Napoli, Lecce, Palermo, Bologna, Venezia e Firenze - sono le città di cui [Inside Airbnb](https://insideairbnb.com/about/) fornisce dati e che sono abbastanza grandi e "turistiche" (Lecce e Palermo si trovano nei file delle rispettive regioni). Inside Airbnb fa uno scraping regolare dei dati da Airbnb e noi, come prima, usiamo quelli dell'ultima mandata disponibile - per diverse città è la stessa del precedente post ma per alcune abbiamo l'aggiornamento ma si tratta comunque di date dell'estate 2025.

Un host può avere proprietà ovunque, in linea di principio. Se per ogni città isoliamo gli host unici e contiamo quanti esistono in ciascuna altra città, ci tiriamo fuori la _heatmap_ qui sotto:

![Una heatmap della % di host che esistono in ciascuna coppia di città, i numeri vanno dal 0.41% della coppia Roma-Milano allo 0.03% della coppia Napoli-Bologna.]({{ '/assets/hosts_overlap.jpg' | relative_url }})

Praticamente, i numeri illustrati mostrano la percentuale di host che è mutua tra due città, ovvero che esiste in entrambe. Per esempio, Milano ha 10691 host, Roma ne ha 20523; di questi, 127 esistono (hanno proprietà) in entrambe le città quindi la percentuale sul totale degli host tra di loro è 0.41%. 

Osserviamo che è vero che i numeri sono molto piccoli, ma sono anche vari, cioè la forbice (dal minimo 0.03% di Napoli-Bologna al massimo 0.41% di Roma-Milano) è piuttosto ampia! Più host mutui significa molto probabilmente più penetrazione di grossi gruppi - se i 127 host mutui tra Roma e Milano aumentano nel tempo vedremo più proprietà in mano alle stesse entità. Ma per ora, appunto, sembra che generalmente i grossi gruppi non hanno una grande sovrapposizione con altri.

Attenzione però: noi abbiamo solo i dati di queste 8 città, non tutto il paese (o il globo) - quindi possiamo vedere solo la sovrapposizione tra queste, ma è altamente probabile che la faccenda sia più variegata localmente, per esempio è possibile che i grossi gruppi di Firenze siano anche quelli di, diciamo, Pisa o Livorno. Non abbiamo modo di verificarlo, ma a livello nazionale non c'è grossa sovrapposizione e il numero relativamente alto di Roma e Milano può essere dovuto alla natura delle due città, rispettivamente la capitale politica e quella economica del paese. Come per tutto il resto, espanderemo le indagini ad altri paesi.

# Presenza in città e altrove

Ma se guardiamo agli host singolarmente, che presenza hanno quelli più grossi di ogni città in quella città (come percentuale di proprietà sul totale di quelle che hanno)? Abbiamo visto sopra che la sovrapposizione degli host tra città è generalmente scarsa, ma ci sono host grossi che sono anche molto diffusi sul territorio?

Ignorando gli host che hanno un solo listing, che ovviamente hanno il 100% delle loro proprietà in una sola città, se calcoliamo per ogni città _separatamente_ la percentuale di listing che ciascun host ha in quella città notiamo che generalmente chi più ha è anche più diffuso, come ci si aspetterebbe. Per visualizzare questo risultato possiamo usare la media delle percentuali di listing sulla città per categorie di listings totali:
* da 2 a 10 listing (host ancora piccoli)
* da 10 a 20 listing (host medi)
* da 21 a 50 listing (host abbastanza grossi)
* più di 50 listing (host maggiori)

![Grafico a barre della media della % di listing che un host ha in ciascuna città, media fatta sulle categorie di listing totali specificate nel testo. Si vede che ovunque la % decresce col numero di listings totali.]({{ '/assets/avg_listing_share_by_total_listings_city.png' | relative_url }})

Ovviamente il binnaggio è arbitrario, ma il risultato non cambia se ne usiamo uno diverso: chi più ha tende anche a essere esteso oltre il territorio della città. 
Per esempio, abbiamo casi estremi come quello di [E-Domizil Daniel](https://www.airbnb.co.uk/users/show/685495832) che ha un totale di più di 1000 listings in totale sparsi per il mondo, di cui una manciata a Bologna, Firenze, Roma e Venezia, e quindi uno share basso in ogni città (sotto l'1%), e ce ne sono diversi così.

Vediamo la situazione per il maggiore host di ognuna città:

| Città  | Host maggiore | Num. listings in città | % dei propri listing nella città |
| ------------- | ------------- | ------------- | 
| Bologna  | [Wonderful italy Emilia-Romagna](https://www.airbnb.com/users/show/487811050	)  | 182 | 99% |
| Firenze  | [MMega Homes And Villas](https://www.airbnb.co.uk/users/show/23904874)  | 242 | 60% |
| Milano  | [Italianway](https://www.airbnb.com/users/show/27693585)  | 480 | 99% |
| Napoli  | [Dimorra](https://www.airbnb.com/users/show/128841116)  | 144 | 95% |
| Roma  | [IFlat](https://www.airbnb.co.uk/users/show/23904874)  | 252 | 96%  |
| Venezia  | [Veniceapartment-com](https://www.airbnb.co.uk/users/show/23904874)  | 142 | 100% |
| Lecce  | [Lecce Selection](https://www.airbnb.co.uk/users/show/524849479)  | 54 | 38%  |
| Palermo  | [Wonderful Italy Sicilia](https://www.airbnb.co.uk/users/show/487814742)  | 172 | 70% |

Dunque alcuni esistono sostanzialmente solo in quella città, il che significa che si sono allargati lì senza espandersi altrove, altri sono magari partiti da lì e si sono espansi o hanno da subito acquisito proprietà in diversi luoghi.

Note: 
* piccoli errori o discrepanze nello scraping sono possibili - per esempio è possibile che le percentuali vicine al 100% siano in realtà un 100%
* rispetto al precedente [post](https://bernomone.github.io/citybreaking/italiano/2025/10/19/gini-italia.html) sugli host maggiori, i nomi sono perlopiù gli stessi ma il numero di listing può essere cambiato per via della nuova mandata di dati (dati aggiornati)
* per Lecce, l'host maggiore è cambiato rispetto al vecchio post - il precedente, ["Barbarhouse SRL"](https://www.airbnb.co.uk/users/show/9632167) è ora al secondo posto per numero di listing, con 51, e solo il 3% di share a Lecce (il grosso lo ha in provincia)

Sarà interessante vedere come questi risultati si presentano in altri paesi.