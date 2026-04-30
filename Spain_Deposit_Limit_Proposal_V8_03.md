---
country: Spain
document_name: Spain Deposit Limit Process Proposal Document
source_file: Spain Deposit Limit Proposal V8 03.pdf
extracted_date: 2026-04-30
jurisdiction: Spain
---

# Spain Deposit Limit Process Proposal Document

**Author(s):** Rita Sewdayal  
**Version:** 8.03  
**Release Date:** 01 June 2015

Spain Deposit Limit Process Proposal Document confidential  
© 2014 Derivco (Pty) Ltd All Rights Reserved Page 2 of 15  
This document is intended for the use of Derivco (Pty) Ltd only. It contains information that is privileged and that is the intellectual property of Derivco (Pty) Ltd. You may neither copy nor use it, nor disclose it to anyone else. If you have received this document in error, please notify us immediately.

## Revision History

| Revision | Date | Name | Comments / Reason |
|---|---|---|---|
| 1.00 | 12 August 2014 | Rita S | Initial Draft |
| 2.00 | 15 August 2014 | Rita S | Updated Visio Diagram and processes based on investigating Betway’s input. |
| 3.00 | 19 August 2014 | Rita S | Updated Visio to include canceling a pending limit increase prior to the waiting periods. |
| 4.00 | 10 September 2014 | Rita S | Included Caiman high level requirements. |
| 5.00 | 17 September 2014 | Rita S | Additional Caiman requirements added |
| 6.00 | 29 September 2014 | Rita S | Included the 3 month waiting period between the 1st and 2nd request. |
| 7.00 | 05 December 2014 | Rita S | Process Flows have been updated and split into 2. Updated document as per the updated process flows. |
| 8.00 | 22 January 2015 | Rita S | Process Flows updated as per session with eCogra. |
| 8.01 | 29 January 2015 | Rita S | Added 2.3.4.3 requirement. |
| 8.02 | 15 April 2015 | Rita S | Updated all dialog wireframes |
| 8.03 | 1 June 2015 | Rita S | Updated 2.3.3.2<br>Updated 2.3.3.7. (d)<br>Updated 2.3.3.7. (e)<br>Updated 2.3.4.2. (c)<br>Updated 2.3.4.2. (d)<br>Updated Figure 7 to include Cancel button |

## Table of Contents

Contents

1 INTRODUCTION ............................................................................................................. 5  
1.1 OVERVIEW ............................................................................................................. 5  
1.2 SCOPE ................................................................................................................... 5  
2 BUSINESS REQUIREMENTS ................................................................................................ 6  
2.1 REGULATORY REQUIREMENTS .................................................................................... 6  
2.2 PLAYER PROCESS FLOW ............................................................................................ 7  
2.3 THE DEPOSIT LIMIT PROCESS ..................................................................................... 8  

Spain Deposit Limit Process Proposal Document confidential  
© 2014 Derivco (Pty) Ltd All Rights Reserved Page 4 of 15  
This document is intended for the use of Derivco (Pty) Ltd only. It contains information that is privileged and that is the intellectual property of Derivco (Pty) Ltd. You may neither copy nor use it, nor disclose it to anyone else. If you have received this document in error, please notify us immediately.

## List of Figures

FIGURE 1 - DEPOSIT LIMIT 1ST INCREASE REQUEST- PLAYER PROCESS FLOW  
FIGURE 2 - DEPOSIT LIMIT 2ND REQUEST PROCESS FLOW  
FIGURE 3 - RESPONSIBLE GAMING LIMITS PAGE FOR CASINO  
FIGURE 4 – CURRENT RESPONSIBLE GAMING TEST INSTRUCTIONS MESSAGE  
FIGURE 5 – CURRENT RESPONSIBLE GAMING TEST QUESTIONS  
FIGURE 6 - SUCCESSFUL 1ST REQUEST MESSAGE  
FIGURE 7 - CURRENT PENDING REQUEST SCREEN  
FIGURE 8 – CURRENT CONFIRMATION OF CANCELLATION OF PENDING REQUEST  
FIGURE 9 - NEW DEPOSIT ACTIVATED MESSAGE  
FIGURE 10 - UNSUCCESSFUL IN ASSESSMENT MESSAGE  
FIGURE 11 - WAITING PERIOD DIALOGUE FOR 2ND REQUEST  
FIGURE 12 - ADDITIONAL REQUEST TO INCREASE DEPOSIT LIMIT MESSAGE  

## List of Tables

TABLE 1 - DEPOSIT LIMIT REGULATORY REQUIREMENTS

