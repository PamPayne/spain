---
country: Spain
document_name: "D3S Developer's Guide Web Services Integration"
source_file: "Morpho_D3S_JEL_DeveloperGuide_WSES_v3.5.8en.pdf"
extracted_date: "2026-04-30"
jurisdiction: "Spain"
---

# D3S Developer's Guide Web Services Integration

**IDEMIA RESTRICTED**

D3S Gaming Safe - Spain  
DGOJ model version 2.11  
Ref. : Morpho_D3S_JEL_DeveloperGuide_WSES  
Version 3.5.8 – 2018/01/11

**IDEMIA RESTRICTED**

D3S Developer's Guide, SAFE Integration Guide – Datamodel Version 2.11  
Ref.: Morpho_D3S_JEL_DeveloperGuide_WSES – version 3.5.8 2/90  
Communication, reproduction or use prohibited without prior authorization of Morpho

**Reference:**  
Morpho_D3S_JEL_DeveloperGuide_WSES

**Version:**  
3.5.8

**Latest update:**  
2018/01/11

**Confidentiality level:**  
RESTRICTED

**Distribution**  
Addresses Diffusion scope

## Update tables of the document

| Version N° | State | Date | Author | Update scope |
|---|---|---|---|---|
| 1.0 | T | 07/09/11 | Dictao | First release with FixedOdds, Player and Finance services |
| 1.1 | T | 16/09/11 | Dictao | Global update, Casino/PVP/Poker/Poolgame services add |
| 1.2 | T | 30/09/11 | Dictao | Update |
| 1.3 | T | 10/10/11 | Dictao | Update according to DGOJ Modelo v0.3 |
| 1.4 | T | 20/10/11 | Dictao | Fixed field/type name and description. Added JUD record. Added RAW API. |
| 1.5 | T | 25/10/11 | Dictao | Updated according to Modelo v0.4. |
| 1.6 | T | 04/11/11 | Dictao | Updated according to Modelo v0.5. |
| 1.7 | T | 28/11/11 | Dictao | Updated according to Modelo v1.0 |
| 1.8 | T | 20/06/12 | Dictao | Field description precisions |
| 1.9 | T | 30/07/12 | Dictao | Precisions and corrections |
| 2.0 | T | 05/06/12 | Dictao | Precisions on return values and idempotence |
| 2.1 | T | 03/12/13 | Dictao | Correction on subrecordTotal rules |
| 2.2 | V | 09/04/14 | Dictao | Precisions about the SMS cost breakdown. Bingo variants have been relaxed |
| 3.0 | T | 29/08/14 | Dictao | Precisions about the contributions to and winnings from jackpots. Update to reflects the changes of the DRAFT version of the datamodel version 2 |
| 3.1 | V | 31/10/14 | Dictao | Updates to reflects the changes of the final published version of the datamodel version 2 |
| 3.2 | V | 20/01/15 | Dictao | Update passport example, table p 16. All breakdowns are optional if the total is “0”. Calculation of the GGR. Handling of version 2.1 of the datamodel |
| 3.2.1 | V | 16/02/15 | Dictao | Uptable of the event table: OPT and ORT are only required on a monthly basis. Suppression of unused WSDL URLs |
| 3.3 | V | 19/03/15 | Dictao | When there is nothing relevant to daily record, there are no “player” fields. In the SessionTotal record, the “placementLimit” field description has been updated. Previous color highlights removed |
| 3.4 | V | 10/04/15 | Morpho | Clarifications following feedback from the DGOJ on the following fields: - “bonus” - “commission” - “GGR” - “placementLimit” - “amount” (all amount fields) |
| 3.5 | V | 08/06/15 | Morpho | Adding “period” field to cancellation records. Correction of the description of the records that may or may not be split in subrecords. RUD, RUR, RUG, CJD, JUD, CEV, JUA may be split |
| 3.5.1 | V | 23/09/15 | Morpho | Support of the v2.2 model. P 29 and 30, precision about the nature of the date used in RecordBase and RecordRef. P 36 CEV, correction of the type for Sports “D” instead of “S” P 39, the “outcomeDate” field was not indicated as mandatory. P 40, precisions about the eventID field of the JUA records. P 49, the “sessionVariant” field may not be an empty string, but the field is optional. RUD and CJD records: only provide the playerID of your platform (multiple playerID are not allowed even if the player participated in network games) |
| 3.5.2 | V | 05/10/15 | Morpho | Support of the v2.4 model. P 27: new sportCode 67 and 68 have been added. P 39: description of the correct usage of “Simple”, “Multiple” & “Complex” bet types. |
| 3.5.3 | V | 29/10/15 | Morpho | RUD: provide the playerID on your platform and the ones on the on the network operators’s platform if the player participates in network games. P 60 : RUD “document” is a mandatory field for non residents |
| 3.5.4 | V | 06/01/16 | Morpho | Support of the v2.5 model : P 27, 38: new sportCode 998 has been added. Support of the v2.7 model : P 26, 37: new sportCode 11 has been added. P 28: new gameType values only to be used by SELAE PDM, PHM, PLN, PLP, PEU, PBL, PGP, PLT, OLN, OLP, OEU, OBL , OGP, OLT have been added. P 27: new countryCode AN has been added for the Netherlands Antilles. |
| 3.5.5 | V | 23/02/16 | Morpho | P 35, 40 : all the events referenced in a JU record have to be referenced in the CEV record of that month or in a previous CEV record. Replacement : only previously submitted records may be replaced |
| 3.5.6 | V | 29/06/16 | Morpho | Support of the v2.6 model : P 27, 39: sportCode 69, 70, 71 have been added. P 28 : add “fixed terminal” as payment method type. P 26, 38 : Changing the use of sportCode 28 that should be used for the “freestyle wrestling” only |
| 3.5.7 | V | 08/11/16 | Morpho | Support of the v2.10 model : P 27, 39: sportCode 72, 73 have been added |
| 3.5.9 | V | 11/01/18 | Morpho | Support of the v2.11 model : P 40, 45, 47, 50, 52, 55, 58: Report games with International liquidity have been added |

1  
T: working document; V: Validated

**IDEMIA RESTRICTED**

D3S Developer's Guide, SAFE Integration Guide – Datamodel Version 2.11  
Ref.: Morpho_D3S_JEL_DeveloperGuide_WSES – version 3.5.8 4/90  
Communication, reproduction or use prohibited without prior authorization of Morpho

## CONTENTS

- CONTENTS .................................................................................................................................................. 4
- 1. INTRODUCTION ....................................................................................................................................... 8
  - 1.1 Special note for Spain ......................................................................................................................... 8
- 2. PRINCIPLES ............................................................................................................................................ 9
  - 2.1 Architecture......................................................................................................................................... 9
  - 2.2 Environments ...................................................................................................................................... 9
  - 2.3 Web Service connection ..................................................................................................................... 9
  - 2.4 WSDL convention ............................................................................................................................. 10
    - 2.4.1 WSDL definition ............................................................................................................................. 10
    - 2.4.2 WSDL example .............................................................................................................................. 10
  - 2.5 XSD convention ................................................................................................................................ 10
    - 2.5.1 XSD definitions .............................................................................................................................. 10
    - 2.5.2 XSD example ................................................................................................................................. 11
  - 2.6 Exception management .................................................................................................................... 11
    - 2.6.1 UserFaultException........................................................................................................................ 11
    - 2.6.2 SystemFaultException ................................................................................................................... 11
  - 2.7 Records passed as a list in all methods ............................................................................................ 12
  - 2.8 Return value ..................................................................................................................................... 12
  - 2.9 Idempotence ..................................................................................................................................... 12
    - 2.9.1 Principles ....................................................................................................................................... 12
    - 2.9.2 Guidelines ...................................................................................................................................... 13
  - 2.10 Record reference ............................................................................................................................ 13
- 3. WEB SERVICES DOCUMENTATION ......................................................................................................... 15
  - 3.1 Web Services Overview .................................................................................................................... 15
- Please make sure to only use the WSDL included in the SDK ................................................................... 15
  - 3.2 Records and Events.......................................................................................................................... 15
  - 3.3 FixedOdds Service............................................................................................................................ 18
    - 3.3.1 Add a bet description ..................................................................................................................... 18
    - 3.3.2 Replace a game instance .............................................................................................................. 18
    - 3.3.3 Cancel a game instance ................................................................................................................ 18
  - 3.4 Casino Service.................................................................................................................................. 19
    - 3.4.1 Add a game instance ..................................................................................................................... 19
    - 3.4.2 Replace a game instance .............................................................................................................. 19
    - 3.4.3 Cancel a game instance ................................................................................................................ 19
  - 3.5 Player-Versus-Player (PVP) Service ................................................................................................ 19
    - 3.5.1 Add a game instance ..................................................................................................................... 19
    - 3.5.2 Replace a game instance .............................................................................................................. 20
    - 3.5.3 Cancel a game instance ................................................................................................................ 20
  - 3.6 Poker Cash Game Service ............................................................................................................... 20
    - 3.6.1 Add a game instance ..................................................................................................................... 20
    - 3.6.2 Replace a game instance .............................................................................................................. 20
    - 3.6.3 Cancel a game instance ................................................................................................................ 21
  - 3.7 Poker Tournament Service ............................................................................................................... 21
    - 3.7.1 Add a game instance ..................................................................................................................... 21
    - 3.7.2 Replace a game instance .............................................................................................................. 21
    - 3.7.3 Cancel a game instance ................................................................................................................ 22
  - 3.8 Player Registration Service............................................................................................................... 22
    - 3.8.1 Add an new event about player information ................................................................................... 22
    - 3.8.2 Replace an existing event about player information ...................................................................... 22
    - 3.8.3 Cancel a player event .................................................................................................................... 22
  - 3.9 Finance Service ................................................................................................................................ 23
    - 3.9.1 Add an new event about finance .................................................................................................... 23
    - 3.9.2 Replace an existing event about finance ....................................................................................... 23
    - 3.9.3 Cancel a finance record ................................................................................................................. 23
  - 3.10 Raw Service .................................................................................................................................... 23
    - 3.10.1 Record a new event ..................................................................................................................... 23
    - 3.10.1 Replace an existing event ............................................................................................................ 24
    - 3.10.2 Cancel a previously recorded event ............................................................................................. 24
- 4. WSDL CALLS PROFILE, XSD SCHEMA AND GENERATED TYPES FOR SPAIN REGULATED GAMING MARKET 25
  - 4.1 Spanish records vs Dictao types relationship ................................................................................... 25
  - 4.2 Fundamental Types .......................................................................................................................... 26
  - 4.3 Common types .................................................................................................................................. 26
    - 4.3.1 Simple types .................................................................................................................................. 26
    - 4.3.2 PlayerID ......................................................................................................................................... 30
    - 4.3.3 RecordBase ................................................................................................................................... 30
    - 4.3.4 ChunkRecordBase ......................................................................................................................... 30
    - 4.3.5 RecordRef ...................................................................................................................................... 31
    - 4.3.6 Period ............................................................................................................................................ 31
    - 4.3.7 Amount .......................................................................................................................................... 31
    - 4.3.8 OperatorBreakdown ....................................................................................................................... 32
    - 4.3.9 JackpotBreakdown......................................................................................................................... 32
    - 4.3.10 GameRecordDetails (JUD) .......................................................................................................... 33
  - 4.4 Fixed-Odds Types............................................................................................................................. 36
    - 4.4.1 FixedOddsRecord .......................................................................................................................... 36
    - 4.4.2 FixedOddsReplacement ................................................................................................................ 36
    - 4.4.3 FixedOddsCancellation .................................................................................................................. 36
    - 4.4.4 EventCatalog (CEV)....................................................................................................................... 37
    - 4.4.5 BettingSummary (JUT) .................................................................................................................. 40
    - 4.4.6 BetAdjustment (JUA) ..................................................................................................................... 42
  - 4.5 Casino Types .................................................................................................................................... 43
    - 4.5.1 CasinoRecord ................................................................................................................................ 43
    - 4.5.2 CasinoReplacement....................................................................................................................... 44
    - 4.5.3 CasinoCancellation ........................................................................................................................ 44
    - 4.5.4 SessionTotal (JUT) ........................................................................................................................ 44
    - 4.5.5 BaccaraTotal (JUT) ........................................................................................................................ 47
  - 4.6 PVP Types ........................................................................................................................................ 48
    - 4.6.1 PVPRecord .................................................................................................................................... 48
    - 4.6.2 PVPReplacement........................................................................................................................... 49
    - 4.6.3 PVPCancellation ............................................................................................................................ 49
    - 4.6.4 BingoTotal (JUT) ............................................................................................................................ 49
    - 4.6.5 ContestTotal (JUT)......................................................................................................................... 51
  - 4.7 Poker-Cash Game Types ................................................................................................................. 53
    - 4.7.1 PokerCashGameRecord ................................................................................................................ 53
    - 4.7.2 PokerCashGameReplacement ...................................................................................................... 53
    - 4.7.3 PokerCashGameCancellation ........................................................................................................ 54
    - 4.7.4 PokerCashGameTotal (JUT) ......................................................................................................... 54
  - 4.8 Poker-Tournament Types ................................................................................................................. 56
    - 4.8.1 PokerTournamentRecord............................................................................................................... 56
    - 4.8.2 PokerTournamentReplacement ..................................................................................................... 56
    - 4.8.3 PokerTournamentCancellation ...................................................................................................... 56
    - 4.8.4 PokerTournamentTotal (JUT) ........................................................................................................ 56
  - 4.9 Player Registration Types ................................................................................................................. 58
    - 4.9.1 PlayerRecord ................................................................................................................................. 58
    - 4.9.2 PlayerReplacement........................................................................................................................ 59
    - 4.9.3 PlayerCancellation ......................................................................................................................... 59
    - 4.9.4 PlayerRegistrationDetails (RUD).................................................................................................... 59
    - 4.9.5 NetworkPlayerRegistration (RUR) ................................................................................................. 65
    - 4.9.6 WinnerRegistrationDetails (RUG) .................................................................................................. 66
    - 4.9.7 PlayerRegistrationTotal (RUT) ....................................................................................................... 70
  - 4.10 Finance Types ................................................................................................................................ 72
    - 4.10.1 FinanceRecord............................................................................................................................. 72
    - 4.10.2 FinanceReplacement ................................................................................................................... 72
    - 4.10.3 FinanceCancellation .................................................................................................................... 73
    - 4.10.4 PlayerAccountDetails (CJD) ........................................................................................................ 73
    - 4.10.5 PlayerAccountTotal (CJT) ............................................................................................................ 77
    - 4.10.6 OperatorAccountTotal (OPT) ....................................................................................................... 80
    - 4.10.7 NetworkOperatorAccountTotal (ORT) .......................................................................................... 82
    - 4.10.8 JackpotTotal (BOT) ...................................................................................................................... 83
    - 4.10.9 BankOperation ............................................................................................................................. 87
    - 4.10.10 PaymentBreakdown ................................................................................................................... 87
    - 4.10.11 GameBreakdown ....................................................................................................................... 88
    - 4.10.12 OtherBreakdown ........................................................................................................................ 88
  - 4.11 Raw Types ...................................................................................................................................... 88
    - 4.11.1 Raw Records ............................................................................................................................... 88
    - 4.11.1 SOAP Snippet .............................................................................................................................. 89

**IDEMIA RESTRICTED**

D3S Developer's Guide, SAFE Integration Guide – Datamodel Version 2.11  
Ref.: Morpho_D3S_JEL_DeveloperGuide_WSES – version 3.5.8 8/90  
Communication, reproduction or use prohibited without prior authorization of Morpho

## 1. INTRODUCTION

The D3S software is a secure storage module enabling gaming applications to store records of gaming events. Typically, such records are needed for regulatory compliance. D3S implements the jurisdiction-specific requirements such as data formats, cryptographic seals, and communication protocols with the regulator.

This guide describes the communication API between the gaming application and D3S.

It contains 4 chapters:

- The present introduction chapter
- Chapter 2 describes the general principles of use of the Web services
- Chapter 3 describes the Web services for Spain including code snippets
- Chapter 4 describes the object types used by Web services for Spain

### 1.1 Special note for Spain

The Spain gaming regulator “DGOJ” requires licensed operators to store a number of transactions in a device called “Vault”. Dictao’s D3S software is a secure storage server compliant with the regulator Vault specifications.

Gaming  
application

D3S

Regulator

**IDEMIA RESTRICTED**

D3S Developer's Guide, SAFE Integration Guide – Datamodel Version 2.11  
Ref.: Morpho_D3S_JEL_DeveloperGuide_WSES – version 3.5.8 9/90  
Communication, reproduction or use prohibited without prior authorization of Morpho

## 2. PRINCIPLES

### 2.1 Architecture

