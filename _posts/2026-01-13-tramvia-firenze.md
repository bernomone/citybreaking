---
layout: post
title: "Tramvia e Affitti Brevi"
date: 2026-01-13
author: "Bernardo & Martina"
tags: [italia, exchange]
categories: [italiano]
excerpt: Relazione tra la presenza di infrastrutture di trasporto pubblico e nuovi Airbnb
---

La rinnovata attenzione alla sostenibilità dei trasporti ha fatto sì che a Firenze, in tempi relativamente recenti, sia stato ripristinato [un servizio](https://it.wikipedia.org/wiki/Rete_tranviaria_di_Firenze_(1879-1958)) che nel 1800 era esteso anche alle [aree extraurbane](https://it.wikipedia.org/wiki/File:Firenze_-_mappa_rete_filoviaria_-_1958.svg): il tram.
La rete tramviaria di Firenze fu infatti inizialmente realizzata verso la fine del dicianovesimo secolo, pesantemente danneggiata durante la guerra, fu poi ripristinata completamente negli anni 50 del secolo scorso. Mancati ammodernamenti resero però il servizio inadeguato e obsoleto, tanto che nel 1958 il servizio fu soppresso definitivamente. 

Nei primi anni 2000, il comune di Firenze decise di iniziare a ripristinare il servizio, come alternativa alla mobilità su gomma, e la prima linea della nuova rete entrò in servizio nel 2010. Non mancarono le opposizioni alla sua realizzazione: nel 2008 fu indetto un [referendum](https://www1.interno.gov.it/mininterno/export/sites/default/it/sezioni/sala_stampa/notizie/enti_locali/0835_2008_02_18_Referendum_tramvia_Firenze.html_40687498.html) per chiedere ai cittadini se fossero favorevoli o contrari alla realizzazione della prima linea di tram in centro e i NO vinsero. 

Nonostante ciò, due linee di tram (o di "tramvia" come piace dire ai Fiorentini) sono state realizzate e lo sviluppo della rete è ancora oggi [in corso](https://it.wikipedia.org/wiki/Rete_tranviaria_di_Firenze#Futuro), puntando a potenziare le due linee attuali e a costruirne altre 3.

In una città come Firenze, attanagliata dal turismo, mi è capitato spesso di ascoltare persone che riferivano come l'apertura di una nuova linea di tram vicino casa loro si correlasse con l'apertura di nuovi strutture ricettive destinate agli affitti brevi. L'associazione dei due fenomeni sembra senz'altro logica: la facilità con cui si raggiungono zone di interesse turistico con il tram è innegabile e questo potrebbe essere un buon incentivo per scegliere la vicinanza alle sue fermate come luogo ideale per avviare un'attività di ricezione turistica.

Possiamo verificare questa ipotesi usando dei dati? Dimostrare effettivamente un nesso causale fra i due fenomeni non è un compito semplice, ma possiamo almeno verificare se ci sia una qualche correlazione tra loro. Partiamo dal considerare due fonti di dati molto importanti:

1. I dati di [Inside AirBnb](https://insideairbnb.com/) per il comune di Firenze, dai quali selezioniamo solo i "listing" con prima recensione nel 2025 (per rappresentare AirBnb di recente apertura).
2. I [dati](https://dati.toscana.it/dataset/rt-oraritb/resource/1f62d551-65f4-49f8-9a99-e19b02077be3) forniti dalla Regione Toscana sulla rete tramviaria di Firenze. Questi dati sono in formato [GTFS](https://gtfs.org) e permettono facilmente di ottenere la posizione delle fermate del tram.

A questi aggiungiamo altri dati che possono aiutarci a capire la bontà di un'eventuale relazione tra la presenza di fermate e apertura di nuovi AirBnb:

3. I [dati di popolazione](https://data.humdata.org/dataset/kontur-population-italy), estratti dal dataset "Kontur Population: Global Population" che fornisce una griglia esagonale [H3](https://h3geo.org) con lato di 400m. Ciascun esagono ha associata la popolazione residente nel 2023.
4. I [dati di OpenStreetMap sulle attrazioni turistiche](https://overpass-turbo.eu/s/2kyU), raccolti usando la Overpass Api.

Useremo esagoni H3 come unità di analisi.

Introduciamo la popolazione e le attrazioni turistiche come potenziali fattori confondenti fra l'apertura di nuovi Airbnb e la presenza di fermate: ci aspettiamo che sia AirBnb che fermate del tram siano realizzati prevalentemente in aree ad alta densità abitativa e ad alto interesse turistico e questo potrebbe aumentare l'intensità di una loro eventuale correlazione.

## Un po' di mappe

Partiamo dal visualizzare su mappa i nuovi listing nel 2025:

<iframe src='{{ "/assets/post_tramway_hexagon_map_airbnbs.html" | relative_url }}' width='100%' height='600px' frameborder='0' alt=""></iframe>


Possiamo vedere come i nuovi listing aprano prevalentemente in centro, dove in effetti si trovano anche molte fermate. La distanza dal centro della città sembra comunque essere molto rilevante, e le nuove aperture diventano molto rare man mano che questa aumenta.

Se visualizziamo invece la popolazione

<iframe src='{{ "/assets/post_tramway_hexagon_map_population.html" | relative_url }}' width='100%' height='600px' frameborder='0' alt=""></iframe>

vediamo che in effetti le linee del tram seguono le aree ad alta densità abitativa, ma solo nella parte ovest della città (i lavori per la linea che servirà la parte est sono ancora in corso).

Infine, guardando alle attrazioni turistiche:

<iframe src='{{ "/assets/post_tramway_hexagon_map_tourism.html" | relative_url }}' width='100%' height='600px' frameborder='0' alt=""></iframe>

vediamo che le fermate del tram arrivano in zone come molte attrazioni turistiche, ma non nella parte più centrale e a maggior concentrazione. Questo è uno degli effetti della vittoria del NO al referendum del 2008. Il progetto iniziale prevedeva che la rete passasse in vicino al Duomo della città, ma questo elemento fu rivisto dopo la sconfitta referendiaria.

## Correlazioni

Andiamo a vedere adesso in dettaglio come correlano le nostre quatità. Per ogni coppia calcoliamo il [Coefficiente di Correlazione di Spearman](https://en.wikipedia.org/wiki/Spearman%27s_rank_correlation_coefficient) (indicato con r nella figura) che indica se due quantità hanno una correlazione lineare o non lineare. Un coefficiente uguale a 0 o non statisticamente significativo indica che non è stata rilevata nessuna correlazione, mentre un coefficente esattamente uguale a 1(-1) indica una perfetta correlazione(anticorrelazione).

<img src="{{ '/assets/post_tramway_hexagon_scatterplot_matrix.png' | relative_url }}" alt="Correlations" style="display: block; width: 120%; max-width: 1500px; margin: 0 auto;">

Tutte le quantità sono correlate tra loro, in particolare:

- Pannelli nella prima riga: la presenza di nuovi Airbnb è correlata con tutte le quantità, ma le correlazioni più intense sono con la densità di popolazione (r=0.74). Probabilmente questo valore non è molto più vicino ad 1 per effetto del centro storico, leggermente meno abitato delle aree limitrofe ma con più nuove aperture di AirBnb.
-Pannelli nella seconda riga: ci sono correlazioni deboli tra tutte le coppie rimanenti. Particolarmente interessante è la correlazione debole tra popolazione e presenza di fermate del tram: abbiamo infatti visto che, sebbene le fermate del tram siano presenti solo con aree con molta popolazione, molte di queste nella parte est della città non hanno ancora fermate, ma saranno servite in [futuri sviluppi della linea](https://it.wikipedia.org/wiki/Rete_tranviaria_di_Firenze#In_costruzione).

Si potrebbe quindi affermare che le fermate del tram siano degli attrattori per le nuove aperture. Quanto è robusta però la correlazione che abbiamo trovato se consideriamo anche la popolazione e le attrazioni turistiche?

Per verificarlo possiamo usare la [Correlazioni Parziale](https://en.wikipedia.org/wiki/Partial_correlation): questa è una correzione della correlazione tra due variabili tenendo conto delle loro relazioni con un insieme di variabili di controllo. Nel nostro caso consideriamo la correlazione tra nuovi AirBnb e il numero di fermate del tram in un esagono, controllando per la popolazione e le attrazioni turistciche nell'esagono stesso:


| Correlazione | Valore | P-value |
|:------------|:--------|:--------|
|Correlazione di Spearman | 0.500 | 0.000|
|Correlazione di Spearman Parziale (Popolazione) | 0.30 | 0.000|
|Correlazione di Spearman Parziale (Turismo) | 0.35 | 0.000|
|Correlazione di Spearman Parziale (Popolazione+Turismo) | 0.23 | 0.000|

Si trova che la correlazione "sopravvive" al controllo sulla popolazione, sulle attrazioni turistiche, e la loro combinazione anche se in forma attenuata. Sembra quindi che le intuizioni di alcuni cittadini, cioè che la "tramvia" stimoli l'apertura di nuovi Airbnb non sia del tutto infondata. 
Ovviamente, sarebbero necessari altri controlli e un'analisi causale e di robustezza più accurata, ma lo lasciamo per altri post (forse).

## Dati
I dati presentati in questo post, con i conteggi di nuovi Airbnb, fermate del tram e popolazione negli esagoni H3, si trovano [qui](https://github.com/bernomone/citybreaking/tree/main/data/airbnb-tramway-florence/).