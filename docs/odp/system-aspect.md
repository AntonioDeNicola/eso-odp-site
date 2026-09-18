# System Aspect ODP

## Description

The System Aspect Ontology Design Pattern provides a general framework for describing a system from multiple complementary perspectives. A system may be characterized through the services it offers, its internal operations, its physical or organizational infrastructure, its assets, managed objects, commons, and spatial regions.

The pattern also represents the actors associated with system operation and use. Operators perform internal operations, external services leverage those operations, and users access the services provided by the system. Stakeholders—including shareholders, users, and regulators—may have an interest in particular system aspects or services.

By connecting structural, operational, service-oriented, spatial, and stakeholder perspectives, the pattern supports a modular description of complex systems and provides a reusable foundation for more specific energy-system patterns.

---

## Conceptual Diagram
![System Aspect ODP Diagram](../assets/images/system-aspect.png)

---

## Key Concepts

### Core system concepts

- **`system`**: An organized entity whose components, operations, services, resources, and stakeholders can be described through different system aspects.
- **`system_aspect`**: A general perspective, component, property, function, or dimension through which a system can be represented.
- **`system_external_service`**: A service delivered by the system to users or other systems outside its operational boundary.
- **`system_internal_operation`**: An activity or operation performed within the system to enable its functioning and support the provision of external services.
- **`service_request`**: A request for a service or function that the system is expected to provide.

### Structural and spatial aspects

- **`asset`**: A valuable resource, item, or capability associated with the system.
- **`infrastructure`**: The physical or organizational structures and facilities required for the functioning of a system. ESO explicitly models `infrastructure` as a type of `System_aspect`.
- **`managed_object`**: An entity monitored, controlled, maintained, or otherwise handled by the system.
- **`spatial_region`**: A spatially defined area relevant to the structure, operation, or effects of the system.
- **`commons`**: A shared resource or domain whose access, use, or management may involve multiple actors.

### Actors and stakeholder roles

- **`operator`**: An actor responsible for performing or supervising internal system operations.
- **`user`**: An actor who accesses or benefits from an external service provided by the system.
- **`stakeholder`**: An actor with an interest, responsibility, influence, or decision-making role concerning the system.
- **`shareholder`**: A stakeholder with an ownership or financial interest in the system or organization.
- **`regulator`**: A stakeholder responsible for establishing, monitoring, or enforcing rules governing the system.

---

## Main Relationships

| Source concept | Relationship | Target concept |
|---|---|---|
| `system` | `hasSystemAspect` | `system_aspect` |
| `system_external_service` | `isA` | `system_aspect` |
| `system_internal_operation` | `isA` | `system_aspect` |
| `service_request`, `asset`, `commons` | `isA` | `system_aspect` |
| `managed_object`, `spatial_region`, `infrastructure` | `isA` | `system_aspect` |
| `system_external_service` | `leveragesOn` | `system_internal_operation` |
| `operator` | `performs` | `system_internal_operation` |
| `system_external_service` | `hasUser` | `user` |
| `shareholder`, `user`, `regulator` | `isA` | `stakeholder` |
| `stakeholder` | `isInterestedIn` | `system_aspect` |
| `system` | `isPartOf` | `system` |

---

## Interpretation

The pattern combines three complementary perspectives. First, it provides a structural view of a system through assets, infrastructure, managed objects, commons, and spatial regions. Second, it represents the operational relationship between internal operations and externally delivered services. Third, it introduces the social and governance dimension through operators, users, shareholders, regulators, and their interests in system aspects.

This structure makes the pattern suitable for competency questions concerning which aspects compose a system, which internal operations support its external services, who operates or uses those services, and which stakeholders have an interest in particular system components or functions.

> **Modeling note:** The System Aspect ODP is derived from the TERMINUS ontology pattern cited below. ESO version 1.05 imports the principal TERMINUS classes, including `System`, `System_aspect`, `System_external_service`, `System_internal_operation`, `Service_request`, `Asset`, `Commons`, `Managed_object`, `Spatial_region`, `Operator`, and `Stakeholder`. However, most of the subclass and object-property connections shown in the diagram are not reproduced as OWL restrictions in the current ESO file. ESO explicitly models its class `infrastructure` as a subclass of `System_aspect` and declares it equivalent to the TERMINUS `Infrastructure`. The properties `leveragesOn`, `performs`, and `hasUser` are not declared in the current file. The diagram's “System (Internal) Service” is represented here using the ontology term `System_internal_operation`. The diagram also shows `system isPartOf system`, whereas the related imported ecosystem axiom uses `isSubsystemOf` rather than `isPartOf`.

---


## References
[1] A. De Nicola, M. L. Villani, Actionable semantic patterns in the crisis management lifecycle: The TERMINUS ontology, Smart Cities 8 (5)
(2025). doi:10.3390/smartcities8050179.

---

⬅️ [Back to the ODP Catalog](./)


