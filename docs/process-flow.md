# Upgrade Process Evolution

This document presents the evolution of the upgrade request process from the current manual workflow, through a controlled Proof of Concept (PoC), to the target state with full automation.

The diagrams intentionally stay at business-process level and avoid infrastructure-specific implementation details.

---

## 1. Process Evolution

```mermaid
flowchart LR
    A["CURRENT PROCESS<br/><br/>Consultant performs<br/>the process manually"]
    B["PoC<br/>HUMAN IN THE LOOP<br/><br/>Automation prepares<br/>Consultant reviews and approves"]
    C["TARGET<br/>FULL AUTOMATION<br/><br/>Automation handles<br/>standard cases end to end"]

    A --> B --> C
```

**Evolution:** manual process → controlled automation → full automation for standard cases.

---

## 2. Current Process

```mermaid
flowchart TD
    A["Customer requests upgrade"]
    B["Consultant collects<br/>required information"]
    C["Consultant verifies<br/>the request"]
    D["Consultant prepares<br/>the upgrade package"]
    E["Consultant delivers<br/>the result to the customer"]

    A --> B --> C --> D --> E
```

### Key point

**The consultant performs the whole process manually.**

---

## 3. PoC — Human in the Loop

```mermaid
flowchart TD
    A["Customer requests upgrade"]
    B["Automation determines<br/>required information"]
    C["Automation collects / validates<br/>required information"]
    D["Automation prepares<br/>the upgrade package"]
    E["Consultant reviews<br/>the prepared result"]
    F{"Approved?"}
    G["Result delivered<br/>to the customer"]
    H["Correction / manual handling"]

    A --> B --> C --> D --> E --> F
    F -- Yes --> G
    F -- No --> H
    H --> E
```

### Key point

**Automation performs the repetitive work, while the consultant keeps final control.**

This stage validates whether the process is reliable enough before removing the mandatory human approval step.

---

## 4. Target Process — Full Automation

```mermaid
flowchart TD
    A["Customer requests upgrade"]
    B["Automation determines<br/>required information"]
    C["Automation collects / validates<br/>required information"]
    D["Automation prepares<br/>the upgrade package"]
    E{"Standard case?"}
    F["Automation delivers<br/>the result to the customer"]
    G["Consultant handles<br/>the exception"]

    A --> B --> C --> D --> E
    E -- Yes --> F
    E -- No / Exception --> G
```

### Key point

**Standard cases are handled automatically end to end. Exceptions are routed to a consultant.**

---

## Decision Logic

The PoC is not the final operating model.

Its purpose is to verify that the automated process can reliably prepare the correct result while a consultant remains the final approval gate.

If the PoC confirms sufficient reliability and business value, the process can evolve toward full automation for standard cases, with consultants handling only exceptions.
