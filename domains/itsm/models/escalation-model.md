# Escalation model

## Purpose

Functional, hierarchical, vendor, SLA breach, and major incident escalation.

## Functional escalation

| Id | From team | To team | Trigger |
|---|---|---|---|
| `fe-t-desk-01-t-tri-01` | T-DESK-01 | T-TRI-01 | The knowledge script does not resolve the contact or the first-level target expires, and the true owner is not obvious from the category. Triage decides ownership and has no resolution authority. |
| `fe-t-desk-01-t-tri-02` | T-DESK-01 | T-TRI-02 | The knowledge script does not resolve the contact or the first-level target expires, and the true owner is not obvious from the category. Triage decides ownership and has no resolution authority. |
| `fe-t-desk-01-t-app-01` | T-DESK-01 | T-APP-01 | The category names the owning team, so the record goes straight to it as ordinary routing. The reverse direction is not a route: a resolver returning work to the desk breaks closure travelling with the resolver. |
| `fe-t-desk-01-t-app-02` | T-DESK-01 | T-APP-02 | The category names the owning team, so the record goes straight to it as ordinary routing. The reverse direction is not a route: a resolver returning work to the desk breaks closure travelling with the resolver. |
| `fe-t-desk-01-t-app-03` | T-DESK-01 | T-APP-03 | The category names the owning team, so the record goes straight to it as ordinary routing. The reverse direction is not a route: a resolver returning work to the desk breaks closure travelling with the resolver. |
| `fe-t-desk-01-t-plt-01` | T-DESK-01 | T-PLT-01 | The category names the owning team, so the record goes straight to it as ordinary routing. The reverse direction is not a route: a resolver returning work to the desk breaks closure travelling with the resolver. |
| `fe-t-desk-01-t-euc-01` | T-DESK-01 | T-EUC-01 | The category names the owning team, so the record goes straight to it as ordinary routing. The reverse direction is not a route: a resolver returning work to the desk breaks closure travelling with the resolver. |
| `fe-t-desk-01-t-ven-01` | T-DESK-01 | T-VEN-01 | Vendor-eligible hardware work goes to the external supplier desk. The return direction is for mis-routed non-vendor work only, with a documented reason. |
| `fe-t-desk-03-t-tri-02` | T-DESK-03 | T-TRI-02 | The branch desk sends infrastructure faults and multi-branch patterns to infrastructure triage. The lane runs one way. |
| `fe-t-desk-02-t-tri-02` | T-DESK-02 | T-TRI-02 | A cross-domain incident leaves the workplace niche, pre-papered, to infrastructure triage. |
| `fe-t-tri-01-t-app-01` | T-TRI-01 | T-APP-01 | The dispatcher determines the true owning team and reroutes with a documented reason. Reassignment is ordinary work, and ownership escalates rather than bouncing again at bounce four. |
| `fe-t-tri-01-t-app-02` | T-TRI-01 | T-APP-02 | The dispatcher determines the true owning team and reroutes with a documented reason. Reassignment is ordinary work, and ownership escalates rather than bouncing again at bounce four. |
| `fe-t-tri-01-t-app-03` | T-TRI-01 | T-APP-03 | The dispatcher determines the true owning team and reroutes with a documented reason. Reassignment is ordinary work, and ownership escalates rather than bouncing again at bounce four. |
| `fe-t-tri-01-t-plt-01` | T-TRI-01 | T-PLT-01 | The dispatcher determines the true owning team and reroutes with a documented reason. Reassignment is ordinary work, and ownership escalates rather than bouncing again at bounce four. |
| `fe-t-tri-01-t-euc-01` | T-TRI-01 | T-EUC-01 | The dispatcher determines the true owning team and reroutes with a documented reason. Reassignment is ordinary work, and ownership escalates rather than bouncing again at bounce four. |
| `fe-t-tri-01-t-tri-02` | T-TRI-01 | T-TRI-02 | An infrastructure-flavoured ticket that landed in application triage is rerouted to infrastructure triage with its reason. |
| `fe-t-tri-02-t-plt-01` | T-TRI-02 | T-PLT-01 | The dispatcher determines the true owning team and reroutes with a documented reason. Reassignment is ordinary work, and ownership escalates rather than bouncing again at bounce four. |
| `fe-t-tri-02-t-plt-02` | T-TRI-02 | T-PLT-02 | The dispatcher determines the true owning team and reroutes with a documented reason. Reassignment is ordinary work, and ownership escalates rather than bouncing again at bounce four. |
| `fe-t-tri-02-t-euc-01` | T-TRI-02 | T-EUC-01 | The dispatcher determines the true owning team and reroutes with a documented reason. Reassignment is ordinary work, and ownership escalates rather than bouncing again at bounce four. |
| `fe-t-tri-02-t-net-01` | T-TRI-02 | T-NET-01 | The dispatcher determines the true owning team and reroutes with a documented reason. Reassignment is ordinary work, and ownership escalates rather than bouncing again at bounce four. |
| `fe-t-tri-02-t-ven-01` | T-TRI-02 | T-VEN-01 | Hardware replacement or a carrier circuit under a maintenance contract, engaged through the external supplier desk. |
| `fe-t-tri-02-t-desk-03` | T-TRI-02 | T-DESK-03 | A return only: mis-routed branch work goes back with a documented reason, never resolution work. |
| `fe-t-app-01-t-ven-02` | T-APP-01 | T-VEN-02 | The fault sits in vendor-owned code, and the application vendor liaison raises it with the supplier and keeps the record current. |
| `fe-t-app-02-t-ven-02` | T-APP-02 | T-VEN-02 | The fault sits in vendor-owned code, and the application vendor liaison raises it with the supplier and keeps the record current. |
| `fe-t-app-03-t-ven-02` | T-APP-03 | T-VEN-02 | The fault sits in vendor-owned code, and the application vendor liaison raises it with the supplier and keeps the record current. |
| `fe-t-plt-01-t-ven-02` | T-PLT-01 | T-VEN-02 | The fault sits in vendor-owned code, and the application vendor liaison raises it with the supplier and keeps the record current. |
| `fe-t-plt-02-t-ven-01` | T-PLT-02 | T-VEN-01 | Hardware replacement or a carrier circuit under a maintenance contract, engaged through the external supplier desk. |
| `fe-t-euc-01-t-ven-01` | T-EUC-01 | T-VEN-01 | Hardware replacement or a carrier circuit under a maintenance contract, engaged through the external supplier desk. |
| `fe-t-net-01-t-ven-01` | T-NET-01 | T-VEN-01 | Hardware replacement or a carrier circuit under a maintenance contract, engaged through the external supplier desk. |
| `fe-t-app-01-t-com-01` | T-APP-01 | T-COM-01 | A long-running or sensitive case needs user-facing communication grounded in the resolver's worknotes. |
| `fe-t-app-02-t-com-01` | T-APP-02 | T-COM-01 | A long-running or sensitive case needs user-facing communication grounded in the resolver's worknotes. |
| `fe-t-app-03-t-com-01` | T-APP-03 | T-COM-01 | A long-running or sensitive case needs user-facing communication grounded in the resolver's worknotes. |
| `fe-t-com-01-t-app-01` | T-COM-01 | T-APP-01 | A technical question the communicator may not answer goes to the owning resolver. |
| `fe-t-com-01-t-app-02` | T-COM-01 | T-APP-02 | A technical question the communicator may not answer goes to the owning resolver. |
| `fe-t-com-01-t-app-03` | T-COM-01 | T-APP-03 | A technical question the communicator may not answer goes to the owning resolver. |
| `fe-t-com-01-t-inc-01` | T-COM-01 | T-INC-01 | User impact the record understates, raised as a priority review with evidence. |
| `fe-t-aut-01-t-desk-01` | T-AUT-01 | T-DESK-01 | An event-born ticket the automation actor opened is picked up by a person at the next opening. |
| `fe-t-ven-01-t-desk-01` | T-VEN-01 | T-DESK-01 | Mis-routed non-vendor work returns to the desk with a documented reason. Vendor-eligible work never returns unresolved. |

