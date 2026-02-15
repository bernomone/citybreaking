---
layout: post
title: "Tramway and Short-Term Rentals"
date: 2026-01-13
author: "Bernardo & Martina"
tags: [italy, exchange]
categories: [english]
excerpt: Relationship between public transport infrastructure and new Airbnb listings
---

The renewed attention to sustainable transport has led Florence to recently restore [a service](https://en.wikipedia.org/wiki/Trams_in_Florence) that in the 1800s extended even to [suburban areas](https://it.wikipedia.org/wiki/File:Firenze_-_mappa_rete_filoviaria_-_1958.svg): the tram.
Florence's tramway network was initially built toward the end of the nineteenth century, heavily damaged during the war, and then fully restored in the 1950s. However, lack of modernization made the service inadequate and obsolete, so much so that in 1958 the service was permanently discontinued.

In the early 2000s, the municipality of Florence decided to begin restoring the service as an alternative to road transport, and the first line of the new network entered service in 2010. There was no shortage of opposition to its construction: in 2008, a [referendum](https://www1.interno.gov.it/mininterno/export/sites/default/it/sezioni/sala_stampa/notizie/enti_locali/0835_2008_02_18_Referendum_tramvia_Firenze.html_40687498.html) was held to ask citizens whether they were in favor or against the construction of the first tram line in the center, and the NO vote won.

Nevertheless, two tram lines (or "tramvia" as Florentines like to say) have been built, and the network's development is still [ongoing](https://it.wikipedia.org/wiki/Rete_tranviaria_di_Firenze#Futuro) today, aiming to enhance the two current lines and build three more.

In a city like Florence, plagued by tourism, I often heard people mention how the opening of a new tram line near their home correlated with the opening of new accommodation facilities for short-term rentals. The association between these two phenomena certainly seems logical: the ease with which tourist areas can be reached by tram is undeniable, and this could be a good incentive to choose proximity to tram stops as an ideal location to start a tourist accommodation business.

Can we verify this hypothesis using data? Actually demonstrating a causal link between the two phenomena is not a simple task, but we can at least check whether there is any correlation between them. Let's start by considering two very important data sources:

1. Data from [Inside AirBnb](https://insideairbnb.com/) for the municipality of Florence, from which we select only "listings" with first review in 2025 (to represent recently opened Airbnbs).
2. [Data](https://dati.toscana.it/dataset/rt-oraritb/resource/1f62d551-65f4-49f8-9a99-e19b02077be3) provided by the Tuscany Region on Florence's tramway network. This data is in [GTFS](https://gtfs.org) format and easily allows us to obtain the location of tram stops.

To these we add other data that can help us understand the validity of a potential relationship between the presence of stops and the opening of new Airbnbs:

3. [Population data](https://data.humdata.org/dataset/kontur-population-italy), extracted from the "Kontur Population: Global Population" dataset which provides an [H3](https://h3geo.org) hexagonal grid with 400m sides. Each hexagon has the resident population in 2023 associated with it.
4. [OpenStreetMap data on tourist attractions](https://overpass-turbo.eu/s/2kyU), collected using the Overpass API.

We will use H3 hexagons as our unit of analysis.

We introduce population and tourist attractions as potential confounding factors between the opening of new Airbnbs and the presence of stops: we expect both Airbnbs and tram stops to be built predominantly in areas with high population density and high tourist interest, and this could increase the intensity of any potential correlation between them.

## Some Maps

Let's start by visualizing the new listings in 2025 on a map:

<iframe src='{{ "/assets/post_tramway_hexagon_map_airbnbs.html" | relative_url }}' width='100%' height='600px' frameborder='0' alt=""></iframe>


We can see how new listings open predominantly in the center, where indeed many stops are also located. Distance from the city center seems to be very relevant anyway, and new openings become very rare as this increases.

If we instead visualize the population:

<iframe src='{{ "/assets/post_tramway_hexagon_map_population.html" | relative_url }}' width='100%' height='600px' frameborder='0' alt=""></iframe>

we see that indeed the tram lines follow areas with high population density, but only in the western part of the city (construction work for the line that will serve the eastern part is still ongoing).

Finally, looking at tourist attractions:

<iframe src='{{ "/assets/post_tramway_hexagon_map_tourism.html" | relative_url }}' width='100%' height='600px' frameborder='0' alt=""></iframe>

we see that tram stops reach areas with many tourist attractions, but not in the most central part with the highest concentration. This is one of the effects of the NO victory in the 2008 referendum. The initial project envisioned the network passing near the city's Duomo, but this element was revised after the referendum defeat.

## Correlations

Let's now look in detail at how our quantities correlate. For each pair, we calculate the [Spearman Correlation Coefficient](https://en.wikipedia.org/wiki/Spearman%27s_rank_correlation_coefficient) (indicated by r in the figure), which indicates whether two quantities have a linear or non-linear correlation. A coefficient equal to 0 or not statistically significant indicates that no correlation was detected, while a coefficient exactly equal to 1(-1) indicates a perfect correlation (anticorrelation).

<img src="{{ '/assets/post_tramway_hexagon_scatterplot_matrix.png' | relative_url }}" alt="Scatterplot matrix showing Spearman correlations between new Airbnbs, tram stops, population, and tourist attractions in Florence. All variables show positive correlations, with the strongest correlation between Airbnbs and population (r=0.74)." style="display: block; width: 120%; max-width: 1500px; margin: 0 auto;">

All quantities are correlated with each other, in particular:

- Panels in the first row: the presence of new Airbnbs is correlated with all quantities, but the most intense correlations are with population density (r=0.74). This value is probably not much closer to 1 due to the effect of the historic center, slightly less inhabited than surrounding areas but with more new Airbnb openings.
- Panels in the second row: there are weak correlations between all remaining pairs. Particularly interesting is the weak correlation between population and presence of tram stops: we have in fact seen that, although tram stops are present only in areas with high population, many of these in the eastern part of the city do not yet have stops, but will be served in [future line developments](https://it.wikipedia.org/wiki/Rete_tranviaria_di_Firenze#In_costruzione).

One could therefore claim that tram stops are attractors for new openings. How robust, however, is the correlation we found if we also consider population and tourist attractions?

To verify this, we can use [Partial Correlation](https://en.wikipedia.org/wiki/Partial_correlation): this is a correction of the correlation between two variables taking into account their relationships with a set of control variables. In our case, we consider the correlation between new Airbnbs and the number of tram stops in a hexagon, controlling for population and tourist attractions in the hexagon itself:


| Correlation | Value | P-value |
|:------------|:--------|:--------|
| Spearman Correlation | 0.50 | 0.000|
| Partial Spearman Correlation (Population) | 0.30 | 0.000|
| Partial Spearman Correlation (Tourism) | 0.35 | 0.000|
| Partial Spearman Correlation (Population+Tourism) | 0.23 | 0.000|

We find that the correlation "survives" the control for population, tourist attractions, and their combination, albeit in an attenuated form. It therefore seems that the intuitions of some citizens, that the "tramvia" stimulates the opening of new Airbnbs, are not entirely unfounded.
Obviously, other controls and a more accurate causal and robustness analysis would be necessary, but we'll leave that for other posts (maybe).

## Data
The data presented in this post, with counts of new Airbnbs, tram stops, and population in H3 hexagons, can be found [here](https://github.com/bernomone/citybreaking/tree/main/data/airbnb-tramway-florence/).
