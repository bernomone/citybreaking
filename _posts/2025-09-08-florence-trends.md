---
layout: post
title: "How and where are Airbnbs growing in Florence?"
date: 2025-09-18
author: "Bernardo & Martina"
tags: [italy, florence, time-trend]
categories: [english]
excerpt: We look at Airbnb data on Florence, over time and by area. First part, an analysis to get started.
---

As we write in the ["About Page"](https://bernomone.github.io/citybreaking/about/), this is a blog dedicated to analyzing the phenomenon of overtourism in general, starting with the city of Florence, which we cover in this post.

Our basic question is: have Airbnbs grown in Florence? And if so, where?
We'll try to answer using data from the excellent [Inside Airbnb](https://insideAirbnb.com/about/) platform.

# What data we have and how to interpret it

The data snapshots are quarterly so they don't provide very high temporal granularity: for each Airbnb property we can observe its presence/absence every 3 months but we don't have its creation date on the platform. However, we do have the dates of first reviews, which we'll use as a proxy for the creation date to observe trends over time.

Clearly, and this is the major caveat, it's entirely possible (though unlikely) that an active property has received 0 reviews, just as it's possible that a lot of time has passed between the creation date and the date it got its first review. We assume that a property is "new" at the moment it receives its first review.

The data is available from the first quarter of 2024, but reviews start from 2010 - Airbnb was founded in 2007, it probably took a few years to arrive in Italy. Using the first review date for all properties existing since 2024 means we don't have data on all the properties that "died" before 2024, i.e., were removed from the platform.

# Some numbers to start with

In total, considering all snapshots together, we see 16,769 unique properties, of which 14,521 have at least one review, which means that about 2,200 properties have no reviews at all. Since Airbnb encourages users to leave comments and ratings and this is an essential component of the platform, it's quite unusual for a property to have 0 reviews, but there are possible reasons:
* it's very recent (hasn't been used yet or has been used by few people)
* the property is booked through an agency (which doesn't bother to leave reviews after guests leave)
* it's possibly operating in an illicit way (tax evasion): the property uses Airbnb only to market to and attract potential users but the actual transaction is done outside the platform

# Airbnbs in Florence are growing over time

![Temporal trend of Florentine listings on Airbnb, showing a marked acceleration from 2022. Remember that we're only observing properties that were in existence in 2024.]({{ '/assets/Florence_new_listings_per_month.png' | relative_url }})

The figure shows clear temporal growth, particularly pronounced from 2022, the immediate post-COVID period.

# Yes, but where?

For each property we have its precise geolocation. So let's see which areas are most covered in heatmap format. In the interactive visualization below, you can select the year and zoom in on a specific area, but also let time run from the beginning by pressing the Play button. The color indicates the percentage of Airbnb properties, among those available at that time, found in the hexagonal area.

<iframe src='{{ "/assets/listing_first_review.html" | relative_url }}' width='100%' height='600px' frameborder='0' alt=""></iframe>

You can clearly see that initially the few Airbnbs are found almost exclusively in the historic center ("Centro storico"), and gradually begin to spread beyond until in recent years they encompass practically the entire municipal area.

However, we cannot conclude that the Airbnb phenomenon is only recently affecting the outskirts of the centre because the data we have suffers from [**Survivorship Bias**](https://en.wikipedia.org/wiki/Survivorship_bias). Since we only observe properties from 2024, we have no information about listings that were present previously and disappeared from Airbnb before 2024.
In short, we're observing a mix of recent properties and very old properties, but of the latter we only see those that managed to survive in time and that presumably are located in the area most affected by tourism. Therefore, it's plausible that in 2010 other properties outside Florence's center had their first review, but given the different tourism dynamics at the time and the different urban configuration, they are not present in the 2024 data, which is the first year we can observe in our snapshots.
But we nevertheless can get an idea about long-lasting properties.

# Next steps

This was just an appetizer! For Florence we mainly want to understand, and it might still be too early, whether the new municipal regulation (dating from June 2025), which banned the opening of new Airbnbs in the historical center, is having the desired effect or if it's just shifting the problem outside. We'll then look at other cities, try to make comparisons and investigate peculiarities.
