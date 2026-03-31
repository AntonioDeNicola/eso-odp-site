# International Cooperation ODP

## Description
The International Cooperation Ontology Design Pattern represents cooperative interactions among countries and international organizations aimed at addressing shared challenges and pursuing common energy-related goals.

This pattern provides a structured semantic representation that can be reused across the ESO catalog and linked to other patterns when modeling more complex energy-system dynamics.

---

## Conceptual Diagram
![International Cooperation ODP Diagram](../assets/images/international-cooperation.png)

---

## Formal OWL Excerpt

```turtle
@prefix eso:  <http://jerico.casaccia.enea.it/genesys/Energy-System-Ontology_v1.01#> .
@prefix owl:  <http://www.w3.org/2002/07/owl#> .
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .

eso:international_cooperation a owl:Class ;
    rdfs:label "international_cooperation" ;
    rdfs:subClassOf eso:process ;
    rdfs:subClassOf [ a owl:Restriction ; owl:onProperty eso:requires ; owl:someValuesFrom eso:diplomacy ] ;
    rdfs:subClassOf [ a owl:Restriction ; owl:onProperty eso:requires ; owl:someValuesFrom eso:negotiation ] ;
    rdfs:subClassOf [ a owl:Restriction ; owl:onProperty eso:involves ; owl:someValuesFrom eso:country ] ;
    rdfs:subClassOf [ a owl:Restriction ; owl:onProperty eso:involves ; owl:someValuesFrom eso:international_organisation ] ;
    rdfs:subClassOf [ a owl:Restriction ; owl:onProperty eso:pursues ; owl:someValuesFrom eso:common_goal ] ;
    rdfs:subClassOf [ a owl:Restriction ; owl:onProperty eso:addresses ; owl:someValuesFrom eso:shared_challenge ] ;
    rdfs:subClassOf [ a owl:Restriction ; owl:onProperty eso:takesPlaceThrough ; owl:someValuesFrom eso:multilateral_organisation ] ;
    rdfs:subClassOf [ a owl:Restriction ; owl:onProperty eso:isFormalizedThrough ; owl:someValuesFrom eso:agreement ] .
```

---

## Related Classes and Properties

```turtle
@prefix eso:  <http://jerico.casaccia.enea.it/genesys/Energy-System-Ontology_v1.01#> .
@prefix owl:  <http://www.w3.org/2002/07/owl#> .
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .

eso:international_cooperation a owl:Class .
eso:diplomacy a owl:Class .
eso:negotiation a owl:Class .
eso:country a owl:Class .
eso:international_organisation a owl:Class .
eso:agreement a owl:Class .
eso:multilateral_organisation a owl:Class .
eso:common_goal a owl:Class .
eso:shared_challenge a owl:Class .

eso:requires a owl:ObjectProperty .
eso:involves a owl:ObjectProperty .
eso:isFormalizedThrough a owl:ObjectProperty .
eso:takesPlaceThrough a owl:ObjectProperty .
eso:pursues a owl:ObjectProperty .
eso:addresses a owl:ObjectProperty .
```

---

## Key Concepts

- **international_cooperation**: It represents cooperation processes among countries and organizations.
- **diplomacy**: It represents one of the enabling processes of cooperation.
- **negotiation**: It represents another enabling process of cooperation.
- **agreement**: It represents formal arrangements associated with cooperation.
- **shared_challenge**: It represents the challenge being jointly addressed.

---

## Interpretation
The pattern models international cooperation as a structured process involving multiple actors, formal arrangements, and shared objectives. It is useful for representing geopolitical and governance dimensions of energy transition.

---

## Download
- [TTL file](../assets/rdf/international-cooperation.ttl)
