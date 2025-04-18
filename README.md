# knapsack-algorithm-for-energy-project
knapsack algorithm for optimizing energy renovation project

## Context
The developement & application of this greedy algorithm have raised as I had the task to suggest restoration measures for buildings at the [Amperias GmbH](https://www.amperias.com/) company in Germany. The calculation method of the heat load is according to the standard [DIN 12831](https://www.din.de/de/mitwirken/normenausschuesse/nhrs/veroeffentlichungen/wdc-beuth:din21:261292587). In the course of this calculation, for each building structure component, such as walls, roofs, etc., an insulation material has been chosen from a set of choices.

## Objective
An energy consultant assesses the building insulation, sets the requirements, but he/she has many insulation materials for each building component, which responds to the energetic requirements, namely the heating load. But, the performace of each insulation material reduces over time (the rate of depreciation). A well thoughtful choice for each building component should be proactive.
Therefore, I reformulate the objective as to gain the maximum insulation, e.g. minimum heat loss costs, for the whole building while investing the maximum of a given money amount.

## Conditions
- To take into account the rate of depreciation, I set hereafter the lifespan of the building renovation project with 20 years. The assessement considers then heat losses after 20 years of usage for each insulation material. On the other hand, many other factors such as the varying price of the insulation material in the markt, I give with this code an automated solution to possible biases.
- The renovation of a building element can be left out, limitation either due to no sufficient investment amount or because the impact of leaving the building element without any renovation is irrelevant. In the code, we can have as a result: (number of renovated elements) counter < (total number of building elements) df.shape[0]

## Nomenclature

For explenation purpose, I use both signs [] and {} with combined definitions in logics in Math and the programming language Python.

- Inv: the total renovation investment costs
- Hij: heat loss costs for each insulation material after 20 years of usage for each renovation measure j and building element i (In German: Wärmeverlustkosten)
- Kij: the material costs for each renovation measure j and building element i (Materialkosten)
- n: total number of building elements
- m: the maximum count of measures over all building elements for a normalized problem Here is an explenation:

  Mathematical problem:

  - Set E = {E1, E2, ..., En} and each building element Ei has Mij as a set of its possible renovation measures, for i in [1, ..., n] and j in [1, ..., m]</br>
  - In the example given in the image:</br>

    - n = 4
    - E = {"Window", "Ceiling", "Roof", "Wall"}
    - M1 = {"Single-Glazed Window", "Double glazed window"}
    - M2 = {"Mineral wool", "Spray foam", "Rigid foam boards", "Cellulose", "Sheep wool"}
    - M3 = {"Structural insulated panels", "Foam board", "Rigid foam"}
    - M4 = {"Blanket: batts and rolls", "Concrete blocks insulation", "Insulating concrete forms (ICFs)", "Foam board or rigid foam", "Reflective system"}</br>

  Normalized problem:

  - In the programming code, we normalize the sets Mij for all i values in [1, ..., n], the set Mij could be written Mim and the above mentioned example becomes:
    - n = 4, m = 5
    - E = {"Window", "Ceiling", "Roof", "Wall"}
    - M15 = {"", "", "", "Single-Glazed Window", "Double glazed window"}
    - M25 = {"Mineral wool", "Spray foam", "Rigid foam boards", "Cellulose", "Sheep wool"}
    - M35 = {"", "", "Structural insulated panels", "Foam board", "Rigid foam"}
    - M45 = {"Blanket: batts and rolls", "Concrete blocks insulation", "Insulating concrete forms (ICFs)", "Foam board or rigid foam", "Reflective system"}
  - Note that, the measure "" in each set measures means that no measure could be taken, so the costs are taken in the algorithm 0.0 price unit (price unit: €, $, ... etc.). The costs' sets could be then written for example:
    - K15 = [0.0, 0.0, 0.0, 10, 13]
    - K25 = [45, 56, 67, 18, 19]
    - K35 = [0.0, 0.0, 32.5, 16, 11]
    - K45 = [93, 34, 45, 95, 23]

## Study case

To grafically present the problem, here is an example of possible measures for a set of building components.

![Renovation project - Presentation example with four building components](<resources/renovation for a building - diagram.jpg>)

The deduction of the values of Hlc for each insulation material and building component can be done after heat loss calculations with the norm [DIN 12831](https://www.din.de/de/mitwirken/normenausschuesse/nhrs/veroeffentlichungen/wdc-beuth:din21:261292587).

The problem is solved as follows:
- as
- Minimize the product "heat loss costs" (Hij) times "material costs" (Kij) for each building component and insulation material.


## Credits