Spain Deposit Limit Process Proposal Document confidential  
© 2014 Derivco (Pty) Ltd All Rights Reserved Page 5 of 15  
This document is intended for the use of Derivco (Pty) Ltd only. It contains information that is privileged and that is the intellectual property of Derivco (Pty) Ltd. You may neither copy nor use it, nor disclose it to anyone else. If you have received this document in error, please notify us immediately.

## 1 Introduction

### 1.1 Overview

The National Gambling Commission of Spain has introduced regulations with regard to responsible Gambling specifically around the deposit limit process. This document will highlight those requirements and will present the proposal for meeting these Deposit limit requirements with automation being the focus.  
These regulations are in accordance with the provisions details in Article 36.3 of the Royal Decree.

### 1.2 Scope

In Scope

- The features specified in this document apply to Casino for the Spain platform on Deposit Limits.
- Translations must be accommodated in Spanish.

Out of Scope

- Dependencies across products and platforms haven’t been explicitly highlighted in this document.

The document will not provide analysis for Backoffice, DB, IT or any technical analysis.

Spain Deposit Limit Process Proposal Document confidential  
© 2014 Derivco (Pty) Ltd All Rights Reserved Page 6 of 15  
This document is intended for the use of Derivco (Pty) Ltd only. It contains information that is privileged and that is the intellectual property of Derivco (Pty) Ltd. You may neither copy nor use it, nor disclose it to anyone else. If you have received this document in error, please notify us immediately.

## 2 Business Requirements

### 2.1 Regulatory Requirements

| Ref | Requirement | User Story |
|---|---|---|
| 2a | When the participant requests the disappearance of any limitation on their deposits or for the first time requests an increase of the limits thereof, gambling operators will facilitate the completion of the test for responsible gaming and prevention of addictive gambling referred to above. | As a player, I can choose to remove any deposit limits currently set by default or increase the current deposit limits. If it is my first request then I would need to complete a responsible gaming test in order to proceed with my request to increase or remove my deposit limits. |
| 2b | In the event that the answer to any of the test questions approved by this resolution is positive, the gambling operator may not increase the amount of deposits or remove the limits set for the deposit account of the participant concerned. Furthermore, the latter cannot reapply for an increase in the limit or for the disappearance of said limit until 7 days have elapsed from the taking of the test. | As a player if any of my answers are positive (yes), then the Operator may not increase my deposit limit request. I will not be able to reapply to increase or remove my deposit limit until 7 days have elapsed since taking the test. |
| 2c | In the event that the answers to all questions of said test are negative, the new limits or disappearance of these will take effect within seven days from the completion of the test approved by this resolution. | As a player if I have responded with all ‘No’s, then this is deemed as a positive result for the test and my request will be processed within 7 days. During the 7 day cooling off period, as a player I may cancel the pending request and add a new one. The 7 day cooling off period will be automatically readjusted based on the new request timeframe. |
| 2d | In the case of the second or subsequent requests for limit increases by the same participant, the gambling operator must perform a historical analysis of the history of the participant. The new limits come into force three days after the analysis is performed with positive results. | As a player if this is my second or subsequent request to increase or remove my deposit limit, the system will flag my intentions with the Operator so that they can perform a historical analysis of my history. A 3 month cooling off period must be adhered to between my 1st and 2nd request. If the Operator approves my request, it will be activated 3 days after the analysis was performed. The Operator must notify me of the outcomes. During the 3 day cooling off period, as player I may cancel the pending request and add a new request. The Operator will be notified via the back office tools and the 3 day cooling off period will be adjusted accordingly. |

Table 1 - Deposit Limit Regulatory Requirements

Spain Deposit Limit Process Proposal Document confidential  
© 2014 Derivco (Pty) Ltd All Rights Reserved Page 7 of 15  
This document is intended for the use of Derivco (Pty) Ltd only. It contains information that is privileged and that is the intellectual property of Derivco (Pty) Ltd. You may neither copy nor use it, nor disclose it to anyone else. If you have received this document in error, please notify us immediately.

### 2.2 Player Process Flow

Figure 1 - Deposit Limit 1st Increase Request- Player Process Flow

