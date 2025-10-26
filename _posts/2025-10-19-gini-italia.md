---
layout: post
title: "Chi ha più Airbnb nelle città italiane?"
date: 2025-10-19
author: "Bernardo & Martina"
tags: [Italia, inequality]
categories: [italiano]
excerpt: Esploriamo la distribuzione di Airbnb per ospite per varie città
---

Dopo aver notato come [le proprietà in affitto temporaneo su Airbnb a Firenze crescono nel tempo](https://bernomone.github.io/citybreaking/italiano/2025/09/30/andamenti-temporali-firenze.html), in questo post ci siamo posti la domanda: "quanto è diseguale la città in termini di chi possiede queste proprietà?" e abbiamo deciso di fare confronti con altre città, restando per ora all'interno dei confini nazionali.

# L'indice di Gini 

In economia, l'[indice (o coefficiente) di Gini](https://it.wikipedia.org/wiki/Coefficiente_di_Gini) si usa per misurare la disuguaglianza nella distribuzione di ricchezza in una popolazione. È un classico indicatore, sotto forma di numero tra 0 e 1 - una società completamente egalitaria, dove cioè tutte le persone posseggono la stessa percentuale di ricchezza, ha un Gini pari a 0, che cresce quanto più invece si genera una separazione tra chi ha molto e chi poco. [Our World in Data](https://ourworldindata.org/grapher/economic-inequality-gini-index?time=2024) ha delle belle grafiche interattive sul Gini per paese e si vede che tra i casi più lampanti di disuguaglianza abbiamo il Sudafrica, per ovvi motivi dovuti a colonialismo e apartheid. L'indicatore prende il nome da Corrado Gini, che fu un economista (italiano) attivo nella prima metà del '900, noto per i suoi contributi in statistica economica e demografia.

Noi vogliamo usare l'indice di Gini per misurare quanto è diseguale una città in termini di chi possiede quante proprietà Airbnb - più gli alloggi turistici sono concentrati in mano a pochi ospiti e più questo indicatore si avvicinerà a 1.

Come prima usiamo i dati di [Inside Airbnb](https://insideairbnb.com/about/) che fa uno scraping regolare di Airbnb e consideriamo le 8 città italiane di cui lì abbiamo i dati da: Milano, Firenze, Roma, Bologna, Venezia, Lecce, Napoli, Palermo. I dati esistono anche per Bergamo ma l'abbiamo esclusa perché preferiamo usare capoluoghi di regione e/o città che ci aspettiamo siano molto turistiche (e lo siano sempre state); da notare che mentre tutte le altre città sono fornite da Inside Airbnb come a se stanti, Palermo e Lecce si trovano nei file di (rispettivamente) "Sicilia" e "Puglia", regioni che evidentemente vengono tirate giù in toto nello scraping, probabilmente perché le loro città singole non hanno molti dati ed è preferibile accorparli. 

Useremo i dati dell'ultima mandata di scraping disponibile ad ora, che può avere una data leggermente diversa (di qualche giorno o mese) da città a città, ma non ci aspettiamo differenze sostanziali per la nostra analisi - i dati sono comunque tutti aggiornati all'estate 2025.

Calcoliamo, per ognuna di queste città, l'indice di Gini, considerando tutte le proprietà che ogni ospite ha *in quella città* (questo dettaglio è importante!).

![Gini index for the 8 aforementioned Italian cities, Palermo comes as the least unequal, Milan the most unequal, but the differences are not very large.]({{ '/assets/gini_index_listings_per_host.png' | relative_url }})

Tutte le città sono diseguali, ma ognuna è diseguale a modo suo ([semi-cit](https://www.goodreads.com/quotes/7142-all-happy-families-are-alike-each-unhappy-family-is-unhappy)).
Palermo appare come la meno diseguale, Milano la peggiore, anche se la differenza tra i loro Gini non è drammatica. Dobbiamo tener conto del fatto che si tratta ovviamente di città diverse in termini di taglia e popolazione, ma anche, probabilmente, di volumi turistici.

Ci aspettiamo che ovunque esistano agenzie che o gestiscono Airbnb per conto di singoli proprietari e quindi li raggruppano assieme, o ne detengono la proprietà direttamente, quindi molto probabilmente gli ospiti più grossi non sono degli individui; andiamo a vedere chi sono. Vale la pena notare che se di agenzie si tratta, non è detto che queste operino solo sul territorio della città in esame, potrebbero avere in inventario alloggi ovunque, e questa è una cosa che indagheremo più in là - i risultati di questo post si riferiscono solo alle proprietà che un ospite ha nella città stessa.

| Città  | Numero Airbnb totali | % Airbnb dell'ospite maggiore |
| ------------- | ------------- | ------------- | 
| Palermo  | 7600  | 2.8% |
| Roma  | 36309  | 0.7% |
| Napoli | 10669  | 1.3% |
| Lecce | 2213  | 2.2% |
| Bologna | 4642  | 3.9% |
| Venezia  | 8590  | 1.7% |
| Firenze | 13043  | 1.9% |
| Milano  | 22540  | 2.1% |

In tabella, il numero di proprietà in affitto su Airbnb per ogni città assieme alla percentuale che l'ospite più grosso ha *in quella città*. Si vede che ci sono belle differenze in termini di numero di alloggi totali ma si tratta comunque di varie migliaia in ciascuna città, e che le percentuali sono parecchio diverse, Bologna ha quasi il 4% degli alloggi in mano allo stesso ospite, Roma solo lo 0.7%. Vediamo ora chi sono questi ospiti!

# Chi sono gli ospiti maggiori

Sono tutte agenzie (cioè non singoli proprietari), il che non sorprende, visti i numeri.

* Bologna: ["Wonderful Italy Emilia-Romagna"](https://www.airbnb.co.uk/users/show/487811050), che si autodescrive come il gruppo di case vacanza più grosso in Italia, con un portfolio di 2400 case in diversi parti del territorio nazionale - a Bologna ne hanno 182
* Palermo: lo stesso gruppo nella sua branca regionale, ["Wonderful Italy Sicily"](https://www.airbnb.co.uk/users/show/487814742) - a Palermo ha 216 alloggi
* Lecce: ["Barbarhouse SRL"](https://www.airbnb.co.uk/users/show/9632167), ancora un'agenzia che ha lì 49 alloggi (Lecce è la città con meno alloggi di tutte tra quelle che abbiamo, un numero nettamente minore delle altre)
* Milano: ["Italianway"](https://www.airbnb.com/users/show/27693585), che dichiara di operare su diverse parti d'Italia, a Milano ha ben 480 alloggi
* Firenze: ["MMega Homes And Villas"](https://www.airbnb.co.uk/users/show/23904874), che lì ha 242 alloggi e pure dichiara di operare su diverse destinazioni
* Venezia: ["Veniceapartment-com"](https://www.airbnb.com/users/show/2634978), ha lì 142 alloggi e opera solo su Venezia
* Napoli: ["Dimorra"](https://www.airbnb.co.uk/users/show/128841116), con 137 alloggi lì
* Roma: ["IFlat"](https://www.airbnb.co.uk/users/show/23532561), con 244 alloggi lì

In un post successivo proveremo a guardare alla distribuzione territoriale dei gruppi più grossi. Un'altra cosa che proveremo poi a fare è misurare come cambiano le cose se separiamo i proprietari individuali dalle agenzie.

# Le distribuzioni di alloggi per ospite più da vicino

Se raggruppiamo il numero di alloggi per ospite nelle categorie:

* 1 solo
* 2 o 3
* tra 4 e 10
* tra 10 e 100
* più di 100

e andiamo a contare il numero di ospiti che hanno questi numeri di alloggi, sempre per città, otteniamo i risultati qui in figura:

![Percentage of hosts with given numbers (bucketed) of Airbnb listings. ]({{ '/assets/hosts_listings_buckets.png' | relative_url }})

Le distribuzioni non cambiano in maniera drammatica, ma vediamo che che Milano è la città con la maggiore percentuale di proprietari di singolo immobile (quasi il 79%, che con tutta probabilità saranno degli individui e non gruppi) e che solo Lecce (come visto di sopra infatti) non ha alcun proprietario con più di 100 immobili.

Continueremo questo tipo di analisi in post successivi, alla prossima!