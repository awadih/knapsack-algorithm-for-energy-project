# knapsack-algorithm-for-energy-project
knapsack algorithm for optimizing energy renovation project

## Context
The developement & application of this greedy algorithm have raised as I had the task to suggest restoration measures for buildings at the [Amperias GmbH](https://www.amperias.com/) company in Germany. The calculation method of the heat load is according to the standard [DIN 12831](https://www.din.de/de/mitwirken/normenausschuesse/nhrs/veroeffentlichungen/wdc-beuth:din21:261292587). In the course of this calculation, for each building structure component, such as walls, roofs, etc., an insulation material has been chosen from a set of choices.

## Objective
An energy consultant assesses the building insulation, sets the requirements, but he/she has many insulation materials for each building component, which responds to the energetic requirements, namely the heating load. But, the performace of each insulation material reduces over time (the rate of depreciation). A well thoughtful choice for each building component should be proactive.
Therefore, I reformulate the objective as to gain the maximum insulation, e.g. minimum heat loss costs, for the whole building while investing a given money amount.

## Conditions
To take into account the rate of depreciation, I set hereafter the lifespan of the building renovation project with 20 years. The assessement considers then heat losses after 20 years of usage for each insulation material. On the other hand, many other factors such as the varying price of the insulation material in the markt, I give with this code an automated solution to possible biases.

## Study case

To grafically present the problem, here is an example of possible measures for a set of building components.
![Renovation project - Presentation example with four building components](<resources/renovation for a building - diagram.jpg>)

We formulate the problem as follows:

## Credits