This documentation describes the WSDL  
1 bindings that will be used to store gaming events for regulatory purposes.

This API is provided in a “Software as a Service” offer. It requires only that the gaming operator fulfills the security requirements (connection, privacy …) and provides correct information about players, gaming status and other notification at the right time.

The SAFE services will then format, sign, timestamp, encrypt and store corresponding events XML files according to the regulatory rules.

The tracing methods are generic for all countries. But to fulfill regulatory requirements, per-country information are specified inside methods parameters, described in XML Schema data structure.

### 2.2 Environments

Three platforms are available:

- Integration platform: updated to latest version, this service will be maintained to enable adoption and debugging to new customer or during major updates;
- Load testing platform: we may open our load testing platform for customers which are looking for a production configuration dedicated to load balancing tests; load testing schedules must be agreed upon prior to the actual tests
- Production platform: backup, monitored, redundant, load-balanced, this platform is dedicated to our customers and real production environment. It must not be used for either functional or load tests, as records on this platform are published to the regulator

Please note that records sent to the latter are handled and charged as real gaming events.

### 2.3 Web Service connection

The applications calling the Web services are authenticated at the D3S by X.509 certificate (SSL with mutual authentication) provided by Dictao.

The access control mechanisms of the D3S ensure that the source of a record is correctly authenticated and authorized through the SSL authentication certificate.

To specify the certificates using the following JVM parameters (replace brackets with ad hoc values):

- `-Djavax.net.ssl.keyStore=[path/to/your/certificate/yourCertificate.p12]`
- `-Djavax.net.ssl.keyStorePassword=[passwordOfYourKeystore]`
- `-Djavax.net.ssl.keyStoreType=PKCS12`
- `-Djavax.net.ssl.trustStore=[path/to/the/truststore/truststore.jks]`

1  
http://en.wikipedia.org/wiki/Web_Services_Description_Language

**IDEMIA RESTRICTED**

D3S Developer's Guide, SAFE Integration Guide – Datamodel Version 2.11  
Ref.: Morpho_D3S_JEL_DeveloperGuide_WSES – version 3.5.8 10/90  
Communication, reproduction or use prohibited without prior authorization of Morpho

- `-Djavax.net.ssl.trustStorePassword=[passwordOfTruststore]`

You can test your connection through the connect method of the “d3sc” command line tool that is available inside the SDK (See the README.txt file in the root directory of the provided archive).

### 2.4 WSDL convention

#### 2.4.1 WSDL definition

The WSDL documents follow the given convention:

- filename: `d3s-jel-<PortName>-v<V>.wsdl`
- endpoint: `https://d3s.dictao.com/d3s/jel/es/service/<PortName>/v<V>[rc<X>]`

The WSDL PortName can take one of those values (jackpot, casino, fixed-odds, manager, poker-cash-game, poker-tournament, pool-game, finance, pvp). Each WSDL defined a unique port type with the following naming convention.

`<PortName>Port`

`add<Acrynom>(<PortName>Record records): recordPath`  
`replace<Acrynom>(<PortName>Replacement records): recordPath`  
`cancel<Acrynom>(<PortName>Cancellation records): recordPath`

#### 2.4.2 WSDL example

filename : `d3s-jel-casino-v2.wsdl`  
location : `https://d3s.dictao.com/d3s/jel/es/service/casino/v2`

`CasinoPort`  
`addCAR(CasinoRecord)`  
`replaceCAR(CasinoReplacement)`  
`cancelCAR(CasinoCancellation)`

### 2.5 XSD convention

#### 2.5.1 XSD definitions

The XSD documents follow the given convention:

- filename: `d3s-jel-<PortName>-<vYYYY_MM>.xsd`
- namespace: `https://dictao.com/d3s/jel/es/service/<PortName>/v<MMMM_YY>.xsd`

`<PortName>Record`  
Choice  
`<BusinessType1>`  
`<BusinessType2>`

`<PortName>Replacement`  
RecordRef:previous  
FinanceRecord:current

`<PortName>Cancellation`  
RecordRef:previous

**IDEMIA RESTRICTED**

D3S Developer's Guide, SAFE Integration Guide – Datamodel Version 2.11  
Ref.: Morpho_D3S_JEL_DeveloperGuide_WSES – version 3.5.8 11/90  
Communication, reproduction or use prohibited without prior authorization of Morpho

`< BusinessType1>`  
...

#### 2.5.2 XSD example

filename : `d3s-jel-casino-v2011_02.xsd`  
namespace: `https://dictao.com/d3s/jel/es/service/casino/v2011_02.xsd`

`CasinoRecord`  
choice  
`CasinoReplacement`  
`RecordBase:before`  
`CasinoRecord:after`  
`CasinoCancellation`  
`RecordBase:before`  
`RecordBase:after`  
`BlackjackGame`  
extension `RecordJUT`

### 2.6 Exception management

All the methods can throw exceptions of two types specific to D3S and exposed by the WSDL:

- `UserFaultException`
- `SystemFaultException`

#### 2.6.1 UserFaultException

They are related to input data provided by the client. They contain an error code specified by the WSDL (file `d3s-jel-error-v1.xsd` in folder `/wsdl/es/v2`).

These exceptions regard problems related to user data, the client application should always catch them as it should know how to handle them (modify input data; inform the end user, etc). In any case the client application must not resend this data without correcting it first.

The D3S server is still operational; it just needs correct input data to handle the record.

Example: invalid input data, violation of other constraint,

#### 2.6.2 SystemFaultException

They are related to the execution environment of the D3S. They contain an error code specified by the WSDL.

##### 2.6.2.1 Internal error

If the error code specifies an internal error, it is recommended to contact Dictao support.

These exceptions correspond to anomalies not managed in D3S; the client application should stop the treatment and log the error.

These exceptions denote an error requiring maintenance.

**IDEMIA RESTRICTED**

D3S Developer's Guide, SAFE Integration Guide – Datamodel Version 2.11  
Ref.: Morpho_D3S_JEL_DeveloperGuide_WSES – version 3.5.8 12/90  
Communication, reproduction or use prohibited without prior authorization of Morpho

##### 2.6.2.2 Other cases

These exceptions corresponding to problems on the environment, such as network connectivity, the client application should “try again later”, or stop the treatment. Choice should be based on the interpretation of the exception code.

The client application should log the error.

The return to a normal service of D3S requires a modification of the environment independent of the client application or of D3S itself. For example lost network connectivity is reestablished.

### 2.7 Records passed as a list in all methods

The various method `addXYZ`, `replaceXYZ`, `cancelXYZ` calls take a list of records, replacements and cancellations as input. This allows processing multiple orders in a single network round trip.

The maximum number of records submitted in a single call is limited to 1000. We recommend that you limit the size of the payload to lower the latency.

### 2.8 Return value

When a web service call succeeds, that is when no exception is thrown during the call, the server returns a single String value. This value represents an id assigned by the server to the call (since a call may store several records at once in the safe, this callID may concern several records and may not be considered as a recordID). The client application should log it for reference, as it may be used to track some information in the server logs.

This id represents the acknowledgement that the server received the data, and that it takes the responsibility of processing it and making it available to the regulator according to their specifications.

### 2.9 Idempotence

#### 2.9.1 Principles

