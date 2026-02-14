---
layout: post
title: "Tramvia e Affitti Brevi"
date: 2026-01-13
author: "Bernardo & Martina"
tags: [italia, exchange]
categories: [italiano]
excerpt: Relazione tra la presenza di infrastrutture di trasporto pubblico e nuovi Airbnb
---

La rinnovata attenzione alla sostenibilità dei trasporti ha fatto sì che a Firenze, in tempi relativamente recenti, si lavori al ripristino di [un servizio](https://it.wikipedia.org/wiki/Rete_tranviaria_di_Firenze_(1879-1958)) che nel 1800 era esteso anche alle aree extraurban: il tram.

Non sono ovviamente mancate le opposizioni alla sua realizzazione: nel 2008 fu indetto un [referendum](https://www1.interno.gov.it/mininterno/export/sites/default/it/sezioni/sala_stampa/notizie/enti_locali/0835_2008_02_18_Referendum_tramvia_Firenze.html_40687498.html) per chiedere ai cittadini se fossero favorevoli o contrari alla realizzazione della prima linea di tram in centro e i NO vinsero. 

Nonostante ciò, le linee di tram (o di "tramvia" come piace dire ai Fiorentini) sono state realizzate e lo sviluppo della rete è ancora oggi in corso.

In una città come Firenze, attanagliata dal turismo, mi è capitato spesso di ascoltare persone che riferivano come l'apertura di una nuova linea di tram vicino casa loro si correlasse con l'apertura di nuovi stutture ricettive destinate agli affitti brevi. L'associazione dei due fenomeni sembra senz'altro logica: la facilità con cui si raggiungono zone di interesse turistico con il tram è innegabile e questo potrebbe essere un buon incentivo per scegliere la vicinanza alle sue fermate come luogo ideale per avviare un'attività di ricezione turistica.

Possiamo verificare questa ipotesi usando dei dati? Ci possiamo provare. Partiamo dal considerare due fonti di dati molto importanti:

1. I dati di [Inside AirBnb](https://insideairbnb.com/) per il comune di Firenze, dai quali selezioniamo solo i "listing" con prima recensione nel 2025 (per rappresentare AirBnb di recente apertura).
2. I [dati](https://dati.toscana.it/dataset/rt-oraritb/resource/1f62d551-65f4-49f8-9a99-e19b02077be3) forniti dalla Regione Toscana sulla rete tramviaria di Firenze. Questi dati sono in formato [GTFS](https://gtfs.org) e permettono facilmente di ottenere la posizione delle fermate del tram.

A questi aggiungiamo un terzo dato che può aiutare a capire la bontà di un'eventuale relazione tra la presenza di fermate e apertura di nuovi AirBnb:

3. I [dati di popolazione](https://data.humdata.org/dataset/kontur-population-italy), estratti dal dataset "Kontur Population: Global Population" che fornisce una griglia esagonale [H3](https://h3geo.org) con lato di 400m. Ciascun esagono ha associata la popolazione residente nel 2023.

Useremo proprio gli esagoni di questo dataset come unità di analisi.

Introduciamo la popolazione come potenziale fattore confondente fra l'apertura di nuovi Airbnb e la presenza di fermate: ci aspettiamo che sia AirBnb che fermate del tram siano realizzati prevalentemente in aree ad alta densità abitativa e questo potrebbe aumentare l'intensità di una loro eventuale correlazione.

## Un pò di mappe

Partiamo dal visualizzare su mappa i nuovi listing nel 2025 (panello di destra), la popolazione (pannello di sinistra) e le fermate del tram (in blu in entrambi i pannelli):

<iframe src='{{ "/assets/post_tramway_hexagon_interactive_dual_map.html" | relative_url }}' width='100%' height='600px' frameborder='0' alt=""></iframe>

Possiamo vedere come i nuovi listing aprano prevalentemente in centro, dove in effetti si trovano anche molte fermate. La distanza dal centro della città sembra comunque essere molto rilevante, e le nuove aperture diventano molto rare man mano che questa aumenta.
Considerando la popolazione, vediamo che in effetti le linee del tram seguono le aree ad alta densità abitativa, ma solo nella parte ovest della città (i lavori per la linea che servirà la parte est sono ancora in corso).
Confrontando le due mappe si può notare come le aree con le maggiori aperture non siano in realtà quelle più popolate in assoluto: sono le aree del centro storico ad alta attrattività turistica. Le aree limitrofe hanno una densità di popolazione maggiore.

## Correlazioni

Andiamo a vedere adesso in dettaglio come correlano le nostre quatità. Per ogni coppia calcoliamo il [Coefficiente di Correlazione di Spearman](https://en.wikipedia.org/wiki/Spearman%27s_rank_correlation_coefficient) che indica se due quantità hanno una correlazione lineare o non lineare. Un coefficiente uguale a 0 o non statisticamente significativo indica che non è stata rilevata nessuna correlazione, mentre un coefficente esattamente uguale a 1(-1) indica una perfetta correlazione(anticorrelazione).

<img src="{{ '/assets/post_tramway_hexagon_scatterplot_matrix.png' | relative_url }}" alt="Correlations" style="display: block; width: 120%; max-width: 1500px; margin: 0 auto;">

- Pannello di sinistra: Popolazione in ogni esagono vs numero di fermate del tram. Il coefficente di Spearman (indicato con r) e maggiore di 0 e statisticamente significativo, ma molto minore di 1. Abbiamo infatti visto che, sebbene le fermate del tram siano presenti solo con aree con molta popolazione, molte di queste non hanno ancora fermate.
- Pannello centrale: Popolazione vs numero di nuovi Airbnb. In questo caso la relazione è molto più forte, come si vede sia dalla figura che dal valore di r=0.735. Probabilmente questo valore non è molto più vicino ad 1 per effetto del centro storico, leggermente meno abitato delle aree limitrofe ma con più nuove aperture di AirBnb.
- Pannello di destra: correlazione tra la presenza di fermate del tram in un esagono ed il numero di nuove aperture di AirBnb. Sia il boxplot che r=0.5 confermano la presenza di una relazione.

Si potrebbe quindi affermare che le fermate del tram siano degli attrattori per le nuove aperture. Quanto è robusta però la correlazione che abbiamo trovato se consideriamo anche la popolazione?

Per verificarlo possiamo usare la [Correlazioni Parziale](https://en.wikipedia.org/wiki/Partial_correlation): questa è una correzione della correlazione tra due variabili tenendo conto delle loro relazioni con un insieme di variabili di controllo. Nel nostro caso consideriamo la correlazione tra nuovi AirBnb e il numero di fermate del tram in un esagono, controllando per la popolazione nell'esagono stesso:


| Correlazione | Valore | P-value |
|:------------|:--------|:--------|
|Correlazione di Spearman | 0.500 | 0.000|
|Corralzione di Spearman Parziale | 0.298 | 0.0001|

Si trova che la correlazione "sopravvive" al controllo sulla popolazione, anche se in forma attenuata. Sembra quindi che le intuizioni di alcuni cittadini, cioè che la "tramvia" stimoli l'apertura di nuovi Airbnb non sia del tutto infondata. 
Ovviamente, sarebbero necessari altri controlli e l'introduzione di altre variabili come ad esempio l'attrattività turistica per verificare quest'ipotesi in modo più approfondito, ma lo lasciamo per altri post.

## Dati
I dati presentati in questo post, con i conteggi di nuovi Airbnb, fermate del tram e popolazione negli esagoni H3, si trovano [qui](https://github.com/bernomone/citybreaking/tree/main/data/airbnb-tramway-florence/).