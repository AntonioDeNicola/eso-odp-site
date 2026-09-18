# Energy Waste ODP

## Description

The Energy Waste Ontology Design Pattern represents energy waste as unnecessary or inefficient energy use that increases consumption without producing corresponding benefits. It connects wasteful behaviour with technological causes, higher energy consumption, economic costs, and impacts on the environment.

The pattern also places energy waste within the wider context of energy usage and user behaviour. Energy usage is attributable to an energy end user and implies energy consumption, while the user's behaviour is shaped by behavioural drivers and is associated with the way energy is used.

By connecting behaviour, technology, consumption, cost, environmental impact, and user satisfaction, the pattern supports a structured analysis of why energy waste occurs and what consequences it produces within an energy system.

---

## Conceptual Diagram
![Energy Waste ODP Diagram](../assets/images/energy-waste.png)

---

## Key Concepts

### Core concepts

- **`energy_waste`**: The unnecessary or inefficient use of energy resources, leading to increased consumption without corresponding benefits. In ESO, it is modeled as a type of `behavior` and `sustainable_and_environmental_behavior`.
- **`energy_usage`**: The amount of energy used by individuals, communities, industries, or societies to meet needs and perform activities. It is modeled both as a service request and as an energy process.
- **`energy_consumption`**: The amount of energy consumed to carry out activities and meet energy needs; increased consumption can lead to higher costs.

### Causes and behavioural factors

- **`technology`**: The technological factor to which energy waste may be attributed, for example through inefficient equipment, systems, or processes.
- **`behavior`**: The way an actor acts or makes choices. Energy waste is formally represented as a specialized behaviour, and an energy end user has a behaviour.
- **`behavior_driver`**: A factor that influences or motivates an actor to engage in particular actions or make particular choices.
- **`energy_end_user`**: An individual, household, business, or organization that uses energy for activities such as heating, cooling, lighting, transport, or industrial processes.

### Consequences and user perspective

- **`cost`**: The economic consequence that may increase when energy consumption rises.
- **`environment`**: The environmental system affected by unnecessary or inefficient energy use.
- **`user_satisfaction`**: The level of contentment or fulfilment perceived by an energy end user in relation to a product, service, system, or experience.

---

## Main Relationships

| Source concept | Relationship | Target concept |
|---|---|---|
| `energy_waste` | `isA` | `behavior`, `sustainable_and_environmental_behavior` |
| `energy_waste` | `isDueTo` | `technology` |
| `energy_waste` | `increases` | `energy_consumption` |
| `energy_waste` | `hasImpactOn` | `environment` |
| `energy_usage` | `implies` | `energy_consumption` |
| `energy_usage` | `isDueTo` | `energy_end_user` |
| `energy_consumption` | `increases` | `cost` |
| `energy_end_user` | `hasBehavior` | `behavior` |
| `energy_end_user` | `hasBehaviorDriver` | `behavior_driver` |
| `user_satisfaction` | `isPerceivedBy` | `energy_end_user` |

---

## Interpretation

The pattern combines three complementary perspectives. First, it represents energy waste as a behaviour caused by technological conditions and capable of increasing energy consumption. Second, it connects consumption with higher economic costs and waste with environmental consequences. Third, it places energy use within a behavioural context in which end users act according to behavioural drivers and perceive a level of satisfaction.

This structure makes the pattern suitable for competency questions concerning the causes of energy waste, its effects on consumption, cost, and the environment, and the behavioural factors associated with the way end users consume energy.

> **Modeling note:** In ESO version 1.05, the concept shown as **Energy User** in the diagram corresponds to `energy_end_user`. The relation `energy_end_user hasBehaviorDriver behavior_driver` is inherited through the class hierarchy because `energy_end_user` is an `energy_market_participant`, an `energy_market_participant` is a `market_participant`, and a `market_participant` is an `actor`; the formal axioms for `actor` include `hasBehaviorDriver`. The ontology also explicitly states that `energy_waste` is a subclass of both `behavior` and `sustainable_and_environmental_behavior`.

---
⬅️ [Back to the ODP Catalog](./)