The server implements a mechanism to avoid processing repeated successful calls with the same data, therefore ensuring the web service idempotence (http://en.wikipedia.org/wiki/Idempotence).

Therefore in any case you have no way to know that your call was received by the D3S server, you should carry out the same call again until you get a response (either an Exception, or a return value).

The idempotence works at the call level, not at the record level. This is important as the payload of a call to the safe may contain several records.

The idempotence function has the following characteristics:

- There is one history cache per client certificate. Therefore a repeated call may only be detected if it comes from a client using the same certificate
- A cache is limited to 10,000 calls. Therefore a repeated call will not be detected if more than 10,000 calls happened to the server since the original call.
- A call is identified by the web services call SOAP body. Therefore only exact duplicates will be detected as such.

**IDEMIA RESTRICTED**

D3S Developer's Guide, SAFE Integration Guide – Datamodel Version 2.11  
Ref.: Morpho_D3S_JEL_DeveloperGuide_WSES – version 3.5.8 13/90  
Communication, reproduction or use prohibited without prior authorization of Morpho

Duplicate calls prevention is very important; this is why we ask you to follow these guidelines to the letter to ensure duplicates are not created.

#### 2.9.2 Guidelines

Only by following the guidelines hereunder can we make sure there are no duplicates in the safe. Hereunder, what we call “client” is a machine or a machine pool (in case of redundancy) that stores data in the safe. A “client” composed of several physical machines may only be considered as such if they share the same message queue. If they do not, they have to be considered different clients for the purpose of idempotence.

- You should use one certificate per production client that is susceptible to record data in the safe. This regards the clients of your suppliers as well (if you and two suppliers write to the safe, you should have at least three different certificates). Dictao will provide these certificates for free on request from a customer operator.

  This ensures that a client can benefit from its own history cache and no other client will use up its history cache will the former is down.

- If a client goes down do not migrate its queue of pending calls to another one. If another client tries to send the same calls to the safe, the calls will be duplicated.

  Since different clients use different certificates, they do not rely on the same history cache.

- If you want to retry a call, retry it quickly; do not put it in an error queue that will be dealt manually later.

  If you retry this call after over 10,000 calls have been submitted to the safe (successfully or not), the original call will be out of the cache and the retry will not be caught as a repetition.

- If you want to retry a call, retry it exactly as it was; do not modify anything in the payload (recordId, list of the records in this call, order of the records in this call, etc.)

  If you change anything in the call, the safe will flag it as a different call, even if some of the records in that call are strictly the same as before: idempotence is at call level, not record level.

### 2.10 Record reference

The cancellation methods take an argument “RecordRef” which contains the strict minimum information to:

- Uniquely identify the previously recorded instance that must be cancelled,
- Allows the vault to save the cancellation in the appropriate record structure as defined by the regulator.

This has an impact on the structures of object definitions: the reference must be filled at a minimum with the recordId and the record type. Depending on the type of record, if a gametype, a periodicity, or a period are present they will be also required.

Here are two examples.

```java
// Example for OperatorAccountTotal case
RecordRef newpreviousOAT = new RecordRef();
newpreviousOAT.setOperatorId("operator");
newpreviousOAT.setRecordId("4572752142472");
newpreviousOAT.setDate(newInstanceOAT.getOperatorAccountTotal().getDate());
newpreviousOAT.setRecordType(RecordType.OPERATOR_ACCOUNT_TOTAL);
newpreviousOAT.setGameType(GameType.BLJ);
newpreviousOAT.setPeriodicity(Periodicity.PER_MONTH);
newpreviousOAT.setPeriod(new Period().withMonth(newInstanceOAT.getMonth()));
// Example for PlayerAccountTotal case
RecordRef newpreviousPAT = new RecordRef();
newpreviousPAT.setOperatorId("operator");
newpreviousPAT.setRecordId("4572752142472");
newpreviousPAT.setDate(newInstancePAT.getPlayerAccountTotal().getDate());
newpreviousPAT.setRecordType(RecordType.PLAYER_ACCOUNT_TOTAL);
newpreviousPAT.setPeriodicity(Periodicity.PER_DAY);
newpreviousPAT.setPeriod(newInstancePAT.getPeriod()));
```

**IDEMIA RESTRICTED**

D3S Developer's Guide, SAFE Integration Guide – Datamodel Version 2.11  
Ref.: Morpho_D3S_JEL_DeveloperGuide_WSES – version 3.5.8 15/90  
Communication, reproduction or use prohibited without prior authorization of Morpho

## 3. WEB SERVICES DOCUMENTATION

Each of the game types authorized is handled by a service with a number of game-type-specific functions. This section describes each game type.

For all services we define the notions of “records”, “replacement” and “cancellation”. Typically, a record represents an item from the game catalogue such as an actual poker tournament, or a bet type on an actual sports event. Replacement and cancelation as special record typically used to correct information that has been previously stored in the vault.

### 3.1 Web Services Overview

Nine different WSDL services are available:

- One handles the players lifecycle (Player service);
- One handles all financial related events (Finance service);
- 6 are related to the major game types (casino, fixed odds, generic game, poker cash game, poker tournament, player versus player);
- And the last one handles all types of records in raw format (the regulator’s data format)

| Service | Port | Method | WSDL location |
|---|---|---|---|
| PlayerService | playerPort | addPLR replacePLR cancelPLR | `<SDK>/wsdl/es/v1/d3s-jel-player-v1.wsdl` |
| FinanceService | financePort | addFIR replaceFIR cancelFIR | `<SDK>/wsdl/es/v1/d3s-jel-finance-v1.wsdl` |
| CasinoService | casinoPort | addCAR replaceCAR cancelCAR | `<SDK>/wsdl/es/v1/d3s-jel-casino-v1.wdl` |
| FixedOddsService | fixedOddsPort | addFOR replaceFOR cancelFOR | `<SDK>/wsdl/es/v1/d3s-jel-fixed-odds-v1.wsdl` |
| PokerCashGameService | pokerCashGamePort | addPCR replacePCR cancelPCR | `<SDK>/wsdl/es/v1/d3s-jel-poker-cash-game-v1.wsdl` |
| PokerTournamentService | pokerTournamentPort | addPTR replacePTR cancelPTR | `<SDK>/wsdl/es/v1/d3s-jel-poker-tournament-v1.wsdl` |
| PVPService | pvpPort | addPVR replacePVR cancelPVR | `<SDK>/wsdl/es/v1/d3s-jel-pvp-v1.wsdl` |
| RawService | rawPort | record | `<SDK>/wsdl/es/v1/d3s-jel-raw-v1.wsdl` |

Please make sure to only use the WSDL included in the SDK

### 3.2 Records and Events

A record is a container of event that must be stored into the vault. Each Web service endpoint defines its own record type, which holds a choice of XML elements. Each web service calls take a list of one or multiple records as parameters.

**IDEMIA RESTRICTED**

D3S Developer's Guide, SAFE Integration Guide – Datamodel Version 2.11  
Ref.: Morpho_D3S_JEL_DeveloperGuide_WSES – version 3.5.8 16/90  
Communication, reproduction or use prohibited without prior authorization of Morpho

This design offers maximum flexibility. For instance, the capture device can either send over the wire:

- A combined list of PlayerAccountDetails event and PlayerRegistrationDetails event in a single call, from a single capture device.
- A list of PlayerAccountDetails event in a first call followed by a list of PlayerRegistrationDetails event in a second call. Both calls coming from a single capture device or multiple devices in any order.

The table below summarizes the Record, Event and the time whenever they should be sent to the vault to conform to the Spain regulation.

**IDEMIA RESTRICTED**

D3S Developer's Guide, SAFE Integration Guide – Datamodel Version 2.11  
Ref.: Morpho_D3S_JEL_DeveloperGuide_WSES – version 3.5.8 17/90  
Communication, reproduction or use prohibited without prior authorization of Morpho

| Event category | Event type | Operators managing (owning) player accounts | Operators managing their own (non network) game | Network operators managing network games | Operators managing bets (fixed odds & bet exchange) local & network | Operators only offering contests (and games without prior user registration) | API equivalent | Real-time | Daily (before 4:00 on the next day) | Monthly (before 23:59 on the next day) |
|---|---|---|---|---|---|---|---|---|---|---|
| RU (User Registration) | RUT | X | X |  |  |  | PlayerRegistrationTotal |  | X(*) | X(*) |
| RU (User Registration) | RUD | X |  |  |  |  | PlayerRegistrationDetails | X | X |  |
| RU (User Registration) | RUR |  |  | X |  |  | NetworkPlayerRegistration |  |  | X |
| RU (User Registration) | RUG |  |  |  |  | X | WinnerRegistrationDetails |  |  | X |
| CJ (Gaming account) | CJT | X | X | X |  |  | PlayerAccountTotal |  | X | X |
| CJ (Gaming account) | CJD | X | X | X |  |  | PlayerAccountDetails | X | X |  |
| OP (Operator account) | OPT | X | X |  |  |  | OperatorAccountTotal |  |  | X |
| OP (Operator account) | ORT |  |  | X |  |  | NetworkOperatorAccountTotal |  |  | X |
| OP (Operator account) | BOT | X | X | X | X |  | JackpotTotal |  |  | X |
| JU (Game events) | JUD | X | X | X | X |  | GameDetails | X |  |  |
| JU (Game events) | JUA |  |  |  | X |  | BetAdjustmentRecord |  |  | X |
| JU (Game events) | CEV |  |  |  | X |  | EventCatalogRecord |  |  | X |
| JU (Game events) | JUT | X | X | X | X |  | CasinoRecord / BaccaraTotal | At the end of the baccarat hand |  |  |
| JU (Game events) | JUT | X | X | X | X |  | SessionTotal | At the end of the roulette, blackjack, slots and complementary game session |  |  |
| JU (Game events) | JUT | X | X | X | X |  | FixedOddsRecord / BettingSummary | At the moment the outcomes of the events involved in the bets are known |  |  |
| JU (Game events) | JUT | X | X | X | X |  | PokerCashGameRecord / PokerCashGameTotal | At the end of each poker hand |  |  |
| JU (Game events) | JUT | X | X | X | X |  | PokerTournamentRecord / PokerTournamentTotal | At the end of the tournament |  |  |
| JU (Game events) | JUT | X | X | X | X |  | PVPRecord / BingoTotal | At the end of the bingo game |  |  |
| JU (Game events) | JUT | X | X | X | X |  | PVPRecord / ContestTotal | At the end of the contest |  |  |

(*) Network operators do NOT provide a daily RUT. They only provide it monthly, like the RUR.

Note: An operator may fit the definition of several columns, like being a network operator and offering bets

**IDEMIA RESTRICTED**

D3S Developer's Guide, SAFE Integration Guide – Datamodel Version 2.11  
Ref.: Morpho_D3S_JEL_DeveloperGuide_WSES – version 3.5.8 18/90  
Communication, reproduction or use prohibited without prior authorization of Morpho

### 3.3 FixedOdds Service

This service is used to record fixed odds betting and bet exchange transactions, such as sportsbook.

In fixed odds, an instance is the context of an event whose outcome may be bet upon. It is the combination of an event (e.g. “Newcastle v Arsenal 13/08/2011 15:00 BST”; “Wimbledon Mens Tennis 2012”) with the type of bet (e.g. outright winner, result of a football match, amount of goals, etc …).

Below, the description of function calls.

#### 3.3.1 Add a bet description

The java prototype of the function is:

`String addFOR(List<FixedOddsRecord> records) throws SystemFaultException, UserFaultException`

See section “Records and Events” above to know when to call this method

#### 3.3.2 Replace a game instance

The java prototype of the function is:

`String replaceFOR(List<FixedOddsReplacement> records) throws SystemFaultException, UserFaultException`

If you have to modify an instance previously added (and thus recorded) for any reason (platform error, cheating detected, etc.), you shall call `replaceFOR()` with the “updated” information as parameters.

The `FixedOddsReplacement` parameter identifies the previous record that was recorded with `addFOR()` along with the new `FixedOddsRecord` value that must be recorded as a replacement.

You can only call a replacement for a record that was previously submitted.

#### 3.3.3 Cancel a game instance

The java prototype of the function is:

`String cancelFOR (List<FixedOddsCancellation> records) throws SystemFaultException, UserFaultException`

Cancelling a game instance without replacing it can be achieved through a call to this method with a record reference.

The `FixedOddsCancellation` parameter contains a complete reference of the previous record.

**IDEMIA RESTRICTED**

D3S Developer's Guide, SAFE Integration Guide – Datamodel Version 2.11  
Ref.: Morpho_D3S_JEL_DeveloperGuide_WSES – version 3.5.8 19/90  
Communication, reproduction or use prohibited without prior authorization of Morpho

### 3.4 Casino Service

Below, the description of function calls.

#### 3.4.1 Add a game instance

The java prototype of the function is:

`String addCAR(List<CasinoRecord> records) throws SystemFaultException, UserFaultException`

See section “Records and Events” above to know when to call this method

#### 3.4.2 Replace a game instance

The java prototype of the function is:

`String replaceCAR(List<CasinoReplacement> records) throws SystemFaultException, UserFaultException`

If you have to modify an instance previously added (and thus recorded) for any reason (platform error, cheating detected, etc.), you shall call `replaceCAR()` with the “updated” information as parameters.

The `CasinoReplacement` parameter identifies the previous record that was recorded with `addCAR()` along with the new `CasinoRecord` value that must be recorded as a replacement.

You can only call a replacement for a record that was previously submitted.

#### 3.4.3 Cancel a game instance

The java prototype of the function is:

`String cancelCAR (List<CasinoCancellation> records) throws SystemFaultException, UserFaultException`

Cancelling a game instance without replacing it can be achieved through a call to this method with a record reference.

The `CasinoCancellation` parameter contains a complete reference of the previous record.”

### 3.5 Player-Versus-Player (PVP) Service

Below, the description of function calls.

#### 3.5.1 Add a game instance

The java prototype of the function is:

`String addPVR (List<PVPRecord> records) throws SystemFaultException, UserFaultException`

**IDEMIA RESTRICTED**

D3S Developer's Guide, SAFE Integration Guide – Datamodel Version 2.11  
Ref.: Morpho_D3S_JEL_DeveloperGuide_WSES – version 3.5.8 20/90  
Communication, reproduction or use prohibited without prior authorization of Morpho

See section “Records and Events” above to know when to call this method

#### 3.5.2 Replace a game instance

The java prototype of the function is:

`String replacePVR (List<PVPReplacement> replacements) throws SystemFaultException, UserFaultException`

If you have to modify an instance previously closed (and thus recorded) for any reason (platform error, cheating detected, etc.), you shall call `replacePVR()` with the “updated” information as parameters.

The `PVPReplacement` parameter identifies the previous record that was recorded with `addPVR()` along with the new `PVPRecord` value that must be recorded as a replacement.

You can only call a replacement for a record that was previously submitted.

#### 3.5.3 Cancel a game instance

The java prototype of the function is:

`String cancelPVR (List<PVPCancellation> cancellations) throws SystemFaultException, UserFaultException`

Cancelling a game instance without replacing it can be achieved through a call to this method with a record reference.

The `PVPCancellation` parameter contains a complete reference of the previous record.

### 3.6 Poker Cash Game Service

Below, the description of function calls.

#### 3.6.1 Add a game instance

The java prototype of the function is:

`String addPCR (List<PokerCashGameRecord> records) throws SystemFaultException, UserFaultException`

See section “Records and Events” above to know when to call this method

#### 3.6.2 Replace a game instance

The java prototype of the function is:

`String replacePCR (List< PokerCashGameReplacement > records) throws SystemFaultException, UserFaultException`

**IDEMIA RESTRICTED**

D3S Developer's Guide, SAFE Integration Guide – Datamodel Version 2.11  
Ref.: Morpho_D3S_JEL_DeveloperGuide_WSES – version 3.5.8 21/90  
Communication, reproduction or use prohibited without prior authorization of Morpho

If you have to modify an instance previously closed (and thus recorded) for any reason (platform error, cheating detected, etc.), you shall call `replacePCR()` with the “updated” information as parameters.

The `PokerCashGameReplacement` parameter identifies the previous record that was recorded with `addPCR()` along with the new `PokerCashGameRecord` value that must be recorded as a replacement.

You can only call a replacement for a record that was previously submitted.

#### 3.6.3 Cancel a game instance

The java prototype of the function is:

`String cancelPCR (List< PokerCashGameCancellation > records) throws SystemFaultException, UserFaultException`

Cancelling a game instance without replacing it can be achieved through a call to this method with a record reference.

The `PokerCashGameCancellation` parameter contains a complete reference of the previous record.

### 3.7 Poker Tournament Service

Below, the description of function calls.

#### 3.7.1 Add a game instance

The java prototype of the function is:

`String addPTR(List< PokerTournamentRecord > records) throws SystemFaultException, UserFaultException`

See section “Records and Events” above to know when to call this method

#### 3.7.2 Replace a game instance

The java prototype of the function is:

`String replacePTR(List< PokerTournamentReplacement > records) throws SystemFaultException, UserFaultException`

If you have to modify an instance previously closed (and thus recorded) for any reason (platform error, cheating detected, etc.), you shall call `replacePTR()` with the “updated” information as parameters.

The `PokerTournamentReplacement` parameter identifies the previous record that was recorded with `addPTR()` along with the new `PokerTournamentRecord` value that must be recorded as a replacement.

You can only call a replacement for a record that was previously submitted.

**IDEMIA RESTRICTED**

D3S Developer's Guide, SAFE Integration Guide – Datamodel Version 2.11  
Ref.: Morpho_D3S_JEL_DeveloperGuide_WSES – version 3.5.8 22/90  
Communication, reproduction or use prohibited without prior authorization of Morpho

#### 3.7.3 Cancel a game instance

The java prototype of the function is:

`String cancelPTR (List<PokerTournamentCancellation> records) throws SystemFaultException, UserFaultException`

Cancelling a game instance without replacing it can be achieved through a call to this method with a record reference.

The `PokerTournamentCancellation` parameter contains a complete reference of the previous record.

### 3.8 Player Registration Service

Below, the description of function calls.

#### 3.8.1 Add an new event about player information

The java prototype of the function is:

`String addPLR (List<PlayerRecord> records) throws SystemFaultException, UserFaultException`

See section “Records and Events” above to know when to call this method

#### 3.8.2 Replace an existing event about player information

The java prototype of the function is:

`String replacePLR (List<PlayerReplacement> records) throws SystemFaultException, UserFaultException`

If you have to modify a player event previously sent (and thus recorded) for any reason (platform error, account theft, etc.), you shall call `replacePLR()` with the “updated” information as parameters.

The `PlayerReplacement` parameter identifies the previous record that was recorded with `addPLR()` along with the new `PlayerRecord` value that must be recorded as a replacement.

You can only call a replacement for a record that was previously submitted.

#### 3.8.3 Cancel a player event

The java prototype of the function is:

`String cancelPLR (List<PlayerCancellation> records) throws SystemFaultException, UserFaultException`

Cancelling a game instance without replacing it can be achieved through a call to this method with a record reference.

The `PlayerCancellation` parameter contains a complete reference of the previous record.

**IDEMIA RESTRICTED**

D3S Developer's Guide, SAFE Integration Guide – Datamodel Version 2.11  
Ref.: Morpho_D3S_JEL_DeveloperGuide_WSES – version 3.5.8 23/90  
Communication, reproduction or use prohibited without prior authorization of Morpho

### 3.9 Finance Service

Below, the description of function calls.

#### 3.9.1 Add an new event about finance

The java prototype of the function is:

`String addFIR (List<FinanceRecord> records) throws SystemFaultException, UserFaultException`

See section “Records and Events” above to know when to call this method

#### 3.9.2 Replace an existing event about finance

The java prototype of the function is:

`String replaceFIR (List< FinanceReplacement> records) throws SystemFaultException, UserFaultException`

If you have to modify a financial event previously sent (and thus recorded) for any reason (platform error, account theft, etc.), you shall call `replaceFIR()` with the “updated” information as parameters.

The `FinanceReplacement` parameter identifies the previous record that was recorded with `addFIR()` along with the new `FinanceRecord` value that must be recorded as a replacement.

You can only call a replacement for a record that was previously submitted.

#### 3.9.3 Cancel a finance record

The java prototype of the function is:

`String cancelFIR (List< FinanceCancellation> records) throws SystemFaultException, UserFaultException`

Cancelling a game instance without replacing it can be achieved through a call to this method with a record reference.

The `FinanceCancellation` parameter contains a complete reference of the previous record.

### 3.10 Raw Service

Below, the description of function calls.

#### 3.10.1 Record a new event

The java prototype of the function is:

`String record(List<RawRecord> records) throws SystemFaultException, UserFaultException`

See section “Records and Events” above to know when to call this method

The data that get transmitted follow the Spanish gaming regulator-defined format

This API shall be used when the gaming application formats messages according to the regulator-defined format. This call comes as an altenative to the previously defined ones.

**IDEMIA RESTRICTED**

D3S Developer's Guide, SAFE Integration Guide – Datamodel Version 2.11  
Ref.: Morpho_D3S_JEL_DeveloperGuide_WSES – version 3.5.8 24/90  
Communication, reproduction or use prohibited without prior authorization of Morpho

For example, the effect of the various “addXYZ” methods can be add by passing various Registro* types (RegistroSesion,,…).

#### 3.10.1 Replace an existing event

The java prototype of the function is the same:

`String record (List< RawRecord > records) throws SystemFaultException, UserFaultException`

To get what the replaceXYZ methods do, call this method with a sutable Registro* object: E.g. to replace a RegistroRuleta event, you’d need to call this method with another RegistroRuleta object, with the fieldsRectificacion.RegistroId and Rectificacion.RegistroFecha appropriately defined.

#### 3.10.2 Cancel a previously recorded event

The java prototype of the function is the same:

`String record (List< RawRecord > records) throws SystemFaultException, UserFaultException`

Calling this method with a RegistroAnulador type object is the equivalent of the various cancelXYZ methods.

**IDEMIA RESTRICTED**

D3S Developer's Guide, SAFE Integration Guide – Datamodel Version 2.11  
Ref.: Morpho_D3S_JEL_DeveloperGuide_WSES – version 3.5.8 25/90  
Communication, reproduction or use prohibited without prior authorization of Morpho

## 4. WSDL CALLS PROFILE, XSD SCHEMA AND GENERATED TYPES FOR SPAIN REGULATED GAMING MARKET

This section describes the calls that have to be implemented and the types of object used in the function calls.

For each service, the service calls are described and the code snippets are given to have a global view of the functions usage.

N.B: These code snippets are short reusable pieces of source code however they are incomplete. They for example do not expose all technical details for setting up the connection. To see the complete source code, please have a look at the “samples” module delivered in the SDK.

A README.txt file is at your disposal for every sample to indicate the procedure for the compilation.

As a general rule, each function authorizes one argument (see the prototypes of function calls in the section “Function calls”) and each argument contains specifics data defined in the XSD schema.

For each type of object below, a description, a type and the cardinality are given for every parameter.

### 4.1 Spanish records vs Dictao types relationship

The required Spanish records are mapped to the Dictao services / nodes as followed:

- Player registration records (RUT, RUD, RUR, RUG) must be provided through player service and PlayerRecord node (daily and monthly basis);
- Finance transfer records (CJT, CJD, OPT and ORT) must be provided through finance service and FinanceRecord node (daily and monthly basis);
- for Game records (JUT, JUD, JUA, and CEV):
  - PokerCash and PokerTournament must be provided through the poker service;
  - Roulette, Blackjack, Bacarra and Slots records must be provided through the casino service;
  - Bingo and Contest records must be provided through the PVP service;
  - Bet records (fixed odds and bet exchange) must be provided through the fixed odds service;
- Periodic records
  - Daily should be encompasses changes done from midnight to midnight; they must be record before 4:00 AM the next day.
  - Monthly should be recorded the first day of each month.

**IDEMIA RESTRICTED**

D3S Developer's Guide, SAFE Integration Guide – Datamodel Version 2.11  
Ref.: Morpho_D3S_JEL_DeveloperGuide_WSES – version 3.5.8 26/90  
Communication, reproduction or use prohibited without prior authorization of Morpho

### 4.2 Fundamental Types

The fundamental XML Schema types are prefix with `xs:` in the description below. For example, strings are typed as `xs:string`.

### 4.3 Common types

The common Dictao types are prefix with `co:` namespace in the description below. For example, player statuses are typed as `co:CNJStatus`.

### 4.3.1 Simple types

| Name | Description | Base type | Sample or list of values |
|---|---|---|---|
| date-yyyymm | Date (precision of the month) This field has to be 6 digits exactly | xs:string | “201110” |
| duration-hhmmss | Duration in hours, minutes and seconds for slots. This field has to be exactly 6 characters, so: - A duration of 1h30m06sec will be coded “013006” - No duration may exceed 99h59m59sec | xs:string | “013006” |
| SportCode | Identification code of the Sport for bets. The only authorized values are: This field can only take one of the following values: 1. Athletics 2. Motor sports 3. Badminton 4. Basketball 5. Handball 6. Baseball 7. Biathlon, Triathlon, others 8. Billiards 9. Boxing 10. Cycling 11. Cyclo-cross 12. Cricket 13. Darts 14. Winter sports 15. Equestrianism 16. Fencing 17. Football 18. American football 19. Australian rules football 20. Futsal 21. Gymnastics 22. Golf 23. Weightlifting 24. Ice hockey 25. Field hockey 26. Roller hockey 27. Judo 28. Wrestling for “Freestyle wrestling” 29. Motorcycle 30. Swimming 31. Padel tennis 32. Skating 33. Basque pelota 34. Rowing 35. Rugby 36. Snooker 37. Squash 38. Taekwondo | xs:string | “9” |

**IDEMIA RESTRICTED**

D3S Developer's Guide, SAFE Integration Guide – Datamodel Version 2.11  
Ref.: Morpho_D3S_JEL_DeveloperGuide_WSES – version 3.5.8 27/90  
Communication, reproduction or use prohibited without prior authorization of Morpho

39. Tennis  
40. Table tennis  
41. Archery  
42. Sports Shooting  
43. Sailing  
44. Volleyball  
45. Beach volleyball  
46. Water polo  
47. Chess  
48. Apnea  
49. Fistball  
50. Beach Handball  
51. Lawn bowling  
52. Bowling  
53. Curling  
54. Combat Sport  
55. Gaelic Games  
56. Basque Sports  
57. Floorball  
58. Indoor Football  
59. Beach Soccer  
60. Lacrosse  
61. Netball  
62. Petanque  
63. Canoeing  
64. Kiiking  
65. Softball  
66. Surf  
67. Bandy  
68. MMA-Mixed Martial Art  
69. Indoor bowling  
70. Pesäpallo  
71. WWE Wrestling  
72. Sumo  
73. Sepak takraw  
998. neither sport nor horse  
999. other sport : If the sport does not exist in the list

**IDEMIA RESTRICTED**

D3S Developer's Guide, SAFE Integration Guide – Datamodel Version 2.11  
Ref.: Morpho_D3S_JEL_DeveloperGuide_WSES – version 3.5.8 28/90  
Communication, reproduction or use prohibited without prior authorization of Morpho

| Name | Description | Base type | Sample or list of values |
|---|---|---|---|
| PaymentMethodType | Identification code of the type of payment method. The only authorized values are: - “1”: Cash - “2”: Prepayment - “3”: Bank transfer - “4”: Credit Card - “5”: Debit Card - “6”: Electronic wallet - “7”: Check/Cheque - “8”: Premium SMS - “9”: Money order - “10”: Treasury services - “11”: Payment through a telecom operator - “12”: Premium phone call - “13”: Generic Payment Card (Credit or Debit) - not available in model 2.0 - “14”: Fixed terminal - “99”: Another method, in which case the field “otherPaymentMethodType” has to be filled | xs:string | “4” |
| SessionVariant | The variant of a session game. This field may only take the following values. Blackjack specific - “21” : Super21 - “AM”: American - “CL”: Classic - “PO”: Pontoon - “SU”: Surrender Roulette specific - “American” - “French” | xs:string | “French” |

**IDEMIA RESTRICTED**

D3S Developer's Guide, SAFE Integration Guide – Datamodel Version 2.11  
Ref.: Morpho_D3S_JEL_DeveloperGuide_WSES – version 3.5.8 29/90  
Communication, reproduction or use prohibited without prior authorization of Morpho

| Name | Description | Base type | Sample or list of values |
|---|---|---|---|
| CountryCode | Two letters ISO country code. The accepted values are restricted to the list of the 249 current officially assigned ISO 3166-1 alpha-2 codes (http://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) as of October 2014. If a country gets a new ISO code after October 2014, you will not be able to report it | xs:string | ES AN |
| Euros | Euro amount with two decimal. - a credit, the amount is positive. - a debit, the amount is negative | xs:decimal | 100.50 |
| CNJStatus | State in which the operator is asked to distinguish between “A” – Activo [Active] “AC” – Anulacion contrato [the operator has proven that the participant has engaged in fraud, collusion or the account was used by third parties, and has acted unilaterally to terminate the contract.] “S” – Suspendido [Suspended by player request or player inactive for 2 years] “C” – Cancelado [Cancelled for expiration of temporary account or player suspended for 4 years] “SC” – Suspendido cautelarmente [the operator has warned the player of a collusive or fraudulent conduct or use of the account by third parties and the operator has chosen to suspend as a precautionary measure] (Involuntary exclusion) “PR” – Prohibido [Forbidden] RGIAJ [Spanish initials for General Gaming Access Interdiction Record] “O” – Otros [Others] | xs:string | “A" |
| GameType | Variant of the game, for example Omaha or Hold’em for poker. Possible values are: - "ADC": Counterpart Sports bets - "AHC”: Counterpart Horserace Bets - “ADX”: Sports Bet exchange - "ADM": Mutual Sports Bets - "AHM": Mutual Horseracing Bets - “AHX”: Horserace Bet exchange - “AOC”: Counterpart Outrights - “AOX” : Other Bet exchange - "RLT": Roulette - "BNG": Bingo - “BLJ”: :Blackjack - "POC": Poker Cash - “POT”: Poker Tournament - “AZA” : Slots - "COC": Contests - “PUN”: Baccara - “COM”: Additional game - ”PDM” : ONLY FOR SELAE / DO NOT USE - ”PHM” : ONLY FOR SELAE / DO NOT USE - ”PLN”: ONLY FOR SELAE / DO NOT USE - ”PLP” : ONLY FOR SELAE / DO NOT USE - ”PEU” : ONLY FOR SELAE / DO NOT USE - ”PBL” : ONLY FOR SELAE / DO NOT USE - ”PGP” : ONLY FOR SELAE / DO NOT USE - ”PLT” : ONLY FOR SELAE / DO NOT USE - ”OLN” : ONLY FOR SELAE / DO NOT USE - ”OLP” : ONLY FOR SELAE / DO NOT USE - ”OEU” : ONLY FOR SELAE / DO NOT USE - ”OBL” : ONLY FOR SELAE / DO NOT USE - ”OGP” : ONLY FOR SELAE / DO NOT USE - ”OLT” : ONLY FOR SELAE / DO NOT USE | xs:string | “ADC” |

**IDEMIA RESTRICTED**

D3S Developer's Guide, SAFE Integration Guide – Datamodel Version 2.11  
Ref.: Morpho_D3S_JEL_DeveloperGuide_WSES – version 3.5.8 30/90  
Communication, reproduction or use prohibited without prior authorization of Morpho

| Name | Description | Base type | Sample or list of values |
|---|---|---|---|
| RecordType | Enumerated list of record types: -"PlayerRegistrationDetails" -"PlayerRegistrationTotal" –“NetworkPlayerRegistration” –“WinnerRegistrationDetails” -"PlayerAccountDetails" -"PlayerAccountTotal" -"OperatorAccountTotal" -"NetworkOperatorAccountTotal" -"JackpotTotal" -"GameDetails" -"GameTotal" –“BetAdjustmentRecord” –“EventCatalogRecord” | xs:string | PlayerRegistrationDetails |
| Periodicity | Type of periodic record. Allowed values are: - “PerDay” - “PerMonth” | xs:string | “PerDay” |

### 4.3.2 PlayerID

| Field | Description | Type | Mandatory | Example of value |
|---|---|---|---|---|
| operatorId | ID of the operator (given by DGOJ) owning/managing the player | xs:string | Yes | 3ZFD85857378FF |
| playerId | Unique identifier of the player in the operator IS. This is a technical ID, it shall not be anything "private" or "personal" like a social security number. | xs:string | Yes | PJHSQ2424 |

### 4.3.3 RecordBase

| Field | Description | Type | Mandatory | Example of value |
|---|---|---|---|---|
| operatorId | ID of the operator (given by DGOJ) managing the game | xs:string | Yes | 3ZFD85857378FF |
| recordId | ID provided by the operator to identify the record that will be stored in the vault. This ID : - allows the regulator to consolidate all the subrecords together - has to be used when a record has to be replaced or canceled This ID has to be unique for a given vault. | xs:string | Yes | 743E-422E-21DA-3C1D |
| date | Date/time the record was extracted from your information system. Note that this not the time the vault is called. Indeed, if you need to resend the record to the vault by making a new call, the entire record must stay the same for the idempotence mechanism to function properly. – This date will be required in case a replacement or cancellation call needs to be issued | xs:dateTime | Yes | 2011-10-04T19:44:51.346+02:00 |

### 4.3.4 ChunkRecordBase

| Field | Description | Type | Mandatory | Example of value |
|---|---|---|---|---|
| + RecordBase (inherited fields) |  |  |  |  |
| subRecordId | This has to be a number between 1 and the nextField “subRecordTotal” included | xs:positiveInteger | Yes | 1 |
| subRecordTotal | Number of subrecords. Subrecords are used for PlayerAccountDetails (CJD), PlayerRegistrationDetails (RUD), NetworkPlayerRegistration (RUR) WinnerRegistrationDetails (RUG), GameDetails (JUD), EventCatalog (CEV) and BetAdjustment (JUA) when records involve more than 1 000 players or events. In that case, records are split in subrecords per slice of 1 000 players or events. | xs:positiveInteger | Yes | 1 |

### 4.3.5 RecordRef

| Field | Description | Type | Mandatory | Example of value |
|---|---|---|---|---|
| operatorId | ID of the operator (given by DGOJ) managing the game | xs:string | Yes | 3ZFD85857378FF |
| recordId | ID provided by the operator to identify the record that will be stored in the vault. This ID : - allows the regulator to consolidate all the subrecords together - has to be used when a record has to be replaced or canceled This ID has to be unique for a given vault. | xs:string | Yes | GUID |
| date | Date/time used in the original record sent to the vault. This date is used by the regulator to find the original record. | xs:dateTime | Yes | 2011-10-04T19:44:51.346+02:00 |
| gameType | Type of game | co:GameType | No | “POC” |
| periodicity | The periodicity of the record. It may take only 2 values: - PerDay - PerMonth | co:Periodicity | No | “PerDay” |
| period | The period the referenced record corresponded to | co:Period | No | - |
| recordType | Type of record to cancel. | co:RecordType | No | “PlayerRegistrationTotal” |

### 4.3.6 Period

| Field | Description | Type | Mandatory | Example of value |
|---|---|---|---|---|
| Choice |  |  |  |  |
| day | The period of time the record applies to as an identified day | xs:date | Yes | 2011-10-06+02:00 |
| month | The period of time the record applies to as an identified month | co:date-yyyymm | Yes | “201110” |

### 4.3.7 Amount

| Field | Description | Type | Mandatory | Example of value |
|---|---|---|---|---|
| line | Breakdown of the amount per line of unit (cash in Euros or other type of unit defined by the operator) | Line | No | - |

#### 4.3.7.1 Amount.Line

| Field | Description | Type | Mandatory | Example of value |
|---|---|---|---|---|
| amount | Total amount for this type of line. If the movement is - a credit, the amount is positive. - a debit, the amount is negative. The nature (credit or debit) is generally related to the player account The DGOJ has expressed that : - as a general rule, a maximum of 4 digits should be used - if required, an operator may exceptionally use up to 9 digits | co:decimal | Yes | 124554.45 |
| unit | Description of the amount type (EUR for movement with real money, it can also be fidelity points or other operator values) | xs:string | Yes | “EUR” |

### 4.3.8 OperatorBreakdown

| Field | Description | Type | Mandatory | Example of value |
|---|---|---|---|---|
| total | Total amount of transfered money in this breakdown sub divided by unit | co: Amount | Yes | 124554.45 |
| breakdown | Breakdown entries of money transfer per operator (unbounded sequence). This field may be omitted if “total” above is “0” | Breakdown | No | - |

#### 4.3.8.1 OperatorBreakdown.Breakdown

| Field | Description | Type | Mandatory | Example of value |
|---|---|---|---|---|
| operatorId | ID of the operator (given by DGOJ) owning/managing the player | xs:string | Yes | 3ZFD85857378FF |
| amount | Amount of money moved from the account subdivided by unit | co:Amount | Yes | 457.78 |

### 4.3.9 JackpotBreakdown

| Field | Description | Type | Mandatory | Example of value |
|---|---|---|---|---|
| total | Total amount of transfered money in this breakdown | co:Amount | Yes | - |
| breakdown | Breakdown entries of money transfer by individual Jackpot (unbounded sequence). This field may be omitted if “total” above is “0” | Breakdown | No | - |

#### 4.3.9.1 JackpotBreakdown.Breakdown

| Field | Description | Type | Mandatory | Example of value |
|---|---|---|---|---|
| jackpotId | Unique ID of the jackpot given by the operator | xs:string | Yes | 3ZFD85857378FF |
| jackpotDesc | Human readable description of the jackpot | xs:string | Yes | “Super prize for valued players” |
| amount | Amount of money moved from the account. If the movement is - a credit to the jackpot, the amount is positive. - a debit from the jackpot (jackpot release), the amount is negative | co: Amount | Yes | - |

### 4.3.10 GameRecordDetails (JUD)

**Goal**

The GameRecordDetails shall contain information about games, tournaments, matches or sessions.

- Bets: each combination of sports, competitions, events and facts upon which bets are placed.
- Poker cashgame & punto banco: each hand.
- Poker tournament: each tournament
- Bingo: each game of bingo
- Contests: each contest
- Roulette, blackjack, complementary games and slot machines: each session

**Concerned operators**

This record shall be submitted by every operator that manages the game, either completely or network operators managing a co-organised network. Operators who only manage players but not games do not submit this record.

**Trigger**

Games Records data must be generated in real time by the operator's system in such a way that information about the event is collected as it occurs in the system.

The events shall be:

- Betting: the moment the outcomes of the events involved in the bets are known
- Poker cashgame & punto banco: at the end of the hand.
- Poker tournament: at the end of the tournament.
- Bingo: at the end of the game.
- Contests: at the end of each contest.
- Roulette, blackjack, complementary games and slot machines: at the end of the session

Corrections, cancellations or adjustments to games made after their original transmission to the SAFE shall be reported as rectifications, it being in no case possible to erase the original corrected, cancelled or adjusted transaction. This shall be done for all games where these circumstances occur, with the exception of bets, whose corrections and adjustments must be reported individually in the BetAdjustment record. This file shall collect any correction or adjustment to bets already made, indicating the amounts and reasons.

When a variation in gaming records is due to reasons other than from the normal operation of the games, such as errors in the generation of the report or other errors of a technical nature, the transmission of the correct data shall be made by means of a record replacement.

One of such records may not describe more than 1 000 players. If you want to report more than 1 000 players, you have to split the record into subrecords, each of them containing exactly 1 000 players but the last one.

| Field | Description | Type | Mandatory | Example of value |
|---|---|---|---|---|
| + ChunkRecordBase (inherited fields) |  |  |  |  |
| gameId | Unique identifier of the bet instance | xs:string | Yes | PJD24DS |
| gameType | Type of game | co:GameType | Yes | - |
| player | Unbounded sequence of players descriptions | Player | Yes | - |

#### 4.3.10.1 GameRecordDetails.Player

| Field | Description | Type | Mandatory | Example of value |
|---|---|---|---|---|
| playerID | Identification of the player | co:PlayerID | Yes | - |
| placement | Amount wagered toward the game itself (including contributions to jackpots) on this instance (broken down by unit). This value is negative, | co:Amount | Yes | 145.47 |
| refund | Amount refunded to the player if the game is canceled for any reason (broken down by unit). This value is positive | co:Amount | Yes | 145.47 |
| cashWinnings | Value of all the cash winnings during this instance (including winnings from jackpots). (broken down by unit). This value is positive. | co: Amount | Yes | 145.47 |
| inKindPrizes | Value of all the winnings in kind during this instance. (broken down by unit).This value is positive. | co: Amount | Yes | 145.47 |
| inKindPrizesBreakdown | Breakdown by prizes description | InKindPrizesBreakdown | No | - |
| betId | Unique identifier of the bet. This ID has to be unique across the whole information system. Different players or different bets may never share the same betId. Using a UUID is strongly recommended. Only fill this field if the game type is “bets”. | xs:string | No | 543ab-65fe-5694-5445 |
| betDate | The date and time the bet was placed. Only fill this field if the game type is “bets” | xs:datetime | No |  |
| betExchange | Unbounded list of the betexchanges This describes all the bet exchanged by the player in this bet slip. There are as many of this field as there are “bettors” exchanging bets with the concerned player (whose record this is) Only fill this field if the game type is “bet exchange” | BetExchangeBreakdown | No |  |
| slotsSessionLimits | If the player has set limits for the slots session, fill this field Only fill this field if the game type is “slots” (AZA) | SlotsSessionLimits | No |  |

#### 4.3.10.1 GameRecordDetails.Player.InKindPrizesBreakdown

| Field | Description | Type | Mandatory | Example of value |
|---|---|---|---|---|
| description | Description of the prize | xs:string | Yes | - |
| amount | Monetary value of the prize subdivided by unit. | co: Amount | Yes | 145.47 |

#### 4.3.10.2 GameRecordDetails.Player.BetExchangeBreakdown

| Field | Description | Type | Mandatory | Example of value |
|---|---|---|---|---|
| challenge | This flag indicates whether or not the exchanges are a “challenge”. The bet is considered a challenge when the bettor knows the person he is betting against. | xs:boolean | No | true |
| exchanges | Unbounded sequence of all the bets that have been exchanged between the bettor and the person he is betting against in this betID | Exchange | No | - |

#### 4.3.10.3 GameRecordDetails.Player.BetExchangeBreakdown.Exchange

| Field | Description | Type | Mandatory | Example of value |
|---|---|---|---|---|
| layOrBack | Describes whether this end of the bet exchange is lay or back. The only possible values are: - “Lay” - “Back” | xs:string | Yes | “Lay” |
| ticketId | Unique identifier of the bet that has been exchanged. The same identifier has to be used by the other player with which the exchange occurred. Using a UUID is strongly recommended. | xs:string | Yes | 543ab-65fe-5694-5445 |

#### 4.3.10.4 GameRecordDetails.Player.SlotsSessionLimits

| Field | Description | Type | Mandatory | Example of value |
|---|---|---|---|---|
| durationLimit | This is set by the player : maximum duration of the session This field has to be exactly 6 characters, so: - A duration of 1h30m06sec will be coded “013006” No duration may exceed 99h59m59sec | co:duration-hhmmss | Yes | “020000” |
| placementLimit | This is set by the player : maximum amount that may be lost during the session (in euros): amount wagered – amount won during the session. This does not take any bonus into account. This does not describe the maximum amount wagered by the player during the session. | co:Euros | Yes | 350 |

### 4.4 Fixed-Odds Types

#### 4.4.1 FixedOddsRecord

| Field | Description | Type | Mandatory | Example of value |
|---|---|---|---|---|
| Choice |  |  |  |  |
| bettingSummary | The total transferred money and various breakdown of a bet with fixed odds bet | BettingSummary | Yes | See the value of each subfield |
| bettingDetails | The details of a bet with fixed odds | co:GameRecordDetails | Yes | See the value of each subfield |
| betAdjustment | A description of all the resettlement of the previous month | BettingAdjustment | Yes | See the value of each subfield |
| eventCatalog | A catalog of all the events available for bet placement during the previous month | EventCatalog | Yes | See the value of each subfield |

#### 4.4.2 FixedOddsReplacement

| Field | Description | Type | Mandatory | Example of value |
|---|---|---|---|---|
| previous | Reference to a record previously stored in the vault, that has to be modified | co:RecordBase | Yes | - |
| current | The new record that shall replace the old one referenced in “previous” | FixedOddsRecord | Yes | - |

#### 4.4.3 FixedOddsCancellation

| Field | Description | Type | Mandatory | Example of value |
|---|---|---|---|---|
| previous | Reference to a record previously stored in the vault that has to be canceled. | co:RecordRef | Yes | - |
| Cancellation | The cancellation record that invalidates the one referenced in”previous” | co:RecordBase | Yes | - |

#### 4.4.4 EventCatalog (CEV)

**Goal**

The EventCatalogRecord references any single event upon which the operator may accept bets. It shall contain all the events on which the operator has accepted bets on in the previous month.

You have to ensure that all the events involved in any bet placement, settlement or resettlement record have been reported in the CEV of that month or a previous CEV record. This is important for edge cases. For instance when the operator reports settlement or resettlement of bets placed before the operator started reporting the CEV records.

Although it is allowed to report an event in several CEV records, the DGOJ prefers a given event to be reported only once, when the operator starts accepting bets on the event, but not in later CEV records even if the operator continues accepting bets involving this event in the following months.

If an event is reported in several CEV records, the data reported for this event has to be exactly the same in all the CEV reporting the event. In the end, the DGOJ will consider the eventStartDate and eventEndDate reported in the JU as the real dates for the event.

**Concerned operators**

Operators who offer bets.

**Trigger**

This record is to be submitted monthly.

One of such records may not describe more than 1 000 events. If you want to report more than 1 000 events, you have to split the record into subrecords, each of them containing exactly 1 000 events but the last one.

| Field | Description | Type | Mandatory | Example of value |
|---|---|---|---|---|
| operatorId | ID of the operator (given by DGOJ) managing the bet | xs:string | Yes |  |
| recordId | ID provided by the operator to identify the record that will be stored in the vault. This ID : - allows the regulator to consolidate all the subrecords together - has to be used when a record has to be replaced or canceled This ID has to be unique for a given vault. | xs:string | Yes | 743e-422e-21da-3c1d |
| subRecordId | This has to be a number between 1 and the value of the next field (subRecordTotal) included | xs:positiveInteger | Yes | 1 |
| subRecordTotal | Number of subrecords. Subrecords are used when this record involves more than 1 000 events. In that case, records are split in subrecords per slice of 1 000 events | xs:positiveInteger | Yes | 1 |
| date | Date/time on which the record is generated, not the time the vault is called – This date will be required in an optional replacement or cancellation call | xs:dateTime | Yes | 2011-10-04T19:45:51.346+02:00 |
| month | The month this record regards | co:date-yyyymm | Yes | 201406 |
| event | List of events on which bet have been accepted in the previous month | Event | No | - |

#### 4.4.4.1 EventCatalog.Event type

| Field | Description | Type | Mandatory | Example of value |
|---|---|---|---|---|
| eventId | This is the ID that has been used to reference this event in all the bets placed during the previous month. Using a UUID is recommended | xs:string | Yes | 585ab-687fe-56aa-5445 |
| eventDescription | Humand readable description of the event as it appears to the players | xs:string | Yes | “Manchester – Barça 12/11/2011” |
| eventStartDate | Date of the start of the event | xs:dateTime | Yes | 2011-10-05T19:44:51.346+02:00 |
| eventEndDate | Date of the end of the event | xs:dateTime | Yes | 2011-10-06T19:44:51.346+02:00 |
| eventType | This describes the category of the event at a high level. The only accepted values are: - “D” : sports competition - “H” : horse racing - “O” : other categories | xs:string | Yes | “H” |
| market | Numerical value identifying the sport involved in the event. The operator shall verify the existence of the sport on the list provided. If it is on the list, the operator must use the code on the list, for example to indicate the sport of Sailing, code "43" will be used. If it is not on the list, the operator shall apply via the electronic office for inclusion of the corresponding sport, until then using type "999. (<nombre_deporte>)” [sport_name], including the name of the sport in question in brackets. The DGOJ web site will maintain an updated list of sports. It will not be necessary for the list to be updated for the operator to be able to market the sport in question This field can only take one of the following values: 1. Athletics 2. Motor sports 3. Badminton 4. Basketball 5. Handball 6. Baseball 7. Biathlon, Triathlon, others 8. Billiards 9. Boxing 10. Cycling 11. Cyclo-cross 12. Cricket 13. Darts 14. Winter sports 15. Equestrianism 16. Fencing 17. Football 18. American football | co:SportCode | Yes | 13 |

**IDEMIA RESTRICTED**

D3S Developer's Guide, SAFE Integration Guide – Datamodel Version 2.11  
Ref.: Morpho_D3S_JEL_DeveloperGuide_WSES – version 3.5.8 39/90  
Communication, reproduction or use prohibited without prior authorization of Morpho

19. Australian rules football  
20. Futsal  
21. Gymnastics  
22. Golf  
23. Weightlifting  
24. Ice hockey  
25. Field hockey  
26. Roller hockey  
27. Judo  
28. Wrestling for “Freestyle wrestling”  
29. Motorcycle  
30. Swimming  
31. Padel tennis  
32. Skating  
33. Basque pelota  
34. Rowing  
35. Rugby  
36. Snooker  
37. Squash  
38. Taekwondo  
39. Tennis  
40. Table tennis  
41. Archery  
42. Sports Shooting  
43. Sailing  
44. Volleyball  
45. Beach volleyball  
46. Water polo  
47. Chess  
48. Apnea  
49. Fistball  
50. Beach Handball  
51. Lawn bowling  
52. Bowling  
53. Curling  
54. Combat Sport  
55. Gaelic Games  
56. Basque Sports  
57. Floorball  
58. Indoor Football  
59. Beach Soccer  
60. Lacrosse  
61. Netball  
62. Pétanque  
63. Canoeing  
64. Kiiking  
65. Softball  
66. Surf  
67. Bandy  
68. MMA-Mixed Martial Art  
69. Indoor bowling  
70. Pesäpallo  
71. WWE Wrestling  
72. Sumo  
73. Sepak takraw  
998. neither sport nor horse  
999. other sport : If the sport does not exist in the list, then use “999” and fill the next field.

| Field | Description | Type | Mandatory | Example of value |
|---|---|---|---|---|
| otherMarket | This field is only used when the previous one is “999”. In this case, this field describes the new market | xs:string | No | Pigeon race |
| competition | This field describes the competition the event belongs to, if any. For instance, many events may belong to the same competition (championship, world cup, …) | xs:string | No | “Football worldcup 2014” |

#### 4.4.5 BettingSummary (JUT)

**Goal**

The BettingSummary shall contain information about each combination of sports, competitions, events and facts upon which bets are placed.

**Concerned operators**

This record shall be submitted by every operator that manages the game, either completely or network operators managing a co-organised network. Operators who only manage players but not games do not submit this record.

**Trigger**

Games Records data must be generated in real time by the operator's system in such a way that information about the event is collected as it occurs in the system.

The events shall be reported the moment when the events involved in the bet are known

Corrections, cancellations or adjustments to bets must be reported individually in the BetAdjustmentRecord. This file shall collect any correction or adjustment to bets already made, indicating the amounts and reasons.

When a variation in gaming records is due to reasons other than from the normal operation of the games, such as errors in the generation of the report or other errors of a technical nature, the transmission of the correct data shall be made by means of a record replacement.

| Field | Description | Type | Mandatory | Example of value |
|---|---|---|---|---|
| operatorId | ID of the operator (given by DGOJ) managing the bet | xs:string | Yes |  |
| recordId | ID provided by the operator to identify the record that will be stored in the vault. This ID : - allows the regulator to consolidate all the subrecords together - has to be used when a record has to be replaced or canceled This ID has to be unique for a given vault. | xs:string | Yes | 743e-422e-21da-3c1d |
| subRecordId | Should always be 1 since this record is never split. | xs:positiveInteger | Yes | 1 |
| subRecordTotal | Should always be 1 since this record is never split. | xs:positiveInteger | Yes | 1 |
| date | Date/time on which the record is generated, not the time the vault is called – This date will be required in an optional replacement or cancellation call | xs:dateTime | Yes | 2011-10-04T19:45:51.346+02:00 |
| gameId | Unique identifier of the bet instance | xs:string | Yes | PJD24DS |
| gameDesc | Human readable description of the bet instance | xs:string | Yes | “Manchester – Barça match 12/11/2011” |
| gameType | Type of the bet | co:GameType | Yes | - |
| startDate | Date at which the first events starts | xs:dateTime | Yes | 2011-10-04T19:44:51.346+02:00 |
| endDate | Date at which the last event ends | xs:dateTime | Yes | 2011-10-05T19:44:51.346+02:00 |
| networkGame | Is the game organized between several operators in a network | xs:boolean | Yes | “true” |
| postponed | Has the game been postponed | xs:boolean | No | “false” |
| suspended | Has the game been suspended | xs:boolean | No | “false” |
| canceled | Has the game been canceled | xs:boolean | No | “false” |
| internationalLiq | report games with International liquidity | xs:boolean | No | “false” |
| total | Complex type that includes subfields giving the total amount of participation, and the breakdown for each involved operator | Total | Yes | - |
| live | Is this a live bet. If one of the related events is live, then the whole bet is live | xs:boolean | Yes | ”false” |
| betType | Type of bet restricted to the following values: -“Simple” -“Multiple” -“Complex” If the bet has a single leg on a single event, choose “Simple”. If the bet is composed of several legs, all of them involving the same event, choose “Multiple” (i.e. Barça wins and no penalty in the game). Everything else is “Complex” (i.e. a bet involving several events). | xs:string | Yes | Simple |
| events | List of description of the events on which the game is based | Events | Yes | - |
| numberOfBettors | Number of bettors | xs:nonNegativeInteger | Yes | 263 |

#### 4.4.5.1 BettingSummary.Total type

| Field | Description | Type | Mandatory | Example of value |
|---|---|---|---|---|
| placement | Amount wagered toward the game itself (including contributions to jackpots) on this instance. This value is negative. | co:OperatorBreakdown | Yes | - |
| refund | Amount refunded to the player if the game is canceled for any reason. This value is positive | co:OperatorBreakdown | Yes | - |
| inKindPrizes | Value of all the winnings in kind during this instance. This value is positive. | co:OperatorBreakdown | Yes | - |
| cashWinnings | Value of all the cash winnings during this instance (including winnings from jackpots). This value is positive. | co:OperatorBreakdown | Yes | - |
| jackpot | Amount contributed to the jackpot during this instance (minus the amount distributed from the jackpot if it has been released during this instance). The value may be positive or negative | co:JackpotBreakdown | Yes | - |

#### 4.4.5.2 BettingSummary.Events type

| Field | Description | Type | Mandatory | Example of value |
|---|---|---|---|---|
| eventID | This is the ID used to reference this event in the EventCatalog as it was transmitted in the EventCatalogRecord. Using a UUID is recommended | xs:string | Yes | 585ab-687fe-56aa-5445 |
| outcome | The outcome of the event that allowed the bets to be settled | xs:string | Yes | “Manschester wins 2/0” |
| outcomeDate | The date and time the outcome has been known. | xs:dateTime | Yes | 2014-10-06T19:44:51.346+02:00 |

#### 4.4.6 BetAdjustment (JUA)

**Goal**

The BetAdjustmentRecord describes all the bet resettlements: adjustments made to bets after the winnings have been determined.

You have to ensure that all the events involved in any bet placement, settlement or resettlement record have been reported in the CEV of that month or a previous CEV record. This is important for edge cases. For instance when the operator reports settlement or resettlement of bets placed before the operator started reporting the CEV records.

**Concerned operators**

This record must be transmitted by every operator managing the bets under his license, either completely or a managing the bets of co-organised betting network.

**Trigger**

This record is submitted every month. In the event that there is no adjustment during the period, the record will still be generated, with empty content.

One of such records may not describe more than 1 000 adjustments. If you want to report more than 1 000 adjustments, you have to split the record into subrecords, each of them containing exactly 1 000 adjustments but the last one.

| Field | Description | Type | Mandatory | Example of value |
|---|---|---|---|---|
| operatorId | ID of the operator (given by DGOJ) managing the bet | xs:string | Yes |  |
| recordId | ID provided by the operator to identify the record that will be stored in the vault. This ID : - allows the regulator to consolidate all the subrecords together - has to be used when a record has to be replaced or canceled This ID has to be unique for a given vault. | xs:string | Yes | 743e-422e-21da-3c1d |
| subRecordId | This has to be a number between 1 and the value of the next field (subRecordTotal) included | xs:positiveInteger | Yes | 1 |
| subRecordTotal | Number of subrecords. Subrecords are used when this record involves more than 1 000 adjustments. In that case, records are split in subrecords per slice of 1 000 adjustments | xs:positiveInteger | Yes | 1 |
| date | Date/time on which the record is generated, not the time the vault is called – This date will be required in an optional replacement or cancellation call | xs:dateTime | Yes | 2011-10-04T19:45:51.346+02:00 |
| month | The month this record relate to | co:date-yyyymm | Yes | 201406 |
| adjustment | List of all the bet adjustments of the previous month | Adjustment | No | - |

#### 4.4.6.1 BetAdjustment.Adjustment

| Field | Description | Type | Mandatory | Example of value |
|---|---|---|---|---|
| eventID | This is the ID used to reference this adjusted event in the EventCatalog as it was transmitted in the EventCatalogRecord. This field provides the eventID of the event involved in the resettlement, not all the eventIDs associated with the bet. You may provide more than one “eventID” field Using a UUID is recommended | xs:string | Yes | 543ab-65fe-5694-5445 |
| betID | Unique identifier of the bet. This ID has to be unique across the whole information system. Different players or different bets may never share the same betID. Using a UUID is recommended | xs:string | Yes | 693ab-68fe-56caa-5489 |
| playerID | The playerID of the player impacted by the adjustment | co:PlayerID | Yes | BigJoe43 |
| adjustmentDate | This is the number or events involved in this bet | xs:dateTime | Yes | 2011-10-04T19:45:51.346+02:00 |
| adjustmentReason | This is a human readbale description of the reason for the adjustment | xs:string | Yes | Players have been convinced of rigging the game |
| adjustmentAmount | This describes the amount of the ajustments to the winnings of this betID (the betID identifies the player uniquely as well) If the player earned more money in the end, the sign is positive. It is negative otherwise | Amount | Yes | - |

### 4.5 Casino Types

#### 4.5.1 CasinoRecord

| Field | Description | Type | Mandatory | Example of value |
|---|---|---|---|---|
| Choice |  |  |  |  |
| sessionTotal | The total transferred money and various breakdown of a game of roulette, blackjack, slots or other games | SessionTotal | Yes | - |
| baccaraTotal | The total transferred money and various breakdown of a baccare | BaccaraTotal | Yes | - |
| gameDetails | The details of a game (Roulette, blackjack or baccara) | co:GameRecordDetails | Yes | - |

#### 4.5.2 CasinoReplacement

| Field | Description | Type | Mandatory | Example of value |
|---|---|---|---|---|
| previous | Reference to a record previously stored in the vault, that has to be modified | co:RecordBase | Yes | - |
| current | The new record that shall replace the old one referenced in “previous” | CasinoRecord | Yes | - |

#### 4.5.3 CasinoCancellation

| Field | Description | Type | Mandatory | Example of value |
|---|---|---|---|---|
| previous | Reference to a record previously stored in the vault,that has to be canceled. | co:RecordRef | Yes | - |
| Cancellation | The cancellation record that invalidates the one referenced in”previous” | co:RecordBase | Yes | - |

#### 4.5.4 SessionTotal (JUT)

**Goal**

The SessionTotal shall contain information about each game session of roulette, blackjack, slots and complementary games.

**Concerned operators**

This record shall be submitted by every operator that manages the game, either completely or network operators managing a co-organised network. Operators who only manage players but not games do not submit this record.

**Trigger**

Games Records data must be generated in real time by the operator's system in such a way that information about the event is collected as it occurs in the system.

The events shall be recorded at the end of the session

Corrections, cancellations or adjustments to games made after their original transmission to the SAFE shall be reported as rectifications, it being in no case possible to erase the original corrected, cancelled or adjusted transaction.

When a variation in gaming records is due to reasons other than from the normal operation of the games, such as errors in the generation of the report or other errors of a technical nature, the transmission of the correct data shall be made by means of a record replacement.

**Gaming Session**

A gaming session of a player is the elapsed time a player spends playing on a game.

Slots: the session is the set of game rounds carried out by the player, whether it is in one or in several slot machines, as long as he is connected to a slot machine

**IDEMIA RESTRICTED**

D3S Developer's Guide, SAFE Integration Guide – Datamodel Version 2.11  
Ref.: Morpho_D3S_JEL_DeveloperGuide_WSES – version 3.5.8 45/90  
Communication, reproduction or use prohibited without prior authorization of Morpho

Other games: for other games that are to be reported by session, it is allowed to report in any of the following ways:

- Effective gaming session, time really spent in participating to the game
- User session
- Single round, hand, etc ..

| Field | Description | Type | Mandatory | Example of value |
|---|---|---|---|---|
| operatorId | ID of the operator (given by DGOJ) managing the game | xs:string | Yes | “P24331102” |
| recordId | ID provided by the operator to identify the record that will be stored in the vault. This ID : - allows the regulator to consolidate all the subrecords together - has to be used when a record has to be replaced or canceled This ID has to be unique for a given vault. | xs:string | Yes | 743e-422e-21da-3c1d |
| subRecordId | This has to be a number between 1 and the nextField “subRecordTotal” included. Should always be 1 since this record is never split. | xs:positiveInteger | Yes | 1 |
| subRecordTotal | Should always be 1 since this record is never split. | xs:positiveInteger | Yes | 1 |
| date | Date/time on which the record is generated, not the time the vault is called – This date will be required in an optional replacement or cancellation call | xs:dateTime | Yes | 2011-10-06T19:44:51.346+02:00 |
| gameId | Game identifier | xs:string | Yes | “PJHD442” |
| gameDesc | Description of the game | xs:string | Yes | “Roulette table 4 – draw 463” |
| gameType | Type of game | co:GameType | Yes | - |
| startDate | Date at which the game started | xs:dateTime | Yes | 2011-10-06T19:44:51.346+02:00 |
| endDate | Date at which the game ended | xs:dateTime | Yes | 2011-10-06T19:44:51.346+02:00 |
| networkGame | Is the game organized between several operators in a network | xs:boolean | Yes | “true” |
| postponed | Has the game been postponed | xs:boolean | No | “false” |
| suspended | Has the game been suspended | xs:boolean | No | “false” |
| canceled | Has the game been canceled | xs:boolean | No | “false” |
| internationalLiq | report games with International liquidity | xs:boolean | No | “false” |
| total | Complex type that includes subfields giving the total amount of participation, and the breakdown for each involved operator | SessionTotal.Total | Yes | - |
| variant | This is the variant of the game when it exists. For roulette: - “French” - “American” For blackjack: - “CL”: Clasico - “AM””: Americano - “PO”: Pontoon - “SU”: Surrender - “21”: Super21 For other games, do not provide this field If several different variants have been used during the same sessions, all of them have to be indicated in this field and separated by commas | co:SessionVariant | No | “French” |
| commercialVariant | This is the name used by the operator to describe this specific variant to the player. Should be be filled for: - Roulette - Blackjack - Slots - Complementary games If several different commercial variants have been used during the same sessions, all of them have to be indicated in this field and separated by commas | xs:string | No |  |
| roundsPlayed | This describes the number of games/hands/rounds played during this session | xs:positiveInteger | Yes | 36 |

#### 4.5.4.1 SessionTotal.Total

| Field | Description | Type | Mandatory | Example of value |
|---|---|---|---|---|
| placement | Amount wagered toward the game itself (including contributions to jackpots) during this instance. This value is negative. | OperatorBreakdown | Yes | - |
| refund | Amount refunded to the player if the game is canceled for any reason. This value is positive | OperatorBreakdown | Yes | - |
| inKindPrizes | Value of all the winnings in kind during this instance. This value is positive. | OperatorBreakdown | Yes | - |
| cashWinnings | Value of all the cash winnings during this instance (including winnings from jackpots). This value is positive. | OperatorBreakdown | Yes | - |
| jackpot | Amount contributed to the jackpot during this instance (minus the amount distributed from the jackpot if it has been released during this instance). The value may be positive or negative | JackpotBreakdown | Yes | - |

#### 4.5.5 BaccaraTotal (JUT)

**Goal**

The BaccaraTotal shall contain information about each hand of baccarat / punto banco

**Concerned operators**

This record shall be submitted by every operator that manages the game, either completely or network operators managing a co-organised network. Operators who only manage players but not games do not submit this record.

**Trigger**

Games Records data must be generated in real time by the operator's system in such a way that information about the event is collected as it occurs in the system at the end of the hand.

Corrections, cancellations or adjustments to games made after their original transmission to the SAFE shall be reported as rectifications, it being in no case possible to erase the original corrected, cancelled or adjusted transaction

When a variation in gaming records is due to reasons other than from the normal operation of the games, such as errors in the generation of the report or other errors of a technical nature, the transmission of the correct data shall be made by means of a record replacement.

| Field | Description | Type | Mandatory | Example of value |
|---|---|---|---|---|
| operatorId | ID of the operator (given by DGOJ) managing the game | xs:string | Yes | “P24331102” |
| recordId | ID provided by the operator to identify the record that will be stored in the vault. This ID : - allows the regulator to consolidate all the subrecords together - has to be used when a record has to be replaced or canceled This ID has to be unique for a given vault. | xs:string | Yes | 743e-422e-21da-3c1d |
| subRecordId | Should always be 1 since this record is never split. | xs:positiveInteger | Yes | 1 |
| subRecordTotal | Should always be 1 since this record is never split. | xs:positiveInteger | Yes | 1 |
| date | Date/time on which the record is generated, not the time the vault is called – This date will be required in an optional replacement or cancellation call | xs:dateTime | Yes | 2011-10-06T19:44:51.346+02:00 |
| gameId | Game identifier | xs:string | Yes | “PJHD442” |
| gameDesc | Description of the game | xs:string | Yes | “Baccara table 4 - hand 12” |
| gameType | Type of game | GameType | Yes | - |
| startDate | Date at which the game started | xs:dateTime | Yes | 2011-10-06T19:44:51.346+02:00 |

**IDEMIA RESTRICTED**

D3S Developer's Guide, SAFE Integration Guide – Datamodel Version 2.11  
Ref.: Morpho_D3S_JEL_DeveloperGuide_WSES – version 3.5.8 48/90  
Communication, reproduction or use prohibited without prior authorization of Morpho

| Field | Description | Type | Mandatory | Example of value |
|---|---|---|---|---|
| endDate | Date at which the game ended | xs:dateTime | Yes | 2011-10-06T19:44:51.346+02:00 |
| networkGame | Is the game organized between several operators in a network | xs:boolean | Yes | “true” |
| postponed | Has the game been postponed | xs:boolean | No | “false” |
| suspended | Has the game been suspended | xs:boolean | No | “false” |
| canceled | Has the game been canceled | xs:boolean | No | “false” |
| internationalLiq | Report games with International liquidity | xs:boolean | No | “false” |
| total | Complex type that includes subfields giving the total amount of participation, and the breakdown for each involved operator | BaccareTotal.Total | Yes | - |

#### 4.5.5.1 BaccaraTotal.Total

| Field | Description | Type | Mandatory | Example of value |
|---|---|---|---|---|
| placement | Amount wagered toward the game itself (including contributions to jackpots) during this instance. This value is negative. | OperatorBreakdown | Yes | - |
| refund | Amount refunded to the player if the game is canceled for any reason. This value is positive | OperatorBreakdown | Yes | - |
| inKindPrizes | Value of all the winnings in kind during this instance. This value is positive. | OperatorBreakdown | Yes | - |
| cashWinnings | Value of all the cash winnings during this instance (including winnings from jackpots). This value is positive. | OperatorBreakdown | Yes | - |
| jackpot | Amount contributed to the jackpot during this instance (minus the amount distributed from the jackpot if it has been released during this instance). The value may be positive or negative | JackpotBreakdown | Yes | - |

### 4.6 PVP Types

#### 4.6.1 PVPRecord

| Field | Description | Type | Mandatory | Example of value |
|---|---|---|---|---|
| Choice |  |  |  |  |
| bingoTotal | The total transferred money and various breakdown of a bingo game | BingoTotal | Yes | - |
| contestTotal | The total transferred money and various breakdown of a contest game | ContestTotal | Yes | - |
| gameDetails | The details of a game (Bingo, Contest game or social game) | co:GameRecordDetails | Yes | - |

#### 4.6.2 PVPReplacement

| Field | Description | Type | Mandatory | Example of value |
|---|---|---|---|---|
| previous | Reference to a record previously stored in the vault, that has to be modified | co:RecordBase | Yes | - |
| current | The new record that shall replace the old one referenced in “previous” | PVPRecord | Yes | - |

#### 4.6.3 PVPCancellation

| Field | Description | Type | Mandatory | Example of value |
|---|---|---|---|---|
| previous | Reference to a record previously stored in the vault that has to be canceled. | co:RecordRef | Yes | - |
| cancellation | The cancellation record that invalidates the one referenced in”previous” | co:RecordBase | Yes | - |

#### 4.6.4 BingoTotal (JUT)

**Goal**

The BingoTotal record shall contain information each game of bingo

**Concerned operators**

This record shall be submitted by every operator that manages the game, either completely or network operators managing a co-organised network. Operators who only manage players but not games do not submit this record.

**Trigger**

Games Records data must be generated in real time by the operator's system in such a way that information about the event is collected as it occurs in the system at the end of the bingo game.

Corrections, cancellations or adjustments to games made after their original transmission to the SAFE shall be reported as rectifications, it being in no case possible to erase the original corrected, cancelled or adjusted transaction.

When a variation in gaming records is due to reasons other than from the normal operation of the games, such as errors in the generation of the report or other errors of a technical nature, the transmission of the correct data shall be made by means of a record replacement.

| Field | Description | Type | Mandatory | Example of value |
|---|---|---|---|---|
| operatorId | ID of the operator (given by DGOJ) managing the game | xs:string | Yes | “P24331102” |
| recordId | ID provided by the operator to identify the record that will be stored in the vault. This ID : - allows the regulator to consolidate all the subrecords together - has to be used when a record has to be replaced or canceled This ID has to be unique for a given vault. | xs:string | Yes | 743e-422e-21da-3c1d |
| subRecordId | Should always be 1 since this record is never split. | xs:positiveInteger | Yes | 1 |
| subRecordTotal | Should always be 1 since this record is never split. | xs:positiveInteger | Yes | 1 |
| date | Date/time on which the record is generated, not the time the vault is called – This date will be required in an optional replacement or cancellation call | xs:dateTime | Yes | 2011-10-06T19:44:51.346+02:00 |
| gameId | Game identifier | xs:string | Yes | “PJHD442” |
| gameDesc | Description of the game | xs:string | Yes | “Bingo room 4 - round 12” |
| gameType | Type of game | GameType | Yes | - |
| startDate | Date at which the game started | xs:dateTime | Yes | 2011-10-06T19:44:51.346+02:00 |
| endDate | Date at which the game ended | xs:dateTime | Yes | 2011-10-06T19:44:51.346+02:00 |
| networkGame | Is the game organized between several operators in a network | xs:boolean | Yes | “true” |
| postponed | Has the game been postponed | xs:boolean | No | “false” |
| suspended | Has the game been suspended | xs:boolean | No | “false” |
| canceled | Has the game been canceled | xs:boolean | No | “false” |
| internationalLiq | Report games with International liquidity | xs:boolean | No | “false” |
| total | Complex type that includes subfields giving the total amount of participation, and the breakdown for each involved operator | BingoTotal.Total | Yes | - |
| priceBingoCard | Price of a Bingo card | co:Euros | Yes | 2 |

#### 4.6.4.1 BingoTotal.Total

| Field | Description | Type | Mandatory | Example of value |
|---|---|---|---|---|
| placement | Amount wagered toward the game itself (including contributions to jackpots) during this instance. This value is negative. | OperatorBreakdown | Yes | - |
| refund | Amount refunded to the player if the game is canceled for any reason. This value is positive | OperatorBreakdown | Yes | - |
| inKindPrizes | Value of all the winnings in kind during this instance. This value is positive. | OperatorBreakdown | Yes | - |
| cashWinnings | Value of all the cash winnings during this instance (including winnings from jackpots). This value is positive. | OperatorBreakdown | Yes | - |
| jackpot | Amount contributed to the jackpot during this instance (minus the amount distributed from the jackpot if it has been released during this instance). The value may be positive or negative | JackpotBreakdown | Yes | - |

#### 4.6.5 ContestTotal (JUT)

**Goal**

The ContestTotal shall contain information about each contest.

**Concerned operators**

This record shall be submitted by every operator that manages the game, either completely or network operators managing a co-organised network. Operators who only manage players but not games do not submit this record.

**Trigger**

Games Records data must be generated in real time by the operator's system in such a way that information about the event is collected as it occurs in the system at the end of each contest.

Corrections, cancellations or adjustments to games made after their original transmission to the SAFE shall be reported as rectifications, it being in no case possible to erase the original corrected, cancelled or adjusted transaction.

When a variation in gaming records is due to reasons other than from the normal operation of the games, such as errors in the generation of the report or other errors of a technical nature, the transmission of the correct data shall be made by means of a record replacement.

| Field | Description | Type | Mandatory | Example of value |
|---|---|---|---|---|
| operatorId | ID of the operator (given by DGOJ) managing the game | xs:string | Yes | “P24331102” |
| recordId | ID provided by the operator to identify the record that will be stored in the vault. This ID : - allows the regulator to consolidate all the subrecords together - has to be used when a record has to be replaced or canceled This ID has to be unique for a given vault. | xs:string | Yes | 743e-422e-21da-3c1d |
| subRecordId | Should always be 1 since this record is never split. | xs:positiveInteger | Yes | 1 |
| subRecordTotal | Should always be 1 since this record is never split. | xs:positiveInteger | Yes | 1 |
| date | Date/time on which the record is generated, not the time the vault is called – This date will be required in an optional replacement or cancellation call | xs:dateTime | Yes | 2011-10-06T19:44:51.346+02:00 |
| gameId | Game identifier | xs:string | Yes | “PJHD442” |
| gameDesc | Description of the game | xs:string | Yes | “Contest Love story day 6” |
| gameType | Type of game | co:GameType | Yes | - |
| startDate | Date at which the game started | xs:dateTime | Yes | 2011-10-06T19:44:51.346+02:00 |
| endDate | Date at which the game ended | xs:dateTime | Yes | 2011-10-06T19:44:51.346+02:00 |
| networkGame | Is the game organized between several operators in a network | xs:boolean | Yes | “true” |
| postponed | Has the game been postponed | xs:boolean | No | “false” |
| suspended | Has the game been suspended | xs:boolean | No | “false” |
| canceled | Has the game been canceled | xs:boolean | No | “false” |
| internationalLiq | Report games with International liquidity | xs:boolean | No | “false” |
| total | Complex type that includes subfields giving the total amount of participation, and the breakdown for each involved operator | ContestTotal.Total | Yes | - |
| numberOfPlayers | Total number of players in the contest | xs nonNegativeInteger | Yes | 134561 |
| numberOfWinners | Total number of winners | xs nonNegativeInteger | Yes | 123 |
| numberOfCalls | Total number of phone calls made during the contest | xs nonNegativeInteger | Yes | 342512 |
| minuteCallPrice | Price per minute paid by the player during the phone call | co:Euros | Yes | 0.10 |
| maxCallPrice | Maximum amount paid by a player within a single call | co:Euros | Yes | 1.1 |
| callPriceTotal | Total amount paid by players for calls, all inclusive (call and premium rate) | co:Euros | Yes | 34251.20 |
| callPremiumTotal | Total amount of premium cost paid on the calls by the players. This is the amount that goes to the telecom operator | co:Euros | Yes | 1234.30 |
| NumberOfSMS | Total number of SMS sent | xs nonNegativeInteger | Yes | 134561 |
| SMSPrice | Price of SMS. If multiple prices,indicate the maximum | co:Euros | Yes | 0.10 |
| SMSPriceTotal | Total sum of the amounts paid by all players for their SMS, all inclusive. SMSPriceTotal = SMSPremiumTotal + SMSTelcoPrice + Jackpot. | co:Euros | Yes | 3506.20 |
| SMSPremiumTotal | This the part of the SMSPriceTotal that goes to the gaming operator (not the telco). In other words, this is the placement. In case of you are the SMS service provider, or the SMS aggregator, (not the telco), SMSPremiumTotal = placement. But if you are only a service provider behind the SMS aggregator, SMSPremiumTotal = Placement + SMSPriceGotByAggregator. | co:Euros | Yes | 2075.05 |

#### 4.6.5.1 ContestTotal.Total

| Field | Description | Type | Mandatory | Example of value |
|---|---|---|---|---|
| placement | Amount wagered toward the game itself (including contributions to jackpots) during this instance. This value is negative. | OperatorBreakdown | Yes | - |
| refund | Amount refunded to the player if the game is canceled for any reason. This value is positive | OperatorBreakdown | Yes | - |
| inKindPrizes | Value of all the winnings in kind during this instance (including winnings from jackpots). This value is positive. | OperatorBreakdown | Yes | - |
| cashWinnings | Value of all the cash winnings during this instance (including winnings from jackpots). This value is positive. | OperatorBreakdown | Yes | - |
| jackpot | Amount contributed to the jackpot during this instance (minus the amount distributed from the jackpot if it has been released during this instance). The value may be positive or negative | JackpotBreakdown | Yes | - |

### 4.7 Poker-Cash Game Types

#### 4.7.1 PokerCashGameRecord

| Field | Description | Type | Mandatory | Example of value |
|---|---|---|---|---|
| Choice |  |  |  |  |
| pokerCashGameTotal | The total transferred money and various breakdown of a poker cash game | PokerCashGameTotal | Yes | - |
| pokerCashGameDetails | The details of a poker cash game | co:GameRecordDetails | Yes | - |

#### 4.7.2 PokerCashGameReplacement

| Field | Description | Type | Mandatory | Example of value |
|---|---|---|---|---|
| previous | Reference to a record previously stored in the vault, that has to be modified | co:RecordBase | Yes | - |
| current | The new record that shall replace the old one referenced in “previous” | PokerCashGameRecord | Yes | - |

#### 4.7.3 PokerCashGameCancellation

| Field | Description | Type | Mandatory | Example of value |
|---|---|---|---|---|
| previous | Reference to a record previously stored in the vault that has to be canceled. | co:RecordRef | Yes | - |
| cancellation | The cancellation record that invalidates the one referenced in”previous” | co:RecordBase | Yes | - |

#### 4.7.4 PokerCashGameTotal (JUT)

**Goal**

The GameRecordDetails shall contain information about each hand of poker cash game.

**Concerned operators**

This record shall be submitted by every operator that manages the game, either completely or network operators managing a co-organised network. Operators who only manage players but not games do not submit this record.

**Trigger**

Games Records data must be generated in real time by the operator's system at the end of the poker hand.

Corrections, cancellations or adjustments to games made after their original transmission to the SAFE shall be reported as rectifications, it being in no case possible to erase the original corrected, cancelled or adjusted transaction.

When a variation in gaming records is due to reasons other than from the normal operation of the games, such as errors in the generation of the report or other errors of a technical nature, the transmission of the correct data shall be made by means of a record replacement.

| Field | Description | Type | Mandatory | Example of value |
|---|---|---|---|---|
| operatorId | ID of the operator (given by DGOJ) managing the game | xs:string | Yes | “P24331102” |
| recordId | ID provided by the operator to identify the record that will be stored in the vault. This ID : - allows the regulator to consolidate all the subrecords together - has to be used when a record has to be replaced or canceled This ID has to be unique for a given vault. | xs:string | Yes | 743e-422e-21da-3c1d |
| subRecordId | Should always be 1 since this record is never split. | xs:positiveInteger | Yes | 1 |
| subRecordTotal | Should always be 1 since this record is never split. | xs:positiveInteger | Yes | 1 |
| date | Date/time on which the record is generated, not the time the vault is called – This date will be required in an optional replacement or cancellation call | xs:dateTime | Yes | 2011-10-06T19:44:51.346+02:00 |
| gameId | Game identifier | xs:string | Yes | “PJHD442” |
| gameDesc | Description of the game | xs:string | Yes | “Poker table 4 - hand 12” |
| gameType | Type of game | GameType | Yes | - |
| startDate | Date at which the game started | xs:dateTime | Yes | 2011-10-06T19:44:51.346+02:00 |
| endDate | Date at which the game ended | xs:dateTime | Yes | 2011-10-06T19:44:51.346+02:00 |
| networkGame | Is the game organized between several operators in a network | xs:boolean | Yes | “true” |
| postponed | Has the game been postponed | xs:boolean | No | “false” |
| suspended | Has the game been suspended | xs:boolean | No | “false” |
| canceled | Has the game been canceled | xs:boolean | No | “false” |
| internationalLiq | Report games with International liquidity | xs:boolean | No | “false” |
| total | Complex type that includes subfields giving the total amount of participation, and the breakdown for each involved operator | PokerCashGameTotal.Total | Yes | - |
| variant | Poker variant. This value is a two letter abbreviation of the poker variant used : - TH – Texas Hold’em - DR – Draw - OM – Omaha - ST – Stud | xs:string | Yes | ST |
| commercialVariant | This is the name that the operator is commercializing this game variant as. Should be filled for poker cash game | xs:string | No | “Flash Poker” |
| tableId | Identifier of the table on which the game took place | xs:string | Yes | “T343341” |

#### 4.7.4.1 PokerCashGameTotal.Total

| Field | Description | Type | Mandatory | Example of value |
|---|---|---|---|---|
| placement | Amount wagered toward the game itself (including contributions to jackpots) during this instance. This value is negative. | OperatorBreakdown | Yes | - |
| refund | Amount refunded to the player if the game is canceled for any reason. This value is positive | OperatorBreakdown | Yes | - |
| inKindPrizes | Value of all the winnings in kind during this instance. This value is positive. | OperatorBreakdown | Yes | - |
| cashWinnings | Value of all the cash winnings during this instance (including winnings from jackpots). This value is positive. | OperatorBreakdown | Yes | - |
| jackpot | Amount contributed to the jackpot during this instance (minus the amount distributed from the jackpot if it has been released during this instance). The value may be positive or negative | JackpotBreakdown | Yes | - |

### 4.8 Poker-Tournament Types

#### 4.8.1 PokerTournamentRecord

| Field | Description | Type | Mandatory | Example of value |
|---|---|---|---|---|
| Choice |  |  |  |  |
| pokerTournamentTotal | The total transferred money and various breakdown of a poker tournament | PokerTournamentTotal | Yes | - |
| pokerTournamentDetails | The details of a poker tournament | co:GameRecordDetails | Yes | - |

#### 4.8.2 PokerTournamentReplacement

| Field | Description | Type | Mandatory | Example of value |
|---|---|---|---|---|
| previous | Reference to a record previously stored in the vault, that has to be modified | co:RecordBase | Yes | - |
| current | The new record that shall replace the old one referenced in “previous” | PokerTournamentRecord | Yes | - |

#### 4.8.3 PokerTournamentCancellation

| Field | Description | Type | Mandatory | Example of value |
|---|---|---|---|---|
| previous | Reference to a record previously stored in the vault that has to be canceled. | co:RecordRef | Yes | - |
| cancellation | The cancellation record that invalidates the one referenced in”previous” | co:RecordBase | Yes | - |

#### 4.8.4 PokerTournamentTotal (JUT)

**Goal**

The PokerTournamentTotal shall contain information each poker tournament

**Concerned operators**

This record shall be submitted by every operator that manages the game, either completely or network operators managing a co-organised network. Operators who only manage players but not games do not submit this record.

**IDEMIA RESTRICTED**

D3S Developer's Guide, SAFE Integration Guide – Datamodel Version 2.11  
Ref.: Morpho_D3S_JEL_DeveloperGuide_WSES – version 3.5.8 57/90  
Communication, reproduction or use prohibited without prior authorization of Morpho

**Trigger**

Games Records data must be generated in real time by the operator's system in such a way that information about the event is collected as it occurs in the system at the end of the tournament.

Corrections, cancellations or adjustments to games made after their original transmission to the SAFE shall be reported as rectifications, it being in no case possible to erase the original corrected, cancelled or adjusted transaction.

When a variation in gaming records is due to reasons other than from the normal operation of the games, such as errors in the generation of the report or other errors of a technical nature, the transmission of the correct data shall be made by means of a record replacement.

| Field | Description | Type | Mandatory | Example of value |
|---|---|---|---|---|
| operatorId | ID of the operator (given by DGOJ) managing the tournament | xs:string | Yes | “P24331102” |
| recordId | ID provided by the operator to identify the record that will be stored in the vault. This ID : - allows the regulator to consolidate all the subrecords together - has to be used when a record has to be replaced or canceled This ID has to be unique for a given vault. | xs:string | Yes | 743e-422e-21da-3c1d |
| subRecordId | Should always be 1 since this record is never split. | xs:positiveInteger | Yes | 1 |
| subRecordTotal | Should always be 1 since this record is never split. | xs:positiveInteger | Yes | 1 |
| date | Date/time on which the record is generated, not the time the vault is called – This date will be required in an optional replacement or cancellation call | xs:dateTime | Yes | 2011-10-06T19:44:51.346+02:00 |
| gameId | Game identifier | xs:string | Yes | “PJHD442” |
| gameDesc | Description of the game | xs:string | Yes | “poker tournament Wednesday special 12/01/11” |
| gameType | Type of game | co:GameType | Yes | - |
| startDate | Date at which the game started | xs:dateTime | Yes | 2011-10-06T19:44:51.346+02:00 |
| endDate | Date at which the game ended | xs:dateTime | Yes | 2011-10-06T19:44:51.346+02:00 |
| networkGame | Is the game organized between several operators in a network | xs:boolean | Yes | “true” |
| postponed | Has the game been postponed | xs:boolean | No | “false” |
| suspended | Has the game been suspended | xs:boolean | No | “false” |
| canceled | Has the game been canceled | xs:boolean | No | “false” |
| internationalLiq | Report games with International liquidity | xs:boolean | No | “false” |
| total | Complex type that includes subfields giving the total amount of participation, and the breakdown for each involved operator | PokerTournamentTotal.Total | Yes | - |
| variant | Poker variant. This value is a two letter abbreviation of the poker variant used : - TH – Texas Hold’em - DR – Draw - OM – Omaha - ST – Stud | xs:string | Yes | TH |
| commercialVariant | This is the name that the operator is commercializing this game variant as. Should be filled for poker tournament | xs:string | No | “Flash Poker” |
| numberOfPlayers | Number of participants in the tournament | xs:nonNegativeInteger | Yes | 32423 |

#### 4.8.4.1 PokerTournamentTotal.Total

| Field | Description | Type | Mandatory | Example of value |
|---|---|---|---|---|
| placement | Amount wagered toward the game itself (including contributions to jackpots) during this instance. This value is negative. | OperatorBreakdown | Yes | - |
| refund | Amount refunded to the player if the game is canceled for any reason. This value is positive | OperatorBreakdown | Yes | - |
| inKindPrizes | Value of all the winnings in kind during this instance. This value is positive. | OperatorBreakdown | Yes | - |
| cashWinnings | Value of all the cash winnings during this instance (including winnings from jackpots). This value is positive. | OperatorBreakdown | Yes | - |
| jackpot | Amount contributed to the jackpot during this instance (minus the amount distributed from the jackpot if it has been released during this instance). The value may be positive or negative | JackpotBreakdown | Yes | - |

### 4.9 Player Registration Types

#### 4.9.1 PlayerRecord

| Field | Description | Type | Mandatory | Example of value |
|---|---|---|---|---|
| Choice |  |  |  |  |
| playerRegistrationDetails | Detailed information about the player accounts | PlayerRegistrationDetails | Yes | - |
| playerRegistrationTotal | High level view of the player database, with player count per status | PlayerRegistrationTotal | Yes | - |
| networkPlayerRegistration | Information about the accounts of network players | NetworkPlayerRegistration | Yes | - |
| winnerRegistrationDetails | Information about the winners for certain game types | WinnerRegistrationDetails | Yes | - |

#### 4.9.2 PlayerReplacement

| Field | Description | Type | Mandatory | Example of value |
|---|---|---|---|---|
| previous | Reference to a record previously stored in the vault, that has to be modified | co:RecordBase | Yes | - |
| current | The new record that shall replace the old one referenced in “previous” | PlayerRecord | Yes | - |

#### 4.9.3 PlayerCancellation

| Field | Description | Type | Mandatory | Example of value |
|---|---|---|---|---|
| previous | Reference to a record previously stored in the vault, which has to be canceled. | co:RecordRef | Yes | - |
| Cancellation | The cancellation record that invalidates the one referenced in”previous” | co:RecordBase | Yes | - |

#### 4.9.4 PlayerRegistrationDetails (RUD)

**Goal**

The PlayerRegistrationDetails record contains participants' identification data, those relative to limits on deposits and other configuration data such as the player's status on the gaming platform.

**Concerned operators**

This record must be submitted by operators having a direct relationship with the players and who manage the gaming contracts.

Operators offering games that do not require prior user registration for participation, such as some contest operators, for example, shall not produce these records. Not even for winners or on any other participant.

**Trigger**

The daily record is submitted once a day, the monthly record once a month. This record is submitted even if it “contains” no player data

Daily: The daily user record shall contain the details of new participants or updated participants during the previous day.

Monthly: The monthly user record shall contain the details of every participant existing on the gaming platform, regardless of whether there have been any changes to their data during the previous month. This includes each and every registered user regardless of the status of their account.

This record is submitted even if it “contains” no player data.

One of such records may not describe more than 1 000 players. If you want to report more than 1 000 players, you have to split the record into subrecords, each of them containing exactly 1 000 players but the last one.

| Field | Description | Type | Mandatory | Example of value |
|---|---|---|---|---|
| operatorId | ID of the operator (given by DGOJ) owning/managing the player | xs:string | Yes | 2343434212553 |
| recordId | ID provided by the operator to identify the record that will be stored in the vault. This ID : - allows the regulator to consolidate all the subrecords together - has to be used when a record has to be replaced or canceled This ID has to be unique for a given vault. | xs:string | Yes | 0001-2ea45-6789-2ef11 |
| subRecordId | This has to be a number between 1 and the value of the next field “subRecordTotal” included | xs:positiveInteger | Yes | 2 |
| subRecordTotal | Number of subrecords. Subrecords are used when records involve more than 1 000 players. In that case, records are split in subrecords per slice of 1 000 players | xs:positiveInteger | Yes | 4 |
| date | Date/time the event occurred, not the time the vault is called - Should be stored because the event date requirements in an optional cancellation call | xs:dateTime | Yes | 2011-10-06T19:44:51.346+02:00 |
| periodicity | The periodicity of the record. It may take only 2 values: - PerDay - PerMonth  | co:Periodicity | Yes | “PerDay” |
| period | The period of time the record applies to | co:Period | Yes | - |
| player | The player account details. In rare case there are no player data relevant to this record do not provide this field | Player | No | - |

#### 4.9.4.1 PlayerRegistrationDetails.Player

| Field | Description | Type | Mandatory | Example of value |
|---|---|---|---|---|
| playerId | The operator should always specify the player on its own platform: OperatorId (private operator) + PlayerId. Additionally, if a player participates in network games, the operator must indicate how the player is identified in each of these networks: OperatorId (co-organizer operator) + PlayerId | co:PlayerID | Yes | P2433 |
| registrationDate | This is the date and time the player registered the account. | xs:dateTime | Yes | 2011-10-06T19:44:51.346+02:00 |
| dataChanges | This flag may take three values: - “creation” creation of the player account (this is the first time the account is reported) - “true” some of the player data have been modified - “false” none of the player data have been modified (this value may not be used for daily records) | xs:string | Yes | “true” |
| taxRegion | 2 digit code of the tax province code where the player pays taxes in Spain, identified with the following list. If the player is not a resident, the value is now “22” 01: Andalucía 02: Aragón 03: Asturias 04: Canarias 05: Cantabria 06: Castilla - La Mancha 07: Castilla y León 08: Cataluña 09: Extremadura 10: Galicia 11: Illes Balears 12: La Rioja 13: Madrid 14: Murcia 15: Valencia 16: Diputación Foral de Navarra 17: Diputación Foral de Álava 18: Diputación Foral de Guipúzcoa 19: Diputación Foral de Vizcaya 20: Ceuta 21: Melilla 22: Not resident | xs:string | Yes | “10” |
| Choice |  |  |  |  |
| resident | Choose this if the player is resident in Spain | Resident | Yes | - |
| nonresident | Choose this if the player resides abroad | Nonresident | Yes | - |
| birthdate | The date of birth of the player. | xs:date | Yes | 2011-10-06T19:44:51.346+02:00 |
| login | Login name used by the player to open an instance. It is unique to the operator IS | xs:string | Yes | gdubois |
| nickname | Unbounded sequence of the display names of the player. This is how the user will appear toward other players and may be different from the login. If the user has several nicknames he can use, all of them shall be described here This field is now optional. | xs:string | No | BigJoe24 |
| firstname | The player Firstname | xs:string | Yes | Joe |
| lastname1 | The first lastname of the player | xs:string | Yes | Black |
| lastname2 | The second lastname of the player if any. This field is optional, but only if the player is a foreigner. | xs:string | No | White |
| email | Email address of the player | xs:string | Yes | info@dictao.com |
| sex | The sex of the player. Either "F" or "M". | xs:string | Yes | “M” |
| home | Postal address of the home of the player | Home | Yes | - |
| phone | Phone number of the player | xs:string | Yes | +33625654785 |
| depositLimits | The deposit limits for this specific player | DepositLimits | Yes | - |
| status | Status of the player | Status | Yes | - |
| SVDICheck | This flags dexplains whether check with the SVDI (player vetting service provided by the DGOJ) has been performed. This is not the returned by the SVDI: if the player is not allowed, account registration should be forbidden. | xs:boolean | Yes | true |
| SVDIDate | This is the date and time of the first check of the SVDI that return a positive answer. This field is not provided until a first positive SVDI check has been performed | xs:dateTime | No | 2011-10-06T19:44:51.346+02:00 |
| IDDocumentCheck | This flags dexplains whether the complete verification of the ID documents provided by the players have been performed | xs:boolean | Yes | true |
| IDDocumentDate | This is the date and time of the first positive verification of the ID documents has been performed. This field is not provided until a first verfification has been performed | xs:dateTime | No | 2011-10-06T19:44:51.346+02:00 |

#### 4.9.4.2 PlayerRegistrationDetails.Resident

| Field | Description | Type | Mandatory | Example of value |
|---|---|---|---|---|
| nationality | The 2-letter ISO code of the country nationality of the player The accepted values are restricted to the list of the 249 current officially assigned ISO 3166-1 alpha-2 codes (http://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) | co:CountryISO | Yes | FR |
| Choice |  |  |  |  |
| DNI | The player is a Spanish citizen, this field is his ID number, the ”documento nacional de identidad” | xs:string | Yes | 12345678Z |
| NIE | The player is a foreigner, this field is his “Número de Identidad” | xs:string | Yes | X-0902015-R |

#### 4.9.4.3 PlayerRegistrationDetails.Nonresident

| Field | Description | Type | Mandatory | Example of value |
|---|---|---|---|---|
| nationality | The 2-letter ISO code of the country nationality of the player The accepted values are restricted to the list of the 249 current officially assigned ISO 3166-1 alpha-2 codes (http://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) | co:CountryISO | Yes | FR |
| countryOfResidence | The 2-letter ISO code of the country the player lives in The accepted values are restricted to the list of the 249 current officially assigned ISO 3166-1 alpha-2 codes (http://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) | co:CountryISO | Yes | DE |
| documentType | The kind of document used to identify the player. Only the following values are allowed: - “ID” : Id document - “SS”: Social security number - “PA” : Passport - “DL”: Driver’s licence - “OT”: Other, in this case fill the next field “otherDocumentType” | xs:string | Yes | PA |
| otherDocumentType | This may only be used if the value of the precedent field is “OT” Another type of document has been used to identify the player. | xs:string | No | “Retina scan” |
| document | The reference of the document used to identify the player (i.e. passport number) | xs:string | Yes | “12351 AZE” |

#### 4.9.4.4 PlayerRegistrationDetails.Home

| Field | Description | Type | Mandatory | Example of value |
|---|---|---|---|---|
| address | Physical postal address | xs:string | Yes | 152 avenue de Malakoff |
| city | City of the address | xs:string | Yes | Paris |
| zipcode | Zip code relative to the address | xs:string | Yes | 75015 |
| country | The 2-letter ISO code of the country of the address The accepted values are restricted to the list of the 249 current officially assigned ISO 3166-1 alpha-2 codes (http://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) | co:CountryISO | Yes | FR |

#### 4.9.4.5 PlayerRegistrationDetails.DepositLimits

| Field | Description | Type | Mandatory | Example of value |
|---|---|---|---|---|
| perDay | Deposit limit set for this player during one day. Initial value must be 600 or lower. If the player has no limit, the value is “-1” | co:Euros | Yes | 600 |
| perWeek | Deposit limit set for this player during one week. Initial value must be 1500 or lower If the player has no limit, the value is “-1” | co:Euros | Yes | 1500 |
| perMonth | Deposit limit set for this player during one month. Initial value must be 3000 or lower If the player has no limit, the value is “-1” | co:Euros | Yes | 3000 |

#### 4.9.4.6 PlayerRegistrationDetails.Status

| Field | Description | Type | Mandatory | Example of value |
|---|---|---|---|---|
| CNJStatus | Status of the player account defined by DGOJ | co:CNJStatus | Yes | “A” |
| operatorStatus | Actual status of the player account used internally by the operator | xs:string | Yes | “under investigation” |
| history | History of the previous statuses of the account over the account lifespan. This is a list | History | Yes | - |

#### 4.9.4.7 PlayerRegistrationDetails.History

| Field | Description | Type | Mandatory | Example of value |
|---|---|---|---|---|
| CNJStatus | Status of the player account defined by DGOJ at that time | co:CNJStatus | Yes | “A” |
| operatorStatus | Actual status of the player account used internally by the operator at that time | xs:string | Yes | “under investigation” |
| from | The date the status changed to the one described | xs:dateTime | Yes | 2011-10-06T19:44:51.346+02:00 |

#### 4.9.5 NetworkPlayerRegistration (RUR)

**Goal**

The NetworkPlayerRegistration record describes the identification data of participants in network games, including other configuration data such as the account status on the network platform (active, suspended, blocked, etc.).

The network user record shall contain all the details of participants registered on the gaming platform regardless of whether or not there have been changes to their data during the period and regardless of whether their status is active or not.

**Concerned operators**

This record shall be reported by network operators who manage network games and own a network operator license

**Trigger**

This record is submitted every month. It contains the details of each and every participant registered on the co-organised gaming platform regardless of player status and of the activityMonthly: The monthly user record shall contain the details of every participant existing on the gaming platform, regardless of whether there have been any changes to their data during the previous month. This includes each and every registered user regardless of the status of their account.

This record is submitted even if it “contains” no player data.

One of such records may not describe more than 1 000 players. If you want to report more than 1 000 players, you have to split the record into subrecords, each of them containing exactly 1 000 players but the last one.

| Field | Description | Type | Mandatory | Example of value |
|---|---|---|---|---|
| operatorId | ID of the operator (given by DGOJ) owning/managing the player | xs:string | Yes | 2343434212553 |
| recordId | ID provided by the operator to identify the record that will be stored in the vault. This ID : - allows the regulator to consolidate all the subrecords together - has to be used when a record has to be replaced or canceled This ID has to be unique for a given vault. | xs:string | Yes | 0001-2ea45-6789-2ef11 |
| subRecordId | This has to be a number between 1 and the value of the next field “subRecordTotal” included | xs:positiveInteger | Yes | 2 |
| subRecordTotal | Number of subrecords. Subrecords are used when records involve more than 1 000 players. In that case, records are split in subrecords per slice of 1 000 players | xs:positiveInteger | Yes | 4 |

**IDEMIA RESTRICTED**

D3S Developer's Guide, SAFE Integration Guide – Datamodel Version 2.11  
Ref.: Morpho_D3S_JEL_DeveloperGuide_WSES – version 3.5.8 66/90  
Communication, reproduction or use prohibited without prior authorization of Morpho

| Field | Description | Type | Mandatory | Example of value |
|---|---|---|---|---|
| date | Date/time the event occurred, not the time the vault is called - Should be stored because the event date requirements in an optional cancellation call | xs:dateTime | Yes | 2011-10-06T19:44:51.346+02:00 |
| month | The month this record relate to | co:date-yyyymm | Yes | 201406 |
| player | The player account details In rare case there are no player data relevant to this record do not provide this field | Player | No | - |

#### 4.9.5.1 NetworkPlayerRegistration.Player

| Field | Description | Type | Mandatory | Example of value |
|---|---|---|---|---|
| playerID | Unbounded sequence.The technical IDs of the player in the operator system. Multiple IDs have to be given for the same real user: - The player ID and operatorID used by the operator owning this customer to reference him - the playerID and operatorID used by the network operator (sending this record) to reference this player | co:PlayerID | Yes | P2433 |
| registrationDate | This is the date and time the player account was registerd by the network operator | xs:dateTime | Yes | 2011-10-06T19:44:51.346+02:00 |
| login | Login name used by the player to open an instance. It is unique to the operator IS | xs:string | Yes | gdubois |
| status | Status of the player | Status | Yes | - |

#### 4.9.5.1 NetworkPlayerRegistration.Status

| Field | Description | Type | Mandatory | Example of value |
|---|---|---|---|---|
| cnjStatus | Status of the player account defined by DGOJ | co:CNJStatus | Yes | “A” |
| operatorStatus | Actual status of the player account used internally by the operator | xs:string | Yes | “under investigation” |

#### 4.9.6 WinnerRegistrationDetails (RUG)

**Goal**

The WinnerRegistyrationDetails record describes the winners in games that do not require prior user registration

It contains identification data on participants who have won one or more prizes in those specific games.

**Concerned operators**

This record must be submitted by operators who have been specifically authorised to market games without prior user registration, such as some contest operators, for instance.

**Trigger**

This record shall be submitted every month. It will contain all the users who have won prizes during the previous month. Player who did not win anything are not referenced.

This record is submitted even if it “contains” no player data

One of such records may not describe more than 1 000 players. If you want to report more than 1 000 players, you have to split the record into subrecords, each of them containing exactly 1 000 players but the last one.

| Field | Description | Type | Mandatory | Example of value |
|---|---|---|---|---|
| operatorId | ID of the operator (given by DGOJ) owning/managing the player | xs:string | Yes | 2343434212553 |
| recordId | ID provided by the operator to identify the record that will be stored in the vault. This ID : - allows the regulator to consolidate all the subrecords together - has to be used when a record has to be replaced or canceled This ID has to be unique for a given vault. | xs:string | Yes | 0001-2ea45-6789-2ef11 |
| subRecordId | This has to be a number between 1 and the value of the next field “subRecordTotal” included | xs:positiveInteger | Yes | 2 |
| subRecordTotal | Number of subrecords. Subrecords are used when records involve more than 1 000 players. In that case, records are split in subrecords per slice of 1 000 players | xs:positiveInteger | Yes | 4 |
| date | Date/time the event occurred, not the time the vault is called - Should be stored because the event date requirements in an optional cancellation call | xs:dateTime | Yes | 2011-10-06T19:44:51.346+02:00 |
| month | The month this record relate to | co:date-yyyymm | Yes | 201406 |
| player | List of the personal information of the winners. In the rare case there are no players to report, don’t provide this field | Player | No | - |

#### 4.9.6.1 PlayerRegistrationDetails.Player

| Field | Description | Type | Mandatory | Example of value |
|---|---|---|---|---|
| playerID | Unbounded sequence.The technical IDs of the player in the operator system. Multiple IDs can be given for the same real user. If the player plays network games (games operated by another licenced operator), the playerID and operatorID used by the network operators to reference this player shall be provided as well | co:PlayerID | No | P2433 |
| taxRegion | 2 digit code of the tax province code where the player pays taxes in Spain, identified with the following list. If the player is not a resident, the value is now “22” 01: Andalucía 02: Aragón 03: Asturias 04: Canarias 05: Cantabria 06: Castilla - La Mancha 07: Castilla y León 08: Cataluña 09: Extremadura 10: Galicia 11: Illes Balears 12: La Rioja 13: Madrid 14: Murcia 15: Valencia 16: Diputación Foral de Navarra 17: Diputación Foral de Álava 18: Diputación Foral de Guipúzcoa 19: Diputación Foral de Vizcaya 20: Ceuta 21: Melilla 22: Not resident | xs:string | Yes | “10” |
| Choice |  |  |  |  |
| resident | Choose this if the player is resident in Spain | Resident | Yes | - |
| nonresident | Choose this if the player resides abroad | Nonresident | Yes | - |
| birthdate | The date of birth of the player. | xs:date | Yes | 2011-10-06T19:44:51.346+02:00 |
| firstname | The player Firstname | xs:string | Yes | Joe |
| lastname1 | The first lastname of the player | xs:string | Yes | Black |
| lastname2 | The second lastname of the player if any. This field is optional, but only if the player is a foreigner. | xs:string | No | White |
| email | Email address of the player | xs:string | Yes | info@dictao.com |
| sex | The sex of the player. Either "F" or "M". | xs:string | Yes | “M” |
| home | Postal address of the home of the player | Home | Yes | - |

**IDEMIA RESTRICTED**

D3S Developer's Guide, SAFE Integration Guide – Datamodel Version 2.11  
Ref.: Morpho_D3S_JEL_DeveloperGuide_WSES – version 3.5.8 69/90  
Communication, reproduction or use prohibited without prior authorization of Morpho

| Field | Description | Type | Mandatory | Example of value |
|---|---|---|---|---|
| phone | Phone number of the player | xs:string | Yes | +33625654785 |
| SVDICheck | This flags dexplains whether check with the SVDI (player vetting service provided by the DGOJ) has been performed. This is not the returned by the SVDI: if the player is not allowed, account registration should be forbidden. | xs:boolean | Yes | true |
| SVDIDate | This is the date and time of the first check of the SVDI that return a positive answer. This field is not provided until a first positive SVDI check has been performed | xs:dateTime | No | 2011-10-06T19:44:51.346+02:00 |
| IDDocumentCheck | This flags dexplains whether the complete verification of the ID documents provided by the players have been performed | xs:boolean | Yes | true |
| IDDocumentDate | This is the date and time of the first positive verification of the ID documents has been performed. This field is not provided until a first verfification has been performed | xs:dateTime | No | 2011-10-06T19:44:51.346+02:00 |

#### 4.9.6.2 PlayerRegistrationDetails.Resident

| Field | Description | Type | Mandatory | Example of value |
|---|---|---|---|---|
| nationality | The 2-letter ISO code of the country nationality of the player The accepted values are restricted to the list of the 249 current officially assigned ISO 3166-1 alpha-2 codes (http://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) | co:CountryISO | Yes | FR |
| Choice |  |  |  |  |
| DNI | The player is a Spanish citizen, this field is his ID number, the ”documento nacional de identidad” | xs:string | Yes | 12345678Z |
| NIE | The player is a foreigner, this field is his “Número de Identidad” | xs:string | Yes | X-0902015-R |

#### 4.9.6.3 PlayerRegistrationDetails.Nonresident

| Field | Description | Type | Mandatory | Example of value |
|---|---|---|---|---|
| nationality | The 2-letter ISO code of the country nationality of the player The accepted values are restricted to the list of the 249 current officially assigned ISO 3166-1 alpha-2 codes (http://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) | co:CountryISO | Yes | FR |
| contryOfResidence | The 2-letter ISO code of the country the player lives in The accepted values are restricted to the list of the 249 current officially assigned ISO 3166-1 alpha-2 codes (http://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) | co:CountryISO | Yes | DE |
| documentType | The kind of document used to identify the player. Only the following values are allowed: - “ID document” - “Social security card” - “Passport” - “Driver’s licence” - “Other” | xs:string | Yes | “Passport” |
| otherDocumentType | This may only be used if the value of the precedent field is “Other” Another type of document has been used to identify the player. | xs:string | No | “Retina scan” |
| document | The reference of the document used to identify the player (i.e. passport number) | xs:string | No | “12351 AZE” |

#### 4.9.6.4 PlayerRegistrationDetails.Home

| Field | Description | Type | Mandatory | Example of value |
|---|---|---|---|---|
| address | Physical postal address | xs:string | Yes | 152 avenue de Malakoff |
| city | City of the address