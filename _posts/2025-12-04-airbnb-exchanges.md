---
layout: post
title: "Airbnb Exchanges in Florence"
date: 2025-12-04
author: "Bernardo & Martina"
tags: [italy, exchange]
categories: [english]
excerpt: How to identify Airbnb exchanges between hosts
---

The population of hosts on Airbnb can be roughly divided into categories based on how many listings they own. Very "large" hosts, i.e., those with many listings in their account, are present in [many cities simultaneously](https://bernomone.github.io/citybreaking/italiano/2025/11/22/presenza-in-loco.html) and are gaining [increasingly larger market shares](https://bernomone.github.io/citybreaking/italiano/2025/11/03/gini-trends-italia.html) (except in Rome).

Market concentration occurs in many of the cities we have observed in previous posts, without a substantial increase in the number of listings. This can be explained in two ways:

1. Smaller hosts close their businesses as they are weaker in the market while larger hosts expand by creating new listings. The closures of smaller ones and openings by larger ones balance out in number.
2. Smaller hosts transfer their listings to larger hosts, without changing the overall number of listings. Listing transfers are not natively supported by Airbnb and hosts must resort to [strategies](https://community.withairbnb.com/t5/Help-with-your-business/Selling-my-Airbnb/td-p/1967210#:~:text=Unfortunately%2C%20Airbnb%20does%20not%20allow,the%20property%20on%20your%20account.) to ensure that the new owner maintains the listing's information (and reputation) after the transfer.

These two phenomena are not mutually exclusive and, in this post, we will try to understand how to identify when a new listing belongs to one of these two categories.

## Identifying Listing Transfers

Identifying a new listing that has appeared on the market is relatively simple. [Inside Airbnb](https://insideairbnb.com/get-the-data/) releases data on a set of cities in various snapshots at time intervals of approximately 3 months. To identify a new listing, it's sufficient to consider all listings that appeared for the first time in a data snapshot and were not in previous ones.

How can you recognize if a listing that appeared for the first time already existed and was previously in the hands of another host? There is no simple way, we have defined the following rules:

* We only consider listings that do not appear as single rooms (so only houses and apartments)
* The coordinates of the new listing are exactly the same as one that previously closed
* The number of bedrooms and bathrooms of the new listing are exactly the same as the closed one that has the same coordinates. This can help distinguish new listings that happened to appear with the same coordinates as a previously closed one.

Although these rules may inevitably lead to errors, both false positives (new listings erroneously identified as ownership transfers) and false negatives (transfers not identified), spot checks have convinced us that the adopted strategy is overall reasonable.

The following table shows the ownership transfers identified for Florence in the June 2025 snapshot.

| Previous Listing Name                            | Previous Host Name   | New Listing Name                                 | New Host Name                |
|:-------------------------------------------------|:---------------------|:-------------------------------------------------|:-----------------------------|
| Leoni Bargello Apartment by Mamo Florence        | Claudio              | Leoni Bargello Apartment by Mamo Florence        | Mamo                         |
| Santo Stefano Apartment by Mamo Florence         | Alvise               | Santo Stefano Apartment by Mamo Florence         | Mamo                         |
| Beautiful Apartment Next Duomo                   | Rachelle Khriseth    | Cozy & Charming Florentine Hideaway by Oteego    | Sea N' Rent                  |
| Noa, Deluxe flat in city center                  | Francesco            | Maison - Luxury and Design Three-Room Apartment  | Florence Charming Apartments |
| Cosy and Charming Apartment in Heart of Florence | Nicolò               | Cosy and Charming Apartment in Heart of Florence | Tommaso                      |
| Giacomini Suites (Free Wifi)                     | Edoardo              | Appartamento con 2 bagni privati                 | Roberto                      |
| A Romantic studio                                | Edo & Rita           | Sweet Florence close to Bargello 1               | Nikolozi                     |
| Flat Dona- Santo Spirito neighbourhood           | Margherita           | Flat Dona- Santo Spirito neighbourhood           | Marco                        |
| Maggio Boutique Apartment MBA Pitti Palace      | Beatrice             | MBA Maggio Boutique Apartment Pitti Palace      | Tommaso                      |
| Spacious flat in the historic centre of Florence | Francesca            | Spacious flat in the historic centre of Florence | Gianrocco                    |

You can see how in many cases the listing ID number doesn't change, but only the name (slightly) and the host change.
Particularly interesting is the case of the two listings "acquired" by the [Mamo](https://www.airbnb.it/rooms/33062988) account. There are many cases like those shown in the table in the data: a very small host who owns a listing with a name that includes "by Mamo Florence" transfers their listing to the Mamo account.
We can hypothesize that these hosts were already working for the Mamo chain as managers, and that Mamo then decided to centralize the listings under the main account.

Having the coordinates, we can map where the new listings that emerged in the June 2025 snapshot are located:

<iframe src='{{ "/assets/new_listings_map_20250601.html" | relative_url }}' width='120%' height='800px' frameborder='0' alt=""></iframe>

The red dots on the map represent the listings we identified as ownership transfers, while the blue ones are completely new listings. We can see at a glance that red listings are not the majority, although they are 13% of the total. This percentage varies if we divide hosts based on the number of listings they already own:

- Only 1 listing: 6.61%
- From 2 to 5 listings: 11.64%
- From 5 to 50 listings: 9.84%
- More than 50 listings: 23.95%

As is reasonable to expect, this type of transfer is done more frequently by large hosts who have enough resources to acquire an already established listing and therefore more expensive to take over.

## Data
The data presented in this post, with the categorization of new Airbnbs and their geographical location, can be found [here](https://github.com/bernomone/citybreaking/tree/main/data/airbnb-new-listing-status/).