# Risk ODP

## Description
The Risk Ontology Design Pattern [1] represents critical events affecting system aspects from the perspective of stakeholders, with particular attention to hazards and vulnerabilities.

This pattern provides a structured semantic representation that can be reused across the ESO catalog and linked to other patterns when modeling more complex energy-system dynamics.

---

## Conceptual Diagram
![Risk ODP Diagram](../assets/images/risk.png)

---

## Formal OWL Excerpt

```turtle
@prefix eso:  <http://jerico.casaccia.enea.it/genesys/Energy-System-Ontology_v1.01#> .
@prefix owl:  <http://www.w3.org/2002/07/owl#> .
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .

eso:critical_event_of_system a owl:Class ;
    rdfs:label "critical event of system" ;
    rdfs:subClassOf [ a owl:Restriction ; owl:onProperty eso:hasImpactOn ; owl:someValuesFrom eso:system_aspect ] .

eso:system_aspect a owl:Class ;
    rdfs:subClassOf [ a owl:Restriction ; owl:onProperty eso:hasVulnerability ; owl:someValuesFrom eso:vulnerability ] .

eso:hazard a owl:Class ;
    rdfs:subClassOf [ a owl:Restriction ; owl:onProperty eso:hasImpact ; owl:someValuesFrom eso:critical_event_of_system ] .

eso:stakeholder a owl:Class ;
    rdfs:subClassOf [ a owl:Restriction ; owl:onProperty eso:takesCareOfEvent ; owl:someValuesFrom eso:critical_event_of_system ] .
```

---

## Related Classes and Properties

```turtle
@prefix eso:  <http://jerico.casaccia.enea.it/genesys/Energy-System-Ontology_v1.01#> .
@prefix owl:  <http://www.w3.org/2002/07/owl#> .
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .

eso:critical_event_of_system a owl:Class .
eso:system_aspect a owl:Class .
eso:hazard a owl:Class .
eso:vulnerability a owl:Class .
eso:stakeholder a owl:Class .

eso:hasImpactOn a owl:ObjectProperty .
eso:hasImpact a owl:ObjectProperty .
eso:hasVulnerability a owl:ObjectProperty .
eso:takesCareOfEvent a owl:ObjectProperty .
```

---

## Key Concepts

- **critical_event_of_system**: It represents an event affecting a system.
- **system_aspect**: It represents the aspect of the system affected by an event.
- **hazard**: It represents the source of potential harm.
- **vulnerability**: It represents the susceptibility of the affected aspect.
- **stakeholder**: It represents the actor concerned with the event.

---

## Interpretation
The pattern provides a semantic structure for describing events, their impacts on system aspects, and the vulnerabilities that mediate these impacts. It is especially useful for resilience and crisis-oriented analyses.

---

## Download
- [TTL file](../assets/rdf/risk.ttl)

---

## References
[1] A. De Nicola, M. L. Villani, Actionable semantic patterns in the crisis management lifecycle: The TERMINUS ontology, Smart Cities 8 (5)
(2025). doi:10.3390/smartcities8050179.
