# SLA, OLA, and underpinning contract model

## Purpose

Response, restore, and resolution targets, update cadence, clock rules, calendar binding, suppliers, and breach handling.

## Response targets

| Id | Target hours | Clock | Basis |
|---|---|---|---|
| `P1` | 0.1 | Clock hours from registration, running through nights, weekends and holidays. | Ninetieth percentile of time to first human activity over 3 incidents. |
| `P2` | 3.3 | Clock hours from registration, running through nights, weekends and holidays. | Ninetieth percentile of time to first human activity over 599 incidents. |
| `P3` | 3.1 | Clock hours from registration, running through nights, weekends and holidays. | Ninetieth percentile of time to first human activity over 5147 incidents. |
| `P4` | 16.1 | Clock hours from registration, running through nights, weekends and holidays. | Ninetieth percentile of time to first human activity over 20238 incidents. |
| `P5` | 17.5 | Clock hours from registration, running through nights, weekends and holidays. | Ninetieth percentile of time to first human activity over 14007 incidents. |

## Resolution targets

| Id | Target hours | Clock | Basis |
|---|---|---|---|
| `P1` | 127.2 | Clock hours from registration, running through nights, weekends and holidays. | Ninetieth percentile of registration to closure over 3 incidents. Too few records for a distribution, so the figure sits above P2's and is carried as measured rather than corrected. |
| `P2` | 48.5 | Clock hours from registration, running through nights, weekends and holidays. | Ninetieth percentile of registration to closure over 696 incidents. |
| `P3` | 121.5 | Clock hours from registration, running through nights, weekends and holidays. | Ninetieth percentile of registration to closure over 6561 incidents. |
| `P4` | 197.7 | Clock hours from registration, running through nights, weekends and holidays. | Ninetieth percentile of registration to closure over 22181 incidents. |
| `P5` | 296.3 | Clock hours from registration, running through nights, weekends and holidays. | Ninetieth percentile of registration to closure over 16015 incidents. |

## Restore targets

Not defined for this organization: the organization has no such thing.

## Clock rules

1. When an elapsed time is measured against a target, the clock runs in clock hours from registration, the Open Time on the record, and keeps running through nights, weekends and holidays, because every distribution a target is taken from was measured that way.
2. When a target is stated anywhere, it is the ninetieth percentile of the measured distribution for the band. No separately agreed SLA commitments are specified. Only the listed figures are used as targets.
3. When response is measured, it is the first activity on the record later than registration plus one minute, excluding the open, closed, caused-by CI and quality indicator rows.
4. When resolution is measured, it is registration to closure. Resolved and closed coincide within a minute on 0.94 of records, so there is no separate restore clock and no workaround clock.
5. When the update interval is measured, it is the gap between consecutive communication with customer or mail to customer rows on one record, and the cadence per band, carried in the communication model, is its median. No gap was measured for P1, whose 3 incidents never carried two customer communications, so P1 has no cadence row.
6. When activity appears on a record outside the business window, it is attributed to T-AUT-01 and read as machine activity, never as human effort.

## Support calendar binding

1. When a target clock is set against the support calendar, the clock does not pause outside the business window. The window says when a human can act on the record, not when the target counts, because the measured distributions the targets come from ran through every night and weekend.
2. When a record needs a human outside the business window, it waits for the window to open while its clock runs. No human team is reachable outside Monday to Friday 08:00 to 18:00, there is no on-call rota, and a tier-critical service gets no exception.
3. When a national public holiday falls in the window, it is a non-business day for every human team and the branch network alike, and the clock still runs through it.
4. When a record is worked around the clock, the actor is T-AUT-01, the only coverage that runs outside the business window.

## Suppliers

| Id | Name | Contract type | Liaison team | Services provided |
|---|---|---|---|---|
| `V-IBM` | IBM | managed_service | T-VEN-02 | Outsourced application support and maintenance. |
| `V-COGNIZANT` | Cognizant | managed_service | T-VEN-02 | Outsourced application support and maintenance. |
| `V-ORDINA` | Ordina | managed_service | T-VEN-02 | Outsourced application support and maintenance. |
| `V-HW-MAINTENANCE` | Hardware maintenance vendors, unnamed | underpinning_contract | T-VEN-01 | Maintenance and repair of the hardware estate. |

## Ola rules

1. When a record is reassigned between internal groups, the response and resolution clocks are the record's own and run from registration, so a handoff consumes the target rather than restarting it, and the receiving group inherits whatever remains.
2. When a record has been bounced four times, ownership is escalated rather than the record reassigned again, and every reassignment before that carries a documented reason. Two to three teams per incident is normal and no rule treats a reassignment as a failure.
3. When the desk escalates a record, closure travels with the resolver. The desk may not close what it escalated, triage teams may not resolve or close, and the resolving team closes the record.
4. When vendor-eligible work is held by the external supplier desk, it is not returned unresolved to the service desk. Returns are for mis-routed non-vendor work only, with a documented reason.

## Uc rules

1. When a record sits with a supplier, the internal record is kept current, the vendor reference is logged, and the repair is verified before closure. Pending-vendor is maintained, never a place to park a record, and no record closes on a supplier's word alone.
2. When a supplier's reaction or resolution commitment is sought, none is declared for any supplier and no underpinning contract states a per-priority target, so the organization's own measured target applies to the record for as long as the supplier holds it.
3. When a supplier-held record breaches its target or a contract is disputed, the external supplier desk escalates the breach to supplier management and the application vendor liaison escalates the contract dispute, and neither closes the record to stop the clock.

## Breach rule

1. When the elapsed clock hours on a record pass the target for its band, the record is in breach. A breach is a signal to escalate. The thresholds use historical 90th-percentile timings.
2. When a record reaches half, then three quarters, of its target, the assignee is notified at each point, and at breach the assignee and the assignment group manager are notified together.
3. When a breach is imminent and no documented progress is on the record, the holder escalates the record and notifies their manager. Progress means tangible documented steps on the record, and a note that says still investigating does not count.
4. When a target is breached or a breach is anticipated, the customer is informed, and the breach is taken to the service review with the customer.
