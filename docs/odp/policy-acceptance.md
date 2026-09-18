# Policy Acceptance ODP

## Description

The Policy Acceptance Ontology Design Pattern represents the behavioural factors that shape how actors respond to and support public policies. Rather than treating acceptance as an isolated outcome, the pattern connects an actor's behaviour to internal and external drivers that influence choices, attitudes, and actions.

Internal behaviour drivers include needs, principles, and concerns associated with an actor's beliefs, values, knowledge, emotions, and personal motivations. External behaviour drivers include social norms and policy-dependent factors arising from regulations, institutional arrangements, incentives, penalties, and other policy measures.

By connecting actors, behaviours, social influences, individual motivations, and policy instruments, the pattern supports a structured analysis of the conditions that may encourage or inhibit policy acceptance and behavioural compliance.

---

## Conceptual Diagram
![Policy Acceptance ODP Diagram](../assets/images/policy-acceptance.png)

---

## Key Concepts

### Core behavioural concepts

- **`actor`**: An entity capable of acting and making choices. In ESO, an actor has a behaviour and at least one behaviour driver.
- **`behavior`**: The way in which an actor acts or responds in a given context, including reactions to policies and policy measures.
- **`behavior_driver`**: A factor that influences or motivates an actor to engage in particular actions or make particular choices.
- **`policy_acceptance`**: The conceptual outcome represented by the pattern, concerning the extent to which actors support, adopt, or comply with a policy. It is not declared as a class in the current ESO version.

### Internal behaviour drivers

- **`internal_behavior_driver`**: An intrinsic factor—such as a belief, value, item of knowledge, emotion, or individual need—that influences an actor's choices and actions.
- **`concern`**: An actor's awareness, worry, or apprehension about an issue that may affect attitudes toward a policy.
- **`need`**: A requirement or perceived necessity capable of motivating behaviour. The imported TERMINUS class `Need` is modeled as an internal behaviour driver.
- **`principle`**: A fundamental guideline or rule that provides a basis for beliefs, actions, or behaviour.

### External and policy-dependent drivers

- **`external_behavior_driver`**: A contextual or environmental influence, such as a cultural norm, regulatory policy, societal expectation, or situational factor, that shapes decisions and actions.
- **`social_norm`**: A shared belief or attitude that guides behaviour within a society or social group.
- **`policy-dependent_behavior_driver`**: A driver that influences behaviour through regulations, rules, guidelines, or policies established by governing bodies or institutions.
- **`policy_measure`**: A specific action, intervention, or instrument implemented to achieve the objectives of a policy. In the pattern, it is also a policy-dependent behaviour driver.
- **`incentive`**: A positive motivational influence or benefit designed to encourage a particular action. ESO models it as a type of `policy_instrument`, which is equivalent to `policy_measure`.
- **`penalty`**: A negative consequence or sanction intended to discourage non-compliant or undesired behaviour.
- **`policy`**: A plan of action, set of principles, or institutional course of action supported and operationalized by policy measures.

---

## Main Relationships

| Source concept | Relationship | Target concept |
|---|---|---|
| `actor` | `hasBehavior` | `behavior` |
| `actor` | `hasBehaviorDriver` | `behavior_driver` |
| `internal_behavior_driver` | `isA` | `behavior_driver` |
| `external_behavior_driver` | `isA` | `behavior_driver` |
| `concern`, `need`, `principle` | `isA` | `internal_behavior_driver` |
| `social_norm`, `policy-dependent_behavior_driver` | `isA` | `external_behavior_driver` |
| `policy_measure` | `isA` | `policy-dependent_behavior_driver` |
| `incentive`, `penalty` | `isA` | `policy_measure` |
| `policy_measure` | `supports` | `policy` |

---

## Interpretation

The pattern combines three complementary perspectives. First, it represents policy acceptance through the behaviour of actors. Second, it distinguishes intrinsic motivations—such as needs and principles—from contextual influences such as social norms. Third, it represents policy measures, including incentives and penalties, as external drivers designed to influence behaviour and support a policy.

This structure makes the pattern suitable for competency questions concerning which factors influence an actor's behaviour, whether those factors are internal or external, which policy measures can modify behavioural choices, and how incentives, penalties, and social norms may affect policy acceptance.

> **Modeling note:** In ESO version 1.05, `policy_acceptance` is not declared as an OWL class; it is the interpretative focus of this ODP. The formal ontology explicitly models `actor hasBehavior behavior`, `actor hasBehaviorDriver behavior_driver`, the internal and external driver hierarchies, `policy_measure` as a subclass of `policy-dependent_behavior_driver`, and `policy_measure supports policy`. `Need`, `principle`, and `social_norm` are formally placed in the hierarchy shown in the diagram. The generic classes `concern` and `penalty` are not declared in the current ontology file, although specialized concern concepts exist. `incentive` is formally a subclass of `policy_instrument`; because `policy_instrument` is equivalent to `policy_measure`, it can be inferred to be a policy measure.

---

⬅️ [Back to the ODP Catalog](./)


