# SPARQL Query Examples

This page presents a selection of SPARQL queries that illustrate how to retrieve knowledge from the Energy System Ontology (ESO). The examples focus on energy demand, policy measures, energy-market participants, renewable power generation, and energy strategies. They query the OWL class axioms and restrictions encoded in the ontology.

## SPARQL query example 1

**Which factors does energy demand depend on?**

```sparql
PREFIX owl:  <http://www.w3.org/2002/07/owl#>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
PREFIX eso:  <http://jerico.casaccia.enea.it/genesys/Energy-System-Ontology_v1.05#>

SELECT ?factor
WHERE {
    eso:energy_demand rdfs:subClassOf ?restriction .

    ?restriction a owl:Restriction ;
        owl:onProperty eso:dependsOn ;
        owl:someValuesFrom ?factor .
}
```

## SPARQL query example 2

**Which policy measures support technologies, and which technologies do they support?**

```sparql
PREFIX owl:  <http://www.w3.org/2002/07/owl#>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
PREFIX eso:  <http://jerico.casaccia.enea.it/genesys/Energy-System-Ontology_v1.05#>

SELECT ?policy_measure ?technology
WHERE {
    ?policy_measure rdfs:subClassOf eso:policy_measure ;
        rdfs:subClassOf ?restriction .

    ?restriction a owl:Restriction ;
        owl:onProperty eso:supports ;
        owl:someValuesFrom ?technology .

    ?technology rdfs:subClassOf* eso:technology .
}
```

## SPARQL query example 3

**Which types of stakeholders participate in energy markets?**

```sparql
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
PREFIX eso:  <http://jerico.casaccia.enea.it/genesys/Energy-System-Ontology_v1.05#>

SELECT ?stakeholder
WHERE {
    ?stakeholder rdfs:subClassOf eso:energy_market_participant .
}
```

## SPARQL query example 4

**Which types of renewable power generation depend on weather conditions, and which weather conditions do they depend on?**

```sparql
PREFIX owl:  <http://www.w3.org/2002/07/owl#>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
PREFIX eso:  <http://jerico.casaccia.enea.it/genesys/Energy-System-Ontology_v1.05#>

SELECT ?generationType ?weatherCondition
WHERE {
    ?weatherCondition rdfs:subClassOf eso:weather_condition .

    ?generationType rdfs:subClassOf eso:renewable_power_generation ;
        rdfs:subClassOf ?restriction .

    ?restriction a owl:Restriction ;
        owl:onProperty eso:dependsOn ;
        owl:someValuesFrom ?weatherCondition .
}
```

## SPARQL query example 5

**Which strategies aim at strategic goals that include energy security?**

```sparql
PREFIX owl:      <http://www.w3.org/2002/07/owl#>
PREFIX rdfs:     <http://www.w3.org/2000/01/rdf-schema#>
PREFIX eso:      <http://jerico.casaccia.enea.it/genesys/Energy-System-Ontology_v1.05#>
PREFIX terminus: <http://jerico.casaccia.enea.it/cn-hpc/TERMINUS_upper_ontology_v1.2#>

SELECT ?strategy ?goal
WHERE {
    ?strategy rdfs:subClassOf eso:strategy ;
        rdfs:subClassOf ?restriction .

    ?restriction a owl:Restriction ;
        owl:onProperty terminus:aimsAt ;
        owl:someValuesFrom ?goal .

    eso:energy_security rdfs:subClassOf ?goal .
}
```

---

⬅️ [Back to the ESO home page](./)

