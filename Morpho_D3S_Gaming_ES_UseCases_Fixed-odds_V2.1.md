---
country: Spain
document_name: Fixed-odds Records V2.1 requirements
source_file: Morpho_D3S_Gaming_ES_UseCases_Fixed-odds_V2.1.pdf
extracted_date: 2026-04-30
jurisdiction: Spain
---

# Fixed-odds Records

## V2.1 requirements

### Month #1

#### Market opening

Player 1  
Player 2  
Player 3  
Gaming System  
SAFE

G2:  
“Chelsea v Liverpool  
08/14/2011 15:00 BST”

### Month #2

### Month #3

Monthly report, two events appear in the FixedOddsRecord:

- EventCatalog (CEV)

addFOR

G1:  
“Newcastle v  
Arsenal  
08/13/2011  
15:00 BST”

addFOR

addFOR

### Month

### Day

#### Bets in progress

Player 1  
Player 2  
Player 3  
Gaming System  
SAFE

Bet 3€ on G1  
« home wins »

Bet 10€ on G2 « home wins »

Bet 4€ on G2 « away wins »

Bet 5€ on G1 « home wins »

Daily finance reports (players information in CJD+CJT):

- PlayerAccountDetails (CJD)
- PlayerAccountTotal (CJT)

addFIR

Monthly finance reports (players information in CJD+CJT, live bets in BOT):

- PlayerAccountDetails (CJD)
- PlayerAccountTotal (CJT)
- JackpotTotal (BOT)

Monthly FixedOddRecord, two events appear in the FixedOddsRecord:

- EventCatalog (CEV)

addFIR + addFOR

### Day

Bet 3€ on G2  
« draw »

Bet 4€ on G1 « draw » and G2 « draw »  
Combined bets

addFIR

G1:  
“Newcastle v Arsenal  
08/13/2011 15:00 BST”

G2:  
“Chelsea v Liverpool  
08/14/2011 15:00 BST”

### Month

### Day

### Day

#### Market settlement

Player 1  
Player 2  
Player 3  
Gaming System

addFOR

2 FixedOddsRecord in near real time:

- GameRecordDetails (JUD)
- BettingSummary (JUT)

addFOR

Daily finance reports (players information in CJD+CJT).

- PlayerAccountDetails (CJD)
- PlayerAccountTotal (CJT)

addFIR

addFIR

Monthly finance reports (players information in CJD+CJT, live bets updated in BOT).

- PlayerAccountDetails (CJD)
- PlayerAccountTotal (CJT)
- JackpotTotal (BOT)

Monthly FixedOddRecord:

- EventCatalog (CEV)

addFIR + addFOR

Newcastle 1 v Arsenal 0  
Chelsea 2 v Liverpool 2

SAFE

### Month

#### Market resettlement

Player 1  
Player 2  
Player 3  
Gaming System

### Day

Fixed odds corrected

addFIR

Daily finance reports (the winningsAdjustment attribute reflects the resettlement):

- PlayerAccountDetails (CJD)
- PlayerAccountTotal (CJT)

Monthly finance reports (the winningsAdjustment attribute reflect the resettlement):

- PlayerAccountDetails (CJD)
- PlayerAccountTotal (CJT)

Monthly FixedOddRecord:

- BetAdjustment (JUA)

addFIR + addFOR

SAFE

### Month

### Day

#### Market cancellation

Player 1  
Player 2  
Player 3  
Gaming System  
SAFE

replaceFOR

addFIR

2 FixedOddsRecord in near real time (attribute canceled set and event set in the events attribute):

- GameRecordDetails (JUD)
- BettingSummary (JUT)

addFIR + addFOR

Monthly finance reports (players information updated in CJD+CJT, live bets updated in BOT):

- PlayerAccountDetails (CJD)
- PlayerAccountTotal (CJT)
- JackpotTotal (BOT)

Monthly FixedOddRecord:

- EventCatalog (CEV)

Daily finance reports (players information updated in CJD+CJT):

- PlayerAccountDetails (CJD)
- PlayerAccountTotal (CJT)

Newcastle v  
Arsenal canceled