## Hierarchical escalation

| Id | Trigger | To position |
|---|---|---|
| `he-1` | An agent or a caller needs an authority the agent lacks, a priority override beyond the matrix is wanted, or the contact falls beyond the knowledge script. | pos-shift-lead |
| `he-2` | Sustained overload or a systemic queue failure through a shift, or a bridge ask the desk cannot staff. | pos-incident-mgr |
| `he-3` | An ownership dispute the dispatcher cannot settle, at bounce four at the latest, documented by the dispatcher and arbitrated by the incident manager. | pos-incident-mgr |
| `he-4` | A priority override beyond the matrix, requested with evidence by the desk, the shift lead or the communicator, decided by the practice office that owns the matrix. | pos-incident-mgr |
| `he-5` | A pattern that crosses the major threshold, or a multi-branch pattern from the branch desk, raised as a candidate for the incident manager's decision. | pos-incident-mgr |
| `he-6` | An emergency change needed during a major, requested through the incident manager, or a change a resolver or the problem manager still believes necessary after refusal, or an implementation overrun. | pos-change-mgr |
| `he-7` | A cross-domain root cause a resolver cannot own, or a recurring rule failure in the robots. | pos-problem-mgr |
| `he-8` | A robot misfire with service impact, or a failed deployment with live impact. | pos-incident-mgr |
| `he-9` | A vendor deadline breached or a contract disputed on supplier-held work, escalated by the coordinator through supplier management. | pos-supplier |

