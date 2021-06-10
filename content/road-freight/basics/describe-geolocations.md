---
title: "Describe a Location"
description: "How to describe a location"
date: 2021-05-24
weight: 5
tags:
 - Introduction
 - Topics
 - Basics
 - Geography
references:
  - key: "Rodrigue2020"
    name: "Rodrigue J-P. The Geography of Transport Systems. 3th ed. Taylor & Francis Group; 2020."
    link: "https://www.routledge.com/The-Geography-of-Transport-Systems/Rodrigue/p/book/9780367364632"
draft: false
---

We can use three types of properties to describe a location[^Rodrigue2020]:
- Site details (is there a ramp? is it on the wrong side of the road?);
- Accessibility;
- Socioeconomic environment.

{{< figure src="../assets/describe-geolocations/three-properties-of-a-location.jpg" caption="The three types of properties of a location." >}}

The site details and the socioeconomic environment is understood by the name. Here we will discuss the accessibility of a location.


## Accessibility of a location

Accessibility is a very important property of a location.

{{< figure src="../assets/describe-geolocations/accessibility-demo-1.jpg" caption="Geolocation of two cities A and B. There are more cities close to A than B thus A is more accessible." >}}


Rodrigue et al provided a definition for accessibility: "measure of the capacity of a location to be reached by or to reach different locations."[^Rodrigue2020]

In the above example, we are measuring the accessibility on the surface of the Earth. This is called **contiguous accessibility**. The other perspective of accessibility is using graph, which is called **topological accessibility**.

{{< figure src="../assets/describe-geolocations/topological-accessibility-demo-1.jpg" caption="On a graph, location A has a higher degree than location B. The topological accessibility of A is higher than B." >}}



### Measurement of accessibility

To measure the contiguous accessibility, we can use the number of cities included within a circle. By adjusting the size of the radius, we can even get the cumulative counts for different radius.

{{< figure src="../assets/describe-geolocations/accessibility-demo-1-circles.jpg" caption="Location A is more accessible than location B as A has more cities in its vicinity" >}}

The topological accessibility can be measured by the degrees of the node A and node B.

Using these ideas, we can build scalar values to measure the accessibility of a location, e.g., geographic accessibility $A_G$.

{{< figure src="../assets/describe-geolocations/geographic-accessibility-demo-1.jpg" caption="Graph of connected cities." >}}

$A_G$ is defined as the normalized sum of shortest path from the location to all other cities[^Rodrigue2020]. For example, from city A to city B, we have all the distances shown in the following table.

|  Path |  Distance  |
|:---:|:---:|
|  A->B |  3 |
|  A->C |  2 |
|  A->D |  1 |
|  A->A |  0 |

The geographic accessbility is

{{< m >}}
A_G(A) = \frac{3 + 2 + 1 + 0}{4} = 1.5,
{{< /m >}}

where the denominator $4$ is the normalization factor, i.e., the number of cities being considered on the graph.






[^Rodrigue2020]: {{< cite key="Rodrigue2020" >}}