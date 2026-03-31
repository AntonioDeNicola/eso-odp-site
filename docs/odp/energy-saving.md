# Energy Saving ODP

## Description

The Energy Saving Ontology Design Pattern represents energy saving as a form of behavior that contributes to lowering energy consumption while preserving user satisfaction and generating broader system-level benefits. In ESO, this pattern is connected to the behavioral subsystem and captures how end users, behavioral drivers, energy usage, and benefits are semantically related within energy transition processes.  

This pattern is especially useful for representing demand-side interventions, behavioral change, and efficiency-oriented actions in a way that remains interoperable with the wider ontology structure. In the ontology, `energy-saving` is modeled as a subclass of `behavior`, constrained by restrictions stating that it reduces `energy_consumption`, ensures `user_satisfaction`, and has some `benefit`. 

---

## Conceptual Diagram

![Energy Saving Diagram](../assets/images/energy_saving.png)

---

## Formal OWL Excerpt

```turtle
@prefix eso:  <http://jerico.casaccia.enea.it/genesys/Energy-System-Ontology_v1.01#> .
@prefix owl:  <http://www.w3.org/2002/07/owl#> .
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .

eso:energy_saving a owl:Class ;
    rdfs:subClassOf eso:behavior ;
    rdfs:subClassOf [ a owl:Restriction ; owl:onProperty eso:ensures ; owl:someValuesFrom eso:user_satisfaction ] ;
    rdfs:subClassOf [ a owl:Restriction ; owl:onProperty eso:hasBenefit ; owl:someValuesFrom eso:benefit ] ;
    rdfs:subClassOf [ a owl:Restriction ; owl:onProperty eso:reduces ; owl:someValuesFrom eso:energy_consumption ] ;
    rdfs:label "energy saving" .

eso:energy_end_user a owl:Class ;
    rdfs:subClassOf [ a owl:Restriction ; owl:onProperty eso:hasBehavior ; owl:someValuesFrom eso:behavior ] ;
    rdfs:subClassOf [ a owl:Restriction ; owl:onProperty eso:hasBehaviorDriver ; owl:someValuesFrom eso:behavior_driver ] .

eso:user_satisfaction a owl:Class ;
    rdfs:subClassOf [ a owl:Restriction ; owl:onProperty eso:isPerceivedBy ; owl:someValuesFrom eso:energy_end_user ] .

eso:energy_usage a owl:Class ;
    rdfs:subClassOf [ a owl:Restriction ; owl:onProperty eso:implies ; owl:someValuesFrom eso:energy_consumption ] ;
    rdfs:subClassOf [ a owl:Restriction ; owl:onProperty eso:isDueTo ; owl:someValuesFrom eso:energy_end_user ] .

eso:reduced_energy_costs a owl:Class ;
    rdfs:subClassOf eso:benefit .

eso:energy_security a owl:Class ;
    rdfs:subClassOf eso:benefit .

eso:environmental_benefit a owl:Class ;
    rdfs:subClassOf eso:benefit .

eso:sustainable_development a owl:Class ;
    rdfs:subClassOf eso:benefit .
```

---

## Related Classes and Properties

```turtle
@prefix eso:  <http://jerico.casaccia.enea.it/genesys/Energy-System-Ontology_v1.01#> .
@prefix owl:  <http://www.w3.org/2002/07/owl#> .

eso:energy_saving a owl:Class .
eso:behavior a owl:Class .
eso:energy_end_user a owl:Class .
eso:behavior_driver a owl:Class .
eso:energy_usage a owl:Class .
eso:energy_consumption a owl:Class .
eso:user_satisfaction a owl:Class .
eso:benefit a owl:Class .
eso:reduced_energy_costs a owl:Class .
eso:environmental_benefit a owl:Class .
eso:sustainable_development a owl:Class .
eso:energy_security a owl:Class .

eso:hasBehavior a owl:ObjectProperty .
eso:hasBehaviorDriver a owl:ObjectProperty .
eso:isPerceivedBy a owl:ObjectProperty .
eso:implies a owl:ObjectProperty .
eso:isDueTo a owl:ObjectProperty .
eso:reduces a owl:ObjectProperty .
eso:hasBenefit a owl:ObjectProperty .
eso:ensures a owl:ObjectProperty .
```

---

## Key Concepts

* **energy-saving**: A behaviour aimed at reducing energy consumption while maintaining adequate levels of user satisfaction.
* **energy_end_user**: The actor whose behaviour and perception are relevant to the realization of energy-saving practices.
* **behavior_driver**: The set of internal or external factors influencing user behaviour.
* **energy_consumption**: The process reduced by energy-saving behaviour.
* **user_satisfaction**: A condition that energy saving is expected to preserve.
* **benefit**: The positive outcomes associated with energy saving, including reduced energy costs, environmental benefit, sustainable development, and energy security. 

---

## Interpretation

Within ESO, energy saving is not represented as a purely technical optimization outcome. Rather, it is formalized as a behavioural phenomenon connected to users, drivers, perceived outcomes, and broader socio-technical benefits. This makes the pattern suitable for describing energy transition processes in which behavioural change, policy measures, and system performance interact. 

The pattern also supports integration with adjacent ODPs, particularly those concerning policy acceptance, energy demand, and energy waste, thereby enabling richer representations of demand-side dynamics in energy systems.

---

## Download

* [TTL file](../assets/rdf/energy-saving.ttl)

---

