# Energy Demand ODP

## Description

The Energy Demand Ontology Design Pattern represents energy demand as a service request and an energy process shaped by behavioural, technological, environmental, policy, and economic factors. Energy demand depends on consumer behaviour, weather conditions, energy-efficiency policies, and technologies, while also interacting bidirectionally with the energy market price.

The pattern also describes demand response as an operational strategy initiated by energy providers and grid operators and enabled by policy instruments and market mechanisms. Consumers participate in demand response, which reacts to price signals and may be triggered by grid conditions. By modifying energy demand, demand response contributes to grid balance and peak-demand reduction.

By connecting consumers, market signals, policy instruments, grid conditions, elasticities, and substitution mechanisms, the pattern supports a structured analysis of how energy demand changes and how it can be managed within an energy system.

---

## Conceptual Diagram

![Energy Demand ODP Diagram](../assets/images/energy-demand.png)

---

## Key Concepts

### Core concepts

- **`energy_demand`**: A demand for energy. In ESO, it is modeled both as a `Service_request` and as an `energy_process`.
- **`demand_response`**: A strategy used by energy providers and grid operators to manage electricity demand during periods of peak consumption or supply constraints. It encourages consumers to adjust their electricity use in response to price signals or grid conditions.
- **`consumer`**: An actor who uses goods or services, has a behaviour, and participates in demand response. Consumer income and sensitivity to prices contribute to energy-demand dynamics.

### Demand drivers and market signals

- **`behavior`**: The way in which a consumer acts; in this pattern, it represents behavioural characteristics associated with energy consumption.
- **`weather`**: Short-term atmospheric conditions—including temperature, humidity, precipitation, wind, and cloud cover—that can affect energy use.
- **`technology`**: Information specifying how an artificial object is created; technologies can affect the way energy is consumed and the efficiency of energy services.
- **`energy_efficiency_policy`**: Regulations, incentives, and initiatives intended to improve energy efficiency across economic sectors.
- **`energy_market_price`**: The market value or cost of buying or selling energy resources at a given time, shaped by supply and demand, production costs, policy, and other market conditions.
- **`price_signal`**: A signal conveyed through prices, tariffs, or market incentives that can induce consumers or other market actors to change their energy use.
- **`grid_condition`**: An operational state of the electricity grid that may affect reliability, supply–demand balance, congestion, or the need for demand-side adjustment.
- **`energy_carrier`**: A material or phenomenon used to transport or store energy and between which demand may shift as a result of substitution.

### Elasticities and economic effects

- **`income_elasticity`**: A measure of the responsiveness of energy demand to changes in consumer income.
- **`price_elasticity`**: A measure of the responsiveness of demand to changes in the price of a product or service.
- **`consumer_income`**: The income or economic resources available to a consumer, affecting purchasing capacity and energy demand.
- **`income_effect`**: The change in energy demand associated with a change in consumers’ purchasing power.
- **`substitution_effect`**: A demand-side economic mechanism through which consumers shift demand from a relatively more expensive or less attractive energy carrier or technology to an alternative.
- **`relative_price_change`**: A change in the price relationship between energy carriers, technologies, or services that may alter their relative attractiveness to consumers.

### Actors, instruments, and objectives

- **`energy_provider`**: An entity responsible for supplying or distributing energy to consumers and businesses.
- **`grid_operator`**: An actor responsible for operating and coordinating an electricity grid, including grid balance, reliability, and operational security.
- **`policy-maker`**: An actor who develops or implements public policies and may use policy instruments to influence energy demand and demand response.
- **`researcher`**: An actor who investigates energy-demand dynamics and produces new knowledge about the energy system.
- **`policy_instrument`**: A tool or mechanism used by policymakers to implement or support a policy intervention.
- **`market_mechanism`**: A mechanism or market force that helps determine the price and availability of goods and services.
- **`grid_balance`**: The operational alignment of electricity supply and demand required for stable and reliable grid operation.
- **`peak_demand_reduction`**: The objective of lowering electricity demand during periods of maximum load.

---

## Main Relationships

| Source concept | Relationship | Target concept |
|---|---|---|
| `energy_demand` | `dependsOn` | `behavior`, `energy_efficiency_policy`, `technology`, `weather` |
| `energy_demand` | `hasElasticity` | `income_elasticity`, `price_elasticity` |
| `energy_demand` | `influences` | `energy_market_price` |
| `energy_market_price` | `influences` | `energy_demand` |
| `energy_demand` | `affects` | `grid_condition` |
| `energy_demand` | `isInterestedIn` | `consumer` |
| `demand_response` | `modifies` | `energy_demand` |
| `demand_response` | `respondsTo` | `price_signal` |
| `demand_response` | `aimsAt` | `grid_balance`, `peak_demand_reduction` |
| `consumer` | `participatesIn` | `demand_response` |
| `consumer` | `hasBehavior` | `behavior` |
| `energy_provider`, `grid_operator` | `initiates` | `demand_response` |
| `policy_instrument`, `market_mechanism` | `enables` | `demand_response` |
| `grid_condition` | `triggers` | `demand_response` |
| `price_signal` | `concerns` | `energy_market_price` |
| `income_effect` | `influences` | `energy_demand` |
| `substitution_effect` | `influences` | `energy_demand` |
| `substitution_effect` | `substitutesFrom` / `substitutesTo` | `energy_carrier`, `technology` |
| `income_elasticity` | `measuresResponsivenessTo` | `consumer_income` |
| `price_elasticity` | `measuresResponsivenessTo` | `energy_market_price` |
| `consumer_income` | `givesRiseTo` | `income_effect` |
| `relative_price_change` | `triggers` | `substitution_effect` |
| `relative_price_change` | `influences` | `behavior` |
| `energy_provider`, `policy-maker`, `researcher` | `isInterestedIn` | `energy_demand` |

---

## Interpretation

The pattern combines three complementary perspectives. First, it represents the factors associated with energy demand, including behaviour, weather, technology, energy-efficiency policy, and market prices. The influence between energy demand and energy market price is bidirectional: prices affect demand, while demand also influences market prices. Second, the pattern models economic responsiveness through income elasticity, price elasticity, income effects, and substitution effects. Third, it represents demand response as an intervention enabled by policy and market mechanisms, initiated by energy-system actors, and activated in response to market and grid signals.

This structure makes the pattern suitable for competency questions concerning the factors that shape demand, the mutual relationship between demand and market prices, consumer responsiveness to income and price changes, the actors interested in demand dynamics, and the mechanisms used to manage peak consumption and grid balance.


---

⬅️ [Back to the ODP Catalog](./)


