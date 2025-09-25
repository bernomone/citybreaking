---
layout: post
title: "Come e dove crescono gli Airbnb a Firenze?"
date: 2025-09-18
author: "Bernardo & Martina"
tags: [italia, florence, time-trend]
categories: [italiano]
excerpt: Guardiamo ai dati Airbnb su Firenze, nel tempo e per area. Prima parte, un'analisi per iniziare.
---

Come scriviamo nell'["About"](https://bernomone.github.io/citybreaking/about/), questo è un blog dedicato ad analisi sul fenomeno dell'ipertourismo in senso generale, partendo dalla città di Firenze di cui ci occupiamo in questo post.

La domanda di base è: a Firenze sono cresciuti gli Airbnb? E se si, dove? 
Cercheremo di rispondere usando i dati dell'ottima piattaforma [Inside Airbnb](https://insideAirbnb.com/about/).

# Che dati abbiamo e come interpretarli

Gli snapshot di dati sono trimestrali, quindi non forniscono granularità temporale molto elevata: di ogni struttura si può osservare la presenza/assenza ogni 3 mesi ma non si ha la sua data di creazione sulla piattaforma. Abbiamo però le data delle prime recensioni, che useremo come proxy della data di creazione per osservare andamenti nel tempo.

Chiaramente, e questo è il grosso caveat, è del tutto possibile (anche se improbabile) che una struttura in attività abbia ricevuto 0 recensioni così come che tra la data di creazione e quella della prima recensione sia passato molto tempo. Assumiamo che una struttura sia "nuova" al momento in cui riceve la sua prima recensione.

I dati sono disponibili dal primo trimestre del 2024, ma le recensioni partono dal 2010 - Airbnb è nata nel 2007, ci avrà messo qualche anno ad arrivare in Italia. Usare la data della prima recensione per tutte le strutture esistenti dal 2024 significa non avere dati su tutte le strutture che prima del 2024 sono "morte" ovvero sono state eliminate dalla piattaforma Airbnb.

# Qualche numero per iniziare

In totale, considerando tutti gli snapshot temporali assieme, vediamo 16769 strutture uniche, di cui 14521 con almeno una recensione, quindi circa 2200 strutture non hanno alcuna recensione. Visto che Airbnb spinge gli utenti a lasciare commenti e rating e che questa feature è una componente essenziale della piattaforma, è piuttosto singolare che una struttura ne abbia 0, ma ci sono possibili ragioni:
* è molto recente (non è stata ancora usata o è stata usata da poca gente)
* la struttura viene prenotata attraverso agenzia (che poi non si cura di lasciare recensioni)
* si tratta di (probabile) nero: la struttura usa Airbnb solo come piattaforma per attrarre possibili utenti ma la transazione viene fatta al di fuori della piattaforma

# Gli Airbnb a Firenze crescono nel tempo

--- sto qui 

![Andamento temporale dei listing fiorentini su Airbnb, si vede una marcata accelerazione dal 2022. Ricordiamo che stiamo osservando solo le strutture che nel 2024 erano in esistenza.]({{ '/assets/Florence_new_listings_per_month.png' | relative_url }})

Dalla figura si vede una chiara crescita temporale, particolarmente marcata dal 2022, l'immediato post-COVID.

# Si, ma dove?

Per ogni struttura abbiamo la sua geolocalizzazione precisa. Andiamo quindi a vedere quali aree sono più coperte in formato *heatmap*. Nella visualizzazione interattiva qui sotto, potete selezionare l'anno e zoomare su un'area specifica ma anche far andare il tempo dall'inizio schiacciando il tasto Play. Il colore indica la percentuale di strutture Airbnb, tra quelle disponibili in quel momento, si trova nell'area esagonale.

<iframe src='{{ "/assets/listing_first_review.html" | relative_url }}' width='100%' height='600px' frameborder='0' alt=""></iframe> 

Si vede chiaramente che inizialmente i pochi Airbnb si trovano quasi esclusivamente al centro storico, e pian piano cominciano a dipanarsi oltre finché negli ultimi anni inglobano praticamente tutta l'area del comune.

Non possiamo però concludere che il fenomeno Airbnb stia interessando la periferia solo recentemente perché i dati che abbiamo soffrono di [**Bias del Sopravvissuto**](https://it.wikipedia.org/wiki/Survivorship_bias). Dato che osserviamo le strutture solo dal 2024, non abbiamo informazioni su quelle che erano effettivamente presenti in precedenza e che prima del 2024 sono sparite da Airbnb. 
In poche parole, stiamo osservando un misto di strutture recenti e strutture molto vecchie, ma di queste ultime vediamo solo quelle che sono riuscite a non chiudere nel tempo e che verosimilmente si trovano nell'area più interessata dal turismo. Perciò è plausibile che nel 2010 altre strutture fuori dal centro di Firenze abbiano avuto la loro prima recensione, ma vista le diverse dinamiche del turismo all'epoca e la diversa conformazione urbana, non siano presenti nei dati del 2024, che è il primo anno che possiamo osservare nei nostri snapshot.
Ma ci facciamo un'idea sulle strutture longeve. 

# Prossimi passi

Questo era solo un assaggio! Per Firenze, vogliamo principalmente capire, e potrebbe essere ancora prestino, si la nuova normativa comunale (di giugno 2025), che ha bandito Airbnb al centro, stia avendo un effetto l'effetto sperato o se non faccia altro che spostare il problema fuori dal centro storico. Guarderemo poi ad altre città, proveremo a fare confronti e a indagare particolarità.