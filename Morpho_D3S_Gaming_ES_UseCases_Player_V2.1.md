---
country: Spain
document_name: Player Records V2.1 requirements
source_file: Morpho_D3S_Gaming_ES_UseCases_Player_V2.1.pdf
extracted_date: 2026-04-30
jurisdiction: Spain
---

# Player Records

## V2.1 requirements

### Account creation

Month

Day of registration

Account creation

Player

Operator

Platform

Register

Daily report, this player appears in 2 PlayerRecord:

- PlayerRegistrationDetails (RUD)
- PlayerRegistrationTotal (RUT)

addPLR

addPLR

Daily report, this player appears in 2 PlayerRecord with SVDI information set:

- PlayerRegistrationDetails (RUD)
- PlayerRegistrationTotal (RUT)

Regulator

SAFE

Day of SVDI check

SVDI check

As soon as possible

NIE/DNI requested

addPLR

All registered players appear in the monthly PlayerRecord:

- PlayerRegistrationDetails (RUD)
- PlayerRegistrationTotal (RUT)

### Transfer to lobby

Month

Day

Transfer to lobby

Transfer

addPLR

Monthly report, players appear in 2 PlayerRecord:

- NetworkPlayerRegistration (RUR)
- PlayerRegistrationTotal (RUT)

SAFE

Operator

Platform

Network operator

Platform

### Account suspension

Month

Day

Player

Operator

Platform

Player suspended

Daily report, this player appears in 2 PlayerRecord:

- PlayerRegistrationDetails (RUD)
- PlayerRegistrationTotal (RUT)

addPLR

Suspended players are appearing in all monthly reports. The cnjStatus field indicates that the player is suspended.

addPLR

Monthly report, this player appears in 2 PlayerRecord:

- PlayerRegistrationDetails (RUD)
- PlayerRegistrationTotal (RUT)

SAFE

### Account closure (removed from the database)

Month

Day

Player

Operator

Platform

Close

Daily report, this player appears in 2 PlayerRecord:

- PlayerRegistrationDetails (RUD)
- PlayerRegistrationTotal (RUT)

addPLR

addPLR

Monthly report, this player appears in 2 PlayerRecord:

- PlayerRegistrationDetails (RUD)
- PlayerRegistrationTotal (RUT)

Closed players accounts are appearing in the monthly PlayerRegistrationDetails report of the month’s closure only.

SAFE

### Personal data updates

Month

Day

Player

Operator

Platform

Personal data updates

Daily report, this player appears in 2 PlayerRecord:

- PlayerRegistrationDetails (RUD)
- PlayerRegistrationTotal (RUT)

addPLR

The player updates appears in the daily report of the day of his updates only.
All players are appearing in all monthly reports then. Last updates are included in the report.

addPLR

Monthly report, this player appears in 2 PlayerRecord:

- PlayerRegistrationDetails (RUD)
- PlayerRegistrationTotal (RUT)

SAFE