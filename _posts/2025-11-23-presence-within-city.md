---
layout: post
title: Are the biggest hosts in a city only present there?
date: 2025-11-22
author: "Bernardo & Martina"
tags: [italy, inequality]
categories: [english]
excerpt: Let's see how big the biggest hosts are globally
---

In the [post about the number of properties per host in various Italian cities](https://bernomone.github.io/citybreaking/english/2025/10/19/gini-italy.html), we saw that there are hosts everywhere who own many vacation rentals, likely agencies. Here we ask two things:
* How concentrated are the biggest hosts _in that city_, considering all of their listings?
* How much overlap is there between pairs of cities in terms of common hosts?

As before, we consider data from Milan, Rome, Naples, Lecce, Palermo, Bologna, Venice, and Florence – these are the cities for which [Inside Airbnb](https://insideairbnb.com/about/) provides data, and they are large and "touristy" enough (Lecce and Palermo are found in the files for their respective regions). Inside Airbnb regularly scrapes Airbnb data, and as before, we use the latest available batch – for several of the cities this is the same as the previous post, for others we have an update, but in any case, the data is from summer 2025.

A host can, in principle, have properties anywhere. If for each city we pick the unique hosts and count how many exist in every other city, we get the _heatmap_ below:

![A heatmap of the % of hosts that exist in each city pair, numbers range from 0.41% for Rome-Milan to 0.03% for Naples-Bologna.]({{ '/assets/hosts_overlap.jpg' | relative_url }})

Basically, the numbers shown indicate the percentage of hosts that are mutual between two cities, that is, that exist in both. For example, Milan has 10691 hosts, Rome has 20523; of these, 127 exist (have properties) in both cities, so the percentage of mutual hosts is 0.41%.

The numbers are very small, but also quite varied – the range (from a minimum of 0.03% for Naples-Bologna to a maximum of 0.41% for Rome-Milan) is quite wide! A higher percentage of mutual hosts likely means more penetration by large groups – if the 127 hosts that are in common between Rome and Milan increase over time, we'll see more properties in the hands of the same entities. But for now, it seems that large groups generally don't have much overlap with others.

Important note: we only have data for these 8 cities, not the whole country (or globe) – so we can only see overlap amongst these, but it's entirely possible that the situation is more varied locally. For example, it's possible that the big groups in Florence are also the big ones in, say, Pisa or Livorno. We can't verify this, but at the national level, there's not much overlap, and the relatively high number for Rome and Milan may be due to the nature of the two cities, respectively the political and economic capitals of the country. As always, we'll expand our investigations to other countries.

# Presence in the city and elsewhere

If we look at hosts individually, what presence do the biggest hosts in each city have _in that city_ (definted as the percentage of their total properties)? We saw above that host overlap between cities is generally low, but are there big hosts who are also very widespread?

Ignoring hosts with only one listing (which obviously means they exist 100% in that city only), if we calculate for each city _separately_ the percentage of listings each host has in that city, we generally see that those who have more are also more spread out, as one might expect. To visualize this, we can use the average percentage of listings in the city for categories of total listings:
* 2 to 10 listings (small hosts)
* 10 to 20 listings (medium hosts)
* 21 to 50 listings (fairly big hosts)
* more than 50 listings (major hosts)

![Bar chart of the average % listings a host has in each city, averaged over the listing categories specified above. You can see that everywhere the % decreases as the total number of listings increases.]({{ '/assets/avg_listing_share_by_total_listings_city.png' | relative_url }})

The binning is arbitrary, but results don't change if you use a different one: those who have more also tend to be spread out beyond the city's territory.
For example, there are extreme cases like [E-Domizil Daniel](https://www.airbnb.co.uk/users/show/685495832), who has over 1,000 listings worldwide and just a handful in Bologna, Florence, Rome, and Venice, and thus a low share in each city (below 1%) - there are several hosts like this.

Here's the situation for the biggest host in each city:

| City  | Biggest host | Num. listings in city | % of their listings in the city |
| ------------- | ------------- | ------------- | 
| Bologna  | [Wonderful italy Emilia-Romagna](https://www.airbnb.com/users/show/487811050	)  | 182 | 99% |
| Florence  | [MMega Homes And Villas](https://www.airbnb.co.uk/users/show/23904874)  | 242 | 60% |
| Milan  | [Italianway](https://www.airbnb.com/users/show/27693585)  | 480 | 99% |
| Naples  | [Dimorra](https://www.airbnb.com/users/show/128841116)  | 144 | 95% |
| Rome  | [IFlat](https://www.airbnb.co.uk/users/show/23904874)  | 252 | 96%  |
| Venice  | [Veniceapartment-com](https://www.airbnb.co.uk/users/show/23904874)  | 142 | 100% |
| Lecce  | [Lecce Selection](https://www.airbnb.co.uk/users/show/524849479)  | 54 | 38%  |
| Palermo  | [Wonderful Italy Sicilia](https://www.airbnb.co.uk/users/show/487814742)  | 172 | 70% |

So it looks like some exist almost exclusively in that city, meaning they've expanded there without branching out elsewhere, while others may have started there and then expanded outside the city, or immediately acquired properties in various places.

Notes:
* Small errors or discrepancies due to scraping are possible – for example, percentages close to 100% may actually be 100%
* Compared to the previous [post](https://bernomone.github.io/citybreaking/english/2025/10/19/gini-italy.html) on the biggest hosts, the names are mostly the same but the number of listings may have changed due to the new data batch (updated data)
* For Lecce, the biggest host has changed compared to the old post – the previous one, ["Barbarhouse SRL"](https://www.airbnb.co.uk/users/show/9632167), is now in second place with 51 listings and only 3% share in Lecce (most are in the province)

It will be interesting to see how and if this changes when we look at other countries.