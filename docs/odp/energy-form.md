# Energy Form ODP

## Description

The Energy Form Ontology Design Pattern represents energy through the specific form in which it manifests, such as thermal, mechanical, electrical, or chemical energy. It also models energy conversion as the process through which energy changes from one form into another.

The pattern distinguishes the source energy form entering a conversion process from the destination energy form resulting from that process. Both roles refer to instances of `energy_form`, allowing the same reusable structure to describe many conversion pathways without prescribing particular technologies or energy carriers.

By separating energy, energy forms, and conversion processes, the pattern provides a compact semantic basis for representing conversion chains and for connecting them to other ESO patterns concerning generation, storage, transmission, technologies, and system operations.

---

## Conceptual Diagram
![Energy Form ODP Diagram](../assets/images/energy_form.png)

---

## Key Concepts

### Core concepts

- **`energy`**: A quality of material entities that manifests as the capacity to perform work. In this pattern, energy is associated with at least one energy form.
- **`energy_form`**: A specific manifestation or type of energy, such as thermal, mechanical, electrical, or chemical energy, which can be transferred or converted into another form.
- **`energy_conversion`**: An energy process and internal system operation that transforms a source energy form into a destination energy form. For example, a generator can convert mechanical energy into electrical energy.

### Conversion roles

- **Source energy form**: The form of energy that enters or precedes an energy-conversion process. It is represented as the target of `energy_conversion hasSource energy_form`.
- **Destination energy form**: The form of energy produced by or resulting from an energy-conversion process. It is represented as the target of `energy_conversion hasDestination energy_form`.

---

## Main Relationships

| Source concept | Relationship | Target concept |
|---|---|---|
| `energy` | `hasForm` | `energy_form` |
| `energy_conversion` | `hasSource` | `energy_form` |
| `energy_conversion` | `hasDestination` | `energy_form` |
| `energy_conversion` | `isA` | `energy_process` |
| `energy_conversion` | `isA` | `System_internal_operation` |

---

## Interpretation

The pattern separates what energy is from the form in which it occurs and from the process that transforms it. The `hasForm` relation identifies the manifestation of energy, whereas `hasSource` and `hasDestination` identify the input and output roles of energy forms within a conversion process.

Because both the source and destination are modeled as `energy_form`, the pattern can represent conversion pathways generically. For example, a conversion may map chemical energy to thermal energy, thermal energy to mechanical energy, or mechanical energy to electrical energy. Multiple conversions can be connected to form longer energy-conversion chains.

This structure supports competency questions about the form associated with energy, the source and destination forms of a conversion, and the conversion processes that connect different energy forms.

---

⬅️ [Back to the ODP Catalog](./)


