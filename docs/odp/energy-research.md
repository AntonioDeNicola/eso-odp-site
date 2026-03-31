# Energy Research ODP

## Description
The Energy Research Ontology Design Pattern represents research activities related to the energy domain, including natural science, behavioural science, and design science contributions [1, 2].

This pattern provides a structured semantic representation that can be reused across the ESO catalog and linked to other patterns when modeling more complex energy-system dynamics.

---

## Conceptual Diagram
![Energy Research ODP Diagram](../assets/images/energy-research.png)

---

## Formal OWL Excerpt

```turtle
@prefix eso:  <http://jerico.casaccia.enea.it/genesys/Energy-System-Ontology_v1.01#> .
@prefix owl:  <http://www.w3.org/2002/07/owl#> .
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .

eso:natural_science_research a owl:Class ;
    rdfs:subClassOf [ a owl:Restriction ; owl:onProperty eso:isPartOf ; owl:someValuesFrom eso:energy_research ] ;
    rdfs:subClassOf [ a owl:Restriction ; owl:onProperty eso:addresses ; owl:someValuesFrom eso:environment_subsystem ] ;
    rdfs:subClassOf [ a owl:Restriction ; owl:onProperty eso:addresses ; owl:someValuesFrom eso:energy_operations_subsystem ] ;
    rdfs:subClassOf [ a owl:Restriction ; owl:onProperty eso:develops ; owl:someValuesFrom eso:theory ] ;
    rdfs:subClassOf [ a owl:Restriction ; owl:onProperty eso:develops ; owl:someValuesFrom eso:natural_science_law ] ;
    rdfs:subClassOf [ a owl:Restriction ; owl:onProperty eso:develops ; owl:someValuesFrom eso:natural_science_model ] ;
    rdfs:subClassOf [ a owl:Restriction ; owl:onProperty eso:hasActivity ; owl:someValuesFrom eso:discovery ] ;
    rdfs:subClassOf [ a owl:Restriction ; owl:onProperty eso:hasActivity ; owl:someValuesFrom eso:justification ] .

eso:behavioral_research a owl:Class ;
    rdfs:subClassOf [ a owl:Restriction ; owl:onProperty eso:isPartOf ; owl:someValuesFrom eso:energy_research ] ;
    rdfs:subClassOf [ a owl:Restriction ; owl:onProperty eso:addresses ; owl:someValuesFrom eso:agent_behavior_subsystem ] ;
    rdfs:subClassOf [ a owl:Restriction ; owl:onProperty eso:addresses ; owl:someValuesFrom eso:strategy_subsystem ] ;
    rdfs:subClassOf [ a owl:Restriction ; owl:onProperty eso:addresses ; owl:someValuesFrom eso:policy_subsystem ] ;
    rdfs:subClassOf [ a owl:Restriction ; owl:onProperty eso:develops ; owl:someValuesFrom eso:theory ] ;
    rdfs:subClassOf [ a owl:Restriction ; owl:onProperty eso:hasActivity ; owl:someValuesFrom eso:discovery ] ;
    rdfs:subClassOf [ a owl:Restriction ; owl:onProperty eso:hasActivity ; owl:someValuesFrom eso:justification ] .

eso:design_science_research a owl:Class ;
    rdfs:subClassOf [ a owl:Restriction ; owl:onProperty eso:isPartOf ; owl:someValuesFrom eso:energy_research ] ;
    rdfs:subClassOf [ a owl:Restriction ; owl:onProperty eso:addresses ; owl:someValuesFrom eso:energy_operations_subsystem ] ;
    rdfs:subClassOf [ a owl:Restriction ; owl:onProperty eso:builds ; owl:someValuesFrom eso:construct ] ;
    rdfs:subClassOf [ a owl:Restriction ; owl:onProperty eso:builds ; owl:someValuesFrom eso:model ] ;
    rdfs:subClassOf [ a owl:Restriction ; owl:onProperty eso:builds ; owl:someValuesFrom eso:method ] ;
    rdfs:subClassOf [ a owl:Restriction ; owl:onProperty eso:builds ; owl:someValuesFrom eso:implementation ] ;
    rdfs:subClassOf [ a owl:Restriction ; owl:onProperty eso:hasActivity ; owl:someValuesFrom eso:evaluation ] ;
    rdfs:subClassOf [ a owl:Restriction ; owl:onProperty eso:hasActivity ; owl:someValuesFrom eso:build ] .

eso:environment_subsystem a owl:Class ;
    rdfs:subClassOf [ a owl:Restriction ; owl:onProperty eso:isPartOf ; owl:someValuesFrom eso:energy_domain_of_interest ] .

eso:energy_operations_subsystem a owl:Class ;
    rdfs:subClassOf [ a owl:Restriction ; owl:onProperty eso:isPartOf ; owl:someValuesFrom eso:energy_domain_of_interest ] .

eso:agent_behavior_subsystem a owl:Class ;
    rdfs:subClassOf [ a owl:Restriction ; owl:onProperty eso:isPartOf ; owl:someValuesFrom eso:energy_domain_of_interest ] .

eso:strategy_subsystem a owl:Class ;
    rdfs:subClassOf [ a owl:Restriction ; owl:onProperty eso:isPartOf ; owl:someValuesFrom eso:energy_domain_of_interest ] .

eso:policy_subsystem a owl:Class ;
    rdfs:subClassOf [ a owl:Restriction ; owl:onProperty eso:isPartOf ; owl:someValuesFrom eso:energy_domain_of_interest ] .

```