Spain Player  
Logs in  
Navigate to Deposit  
Limit Page  
Selected  
Remove all  
Limits?  
Increased  
amount > Law  
Limits?  
Requested limit  
> Current limit  
No No  
Yes  
Navigate to Banking  
Assessment  
Taken?  
Display Assessment  
Information  
Dialogue  
Continue link  
selected?  
Yes  
No  
Launch Assessment Yes  
Result = Pass?  
Yes  
Last assessment  
taken > 7 days?  
No  
Cooling Period  
> 7 days?  
Flagged for Analysis  
Show pending  
details on page  
Yes  
Yes  
No  
Yes  
Display Next  
Attempt of  
Assessment  
Dialogue  
No  
Assessment  
passed?  
Display Success  
Dialogue  
Display  
Unsuccessful  
Dialogue  
Yes  
No  
Return to Deposit  
Limit Page  
No  
Return to Lobby  
End  
Yes Yes  
Increment  
decrease  
immediately  
No  
Show Decrease  
details on page

Spain Deposit Limit Process Proposal Document confidential  
© 2014 Derivco (Pty) Ltd All Rights Reserved Page 8 of 15  
This document is intended for the use of Derivco (Pty) Ltd only. It contains information that is privileged and that is the intellectual property of Derivco (Pty) Ltd. You may neither copy nor use it, nor disclose it to anyone else. If you have received this document in error, please notify us immediately.

Figure 2 - Deposit Limit 2nd Request Process Flow

### 2.3 The Deposit Limit Process

#### 2.3.1

A player must be able to control the amount of money they can deposit by setting limits within the ‘Limits’ section of the responsible gaming application.

#### 2.3.2

The default allowed deposit limits must be set and displayed to:

Figure 3 - Responsible Gaming Limits Page for Casino

Spain Deposit Limit Process Proposal Document confidential  
© 2014 Derivco (Pty) Ltd All Rights Reserved Page 9 of 15  
This document is intended for the use of Derivco (Pty) Ltd only. It contains information that is privileged and that is the intellectual property of Derivco (Pty) Ltd. You may neither copy nor use it, nor disclose it to anyone else. If you have received this document in error, please notify us immediately.

- Daily: 600 euros
- Weekly: 1,500 euros
- Monthly: 3, 000 euros

#### 2.3.3

A player must be able to increase any or all of the current limits or remove their limits entirely.

#### 2.3.3.1

If this is the player’s first request to increase deposit limits, the player is required to pass a responsible gaming test before completing the action.  
Below are the scenarios that will be impacted on first request which launches the test:

- Remove all limits
- Requests a higher limit than any or all of the default limits
- Requests a limit that is higher than the current limit set.

#### 2.3.3.2

The player must click on ‘Start Test’ to launch the questions. If the player clicks the ‘Cancel’ button then the player must be navigated back to the Responsible Gaming application.

#### 2.3.3.3

The player must complete all 10 questions.

#### 2.3.3.4

No default options must be available for any of the questions.

#### 2.3.3.5

If player did not answer all of the questions and clicks “Submit”, they will be presented with the following message:  
“Please answer all questions before submitting.”

#### 2.3.3.6

Each attempt of the responsible gaming test must be recorded for tracking purposes.

Figure 4 – Current Responsible Gaming Test Instructions Message

Spain Deposit Limit Process Proposal Document confidential  
© 2014 Derivco (Pty) Ltd All Rights Reserved Page 10 of 15  
This document is intended for the use of Derivco (Pty) Ltd only. It contains information that is privileged and that is the intellectual property of Derivco (Pty) Ltd. You may neither copy nor use it, nor disclose it to anyone else. If you have received this document in error, please notify us immediately.

Below are the responsible gaming test questions:  
Figure 5 – Current Responsible Gaming Test Questions

Spain Deposit Limit Process Proposal Document confidential  
© 2014 Derivco (Pty) Ltd All Rights Reserved Page 11 of 15  
This document is intended for the use of Derivco (Pty) Ltd only. It contains information that is privileged and that is the intellectual property of Derivco (Pty) Ltd. You may neither copy nor use it, nor disclose it to anyone else. If you have received this document in error, please notify us immediately.

#### 2.3.3.7

A player that has answered all questions with a ‘No’ must pass the test.

a) Display a message to the player on successful completion of the test.  
b) After reading the message, on selecting the ‘OK’ button the player must be navigated to the Responsible Gaming page.  
c) A 7 day cooling off period must be imposed on the player.  
d) During the 7 day cooling off period, a player can cancel their pending deposit limit request by selecting the ‘Cancel’ button. A confirmation dialog must be presented to the player, “Are you sure you want to cancel your pending limits? “ If the player selects, ‘Yes’, then remove the pending limits and revert to previous limit. If the player selects ‘No, then dismiss the dialog.  
e) If the player inserts a new value, there is no need to re-take the gambling addiction test. Back-office to track request amendments.

