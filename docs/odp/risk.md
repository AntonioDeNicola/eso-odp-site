# Risk ODP

## Description

The Risk Ontology Design Pattern represents risk through the interaction between hazards, critical events, affected system aspects, and vulnerabilities. A hazard may produce an impact that contributes to a critical system event, while the consequences of that event depend on the characteristics and vulnerabilities of the affected system.

The pattern also introduces the governance dimension of risk by identifying the stakeholder responsible for taking care of a critical event. This allows risk analysis to connect potential sources of harm with event management, system exposure, and organizational responsibility.

By linking hazards, critical events, system aspects, vulnerabilities, and stakeholders, the pattern supports a structured representation of risk identification and assessment within energy systems, infrastructures, ecosystems, and crisis-management contexts.

---

## Conceptual Diagram
![Risk ODP Diagram](../assets/images/risk.png)

---

## Key Concepts

### Core risk concepts

- **`risk`**: The possibility or probability that an event, action, or situation will lead to harm, loss, or another undesirable outcome. In ESO, `risk` is equivalent to `System_risk` from the TERMINUS upper ontology.
- **`critical_event_of_system`**: An event capable of significantly disrupting, damaging, or altering the functioning of a system.
- **`hazard`**: A potential source of danger or harm that may contribute to the occurrence or consequences of a critical system event. The ESO class `hazard` is equivalent to the TERMINUS class `Hazard`.

### System exposure and susceptibility

- **`system_aspect`**: A component, property, function, or dimension of a system that may be affected by a critical event.
- **`vulnerability`**: The susceptibility of a system aspect to harm, disruption, or loss when exposed to a hazard or critical event.

### Governance and responsibility

- **`stakeholder`**: An actor with an interest, responsibility, or decision-making role in relation to the system and the management of a critical event.
- **`event_management`**: The responsibility represented in the pattern by a stakeholder taking care of a critical event, including coordination, response, and recovery activities.

---

## Main Relationships

| Source concept | Relationship | Target concept |
|---|---|---|
| `hazard` | `hasImpact` | `critical_event_of_system` |
| `stakeholder` | `takesCareOfEvent` | `critical_event_of_system` |
| `critical_event_of_system` | `hasImpactOn` | `system_aspect` |
| `system_aspect` | `hasVulnerability` | `vulnerability` |
| `risk` | `equivalentTo` | `system_risk` |
| `hazard` | `equivalentTo` | `Hazard` |

---

## Interpretation

The pattern combines three complementary perspectives. First, it represents the causal dimension of risk by linking a hazard to a critical system event. Second, it captures system exposure and susceptibility through the affected system aspect and its vulnerability. Third, it introduces organizational responsibility by identifying the stakeholder who takes care of the event.

This structure makes the pattern suitable for competency questions concerning which hazards may lead to critical events, which system aspects may be affected, which vulnerabilities influence potential consequences, and which stakeholders are responsible for managing an event.

---

## References
[1] A. De Nicola, M. L. Villani, Actionable semantic patterns in the crisis management lifecycle: The TERMINUS ontology, Smart Cities 8 (5)
(2025). doi:10.3390/smartcities8050179.

---

⬅️ [Back to the ODP Catalog](./)

