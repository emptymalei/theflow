---
title: What is Road Freight
description: Road freight is an important component of modern civilization
weight: 2
tags:
 - Road Freight
 - Introduction
---


> Movements of people, goods and information have always been fundamental components of human societies.
>
> -- J. P. Rodrigue, C. Comtois, and B. Slack, The geography of transport systems. 2006.

A large part of human civilization is to move materials around. Many has played or have been playing their own parts in this great trandition and road transportation is one of the oldest and most important one.

In this part, we will restrict ourselves to road freight for simplicity.

![](../assets/what/undraw_Ride_till_I_can_no_more_44wq.png)

Road freight is a complex system and involves multiple fields of research. If we were to define the objectives of road freight, one of them would be moving materials of some properties (weight, volume, and special requirements) and go through a squence of locations $(P_1, P_2, \cdots, P_m, D_1, D_2, \cdots, D_n)$, under some certain policies (speed limits, height limit, travel restrictions, etc).

## A Case

A simple case is shown in the following Gantt chart.

{{<mermaid>}}
gantt
    title A Workflow
    dateFormat  YYYY-MM-DD
    section Shipper
    Coordinate Pickup           :2020-01-01, 1d
    Coordinate Dropoff          :2020-01-05, 1d
    Receive Proof of Delivery to Shipper     :2020-01-06,1d
    Pay the Carrier             :2020-01-07, 1d
    section Carrier
    Carrier Get Loads      :2020-01-01, 1d
    Fetch Loads at Pickup Location            :2020-01-02, 1d
    Transport to Dropoff Location           :2020-01-03, 2d
    Dropoff      :2020-01-05, 1d
    Provide Proof of Delivery to Shipper     :2020-01-06,1d
    Receive the Payment             :2020-01-07, 1d
{{</mermaid>}}


## How Important is Road Freight

![](https://img.shields.io/badge/WORK-IN%20PROGRESS-orange?style=for-the-badge)




## References

1. https://www.itf-oecd.org/itf-transport-outlook-project