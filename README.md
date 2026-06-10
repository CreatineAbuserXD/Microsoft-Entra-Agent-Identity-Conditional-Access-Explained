# Microsoft-Entra-Agent-Identity-Conditional-Access-Explained

```md
![Conditional Access for Agents](https://github.com/CreatineAbuserXD/Microsoft-Entra-Agent-Identity-Conditional-Access-Explained/blob/main/AgenticEntraID.png)
```

This repository explains how Microsoft Entra Conditional Access applies to Agent Identities, Agent Users, and delegated On-Behalf-Of agent flows.

```
Agent Identity is both an Entra object and a Conditional Access assignment type.
The important security question is not whether an Agent Identity exists in the flow,
but whether it is the evaluated subject for the resource access.
```


```mermaid
flowchart TD
    A["Resource access request"] --> B{"Who is the token subject?"}

    B -->|"Human user"| C["Delegated / OBO agent flow"]
    C --> C1["Agent acts on behalf of user"]
    C1 --> C2["Scope Conditional Access to Users & Groups"]

    B -->|"Agent Identity"| D["Autonomous / app-like agent flow"]
    D --> D1["Agent accesses resource with own identity"]
    D1 --> D2["Scope Conditional Access to Agent Identities"]

    B -->|"Agent User Account"| E["Digital worker / AI teammate"]
    E --> E1["Agent has user-like account"]
    E1 --> E2["Scope Conditional Access to Agent Users (Preview)"]
```







## SOURCES:
- https://learn.microsoft.com/en-us/entra/identity/conditional-access/agent-id?utm_source=chatgpt.com
- https://learn.microsoft.com/en-us/entra/identity/conditional-access/policy-autonomous-agents?tabs=use-custom-security-attributes
- https://learn.microsoft.com/en-us/entra/agent-id/agent-autonomous-app-oauth-flow
- https://learn.microsoft.com/en-us/entra/agent-id/what-are-agent-identities?utm_source=chatgpt.com
- https://learn.microsoft.com/en-us/entra/identity/conditional-access/policy-autonomous-agents?utm_source=chatgpt.com&tabs=use-custom-security-attributes