---

## Related Classes and Properties

```turtle
@prefix eso:  <http://jerico.casaccia.enea.it/genesys/Energy-System-Ontology_v1.01#> .
@prefix owl:  <http://www.w3.org/2002/07/owl#> .

eso:energy_research a owl:Class .
eso:natural_science_research a owl:Class .
eso:behavioral_research a owl:Class .
eso:design_science_research a owl:Class .

eso:environment_subsystem a owl:Class .
eso:energy_operations_subsystem a owl:Class .
eso:agent_behavior_subsystem a owl:Class .
eso:strategy_subsystem a owl:Class .
eso:policy_subsystem a owl:Class .
eso:energy_domain_of_interest a owl:Class . 

eso:theory a owl:Class .
eso:natural_science_law a owl:Class .
eso:natural_science_model a owl:Class .

eso:construct a owl:Class .
eso:model a owl:Class .
eso:method a owl:Class .
eso:implementation a owl:Class .

eso:discovery a owl:Class .
eso:justification a owl:Class .
eso:build a owl:Class .
eso:evaluation a owl:Class .

eso:addresses a owl:ObjectProperty .
eso:develops a owl:ObjectProperty .
eso:builds a owl:ObjectProperty .
eso:hasActivity a owl:ObjectProperty .
```

---

## Key Concepts

- **energy_research**: It represents research activities in the energy domain.
- **natural_science_research**: It represents research focused on environmental and operational subsystems.
- **design_science_research**: It represents artifact-oriented research addressing operational subsystems.
- **behavioral_research**: It represents research addressing behavioural, strategic, or policy subsystems.

---

## Interpretation
The pattern provides a structured way to represent research diversity in the energy domain, connecting methodological traditions with the subsystems they address and the outputs they generate.

---

## Download
- [TTL file](../assets/rdf/energy-research.ttl)

---

## References
[1] A. R. Hevner, S. T. March, J. Park, S. Ram, Design science in information systems research, MIS Quarterly: Management Information Systems 28 (1) (2004) 75 – 105. doi:10.2307/25148625.

[2] S. T. March, A. R. Hevner, Design and natural science research on information technology, Decision Support Systems, 15 (4), pp. 251 - 266 (1995) 251 - 266. doi:10.1016/0167-9236(94)00041-2. 

