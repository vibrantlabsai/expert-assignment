# Classification model

## Purpose

How the reach of a failure and its time sensitivity are graded, the grid that derives a priority from the two, the priority levels themselves, and who may override a derived priority.

## Impact levels

| Level | Label | Criteria | User reach | Service effect | Business effect |
|---|---|---|---|---|---|
| `impact-1` | Extensive or widespread | The incident reaches the whole organization, or it reaches a service in the critical tier. | The entire organization or the branch network. | A critical-tier service is impacted, whose loss stops customer money moving or the branch network working. | Counted in missed windows rather than inconvenience. |
| `impact-2` | Significant or large | The incident reaches multiple departments, teams or locations. | Multiple departments or locations. | A standard-tier service is degraded across more than one group of users. | Staff or customer work degraded across several units without stopping settlement. |
| `impact-3` | Moderate or limited | The incident reaches one user or a few users. | One user, or a few. | No service-wide effect. | Local to the users affected. |

## Urgency levels

| Level | Label | Criteria | Time sensitivity | Degradation tolerance | Delay tolerance |
|---|---|---|---|---|---|
| `urgency-1` | Critical | The entire service is affected and cannot perform its functions. | Immediate. Every hour of delay is an hour the service does not exist. | None. The service is not degraded, it is absent. | None. |
| `urgency-2` | High | A user cannot do their work. | Same working day. | Low. The user is blocked, not slowed. | Hours, not days. |
| `urgency-3` | Medium | Work is not impacted or only moderately impacted, or a workaround exists. | Within the published business window, across days if needed. | Moderate. The user keeps working. | Days. A workaround holds. |

## Priority levels

| Level | Label | Criteria | Response order | Business meaning |
|---|---|---|---|---|
| `P1` | P1 | Derived from the impact by urgency grid, band 1 of four. | 1 | Work stops for the organization or a critical service is down with no way to work. Rare by declaration and by measurement: 3 incidents in the six-month window. |
| `P2` | P2 | Derived from the impact by urgency grid, band 2 of four. | 2 | A critical service degraded, or a wide outage that leaves users blocked. 696 incidents in the window. |
| `P3` | P3 | Derived from the impact by urgency grid, band 3 of four. | 3 | Users blocked or a service moderately impacted across a group. 6561 incidents in the window. |
| `P4` | P4 | Derived from the impact by urgency grid, band 4 of four. | 4 | Limited reach, a workaround exists or work continues. The largest derived band at 22181 incidents. |
| `P5` | P5 | Not derived by the three-code grid. Used when impact and urgency both have code five, the lowest code on each. | 5 | Below the lowest cell of the grid: no user prevented from working and no time pressure. Historical records include 16015 records in this band; roughly half are requests for information logged as incidents. |

## Derivation rule

1. When an incident is registered, the desk agent estimates impact and urgency and priority is read from the grid. It is derived, never typed, and a resolution deadline follows from it.
2. When the bands are counted, there are five and priority one traffic is rare. Priority one incidents are expected to be rare.
3. When impact and urgency both have code five, the incident is P5. This band sits below the displayed three-code matrix; the matrix is not extended or rescaled to include it.

## Matrix

|  | urgency-1 | urgency-2 | urgency-3 |
|---|---|---|---|
| **impact-1** | **P1** | **P2** | **P3** |
| **impact-2** | **P2** | **P3** | **P4** |
| **impact-3** | **P3** | **P4** | **P4** |

## Override rule

| Id | Decision | Actor | May | Must escalate |
|---|---|---|---|---|
| `ov-1` | Overriding the priority derived for any incident | T-INC-01 | override the derived priority on any incident, as the practice office that owns the matrix, and record why on the record |  |
| `ov-2` | A priority the grid does not yield | T-DESK-01 | apply the grid and request a review with evidence, never set a band the grid does not derive | any priority override beyond the matrix, upward to the incident practice office unchanged |
