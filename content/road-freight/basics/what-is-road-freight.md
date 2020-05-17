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

{{< figure src="../assets/what/undraw_Ride_till_I_can_no_more_44wq.png" caption="source: undraw.co">}}

Road freight is a complex system and involves multiple fields of research. If we were to define the objectives of road freight, one of them would be moving materials of some properties (weight, volume, and special requirements) and go through a squence of locations $(P_1, P_2, \cdots, P_m, D_1, D_2, \cdots, D_n)$, under some certain policies (speed limits, height limit, travel restrictions, etc).

## Several Parties Involved

There are two core parties in road freight: the shipper and the carrier. The shipper is the party who provides the load and sets the expectations. The carrier is the party who transports the load.

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

In reality, connecting the shipper and carrier is no easy task. Apart from the two core parties, a third trustworth party is usually invovled. This is the forwarder. The forwarder takes in shipments from the shipper and finds a carrier for the shipment.

Though trivial, it is important to point out that a bunch of other parties, such as infrastructure related parties, policy makers, security staff, routing services, may also participate in this trip.

## How is Road Freight Doing

> In physics, the work is measured by force multiplied by displacement.

To measure the "work" done by road freight, a convinient measure is weight multiplied by the distance of the trip. As an example, the unit of this "work" may be million tonne-kilometer.

Throughout the years, the "work" done by road freight has been growing.

{{< figure src="../assets/what/road_freight_volume_history.png" title="Road Freight Power by Year" caption="OECD (2020), Freight transport (indicator). This figure excludes rail freight.">}}

The investment on road infrastructure has always been huge for many countries.

{{< figure src="../assets/what/road_freight_investiment_history.png" title="Road Freight Investment by Year" caption="ITF (2020), Transport infrastructure investment and maintenance, ITF Transport Statistics (database)">}}




## References

1. https://www.itf-oecd.org/itf-transport-outlook-project
2. [OECD (2020), Freight transport (indicator).](https://data.oecd.org/transport/freight-transport.htm) doi: 10.1787/708eda32-en (Accessed on 17 May 2020)
3. [ITF (2020), "Transport infrastructure investment and maintenance", ITF Transport Statistics (database), https://doi.org/10.1787/g2g55573-en (accessed on 17 May 2020).](https://stats.oecd.org/BrandedView.aspx?oecd_bv_id=trsprt-data-en&doi=g2g55573-en#)