# Leave infrastructure as it is, but have multi-regional sharding deployment as plan B.

## Context and Problem Statement

SoftArchCert needs to absorb up to ten times the current demand.
We should not overlook other points of failure in our infrastructure like:

* Databases
* Queues
* Gateway

Of those, the database tends to be the congestion point in scalability
We will end with 10 x 200 concurrent users per week.

We also lack information about the specific nature of databases or queues.

## Decision Drivers (Why)

* Scalability
* Availability
* Simplicity
* Costs

## Considered Options

* Database Table partition
* Multi-Regional Sharding cloud deployment by market
* Leave infrastructure as it is

## Decision Outcome

We decided to leave infrastructure as it is because the expected demand should not represent a problem for the current
infrastructure.
This way we can focus our efforts on adding AI automation.

We suspect that if this were the real world, the regional regulation, i18n and customization would soner or latter
arrive.
Those concerns are better handled in future projects that would have less uncertainty

It is hard to forecast performance, so we keep the multi-regional sharding deployment as an open option to reach the
desired scalability.

## Consequences (Trade-Offs)

* Good:
    * Time to market
    * Cheapest
    * Easier to maintain
    * YAGNI
    * If needed, we can decide latter when more information is available if
* Bad:
    * Migrating to other solutions latter can be harder
    * We lack the advantages of separated servers: data governance, latency...
    * We may need to do it later at some point

## Pros and Cons of the Options

### Multi-Regional Sharding cloud deployment by market

We can replicate the system in each region in separate cloud deployments.
Each region will have separated queues, databases and gateway reducing the impact of the 10X increase in the load
Regions could align with countries or regulations: US, EU, India, China, etc.

* Good:
    * Data Governance:
        * EU data will be handled in the EU cloud.
        * Auditors from `SALB` and future national equivalents can have full db access to its database.
    * Latency: Nice to have, but not really important
    * Adaptability: sooner or latter governments may require custom behavior
        * Different exams
        * Translated to their language*
        * Graded by architects certified in their country
        * With customized fields (Social security Number in US, National ID Document in EU)
    * Makes it easier to sell a non-profitable business in a region to a third party
* Not so good:
    * Complexity
        * Deployments are harder.
        * More infrastructure to administrate
    * Forces to replicate all the system even as much as the weakest point of the system.
    * Harder to share our certified experts between regions.
    * Potential overkill for 200 candidates per week.

### Partition tables by market

Partitioned tables could help with some searches.

* Good:
    * It Could improve some searches without big changes in the infrastructure
* Bad:
    * It Will not solve most of our issues
        * Won't improve queues
        * Won't solve most DB issues like the number of db connections

### Leave it as is

Modern databases should be able to handle 2000 candidates/week with current use cases.
Even them, distributed solutions like Cassandra or Mongo can scale by adding nodes.
We can even use transparent elasticity in cloud providers like with AWS Aurora.

* Good:
    * Time to market
    * Cheapest
    * Easier to maintain
    * YAGNI
    * If needed, we can decide latter when more information is available if
* Bad:
    * Migrating to other solutions latter can be harder
    * We lack the advantages of separated servers: data governance, latency...
    * We may need to do it later at some point