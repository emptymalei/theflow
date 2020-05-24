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

A large part of human civilization is to move materials around. Many have played or have been playing their own parts in this great tradition and road transportation is one of the most important modes.

{{< figure src="../assets/what/undraw_Ride_till_I_can_no_more_44wq.png" caption="source: undraw.co">}}

Road transportation can either be moving passengers or goods. The latter is also called road freight. In this part, we will focus on road freight.

Road freight is a rather complex system. It depends on multiple fields of research.

## Definition of the Problem

{{< info title="What is Road Freight" >}} The core activity of road freight is to move materials of some properties (weight $W$, volume $V$, and special requirements), $\mathscr L(W,V,\cdots)$, through route $\mathscr R$ in the road network that connects a set of locations $\\{P_1, P_2, \cdots, P_m, D_1, D_2, \cdots, D_n\\}$, under some certain policies $\mathscr P$ (order of locations, speed limits, height limit, travel restrictions, etc), using predefined vehicles $\mathscr V$. {{< /info >}}

In the problem, four key factors are involved:

1. Loads: $\mathscr L$;
2. Routes: $\mathscr R$;
3. Policies: $\mathscr P$;
4. Vehicles/Capacities: $\mathscr V$

Loads are loaded on to the vehicles at the pickup location and unloaded at the dropoff location. Different loads requires different facilities and equipment at pickup and dropoff, as well as different vehicles, routes, and drivers during transportation. Efficient routing also involves information on transportation time requirements, road and traffic status, and weather forecast. Different policies may be enforced by the government and shippers. The vehicles or capacities to be used is a result of the loads and policies.

In many cases, the four factors are interconnect which renders a global optimization problem. Though trivial, it is important to point out that a bunch of other parties, such as infrastructure-related parties, policy makers, security staff, routing services, may also participate in this trip.



### Shipper and Carriers

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

### Forwarders and Marketplaces

In reality, connecting the shipper and carrier is no easy task. Apart from the two core parties, a third trustworthy party is usually involved. This can be either a forwarder or a marketplace. A forwarder takes in shipments from the shipper and finds a carrier for the shipment. A marketplace connects the shippers and carriers directly.

### Network and Terminals

The shipment may not go directly from the pickup location to the dropoff location. Networks and terminals may be use to aggregate shipments or change of transportation mode to maximize efficiency.

{{< figure src="../assets/what/road_freight_terminals.png" title="Network and Terminals">}}


## How is Road Freight Doing

> In physics, the work is measured by force multiplied by displacement. The work done per unit time is the power. There are analogies of work and power in road freight.

To measure the "work" done by road freight, a convenient measure is the weight multiplied by the distance of the trip. As an example, the unit of this "work" may be million tonne-kilometer.

In Europe, many countries rely on road freight for transportation. To get a grasp of this idea, we measure the share of road freight among all the inland transportation modes using the percentage of tonne-kilometer transported by road freight.

{{< figure src="../assets/what/eurostats_road_freight_share_in_modes.png" title="Road Freight Share in EU" caption="Using data from [eurostats](https://ec.europa.eu/eurostat/tgm/refreshTableAction.do?tab=table&plugin=1&pcode=t2020_rk320&language=en)">}}

Throughout the years, the "work" done by road freight has been growing.

{{< figure src="../assets/what/road_freight_volume_history.png" title="Road Freight Power by Year" caption="Using data from OECD (2020), Freight transport (indicator). This figure excludes rail freight.">}}

The investment on road infrastructure each year has always been huge in many countries.

{{< figure src="../assets/what/road_freight_investiment_history.png" title="Road Freight Investment by Year" caption="Using data from ITF (2020), Transport infrastructure investment and maintenance, ITF Transport Statistics (database)">}}



## References

1. [ITF Transport Outlook Project
](https://www.itf-oecd.org/itf-transport-outlook-project)
2. [Modal split of freight transpor (% in total inland freight tonne-km) by Eurostats](https://ec.europa.eu/eurostat/tgm/refreshTableAction.do?tab=table&plugin=1&pcode=t2020_rk320&language=en)
2. [OECD (2020), Freight transport (indicator).](https://data.oecd.org/transport/freight-transport.htm) doi: 10.1787/708eda32-en (Accessed on 17 May 2020)
3. [ITF (2020), "Transport infrastructure investment and maintenance", ITF Transport Statistics (database), https://doi.org/10.1787/g2g55573-en (accessed on 17 May 2020).](https://stats.oecd.org/BrandedView.aspx?oecd_bv_id=trsprt-data-en&doi=g2g55573-en#)