# Energy Research ODP

## Description

The Energy Research Ontology Design Pattern represents research in the energy domain through three complementary traditions: natural science research, behavioral research, and design science research [1, 2]. Each tradition contributes different activities, research artifacts, and perspectives on the energy system.

Natural science research seeks explanations of physical and environmental phenomena by developing theories, natural-science laws, and models through discovery and justification. Behavioral research studies actors, policies, and strategies, also using discovery and justification to develop theories of behaviour and decision making. Design science research addresses practical energy-system problems by building and evaluating constructs, models, methods, and implementations.

The pattern connects these research traditions to the main ESO subsystems and situates those subsystems within the Energy Domain of Interest. It therefore provides a reusable semantic structure for describing what energy research studies, which activities it performs, and which knowledge artifacts or practical solutions it produces.


---

## Conceptual Diagram
![Energy Research ODP Diagram](../assets/images/energy-research.png)

---

## Key Concepts

### Research traditions

- **`energy_research`**: Research focused on phenomena, actors, technologies, operations, policies, and strategies within the energy domain.
- **`natural_science_research`**: Systematic empirical research that studies the natural world through observation, experimentation, data collection, and analysis in order to identify principles, laws, patterns, and explanatory models.
- **`behavioral_research`**: Research aimed at understanding human or organizational behaviour, including actions, decisions, interactions, policies, and strategies.
- **`design_science_research`**: Research that creates and evaluates innovative artifacts or systems in order to address practical problems while producing reusable knowledge.

### Natural and behavioral research outputs

- **`theory`**: A research artifact providing a principled explanation of observed phenomena. Both natural science and behavioral research can develop theories.
- **`natural_science_law`**: A research artifact expressing a regularity or principle identified through natural science research.
- **`natural_science_model`**: A research artifact representing natural phenomena, relationships, or processes.

### Design science artifacts

- **`construct`**: A concept forming part of the vocabulary used to describe a domain and specify solutions to its problems.
- **`model`**: A set of propositions or statements expressing relationships among constructs.
- **`method`**: A sequence of steps, algorithm, or guideline used to perform a task.
- **`implementation`**: The realization or instantiation of an artifact within its intended environment.

### Research activities

- **`discovery`**: A research activity through which previously unknown phenomena, patterns, or explanations are identified.
- **`justification`**: A research activity that supplies evidence and reasoning in support of a proposition, model, explanation, or decision.
- **`build`**: A design science activity through which an artifact is created or assembled.
- **`evaluate`**: A design science activity through which an artifact is assessed against relevant criteria, standards, or objectives.

### Energy-system scope

- **`environment_subsystem`**: The part of the energy domain concerned with environmental conditions, processes, and effects.
- **`energy_operations_subsystem`**: The part of the energy domain concerned with technical and operational energy-system processes.
- **`agent_behaviour_subsystem`**: The part of the energy domain concerned with actors, behaviour, and decision making.
- **`strategy_subsystem`**: The part of the energy domain concerned with strategies, plans, and strategic action.
- **`policy_subsystem`**: The part of the energy domain concerned with policy formulation, implementation, and effects.
- **`energy_domain_of_interest`**: The bounded field within which energy-related phenomena, technologies, operations, actors, strategies, and policies are investigated.

---

## Main Relationships

| Source concept | Relationship | Target concept |
|---|---|---|
| `natural_science_research` | `isPartOf` | `energy_research` |
| `behavioral_research` | `isPartOf` | `energy_research` |
| `design_science_research` | `isPartOf` | `energy_research` |
| `natural_science_research` | `develops` | `theory`, `natural_science_law`, `natural_science_model` |
| `natural_science_research` | `hasActivity` | `discovery`, `justification` |
| `natural_science_research` | `addresses` | `environment_subsystem`, `energy_operations_subsystem` |
| `behavioral_research` | `develops` | `theory` |
| `behavioral_research` | `hasActivity` | `discovery`, `justification` |
| `behavioral_research` | `addresses` | `agent_behaviour_subsystem`, `strategy_subsystem`, `policy_subsystem` |
| `design_science_research` | `builds` | `construct`, `model`, `method`, `implementation` |
| `design_science_research` | `hasActivity` | `build`, `evaluate` |
| `design_science_research` | `addresses` | `energy_operations_subsystem` |
| `theory`, `natural_science_law`, `natural_science_model` | `isA` | `research_artifact` |
| `construct`, `model`, `method`, `implementation` | `isA` | `research_artifact` |
| `discovery`, `justification`, `build`, `evaluate` | `isA` | `research_activity` |
| `environment_subsystem`, `energy_operations_subsystem`, `agent_behaviour_subsystem`, `strategy_subsystem`, `policy_subsystem` | `isPartOf` | `energy_domain_of_interest` |

---

## Interpretation

The pattern distinguishes research according to both purpose and output. Natural science research explains and models observable phenomena; behavioral research explains the behaviour and decisions of actors and institutions; design science research creates and evaluates artifacts that address practical problems. These traditions are complementary rather than mutually exclusive and can be combined within a single energy-research programme.

The subsystem relations define the scope of each tradition. Natural science research addresses environmental and operational aspects, behavioral research addresses actor behaviour, strategy, and policy, and design science research focuses on operational problems and solutions. Because all five subsystems belong to the Energy Domain of Interest, the pattern can connect disciplinary research activities within an integrated representation of the energy system.

> **Modeling note:** The conceptual diagram uses the display label “Evaluation”. The formal restriction `design_science_research hasActivity` points to the class `evaluate`, which is the identifier used in the table above. ESO also contains a distinct class named `evaluation` that is not the target of this restriction.

---

## References

[1] A. R. Hevner, S. T. March, J. Park, and S. Ram, “Design science in information systems research,” *MIS Quarterly*, vol. 28, no. 1, pp. 75–105, 2004. [https://doi.org/10.2307/25148625](https://doi.org/10.2307/25148625).

[2] S. T. March and G. F. Smith, “Design and natural science research on information technology,” *Decision Support Systems*, vol. 15, no. 4, pp. 251–266, 1995. [https://doi.org/10.1016/0167-9236(94)00041-2](https://doi.org/10.1016/0167-9236(94)00041-2).

⬅️ [Back to the ODP Catalog](./)

