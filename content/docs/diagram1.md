---
title: Health Credential
---

# Issuing Health Status Credential

{{< mermaid >}}
sequenceDiagram
    participant C as Citizen
    participant P as Practitioner

    C ->> C: Self issue derived credential
    C ->> P: Send credential
    P ->> P: Sign credential
    P ->> C: Send credential 

{{< /mermaid >}}