Figure 6 - Successful 1st Request Message  
Figure 7 - Current Pending Request Screen- Deposit Limit Page

Spain Deposit Limit Process Proposal Document confidential  
© 2014 Derivco (Pty) Ltd All Rights Reserved Page 12 of 15  
This document is intended for the use of Derivco (Pty) Ltd only. It contains information that is privileged and that is the intellectual property of Derivco (Pty) Ltd. You may neither copy nor use it, nor disclose it to anyone else. If you have received this document in error, please notify us immediately.

f) Once the 7 day cooling off period has elapsed, on next log in, the player must receive a message in the client that the deposit limits is now active.  
g) Once the message has been read, the player has a choice to either select ‘Go to Banking’ where they can make a deposit or the player selects ‘OK’ button which must take the player to the Lobby.

#### 2.3.3.8

A player that has answered any of the questions with a ‘Yes’, must fail the test.

a) A message must be displayed to the player about the outcome of the test.

Figure 8 – Current Confirmation of Cancellation of Pending Request  
Figure 9 - New Deposit Activated Message

Spain Deposit Limit Process Proposal Document confidential  
© 2014 Derivco (Pty) Ltd All Rights Reserved Page 13 of 15  
This document is intended for the use of Derivco (Pty) Ltd only. It contains information that is privileged and that is the intellectual property of Derivco (Pty) Ltd. You may neither copy nor use it, nor disclose it to anyone else. If you have received this document in error, please notify us immediately.

b) Once the message is read, on selecting the ‘Ok’ button, the player must be returned to the Responsible Gaming page.  
c) A player can re-attempt the request and test after a 7 day waiting period.

#### 2.3.4

Player requests increase in deposit limit for a 2nd or subsequent time.

#### 2.3.4.1

If it is the 2nd or subsequent request, the player must have completed a 3 month waiting period since the 1st or previous request.

a) Display a message to a player who attempts a 2nd or subsequent request during the 3 month waiting period.

#### 2.3.4.2

A player is flagged for analysis if it is the 2nd or subsequent request and the 3 month waiting period has elapsed since the previous request.

a) Display a message to the player to inform them of the analysis process.

Figure 10 - Unsuccessful in Assessment Message  
Figure 11 - Waiting Period Dialogue for 2nd Request  
Figure 12 - Additional Request to Increase Deposit Limit Message

Spain Deposit Limit Process Proposal Document confidential  
© 2014 Derivco (Pty) Ltd All Rights Reserved Page 14 of 15  
This document is intended for the use of Derivco (Pty) Ltd only. It contains information that is privileged and that is the intellectual property of Derivco (Pty) Ltd. You may neither copy nor use it, nor disclose it to anyone else. If you have received this document in error, please notify us immediately.

b) A message must be triggered from the system (Back office) to the Operator flagging the specific player for analysis.  
c) On the deposit limit page (Figure 7), the following text must be displayed whilst waiting for the analysis outcome: “You have a pending deposit limit request awaiting analysis results from the Operator.”  
d) The Operator must capture the analysis result into the system (Back Office) at which point a 3 day cooling off period is enforced for a successful player.  
e) On the deposit limit page, the following text must be displayed to the player once a successful analysis result is captured: “You have a pending [period] deposit limit of [amount] which will be applied on [insertDate]” for the duration of the 3 day cooling off period.  
f) A message is sent to the player of the analysis outcome which the Operator will manage.  
g) For a successful player, once the 3 day cooling off period has elapsed, on next login, the player will receive a message notifying them of the activated limits. See Figure 9.  
h) If a player was unsuccessful in the 2nd or subsequent request, a message is sent the player which the Operator will manage.

#### 2.3.4.3

A Player may cancel their 2nd or subsequent request during a pending state.

a) If a Player cancels their pending deposit limit request, the values must be cleared and allow player to insert new values. A ‘Cancel Request’ button must be added to the screen to facilitate this process.  
b) Back office must ensure this record is cancelled and a new one logged for the most recent request.

#### 2.3.5

A player decreases their deposit limit

#### 2.3.5.1

A request to decrease deposit limit, is immediately updated.

a) Display confirmation message to the player as per below:  
“Your limits have been saved and immediately applied.”

Spain Deposit Limit Process Proposal Document confidential  
© 2014 Derivco (Pty) Ltd All Rights Reserved Page 15 of 15  
This document is intended for the use of Derivco (Pty) Ltd only. It contains information that is privileged and that is the intellectual property of Derivco (Pty) Ltd. You may neither copy nor use it, nor disclose it to anyone else. If you have received this document in error, please notify us immediately.