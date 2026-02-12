# ADR \<number>: \<Short Title>

## Status
Proposed | Accepted | Superseded by ADR \<number>

## Context
Describe the situation, constraints, and forces that led to this decision.
Include:
- the problem being solved
- relevant technical, organizational, or operational constraints
- assumptions and tradeoffs that shaped the decision space

## Decision
State the decision clearly and concisely.
This should be a single, unambiguous statement of what was chosen.

## Options Considered
### Option 1: \<Name>
- Summary of the approach
- Pros
- Cons

### Option 2: \<Name>
- Summary of the approach
- Pros
- Cons

### Option 3: \<Name> (optional)
- Summary of the approach
- Pros
- Cons

## Rationale
Explain *why* this option was chosen over the others.
Highlight:
- alignment with long‑term strategy
- risk reduction
- operational impact
- cost/complexity considerations
- stakeholder alignment

## Consequences
Describe the impact of this decision, including:
- positive outcomes
- new constraints introduced
- follow‑up work required
- risks or debt created
- how this decision will be revisited or superseded

## Notes
Any additional context, references, diagrams, or links.

## Example
---
# ADR 014: Standardizing AMI Governance Through Centralized Patterns

## Status
Accepted

## Context
Our AMI governance process was fragmented across 500+ AWS accounts, resulting in inconsistent patching, unclear ownership, and recurring audit findings. Multiple teams maintained their own AMI pipelines with varying levels of automation, documentation, and security controls. This created operational risk, slowed incident response, and made it difficult to enforce baseline compliance requirements.

We needed a unified approach that reduced variance, improved audit readiness, and enabled platform‑level automation without blocking team autonomy.

## Decision
Adopt a centralized, standardized AMI pattern with automated validation and distribution across all AWS accounts.

## Options Considered

### Option 1: Maintain decentralized AMI pipelines
**Pros**
- Maximum team autonomy  
- No migration effort  

**Cons**
- High variance in security posture  
- Difficult to audit  
- Repeated operational issues  
- No clear ownership model  

### Option 2: Fully centralized AMI build service (single pipeline)
**Pros**
- Strongest consistency  
- Simplified audit and compliance  
- Clear ownership  

**Cons**
- Bottleneck risk  
- Limited flexibility for specialized workloads  
- Requires significant platform investment  

### Option 3: Standardized AMI pattern with distributed adoption (chosen)
**Pros**
- Strong baseline consistency  
- Teams retain autonomy for extensions  
- Scales across 500+ accounts  
- Enables automated validation and distribution  

**Cons**
- Requires migration effort  
- Needs ongoing governance and communication  

## Rationale
Option 3 provided the best balance between consistency, autonomy, and long‑term maintainability. It reduced audit risk, enabled automated compliance checks, and aligned with our modernization roadmap without creating a central bottleneck. It also allowed teams to extend the base AMI for specialized workloads while maintaining a secure, validated foundation.

## Consequences
**Positive**
- Improved audit readiness  
- Reduced operational risk  
- Clear ownership and lifecycle management  
- Automated distribution and validation  

**Negative / Follow‑Up**
- Migration effort required across teams  
- Need for ongoing communication and adoption support  
- Requires periodic review to ensure alignment with evolving security standards  

## Notes
This ADR will be revisited annually or when major changes occur in AWS AMI lifecycle tooling or organizational compliance requirements.