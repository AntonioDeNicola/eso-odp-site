# Energy Value Chain ODP

## Description
The Energy Value Chain Ontology Design Pattern describes the main stages of the energy value chain, from primary sources and generation to transmission, storage, distribution, and end use.

This pattern provides a structured semantic representation that can be reused across the ESO catalog and linked to other patterns when modeling more complex energy-system dynamics.

---

## Conceptual Diagram
![Energy Value Chain ODP Diagram](../assets/images/energy-value-chain.png)

---

## Formal OWL Excerpt

```turtle
@prefix eso:  <http://jerico.casaccia.enea.it/genesys/Energy-System-Ontology_v1.01#> .
@prefix owl:  <http://www.w3.org/2002/07/owl#> .
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .

eso:energy_value_chain a owl:Class ;
    rdfs:label "energy value chain" ;
    rdfs:subClassOf [ a owl:Restriction ; owl:onProperty eso:hasSource ; owl:someValuesFrom eso:primary_energy_source ] ;
    rdfs:subClassOf [ a owl:Restriction ; owl:onProperty eso:isGeneratedBy ; owl:someValuesFrom eso:energy_generator ] ;
    rdfs:subClassOf [ a owl:Restriction ; owl:onProperty eso:isTransmittedBy ; owl:someValuesFrom eso:energy_network ] ;
    rdfs:subClassOf [ a owl:Restriction ; owl:onProperty eso:isStoredBy ; owl:someValuesFrom eso:energy_storage_system ] ;
    rdfs:subClassOf [ a owl:Restriction ; owl:onProperty eso:isDistributedBy ; owl:someValuesFrom eso:energy_provider ] ;
    rdfs:subClassOf [ a owl:Restriction ; owl:onProperty eso:hasUser ; owl:someValuesFrom eso:energy_end_user ] .
```

---

## Related Classes and Properties

```turtle
@prefix eso:  <http://jerico.casaccia.enea.it/genesys/Energy-System-Ontology_v1.01#> .
@prefix owl:  <http://www.w3.org/2002/07/owl#> .

eso:energy_value_chain a owl:Class .
eso:primary_energy_source a owl:Class .
eso:energy_generator a owl:Class .
eso:energy_network a owl:Class .
eso:energy_storage_system a owl:Class .
eso:energy_provider a owl:Class .
eso:energy_end_user a owl:Class .

eso:hasSource a owl:ObjectProperty .
eso:isGeneratedBy a owl:ObjectProperty .
eso:isTransmittedBy a owl:ObjectProperty .
eso:isStoredBy a owl:ObjectProperty .
eso:isDistributedBy a owl:ObjectProperty .
eso:hasUser a owl:ObjectProperty .
```

---

## Key Concepts

- **energy**: It represents the core entity moving through the value chain.
- **primary_energy_source**: It represents the original source of energy.
- **energy_generator**: It represents generation infrastructure.
- **energy_network**: It represents transmission infrastructure.
- **energy_storage_system**: It represents storage infrastructure.
- **energy_end_user**: It represents the final recipient of distributed energy.

---

## Interpretation
The pattern provides a compact representation of the stages through which energy flows from source to end user, making it suitable for modeling the operational logic of energy systems.

---

## Download
- [TTL file](../assets/rdf/energy-value-chain.ttl)