## Vendor escalation

| Id | Supplier | Route | Trigger |
|---|---|---|---|
| `ve-v-ibm` | V-IBM | The owning application team or the third-line platform team hands the record to the application vendor liaison, which raises the supplier ticket, logs the vendor reference, tracks the fix into the change pipeline, and keeps the internal record current until the repair is verified. | The fault sits in code this supplier maintains under its managed service. |
| `ve-v-cognizant` | V-COGNIZANT | The owning application team or the third-line platform team hands the record to the application vendor liaison, which raises the supplier ticket, logs the vendor reference, tracks the fix into the change pipeline, and keeps the internal record current until the repair is verified. | The fault sits in code this supplier maintains under its managed service. |
| `ve-v-ordina` | V-ORDINA | The owning application team or the third-line platform team hands the record to the application vendor liaison, which raises the supplier ticket, logs the vendor reference, tracks the fix into the change pipeline, and keeps the internal record current until the repair is verified. | The fault sits in code this supplier maintains under its managed service. |
| `ve-v-hw-maintenance` | V-HW-MAINTENANCE | The desk, infrastructure triage or the platform, workplace and network teams hand the record to the external supplier desk, which engages the maintainer, quarantines the record in pending-vendor while the work is outside, chases at deadline, and verifies the repair before closure. | Hardware replacement or a carrier circuit under a maintenance contract, once the fault is established as the supplier's to repair. |

## Sla breach escalation

1. When the ladder is read, it takes two inputs, the record's derived priority and its elapsed clock hours from registration, and the targets it reads them against are the measured ninetieth percentiles per band. Duration and severity are the only triggers, and both are on the record.
2. When a target is at risk or passed, the holder escalates up its own line and never sideways: a desk agent to the shift lead, the shift lead and any resolver or dispatcher to the incident manager, and a supplier-held record through supplier management. Bouncing the record to another queue is not an escalation, and the practice office watches breaches across every queue as part of process health.
3. When the escalating role is itself the next rung, it records the decision and its rationale on the record and the rung above applies: the shift lead on its own overload goes to the incident manager, and the incident manager on a conflict with another practice owner goes upward from both, since no service management office is declared.
4. When the next rung cannot be reached, the record waits at its derived priority for the next opening of the business window with the escalation written on it, because no human team is reachable outside Monday to Friday 08:00 to 18:00 and nobody acts on another rung's authority. The desk's own escalations go upward unchanged, never resolved in place.
5. The incident manager's decision is final for an incident and is recorded with its rationale. A dispute across practices is escalated above both owners; the destination above those owners is not specified.
6. When a supplier-held record passes its target, the coordinator escalates the breach through supplier management, the internal record stays current with the vendor reference on it, and the record never closes on the supplier's word alone.

## Major incident escalation

1. When a pattern crosses the major threshold, the dispatcher, the branch desk or whoever holds the record raises a candidate to the incident manager, who alone declares, and the candidate is worked at its derived priority meanwhile.
2. When a major is declared, command convenes any team onto the bridge, the desk sends its shift lead with the intake picture, the owning teams send their engineers, the communicator carries the cadence command sets, and an ask the desk cannot staff goes back to the bridge chair.
3. When a major needs an emergency change, the request goes through the incident manager to the change manager, who grants or refuses the lane with the incident manager consulted, and a resourcing conflict the bridge cannot resolve goes to department leads, who sit outside the roster.
4. When a supplier holds a record inside a major, the supplier coordinator keeps the incident manager informed for the bridge's visibility and the record current, and the major's downgrade does not close a record the supplier still holds.
