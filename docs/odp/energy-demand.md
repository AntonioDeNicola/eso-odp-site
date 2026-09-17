# Energy Demand ODP

## Description
The Energy Demand Ontology Design Pattern models energy demand as the outcome of interacting demographic, technological, environmental, behavioural, and economic factors. It also captures the actors that are interested in demand dynamics, such as energy providers, policymakers, and researchers.

This pattern provides a structured semantic representation that can be reused across the ESO catalog and linked to other patterns when modeling more complex energy-system dynamics.

---

## Conceptual Diagram

![Energy Demand ODP Diagram](../assets/images/energy-demand.png)

---

## Formal OWL Excerpt

```turtle
@prefix eso:  <http://jerico.casaccia.enea.it/genesys/Energy-System-Ontology_v1.01#> .
@prefix owl:  <http://www.w3.org/2002/07/owl#> .
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .

eso:energy_demand a owl:Class ;
    rdfs:label "energy_demand" ;
    rdfs:subClassOf eso:service_request ;
    rdfs:subClassOf [ a owl:Restriction ; owl:onProperty eso:dependsOn ; owl:someValuesFrom eso:behavior ] ;
    rdfs:subClassOf [ a owl:Restriction ; owl:onProperty eso:dependsOn ; owl:someValuesFrom eso:economic_condition ] ;
    rdfs:subClassOf [ a owl:Restriction ; owl:onProperty eso:dependsOn ; owl:someValuesFrom eso:energy_efficiency_policy ] ;
    rdfs:subClassOf [ a owl:Restriction ; owl:onProperty eso:dependsOn ; owl:someValuesFrom eso:population ] ;
    rdfs:subClassOf [ a owl:Restriction ; owl:onProperty eso:dependsOn ; owl:someValuesFrom eso:technology ] ;
    rdfs:subClassOf [ a owl:Restriction ; owl:onProperty eso:dependsOn ; owl:someValuesFrom eso:weather ] ;
    rdfs:subClassOf [ a owl:Restriction ; owl:onProperty eso:isInterestedIn ; owl:someValuesFrom eso:energy_provider ] ;
    rdfs:subClassOf [ a owl:Restriction ; owl:onProperty eso:isInterestedIn ; owl:someValuesFrom eso:policy-maker ] ;
    rdfs:subClassOf [ a owl:Restriction ; owl:onProperty eso:isInterestedIn ; owl:someValuesFrom eso:researcher ] .
```

---

## Related Classes and Properties

```turtle
@prefix eso:  <http://jerico.casaccia.enea.it/genesys/Energy-System-Ontology_v1.01#> .
@prefix owl:  <http://www.w3.org/2002/07/owl#> .
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .

eso:energy_demand a owl:Class .
eso:behavior a owl:Class .
eso:economic_condition a owl:Class .
eso:energy_efficiency_policy a owl:Class .
eso:population a owl:Class .
eso:technology a owl:Class .
eso:weather a owl:Class .
eso:energy_provider a owl:Class .
eso:policy-maker a owl:Class .
eso:researcher a owl:Class .

eso:dependsOn a owl:ObjectProperty .
eso:isInterestedIn a owl:ObjectProperty .
```

---

## Key Concepts

- **energy_demand**: It represents the service request for energy that emerges from multiple interacting drivers.
- **behavior**: It captures behavioural factors influencing consumption and demand patterns.
- **economic_condition**: It represents macro- or micro-economic conditions affecting energy demand.
- **energy_efficiency_policy**: It captures policy measures that influence demand through efficiency improvements.
- **population**: It represents demographic conditions associated with demand dynamics.
- **technology**: It represents technological factors affecting energy use and demand.
- **weather**: It represents climatic conditions that shape energy demand.

---

## Interpretation

The pattern formalizes energy demand as a concept shaped by both contextual conditions and stakeholder perspectives. It supports integrated analysis across environmental, policy, behavioural, technological, and economic dimensions.

---

## Download
- [TTL file](../assets/rdf/energy-demand.ttl)
