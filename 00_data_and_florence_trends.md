---
layout: page
title: Data Gathering
permalink: /data_gathering/
main_nav: true
---

# La Raccolta Dati

Ogni analisi che si rispetti parte sempre da una raccolta dati o da una base dati già esistente. Dato che siamo interessati ad osservare il mercato degli affitti brevi in Italia sulla piattaforma AirBnB, la miglior risorsa attualmente disponibile è il sito [Inside Airbnb](https://insideAirbnb.com/get-the-data/).

Inside AirBnb permette di scaricare un anno di dati per varie zone di interesse, con snapshot della piattaforma Airbnb ogni circa 3 mesi. I dati che è possibile scaricare comprendono i seguenti file:

- **listings.csv** La lista delle strutture ricettive attive al momento dello snapshot.
- **calendar.csv** Le date disponibili per ciascuna struttura **TODO: Guardare meglio questi dati e capire cosa sono**
- **reviews.csv** Lo storico di tutte le recensioni di ciascuna struttura.
- **neighbourhoods.geojson** Una divisione in quartieri o comuni dell'area di interesse. 

Considerando i dati italiani, non sembra esserci una ratio precisa dietro la raccolta presente in Inside Airbnb. Sono presenti varie città importanti dal punto di vista turistico e non (e.g. Roma, Milano, Venezia, Firenze, Napoli), ma anche intere regioni non suddivise in città o aree metropolitane (e.g. Sicilia). 

Abbiamo scaricato tutti i dati riguardanti l'Italia al momento e iniziato l'esplorazione dei dati per capirne meglio la struttura. L'idea è quella di avere uno storico sufficientemente lungo da poter osservare cambiamenti su periodi di vari anni. Per la policy stessa di Inside Airbnb, non ci è possibile condividere i dati che collezioniamo, ma potremo diffondere le analisi ed eventualmente gli script senza problemi.

Inside Airbnb non fornisce una documentazione approfondita dei vari campi presenti in ogni file e nella suddivisione spaziale di ogni area. In un prossimo post andremo a descrivere un pò meglio quello che si trova nei vari file e come estrarre qualche informazione interessante. **NOTA: che ne pensi marti?**

Una prima domanda che ci è venuta spontanea è se fosse possibile usare questi dati per capire dove e quando nascono nuovi Airbnb. Gli snapshot trimestrali non consentono però di avere una granularità temporale molto elevata: possiamo osservare un nuovo Airbnb nascere o uno vecchio sparire solo ogni 3 mesi.

Abbiamo quindi pensato che un buon proxy per la data di inizio dell'attività di un Airbnb potesse essere la data della prima recensione (e specularmente l'ultima per la fine della sua attività). Queste ovviamente saranno solo date stimate, l'iscrizione su Airbnb è chiaramente avvenuta mesi prima della prima recensione. Stiamo inoltre escludendo tutte quelle sfortunate strutture che non ricevono nessuna recensione. Ci aspettiamo però che in città ad alta densità turistica questo succeda alquanto di rado.

# Trend Temporali di Firenze

Aggiungiamo un altro bias personale: scegliamo Firenze come primo caso di studio. Queste sono le date di ciascun snapshot (formato YYYY-MM-DD)

- 2024-03-24
- 2024-06-22
- 2024-12-20
- 2025-03-15
- 2025-06-19

Possiamo quindi osservare le strutture su Airbnb a partire dal primo trimestre 2024. Se assumiamo che una struttura sia "nuova" nel mese in cui ha la sua prima recensione, possiamo contare il numero di nuove strutture tempo:


![image](assets/Florence_new_listings_per_month.png)

Come dicevamo, i dati delle recensioni contengono tutto lo storico e quindi troviamo facilmente strutture recensite per la prima volta nel 2010. Con un trend decisamente in crescita nel tempo.

Possiamo inoltre vedere dove sono localizzati negli anni i "nuovi" Airbnb all'interno dell'area di Firenze:

<iframe src='assets/listing_first_review.html' width='100%'></iframe> 

Si vede chiaramente che inizialmente gli Airbnb si concentrano in quello che è il centro storico, che è anche l'area a più alta densità turistica nella città. Negli ultimi anni invece, si vede una proliferazione esterna al centro che ingloba praticamente tutta l'area del comune.

Possiamo quindi dire che il fenomeno sta interessando le aree periferiche solo recentemente? **Ovviamente no!** Dato che osserivamo le strutture solo dal 2024, non abbiamo informazioni su quelle che erano effettivamente presenti in precendenza.
Il fatto che la concentrazione di strutture con una prima recensione nel 2010 fosse prevalmentemente in centro e che siano relativamente poche, fa pensare che il nostro campione di strutture soffra del **Bias del Sopravvissuto**.

In poche parole, stiamo osservando un misto di strutture recenti e strutture molto vecchie, ma di queste ultime vediamo solo quelle che sono riuscite a non chiudere nel tempo e che verosimilmente si trovano nell'area più interessata dal turismo. 
