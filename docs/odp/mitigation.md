# Mitigation ODP

## Description
The Mitigation Ontology Design Pattern captures actions and strategies aimed at reducing negative consequences associated with hazards, critical events, and vulnerabilities affecting systems.

This pattern provides a structured semantic representation that can be reused across the ESO catalog and linked to other patterns when modeling more complex energy-system dynamics.

---

## Conceptual Diagram
![Mitigation ODP Diagram](../assets/images/mitigation.png)

---

## Formal OWL Excerpt

```turtle
@prefix eso:  <http://jerico.casaccia.enea.it/genesys/Energy-System-Ontology_v1.01#> .
@prefix owl:  <http://www.w3.org/2002/07/owl#> .
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .

eso:mitigation a owl:Class ;
    rdfs:label "mitigation" ;
    rdfs:subClassOf eso:system_internal_operation ;
    rdfs:subClassOf [ a owl:Restriction ; owl:onProperty eso:isImplementedBy ; owl:someValuesFrom eso:action ] ;
    rdfs:subClassOf [ a owl:Restriction ; owl:onProperty eso:refersTo ; owl:someValuesFrom eso:strategy ] ;
    rdfs:subClassOf [ a owl:Restriction ; owl:onProperty eso:promotes ; owl:someValuesFrom eso:resilience ] ;
    rdfs:subClassOf [ a owl:Restriction ; owl:onProperty eso:reduces ; owl:someValuesFrom eso:critical_event_of_system ] .
```

---

## Related Classes and Properties

```turtle
@prefix eso:  <http://jerico.casaccia.enea.it/genesys/Energy-System-Ontology_v1.01#> .
@prefix owl:  <http://www.w3.org/2002/07/owl#> .
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .

eso:mitigation a owl:Class .
eso:action a owl:Class .
eso:strategy a owl:Class .
eso:resilience a owl:Class .
eso:critical_event_of_system a owl:Class .
eso:system_aspect a owl:Class .
eso:hazard a owl:Class .
eso:vulnerability a owl:Class .
eso:stakeholder a owl:Class .

eso:isImplementedBy a owl:ObjectProperty .
eso:refersTo a owl:ObjectProperty .
eso:promotes a owl:ObjectProperty .
eso:reduces a owl:ObjectProperty .
eso:hasImpactOn a owl:ObjectProperty .
eso:hasImpact a owl:ObjectProperty .
eso:hasVulnerability a owl:ObjectProperty .
eso:takesCareOfEvent a owl:ObjectProperty .
```

---

## Key Concepts

- **mitigation**: It represents actions aimed at reducing negative consequences.
- **critical_event_of_system**: It represents the event whose impact is reduced.
- **resilience**: It represents the condition promoted through mitigation.
- **hazard**: It represents the source of risk associated with a critical event.
- **vulnerability**: It represents the susceptibility of a system aspect.

---

## Interpretation
The pattern links hazards, system vulnerabilities, critical events, and resilience-promoting actions, making it useful for modeling adaptation and risk reduction processes.

---

## Download
- [TTL file](../assets/rdf/mitigation.ttl)
