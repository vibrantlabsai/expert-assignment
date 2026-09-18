# Support calendar model

## Purpose

Coverage windows, business hours, regional holidays, locations, and after-hours rules.

## Coverage windows

| Id | Name | Days | Hours | Applies to |
|---|---|---|---|---|
| `cal-business` | Business hours | Monday, Tuesday, Wednesday, Thursday, Friday | 08:00 to 18:00 Europe/Amsterdam | Every human team, 19 of the 20 on the roster. |
| `cal-around-the-clock` | Around the clock | Every day | 00:00 to 24:00 | The automation actor T-AUT-01 alone. No human work is scheduled in this window. |

## Business hours

| Id | Name | Start | End | Timezone |
|---|---|---|---|---|
| `bh-standard` | Standard working window | 08:00 | 18:00 | Europe/Amsterdam |

## Region holidays

| Id | Date | Name | Region |
|---|---|---|---|
| `2013-12-25` | 2013-12-25 | Eerste Kerstdag | Netherlands, national |
| `2013-12-26` | 2013-12-26 | Tweede Kerstdag | Netherlands, national |
| `2014-01-01` | 2014-01-01 | Nieuwjaarsdag | Netherlands, national |

## Locations

| Id | Name | Type |
|---|---|---|
| `LOC-HQ` | Utrecht headquarters | headquarters |
| `LOC-NL-BRANCHES` | Local member bank branches | branch |
| `LOC-VENDOR` | Outsourced application support sites | supplier_site |

## After hours rules

1. When a record needs human work outside the business window, it waits for the window to open. There is no on-call rota and no human team is reachable outside it, so a rule that assumes otherwise is unimplementable.
2. When activity appears on a record outside the business window, it is the automation actor T-AUT-01 and is attributed to it, never read as human effort.
3. When a rule states an elapsed time, it names whether the clock runs in business hours or in clock hours, because the two diverge across every night and weekend in this window.
