---
country: Spain
document_name: D3S Online Gaming Spain Edition Functional Specification
source_file: OT-Morpho_D3S_JEL_FunctionalSpec_ES_v2.1en.pdf
extracted_date: 2026-04-30
jurisdiction: Spain
---

# D3S Online Gaming Spain Edition Functional Specification

OT-MORPHO RESTRICTED

11 Boulevard Gallieni  
92130 Issy-les-Moulineaux  
France

D3S Online Gaming Spain Edition  
Functional Specification  
JEL @ Spain

Réf. : OT-Morpho_D3S_JEL_FunctionalSpec_ES  
Version 2.1 2017/07/28

OT-MORPHO RESTRICTED

D3S Online Gaming Spain Edition  
Functional Specification

Réf. : Dictao_D3S_JEL_FunctionalSpec_ES version 2.1 du 2011/10/218 2/110  
Communication, reproduction ou utilisation interdites sauf autorisation préalable de OT-Morpho

**Reference :**  
OT-Morpho_D3S_JEL_FunctionalSpec_ES

**Version :**  
2.1

**Last update:**  
2017/07/28

**Confidentiality level:**  
RESTRICTED

**Diffusion**  
Destinataires Objet de la diffusion

**Table des mises à jour du document**

| N° de version | Etat | Date | Auteur | Objet de la mise à jour |
|---|---|---|---|---|
| 0.1 | T | 14/07/11 | Dictao | Création |
| 0.2 | T | 06/10/11 | Dictao | Updated with EST02, MOD20 and XSD03 |
| 0.3 | T | 21/10/11 | Dictao | Updated with XSD04 |
| 2.0 | V | 17/11/14 | Dictao | Update with the v2 model |
| 2.1 | T | 28/07/17 | OT-Morpho | Review and Update company logo and name |

1  
T : En cours de modification ; V : Validé

OT-MORPHO RESTRICTED

D3S Online Gaming Spain Edition  
Functional Specification

Réf. : Dictao_D3S_JEL_FunctionalSpec_ES version 2.1 du 2011/10/218 3/110  
Communication, reproduction ou utilisation interdites sauf autorisation préalable de OT-Morpho

## SOMMAIRE

- SOMMAIRE .................................................................................................................................................. 3
- 1. INTRODUCTION .................................................................................................................................... 6
  - 1.1 Object of this document ..................................................................................................................... 6
  - 1.2 Targeted audience ............................................................................................................................. 6
  - 1.3 External references ............................................................................................................................ 6
- 2. REQUIREMENTS OVERVIEW .................................................................................................................. 7
  - 2.1 DGOJ Definitions ............................................................................................................................... 7
    - 2.1.1 Internal control system................................................................................................................... 7
    - 2.1.2 Capture device .............................................................................................................................. 7
    - 2.1.3 Gaming Operations Store .............................................................................................................. 7
  - 2.2 SAFE Functional Requirements ......................................................................................................... 7
    - 2.2.1 Capture & Registration of Events .................................................................................................. 7
    - 2.2.2 Dedicated SAFE Database ............................................................................................................ 7
    - 2.2.1 Consultation & Download of Events .............................................................................................. 7
    - 2.2.2 Storage Data Model ....................................................................................................................... 8
    - 2.2.3 Capacity Planning & Management ................................................................................................ 8
    - 2.2.4 Batch Management (Lote) ............................................................................................................. 8
    - 2.2.5 Digital Signature & Timestamp ...................................................................................................... 8
    - 2.2.6 Data Compression and Encryption ................................................................................................ 8
    - 2.2.7 Performance of the Capture device ............................................................................................... 8
  - 2.3 SAFE Hosting Requirements ............................................................................................................. 9
    - 2.3.1 Platform Monitoring........................................................................................................................ 9
    - 2.3.2 Performance of the Gaming Operation Store ................................................................................ 9
    - 2.3.3 Storage Retention .......................................................................................................................... 9
    - 2.3.4 Availability of the ICS ..................................................................................................................... 9
    - 2.3.5 Back-up copy plan ......................................................................................................................... 9
    - 2.3.6 Business continuity ...................................................................................................................... 10
- 3. PRODUCT FUNCTIONS ........................................................................................................................ 11
  - 3.1 Architecture Overview ...................................................................................................................... 11
    - 3.1.1 High-Level Functional Flow ......................................................................................................... 11
    - 3.1.2 Usage Statistics ........................................................................................................................... 12

OT-MORPHO RESTRICTED

D3S Online Gaming Spain Edition  
Functional Specification

Réf. : Dictao_D3S_JEL_FunctionalSpec_ES version 2.1 du 2011/10/218 4/110  
Communication, reproduction ou utilisation interdites sauf autorisation préalable de OT-Morpho

- 3.1.3 Synchronous vs Asynchronous ................................................................................................... 12
- 3.2 Web Service Front-end .................................................................................................................... 13
  - 3.2.1 Overview of the Recording API .................................................................................................... 13
  - 3.2.2 WSDL and SOAP format ............................................................................................................. 13
  - 3.2.3 Synchronous two-way.................................................................................................................. 14
  - 3.2.4 Fault Handling ............................................................................................................................. 14
  - 3.2.5 Duplicated Requests Detection ................................................................................................... 15
  - 3.2.6 Request Context .......................................................................................................................... 15
- 3.3 User Authentication .......................................................................................................................... 15
  - 3.3.1 Transport Layer Security ............................................................................................................. 15
  - 3.3.2 User Directory .............................................................................................................................. 16
  - 3.3.3 Authentication Context................................................................................................................. 16
- 3.4 Validation & Transformation ............................................................................................................. 16
  - 3.4.1 SOAP Body Validation ................................................................................................................. 16
  - 3.4.2 OT-Morpho XML vs DGOJ XML .................................................................................................. 16
  - 3.4.3 Transformation Context ............................................................................................................... 17
- 3.5 Dispatching ...................................................................................................................................... 17
  - 3.5.1 Dispatch Logic ............................................................................................................................. 17
  - 3.5.2 Asynchronous Queuing ............................................................................................................... 18
  - 3.5.3 Top-Level Categories .................................................................................................................. 18
  - 3.5.4 Type of Games ............................................................................................................................ 19
- 3.6 Batch Management .......................................................................................................................... 20
  - 3.6.1 Purpose of batch.......................................................................................................................... 20
  - 3.6.2 Batching Rules ............................................................................................................................ 20
- 3.7 Signature & Timestamp.................................................................................................................... 20
  - 3.7.1 Digital Signature .......................................................................................................................... 20
  - 3.7.2 Time stamping ............................................................................................................................. 22
- 3.8 Compress & Encrypt ........................................................................................................................ 22
  - 3.8.1 Formatting Rules ......................................................................................................................... 22
  - 3.8.2 Compression Algorithm ............................................................................................................... 22
  - 3.8.3 Encryption Algorithm.................................................................................................................... 22
- 3.9 Directory and File Convention .......................................................................................................... 22
  - 3.9.1 Directory Structure ....................................................................................................................... 22
  - 3.9.2 File Naming ................................................................................................................................. 24
  - 3.9.3 OP - Operator Account ................................................................................................................ 25

OT-MORPHO RESTRICTED

D3S Online Gaming Spain Edition  
Functional Specification

Réf. : Dictao_D3S_JEL_FunctionalSpec_ES version 2.1 du 2011/10/218 5/110  
Communication, reproduction ou utilisation interdites sauf autorisation préalable de OT-Morpho

- 3.9.4 JU – Games ................................................................................................................................. 26
- 3.9.5 JU - JUA/CEV .............................................................................................................................. 26
- 3.10 Daily Archiving ............................................................................................................................. 27
  - 3.10.1 Daily Archiving of RegistoJUx Records ....................................................................................... 27
  - 3.10.2 Naming Convention ..................................................................................................................... 28
- 4. DATA MODEL MAPPING RULES .......................................................................................................... 29
  - 4.1 Definitions ........................................................................................................................................ 29
    - 4.1.1 Data Model .................................................................................................................................. 29
    - 4.1.2 Mapping Convention .................................................................................................................... 29
  - 4.2 Complete Mapping ........................................................................................................................... 29

OT-MORPHO RESTRICTED

D3S Online Gaming Spain Edition  
Functional Specification

Réf. : Dictao_D3S_JEL_FunctionalSpec_ES version 2.1 du 2011/10/218 6/110  
Communication, reproduction ou utilisation interdites sauf autorisation préalable de OT-Morpho

## 1. INTRODUCTION

### 1.1 Object of this document

The D3S vault software is a secure storage module enabling gaming applications to store records
of gaming events. Typically, such records are needed for regulatory compliance. D3S implements
the jurisdiction-specific requirements such as data formats, cryptographic seals, and
communication protocols with the regulator.

This document is the functional specification of the D3S vault for the Online Gaming Spanish
Regulation.

It describes the vault regulatory requirements established by the DGOJ and how these
requirements are fulfilled by the D3S software.

### 1.2 Targeted audience

This document is primarily intended to:

- OT-Morpho’s R&D teams that develop, test and deliver the D3S software product,
- OT-Morpho‘s Administration & Support teams that operate the product as a service
  (SAAS).
- External certification teams that evaluate the software product with regard to the DGOJ
  requirement.

### 1.3 External references

- [EST02] Especificaciones Técnicas versión 0.2 - septiembre
- [MOD03] Modelo de datos de monitorización versión 0.3 - 5 de octubre 2011
- [MOD20] R_20141006_Modelo_Datos_Monitorizacion_Registros_Operaciones_Juego -
  6 de octubre 2014
- [XSD03] Modelo de datos de monitorización versión 0.3 archivo XSD - 5 de octubre 2011
- [XSD04] Modelo de datos de monitorización versión 0.4 archivo XSD - 20 de octubre
  2011
- [DSIG] XML Digital Signature http://www.w3.org/TR/xmldsig-core/
- [WSAPI31] OT-Morpho D3S Developer’s Guide, Web service integration, version 3.1
- [XSD20] Modelo de datos de monitorización versión 2.0 archivo XSD - 06 de octubre
  2014

Gaming  
application  
D3S Regulator

OT-MORPHO RESTRICTED

D3S Online Gaming Spain Edition  
Functional Specification

Réf. : Dictao_D3S_JEL_FunctionalSpec_ES version 2.1 du 2011/10/218 7/110  
Communication, reproduction ou utilisation interdites sauf autorisation préalable de OT-Morpho

## 2. REQUIREMENTS OVERVIEW

### 2.1 DGOJ Definitions

#### 2.1.1 Internal control system

**Internal control system** The Internal Control System is the set of components meant to register all the operations and
transactions performed during the development of games seeking to ensure that the National
Game Commission has the possibility to keep permanent control over the operator’s gaming
Activities.

The Internal Control System (ICS) will be formed by the Capture Device and the Gaming
Operation Store.

#### 2.1.2 Capture device

**Capture device** The Capture Device is the component of the Internal Control System whose function is to record
certain information as specified by the DGOJ.

#### 2.1.3 Gaming Operations Store

**Gaming Operations Store** The information extracted from the gaming system by the Capture Device shall be stored, in the
format and structure established by the DGOJ, in a Gaming Operations Store to which the DGOJ
shall be provided permanent access.

### 2.2 SAFE Functional Requirements

#### 2.2.1 Capture & Registration of Events

Operators shall have to equip their Technical Gaming System with an internal control system,
which captures and registers all gaming operations and economic transactions carried out under
the operator's license.

#### 2.2.2 Dedicated SAFE Database

The capture and registration of operations and transactions will be carried out by means of the
internal control system and will be kept in the safe database created to that end.

#### 2.2.1 Consultation & Download of Events

It will be necessary to guarantee the possibility of permanent connection to the Gaming Operation
Store (CAJA) for the DGOJ, establishing an access or service, which permits the consultation
and/or download of the data stored in it at any time.

The operator shall have to establish a data consultation and/or download service that is
permanently available to the DGOJ.

OT-MORPHO RESTRICTED

D3S Online Gaming Spain Edition  
Functional Specification

Réf. : Dictao_D3S_JEL_FunctionalSpec_ES version 2.1 du 2011/10/218 8/110  
Communication, reproduction ou utilisation interdites sauf autorisation préalable de OT-Morpho

#### 2.2.2 Storage Data Model

The data model is defined in detail under the “Monitoring data model” document [MOD20]

The data model establishes a structure of files, which contain information structured in XML,
according to the definition of the monitoring data scheme (XSD-XML Schema Definition).h

#### 2.2.3 Capacity Planning & Management

The vault should provide statistics of the data volume it manages that can be used by DGOJ to
estimate the monthly data volume of both the user registration and gaming account records.

The statistics should be provided for both the uncompressed XML and compressed ZIP files.

#### 2.2.4 Batch Management (Lote)

The data to be stored in the CAJA are grouped into batches. A batch is a single XML document
that groups together multiple DGOJ records as defined in [MOD20].

#### 2.2.5 Digital Signature & Timestamp

Each batch shall be signed by the operator in accordance with the XAdES-BES 1.3.2 standard.

The operator shall provide the DGOJ with the public part of the digital certificate used to sign the
batches. The operator shall be in charge of informing the DGOJ on the revocation of a certificate
used.

The operator may use a certificate of their own or may allow a third party to sign batches, as in
the event that an IT provider provides the CAJA service to the operator, for instance. In this case,
the operator must bear into account that it assumes that the IT provider is signing in its name,
and with the same guarantees and legal validity.

Right now the DGOJ does not require time stamping batches. The DGOJ may require this
possibility, in which case the XAdES-T 1.3.2 standard is expected to be used to sign, and it might
be required to be time stamped through a Time Stamping Authority (TSA) recognized in the
European Economic Area.

#### 2.2.6 Data Compression and Encryption

The batch file must be compress and encrypt using a ZIP file format (“deflate” algorithm) and the
AES 256 encrypting option.

The DGOJ shall provide the password. It shall be the operator's responsibility to guard the
password.

#### 2.2.7 Performance of the Capture device

The Capture device must have enough capacity to process and register the information of the
transactions.

Under normal circumstances, the Capture device must be designed for the information to be
processed, formatted and stored in the CAJA in twice the monitoring time for real time (5 minutes)
at most, which is twice 10 minutes.

OT-MORPHO RESTRICTED

D3S Online Gaming Spain Edition  
Functional Specification

Réf. : Dictao_D3S_JEL_FunctionalSpec_ES version 2.1 du 2011/10/218 9/110  
Communication, reproduction ou utilisation interdites sauf autorisation préalable de OT-Morpho

### 2.3 SAFE Hosting Requirements

#### 2.3.1 Platform Monitoring

The National Game Commission shall permanently monitor gaming operations so as to verify that
the objectives sought in the applicable legislation are fulfilled. The infrastructure for the control of
gaming operations must permit monitoring and supervision by the National Game Commission
(DGOJ), thus guaranteeing the possibility to verify the fulfillment of these goals.

The fundamental elements in the Technical Gaming System are the Central Game Unit and the
Internal Control System

#### 2.3.2 Performance of the Gaming Operation Store

The operator must guarantee that the CAJA has a minimum communication flow in the Internet,
enough to support the DGOJ access:

- Regarding the DGOJ's upload of information (to the Internet), the GOS must have a
  minimum flow ensured in order to allow the maximum download of information created in
  four hours a day (through the defined SFTP protocol). As for the download (from the
  Internet), at least 64 kbps are required.
- As system, the CAJA must be able to provide the performance necessary or more in
  order to guarantee the communication flows above mentioned, regardless of the other
  operations it must perform.

#### 2.3.3 Storage Retention

Gaming operators must be required to store in CAJA all registers corresponding to the last 12
months of activity, at least.

Since the legislation in force requires storing data with information corresponding to the last 6
years of activity, operators must have planned a procedure to recover such information in order
to submit it to the National Game Commission (DGOJ) whenever they are required to do so.

#### 2.3.4 Availability of the ICS

The CAJA may not have more than 48 hours of accumulated failure time per month.

#### 2.3.5 Back-up copy plan

The ICS is a critical component. The organization must implement a procedure to minimize the
risk of losing information to a maximum of 1 day.

If information is lost in the ICS, the operator should have a procedure to extract lost information.

The operator shall repair the loss of information with a new extraction for a maximum period of 1
week.

The DGOJ must be informed as soon as possible of any loss of information affecting the ICS,
including an assessment of the impact as well as the measures plan to adopt.

OT-MORPHO RESTRICTED

D3S Online Gaming Spain Edition  
Functional Specification

Réf. : Dictao_D3S_JEL_FunctionalSpec_ES version 2.1 du 2011/10/218 10/110  
Communication, reproduction ou utilisation interdites sauf autorisation préalable de OT-Morpho

#### 2.3.6 Business continuity

The operator shall have a business continuity procedure, which in the event of a disaster would
allow the ICS to be operative for a period of less than a month, always bearing into account that
if the CAJA is not in operation after 24 hours, the operator shall stop working.

The DGOJ must be informed as soon as possible of any disaster affecting the ICS, including an
assessment of the impact as well as the measures plan to adopt.

OT-MORPHO RESTRICTED

D3S Online Gaming Spain Edition  
Functional Specification

Réf. : Dictao_D3S_JEL_FunctionalSpec_ES version 2.1 du 2011/10/218 11/110  
Communication, reproduction ou utilisation interdites sauf autorisation préalable de OT-Morpho

## 3. PRODUCT FUNCTIONS

### 3.1 Architecture Overview

#### 3.1.1 High-Level Functional Flow

The diagram below illustrates the functional flow of the D3S vault.

The functional flow is as follows:

1. The D3S vault listens for incoming remote request. The messaging and transport protocol
   is SOAP over HTTPS.
2. Whenever a new request arrives, the D3S vault first authenticates the request imitator.
   The authentication is based upon the standard Transport Layer Security (TLS) protocol
   with mutual X509 certificate authentication.
3. The SOAP message goes through a validation and transformation layer. The XML
   records in the SOAP body are parsed and converted to individual DGOJ XML record.
4. Each individual DGOJ XML record goes through a dispatching processor which forwards
   the record to the appropriate batch queue. The dispatching logic is based upon the
   execution context (authenticated operator, vault instance, date, time…) and the relevant
   part of the record content (record type, game type, period…).

OT-MORPHO RESTRICTED

D3S Online Gaming Spain Edition  
Functional Specification

Réf. : Dictao_D3S_JEL_FunctionalSpec_ES version 2.1 du 2011/10/218 12/110  
Communication, reproduction ou utilisation interdites sauf autorisation préalable de OT-Morpho

5. Multiple individual DGOJ XML records are compound together in a single DGOJ XML
   batch. This batching is done according to the regulatory rules in term of number of events
   per batch and maximum elapse time between the first and last events in a batch.
6. Each DGOJ XML batch is digitally signed using the standard XAdES BES 1.3.2 format.
   The signature might eventually be time-stamped, resulting in an extended XAdES-T
   format. The time-stamping is activated or not by configuration.
7. Each DGOJ XML batch is compress then encrypted using the ZIP+AES de-facto
   standard, resulting in a ZIP file. Note that the order is significant and compression must
   always be done before encryption. Encryption adds entropy to the data which make
   compression useless. In the XML DGOJ batch and its corresponding digital signature are
   grouped into the same ZIP batch.
8. Each ZIP batch are written on the disk as they are produced by the system. The files are
   stored on a file system following a strict folder structure and naming convention. The
   layout is based upon the context (operator sending the event, vault processing the event,
   time, batch id…) and the content of the record (record type, game type…).
9. Finally, on a daily basis, a background activity groups individual ZIP files generated the
   previous day into a daily ZIP file (JU record only as detailed later). The daily ZIP file
   cannot exceed 1GB, if total daily volume is greater than 1GB; the daily ZIP file is span
   across multiple chunks of 1GB at most.

#### 3.1.2 Usage Statistics

The functional flow is monitored at the different stages of the processing, including

- The number of requests per second receive on average and peak time,
- The min, max and average request size,
- A breakdown of min, max, average XML DGOJ record size per record type (output of the
  transformation)
- A breakdown of min, max average ZIP size and compression per batch type.
- The average daily storage growth per operator,
- The usage statistics for billing.

#### 3.1.3 Synchronous vs Asynchronous

The functional flow is divided in two parts:

1. The first part is synchronous. It includes the operations 1 to 4 (SOAP request handling,
   authentication, transformation and dispatch).
2. The second part is asynchronous. It includes all the remaining operation 5 to 9 (batch,
   sign, compress & encrypt, store and archive)

The synchronous operations are executed within the thread handling the incoming SOAP request.

The Capture Device caller sends the request and waits until it received a response for the D3S
Vault. The caller thread is blocked while the call is being processed. The D3S returns a status
indicating whether the request was valid or not.

The D3S executes the first 4 operations synchronously in order to fully validate the incoming
request as follows:

OT-MORPHO RESTRICTED

D3S Online Gaming Spain Edition  
Functional Specification

Réf. : Dictao_D3S_JEL_FunctionalSpec_ES version 2.1 du 2011/10/218 13/110  
Communication, reproduction ou utilisation interdites sauf autorisation préalable de OT-Morpho

- It validate that the SOAP message in well-formed. If validation fails, it returns an error
  immediately.
- It authenticates the Capture Device. If the X509 certificate is unknown, it returns an error
  immediately.
- It validates and transforms the body to an individual DGOJ XML. If the validation or
  transformation fails, it returns an error immediately.
- It interprets the relevant part of the DGOJ record, and dispatches it to the right batch
  queue. If the dispatch is not authorized for the authenticated operator, it returns an error
  immediately.

By design, once all these operations have been completed successfully, the D3S knows that it
will be able to complete the remaining operations successfully. Consequently, it returns
immediately a success status code and proceeds with the remaining operations asynchronously.

### 3.2 Web Service Front-end

#### 3.2.1 Overview of the Recording API

The D3S vault exposes its recording API via Web service endpoints using SOAP over HTTPS.

All endpoints are fully described by a WSDL document that is provided:

- Statically within a development kit,
- Dynamically by the endpoint itself.

#### 3.2.2 WSDL and SOAP format

A WSDL document describes the how the service is bound to a specific SOAP message protocol.
Several options exist in the standard, namely RPC and document binding with either encoding or
literal body.

The D3S WSDL uses a document/literal style with request/response wrapped. The style is
illustrated below:

<types>  
<schema>  
<element name="myMethod">  
<complexType>  
<sequence>  
<element name="firstname" type="xs:string"/>  
<element name="lastname" type="xs:string"/>  
</sequence>  
</complexType>  
</element>  
<element name="myMethodResponse">  
<complexType>  
<element name="returnValue" type="xs:int"/>  
</complexType>  
</element>  
</schema>  
</types>  
<message name="myMethod">  
<part element="myMethod" name="input" />

OT-MORPHO RESTRICTED

D3S Online Gaming Spain Edition  
Functional Specification

Réf. : Dictao_D3S_JEL_FunctionalSpec_ES version 2.1 du 2011/10/218 14/110  
Communication, reproduction ou utilisation interdites sauf autorisation préalable de OT-Morpho

</message>  
<message name="myMethodResponse">  
<part element="myMethodResponse" name="output" />  
</message>  
<portType name="PT">  
<operation name="myMethod">  
<input message="myMethod"/>  
<output message="myMethodResponse"/>  
</operation>  
</portType>

The SOAP message sent over the wire is illustrated below

<soap:envelope>  
<soap:body>  
<myMethod>  
<firstname>john</firstname>  
<lastname>doe</lastname>  
</myMethod>  
</soap:body>  
</soap:envelope>

With this style, the XML element defined in the SOAP body can be validate against an XSD
schema.

The WSDL is slightly more complex than a regular document/literal binding, where the element
“myMethod” and “myResponse” don’t exist. However, this style is broadly used and recent Web
service tooling (JAXWS for Java, WCF for .NET and more) detects this pattern and hides these
intermediates elements in the generated code they produce as illustrated below

int myMethod(String firstname, String lastname)

#### 3.2.3 Synchronous two-way

All methods defined in the recording API are both synchronous and two-way.

- The caller sends a request over HTTP and waits for the HTTP response,
- The D3S vault receive the request, executes it and write the response synchronously,
- The caller receives the HTTP response (success or failure) and acts accordingly.

#### 3.2.4 Fault Handling

When the D3S encounters an unexpected condition (invalid caller request, resource missing,
unexpected condition), it returns a SOAP fault to the caller.

Faults are classified in 2 main categories:

- UserError: the caller request is invalid and should be fixed on the caller side. The same
  request must not be resent to the D3S vault.
- SystemError: the D3S system has encountered an unexpected condition. The same
  request might be resubmitted to the D3S once the malfunction is fixed.

OT-MORPHO RESTRICTED

D3S Online Gaming Spain Edition  
Functional Specification

Réf. : Dictao_D3S_JEL_FunctionalSpec_ES version 2.1 du 2011/10/218 15/110  
Communication, reproduction ou utilisation interdites sauf autorisation préalable de OT-Morpho

#### 3.2.5 Duplicated Requests Detection

The availability of the Web service API relies upon the underlying network layer. In general, the
API is in one of the following states:

- The network is up: requests and responses are processed successfully,
- The network is down: requests fail before they reach the D3S vault.

In those situations, no extra care needs to be taken: requests are either fully processed or not
processed at all.

There is one situation that needs special care: if the network goes down while a request is being
processed, the request might have been fully executed by the D3S but the response never reach
the caller. The caller will probably submit the request again, which will eventually be received by
the D3S vault and executed a second time.

In order to prevent these duplicate requests, the D3S uses the following duplicate detection
protocol:

- The caller specifies a unique identifier in each request submitted within the SOAP header.
- When a network error occurs, the caller retries the same request with the same unique
  ID.
- The D3S vault keeps the request ID of the last 5 minutes working period.
- The first request is executed normally, subsequent duplicate requests are ignored.

In high-availability hosting environment, where multiple instances of the D3S vault are deployed
on a Web server hosting farm, the load balancing algorithm must manage session affinity based
upon this unique ID or equivalent.

#### 3.2.6 Request Context

A request context is allocated and populated with the IP address of the requester and forwarded
to the next operation.

### 3.3 User Authentication

#### 3.3.1 Transport Layer Security

The D3S vault implements the standard security protocol “Transport Layer Security” (TLS) to
secure the incoming SOAP requests and outgoing SOAP responses.

TLS is a client-server protocol that fulfills the following objectives:

- Server authentication,
- Client authentication,
- Integrity and confidentiality of exchanged messages.

The authentications are based upon X509 certificates that are issued by known and trusted CA
on both ends.

OT-MORPHO RESTRICTED

D3S Online Gaming Spain Edition  
Functional Specification

Réf. : Dictao_D3S_JEL_FunctionalSpec_ES version 2.1 du 2011/10/218 16/110  
Communication, reproduction ou utilisation interdites sauf autorisation préalable de OT-Morpho

#### 3.3.2 User Directory

Once the TLS channel has been established between the caller and the D3S vault, the vault gets
the SSL X509 certificate of the caller.

From that point, the vault:

- Extract the Issuer DN (DN of the trusted CA that issued the certificate),
- Extract the Subject DN (DN of the caller’s certificate itself),
- Lookup if the user key pair {IssuerDN+SubjectDN} exists in the user directory.

The user directory associates the user key pair {IssuerDN+SubjectDN} with a set of rights and
configuration parameters. This directory is managed by the D3S administrators.

- If the pair exists, the configuration and rights are loaded into the vault and associated to
  the incoming request.
- If the pair doesn’t exist, the D3S vault returns an error immediately.

#### 3.3.3 Authentication Context

An authentication context is allocated and populated with the parameters retrieve from the user
directory and forwarded to the next operation.

### 3.4 Validation & Transformation

#### 3.4.1 SOAP Body Validation

As specified in the Web service section, the Web service WSDL follows the encoding style
document/literal. This style ensures that all messages in the SOAP body are defined in a XSD
document.

As such, the XML can be fully validated against an XSD schema.

#### 3.4.2 OT-Morpho XML vs DGOJ XML

Before being stored, the XML records must go throw different steps including:

1. Capturing the actual information ultimately stored in the XML,
2. Sending the information between the different subsystems up to the vault,
3. Formatting the information in the DGOJ XSD compliant format.

The DGOJ XSD schema defines the structure of the XML document stored onto the file system,
which will eventually be uploaded and interpreted by the regulator.

The DGOJ XSD is not well suited to manipulate the data during these preliminary steps for
different reasons:

- The DGOJ XSD is in Spanish which is not adequate for non-Spanish speaker.

OT-MORPHO RESTRICTED

D3S Online Gaming Spain Edition  
Functional Specification

Réf. : Dictao_D3S_JEL_FunctionalSpec_ES version 2.1 du 2011/10/218 17/110  
Communication, reproduction ou utilisation interdites sauf autorisation préalable de OT-Morpho

- The DGOJ XSD defines the coarse grain compound element that cannot be computed
  until the final processing stage.
- The DGOJ XSD is storage centric, meaning it does that into account how the data are
  capture and sent to the vault.
- The Capture device cannot be shielded from structural changes of the DGOJ XSD.
- …

OT-Morpho has defined its own XSD that address these issues:

- The OT-Morpho XSD is in English,
- The OT-Morpho XSD hides structural changes in the DGOJ XSD,
- The OT-Morpho XSD is fine grain, defining individual element that can be computed
  where the data is capture.
- The OT-Morpho XSD is capture centric, along with the WSDL document, it precisely
  defines what, when and how data is sent to the vault.

The D3S vault implements its own transformation engine. XML records sent to the vault in the
OT-Morpho XML format are transformed in the DGOJ XML format transparently. The data model
mapping is specified in section “4- Data Model Mapping Rules”.

#### 3.4.3 Transformation Context

A transformation context is allocated and populated with the original XML type of the OT-Morpho
record and forwarded to the next operation.

### 3.5 Dispatching

#### 3.5.1 Dispatch Logic

The dispatching logic determines the destination of individual DGOJ XML records.

To that end, it uses the different contexts populated in the previous stages:

- Request context,
- Authentication context,
- Transformation context.

And the content of the individual DGOJ XML elements transformed in the previous stage.

The triage is done as follows:

- The operatorId: this information is retrieved from the authentication context associated to
  the request during the authentication stage and the XML element being processed. Both
  must match.
- The record top-level category: the top-level category is determined from the type of the
  XML element being processed. See section “Top-Level Categories”

OT-MORPHO RESTRICTED

D3S Online Gaming Spain Edition  
Functional Specification

Réf. : Dictao_D3S_JEL_FunctionalSpec_ES version 2.1 du 2011/10/218 18/110  
Communication, reproduction ou utilisation interdites sauf autorisation préalable de OT-Morpho

- The periodicity: the periodicity is determined from the type of the XML element being
  processed. Periodic event inherits from the XML element “RegistroPeriodicoBase”.
- The type of game for JUT: the type of game is determined from XML type being
  processed. Each game type has a specific JUT specialized type (RegistroPokerCash,
  RegistroBlackjack, …)
- The type of game for JUD: this information is extracted from the transformation context
  that keeps the type of the OT-Morpho XML (as of today, the RegistroJUD is not self-
  content and doesn’t contain any information that can be used to determine the related
  game type).

#### 3.5.2 Asynchronous Queuing

The D3S vault maintains a queue for each type of batch that must be produced.

- RUT x (Daily, Monthly)
- RUD x (Daily, Monthly)
- RUR x (Daily, Monthly)
- RUG x (Daily, Monthly)
- CJT x (Daily, Monthly)
- CJD x (Daily, Monthly)
- OPT x (Daily, Monthly)
- ORT x (Daily, Monthly)
- BOT x (Daily, Monthly)
- JUT x (Game Types)
- JUD x (Game Types)
- JUA (Bets only)
- CEV (Bets only)

Once the dispatch logic has completed, the XML record is pushed into one of those queues. The
synchronous processing is completed. The remaining operations will be executed
asynchronously, getting XML events from the queues.

#### 3.5.3 Top-Level Categories

The following table defines the top-level category of individual DGOJ record.

| Top-Level Category | Individual Record |
|---|---|
| RU | RegistroRUT |
|  | RegistroRUD |
|  | RegistroRUR |
|  | RegistroRUG |
| CJ | RegistroCJT |

OT-MORPHO RESTRICTED

D3S Online Gaming Spain Edition  
Functional Specification

Réf. : Dictao_D3S_JEL_FunctionalSpec_ES version 2.1 du 2011/10/218 19/110  
Communication, reproduction ou utilisation interdites sauf autorisation préalable de OT-Morpho

| Top-Level Category | Individual Record |
|---|---|
|  | RegistroCJD |
| OP | RegistroOPT |
|  | RegistroORT |
|  | RegistroBOT |
| JU | RegistroJUD |
|  | RegistroPokerCash |
|  | RegistroPokerTorneo |
|  | RegistroPuntoBanca |
|  | RegistroBingo |
|  | RegistroConcurso |
|  | RegistroApuesta |
|  | RegistroCEV |
|  | RegistroJUA |

#### 3.5.4 Type of Games

The types of game are the following:

- AHC – Fixed-Odds Horseracing Bets
- AHM – Mutual Horseracing Bets
- AHX – Bet Exchange Horseracing Bets
- ADC – Fixed-Odds Sports Bets
- ADX – Bet Exchange Sports Bets
- ADM – Mutual Sports Bets
- AOC – Other Fixed-Odds Bets
- AOX – Other Bet Exchange
- POT – Tournament Poker
- POC – Cash Poker
- BLJ – Blackjack
- PUN – Baccarat
- BNG – Bingo
- RLT – Roulette
- COC – Contests
- AZA – Slots
- COM – Additional Games

OT-MORPHO RESTRICTED

D3S Online Gaming Spain Edition  
Functional Specification

Réf. : Dictao_D3S_JEL_FunctionalSpec_ES version 2.1 du 2011/10/218 20/110  
Communication, reproduction ou utilisation interdites sauf autorisation préalable de OT-Morpho

### 3.6 Batch Management

#### 3.6.1 Purpose of batch

A batch is used to group records together since it would be unmanageable to have a dedicated
XML file for each generated record.

A batch correspond to one file on the file system; it has an identifier that must be unique for a
given digital vault and operator.

For ease of implementation and maintenance, the batch ID generated by the D3S vault is a
globally unique identifier (GUID)

#### 3.6.2 Batching Rules

Batches must be generated according to the following rules:

- Periodical information (RU, CJ, OP): each record will go in one batch or split in several
  batch if the size exceed a predefined threshold.
  - RUD and CJD: up to 1000 players per batch, split in several batch if more than
    1000 players.
  - RUT, CJT, OP: one batch per record.
- Pseudo real-time information (JU): a new batch is generated
  - When a configurable amount of time has elapse between the first record and the
    last record in a batch. The configuration is fixed to 5 minutes.
  - When a configurable amount of record has been packed together. The
    configuration is fixed to 1000 record.

### 3.7 Signature & Timestamp

#### 3.7.1 Digital Signature

The XML batch document must be signed using a digital signature method. The method must
comply with the XAdES BES 1.3.2.

The XAdES standard is an extension of the W3C XML Digital Signature standard [DSIG]. Different
variants of the signature exist; DGOJ authorized the following variants:

- Enveloped signature,
- Enveloping with Manifest signature.

The D3S vault uses the “Enveloping with Manifest” variants; the data and the signature are stored
in two different files:

- A XML “lote.xml” file that contains the actual captured data,
- A XML “enveloping.xml” file that contains the enveloping signature of the data manifest.

OT-MORPHO RESTRICTED

D3S Online Gaming Spain Edition  
Functional Specification

Réf. : Dictao_D3S_JEL_FunctionalSpec_ES version 2.1 du 2011/10/218 21/110  
Communication, reproduction ou utilisation interdites sauf autorisation préalable de OT-Morpho

##### 3.7.1.1 Signature Characteristics

The Manifest element is specifically design to optimize the signature processing. The signature
content is illustrated below

<Signature>  
<SignedInfo>  
...  
<Reference URI="#MyFirstManifest"  
Type="http://www.w3.org/2000/09/xmldsig#Manifest">  
<Transforms>  
<Transform Algorithm="http://www.w3.org/2006/12/xml-c14n11"/>  
</Transforms>  
<DigestMethod Algorithm="http://www.w3.org/2001/04/xmlenc#sha256"/>  
<DigestValue>dGhpcyBpcyBub3QgYSBzaWduYXR1cmUK...=</DigestValue>  
</Reference>  
</SignedInfo>  
...  
<Object>  
<Manifest Id="MyFirstManifest">  
<Reference URI="file: ... lote.xml">  
<DigestMethod Algorithm="http://www.w3.org/2001/04/xmlenc#sha256"/>  
<DigestValue>dGhpcyBpcyBub3QgYSBzaWduYXR1cmUK...=</DigestValue>  
</Reference>  
</Manifest>  
</Object>  
</Signature>

The XML node `<Signature>` is “enveloping” because it contains an inner `<Object>` node that
contains the `<Manifest>` node. The digest algorithm used is SHA256.

The `<SignedInfo>` node has the following characteristics:

- The `<Reference>` Type is set to "http://www.w3.org/2000/09/xmldsig#Manifest".
- The `<Reference>` URI points to the Manifest,
- A C14N transformation is done on the Manifest.

The `<Manifest>` node adds a level on indirection between the signature and the lote.xml file. It
has the following characteristics:

- It defines a single `<Reference>` node,
- The `<Reference>` URI points to the “lote.xml” file using a file scheme.
- The `<Reference>` DigestValue is computed on the “lote.xml” without any transformation.

##### 3.7.1.2 URI

The URI that points to the lote.xml follows the file scheme “file:” and is equal to the relative path
of the file from the DGOJ root directory.

For instance, for a JUT lot, the URI is:

file:DGOJ/JUT/20111019/JUT/BLJ/OperadorId_VaultId_Type_Subtype_Period_Date_BatchId.zip/lote.xml

OT-MORPHO RESTRICTED

D3S Online Gaming Spain Edition  
Functional Specification

Réf. : Dictao_D3S_JEL_FunctionalSpec_ES version 2.1 du 2011/10/218 22/110  
Communication, reproduction ou utilisation interdites sauf autorisation préalable de OT-Morpho

#### 3.7.2 Time stamping

The DGOJ doesn’t require the signature to be time-stamped. This might eventually be required.
In that case, the XAdES BES signature will be extended to a XAdES-T signature.

There is no impact on the overall functional flow. The XAdES-T format simply adds new nodes in
the existing “enveloping.xml” document.

The D3S vault already supports both XAdES-BES and XAdES-T.

### 3.8 Compress & Encrypt

#### 3.8.1 Formatting Rules

The XML files “lote.xml” and corresponding signature “enveloping.xml” are put together in a single
ZIP file.

The ZIP format is a de-facto standard that follows the PKWare specification along with WinZIP
extension.

The encryption is based upon a static password given by the DGOJ and configured in the D3S
vault.

#### 3.8.2 Compression Algorithm

The compression algorithm is "Deflate".

#### 3.8.3 Encryption Algorithm

The encryption algorithm is "AES-256 ".

### 3.9 Directory and File Convention

#### 3.9.1 Directory Structure

The file system storage is organized in directories as illustrated below.

OT-MORPHO RESTRICTED

D3S Online Gaming Spain Edition  
Functional Specification

Réf. : Dictao_D3S_JEL_FunctionalSpec_ES version 2.1 du 2011/10/218 23/110  
Communication, reproduction ou utilisation interdites sauf autorisation préalable de OT-Morpho

##### 3.9.1.1 Common base directories

The level 1 and 2 are follows the same layout for all kind of records

- Level 1: DGOJ
- Level 2: OperadorId

(The inclusion of operator data facilitates the existence of several operators in the same digital
vault)

##### 3.9.1.2 Periodic Records

The periodic records (RU, CJ and OP) are organized as follow:

- Levels 3, 4, 5 & 6:

OT-MORPHO RESTRICTED

D3S Online Gaming Spain Edition  
Functional Specification

Réf. : Dictao_D3S_JEL_FunctionalSpec_ES version 2.1 du 2011/10/218 24/110  
Communication, reproduction ou utilisation interdites sauf autorisation préalable de OT-Morpho

- RU – User Registration
  - Diaro (Daily) / Mensual (Monthly)
    - RUT – User Registration (totals)
    - RUD – User Registration (by player)
  - Mensual
    - RUR – User Registration (network)
    - RUG – User Registration (by winner)
- CJ – Gaming account
  - Diaro (Daily) / Mensual (Monthly)
    - CJT – Gaming account (totals)
    - CJD – Gaming account (by player)
- OP – Operator
  - Subfolder for each Type of Game (see section ‘Type of Game’)
    - Diaro (Daily) / Mensual (Monthly)
- OPT – Operator Account (totals)
- ORT – Network Operator Account (totals)
- BOT – Jackpots and live game rounds Account (totals)

##### 3.9.1.3 Pseudo Real-time Records

The pseudo real-time records (JU) are organized as follows:

- Levels 3, 4, 5 & 6:
  - JU – Game
    - AAAAMMDD Day in progress
      - JUT – Game (totals)
        - Subfolder for each Type of Game
      - JUD – Game (by player)
        - Subfolder for each Type of Game
      - Anteriores
      - Mensual
        - JUA – Adjustment
        - CEV – Event catalog

#### 3.9.2 File Naming

##### 3.9.2.1 RU – User Registration

The naming convention is:

˂OperadorId˃_˂VaultId˃_˂Type˃_˂Subtype˃_˂Period˃_˂Date˃_˂BatchId˃ zip

OT-MORPHO RESTRICTED

D3S Online Gaming Spain Edition  
Functional Specification

Réf. : Dictao_D3S_JEL_FunctionalSpec_ES version 2.1 du 2011/10/218 25/110  
Communication, reproduction ou utilisation interdites sauf autorisation préalable de OT-Morpho

Values:

- ˂OperadorId˃ is the identifier of the operator
- ˂VaultId˃ is the identifier of the digital vault [Vault]
- ˂Type˃ will be RU
- ˂Subtype˃ may be: RUT, RUD, RUR, RUG
- ˂Period˃ may be: D (daily) or M [monthly]
- ˂Date˃ is the date on which the data are declared (not the date of writing in the digital
  vault). It will have the value AAAAMMDD for daily information and AAAAMMM for monthly
  information.
- ˂BatchId˃ is the identifier of the batch

Example:

##### 3.9.2.2 CJ –Gaming Account

The naming convention is:

˂OperadorId˃_˂VaultId˃_<Type>_˂Subtype˃_˂Period˃_˂Date˃_˂BatchId˃ zip

Values:

- ˂OperadorId˃ is the identifier of the operator
- ˂VaultId˃ is the identifier of the digital vault [Vault]
- ˂Type˃ will be CJ
- ˂Subtype˃ may be: CJT, CJD
- ˂Period˃ may be: D (daily) or M [monthly]
- ˂Date˃ is the date on which the data are declared (not the date of writing in the digital vault).
  It will have the value AAAAMMDD for daily information and AAAAMMM for monthly
  information.
- ˂BatchId˃ is the identifier of the lote [batch]

Example:

#### 3.9.3 OP - Operator Account

The nomenclature is:

˂OperadorId˃_˂VaultId˃_˂Type˃_˂Subtype˃_˂Period˃_˂Date˃_˂BatchId˃ zip

Values:

OT-MORPHO RESTRICTED

D3S Online Gaming Spain Edition  
Functional Specification

Réf. : Dictao_D3S_JEL_FunctionalSpec_ES version 2.1 du 2011/10/218 26/110  
Communication, reproduction ou utilisation interdites sauf autorisation préalable de OT-Morpho

- ˂OperadorId˃ is the identifier of the operator
- ˂VaultId˃ is the identifier of the digital vault [Vault]
- ˂Type˃ will be OP
- ˂Subtype˃ may be: OPT, ORT or BOT
- ˂Period˃ may be: D (daily) or M [monthly]
- ˂Date˃ is the date on which the data are declared (not the date of writing in the digital
  vault). It will have the value AAAAMMDD for daily information and AAAAMMM for monthly
  information.
- ˂BatchId˃ is the identifier of the batch

Example:

#### 3.9.4 JU – Games

The files for the day in progress will have the following nomenclature:

˂OperadorId˃_˂VaultId˃_˂Type˃_˂Subtype˃_˂GameType˃_˂DateTime˃_˂BatchId˃ zip

Values:

- ˂OperadorId˃ is the identifier of the operator
- ˂Type˃ will be JU
- ˂Subtype˃may be: JUT or JUD
- <GameType> according to the list of game types (See section ‘Type of Game’)
- ˂DateTime˃ is the date of the batch, format AAAAMMDDHHMMSS [Year-Month-Day-
  Hour-Minute-Second].
- ˂BatchId˃ is the identifier of the batch

Example

#### 3.9.5 JU - JUA/CEV

The files for the day in progress will have the following nomenclature:

˂OperadorId˃_˂VaultId˃_˂Type˃_˂Subtype˃_˂Periodicity˃_˂Date˃_˂BatchId˃ zip

Values:

- ˂OperadorId˃ is the identifier of the operator

OT-MORPHO RESTRICTED

D3S Online Gaming Spain Edition  
Functional Specification

Réf. : Dictao_D3S_JEL_FunctionalSpec_ES version 2.1 du 2011/10/218 27/110  
Communication, reproduction ou utilisation interdites sauf autorisation préalable de OT-Morpho

- ˂Type˃ will be JU
- ˂Subtype˃may be: JUA or CEV
- <GameType> according to the list of game types (See section ‘Type of Game’)
- ˂Date˃ is the date of the batch, format AAAAMM [Year-Month-Day-Hour-Minute-
  Second].
- ˂BatchId˃ is the identifier of the batch

### 3.10 Daily Archiving

#### 3.10.1 Daily Archiving of RegistoJUx Records

The JU batch files for the day in progress are stored individually. Once the day ends, all individual
ZIP files must be aggregated together in a single ZIP file.

As defined in the previous section, the “Level 4 of Game Record” will have a folder for the day in
progress and another folder for the previous days:

- AAAAMMDD (Year-Month-Day) – for the day in progress
- Anteriores – for the previous days

The records for Games are generated in pseudo-real time in the AAAAMMDD folder. The day in
progress will contain all the batches/files generated individually.

When the day finishes (24:00 Spain timezone), the D3S vault lists all generated files on the
previous day and package them all in a single ZIP file without compression.

This packaged ZIP files must keep the relative path (the structure of subfolders from
AAAAMMDD]) and all the batches/files of the day.

The daily ZIP has the following characteristics

- ZIP without compression,
- Up to 1GB at most,
- If the individual ZIP files of the previous day exceed the threshold of 1 GB, several ZIP
  fragment will be generated.
- The daily ZIP files or ZIP fragment must be stored in to the “Anteriores” folder.
- 

Once the daily ZIP processing has completed successfully, the D3S can purge the original files.

- NOTE: There is no explicit requirements to carry out the daily packaging in a target
  time; Several AAAAMMDD (Year-Month-Day) folders might exist during a specific
  period of time.

OT-MORPHO RESTRICTED

D3S Online Gaming Spain Edition  
Functional Specification

Réf. : Dictao_D3S_JEL_FunctionalSpec_ES version 2.1 du 2011/10/218 28/110  
Communication, reproduction ou utilisation interdites sauf autorisation préalable de OT-Morpho

#### 3.10.2 Naming Convention

The packaged files for the Game event of the previous days will have the following nomenclature:

˂OperadorId˃_˂VaultId˃_˂Type˃_DIARIO_˂Date˃_˂ZIP˃

Values:

- ˂OperadorId˃ is the identifier of the operator
- ˂Type˃ [type] will be JU
- ˂Date˃ date of the aggregated day, format AAAAMMDD [Year-Month-Day].
- ˂ZIP˃. The extension must be ‘zip’ but other correlative extensions will appear if
  fragmentation is necessary because the size of 1GB is exceeded.

OT-MORPHO RESTRICTED

D3S Online Gaming Spain Edition  
Functional Specification

Réf. : Dictao_D3S_JEL_FunctionalSpec_ES version 2.1 du 2011/10/218 29/110  
Communication, reproduction ou utilisation interdites sauf autorisation préalable de OT-Morpho

## 4. DATA MODEL MAPPING RULES

### 4.1 Definitions

#### 4.1.1 Data Model

The DGOJ XML data model is detailed in the document [MOD20], [XSD03] and [XSD04].

The OT-Morpho XML data model is detailed in the document [WSAPI].

The sections below summarize the mapping rules between the DGOJ XML and OT-Morpho XML.

#### 4.1.2 Mapping Convention

| DGOJ XML | OT-Morpho XML | Meaning |
|---|---|---|
| <DGOJ element> | < OT-Morpho element> | The specified DGOJ element is mapped to the specified OT-Morpho element. |
| <DGOJ element> | - | The specified <DGOJ element> doesn’t exist in the OT-Morpho definition. It typically happens for structural mapping (flatten or nesting elements), that are handled by the transformation engine without the need of external input. |
| <DGOJ element> | built-in | The specified DGOJ element is computed dynamically by the transformation engine. |
| <DGOJ element> | literal (for instance 1) | The specified DGOJ element is pre-defined in the transformation engine. |
| *<DGOJ element> | *< OT-Morpho element> | One or more values are inherited from the specified types (typically abstract types RegistroBase, RegistroPeriodicoBase, RegistroJUT). This is for convenience only is this specification document to avoid copy and paste in the mapping table. |

### 4.2 Complete Mapping

| OT-Morpho field | DGOJ field |
|---|---|
| /CasinoRecord/sessionTotal | /RegistroSesion |
| /CasinoRecord/sessionTotal/operatorId | /RegistroSesion/Cabecera/OperadorId |
| /CasinoRecord/sessionTotal/recordId | /RegistroSesion/Cabecera/RegistroId |
| /CasinoRecord/sessionTotal/date | /RegistroSesion/Cabecera/Fecha |
| /CasinoRecord/sessionTotal/subRecordId | /RegistroSesion/Cabecera/SubregistroId |
| /CasinoRecord/sessionTotal/subRecordTotal | /RegistroSesion/Cabecera/SubregistroTotal |
| /CasinoRecord/sessionTotal/gameId | /RegistroSesion/JuegoId |
| /CasinoRecord/sessionTotal/gameDesc | /RegistroSesion/JuegoDesc |
| /CasinoRecord/sessionTotal/gameType | /RegistroSesion/TipoJuego |
| /CasinoRecord/sessionTotal/startDate | /RegistroSesion/FechaInicio |
| /CasinoRecord/sessionTotal/endDate | /RegistroSesion/FechaFin |
| /CasinoRecord/sessionTotal/networkGame | /RegistroSesion/JuegoEnRed |
| /CasinoRecord/sessionTotal/postponed | /RegistroSesion/JuegoAplazado |
| /CasinoRecord/sessionTotal/suspended | /RegistroSesion/JuegoSuspendido |
| /CasinoRecord/sessionTotal/canceled | /RegistroSesion/JuegoCancelado |
| /CasinoRecord/sessionTotal/total | /RegistroSesion/Totales |
| /CasinoRecord/sessionTotal/total/placement | /RegistroSesion/Totales/Participacion |
| /CasinoRecord/sessionTotal/total/placement/total | /RegistroSesion/Totales/Participacion/Total |
| /CasinoRecord/sessionTotal/total/placement/total/line | /RegistroSesion/Totales/Participacion/Total/Linea |
| /CasinoRecord/sessionTotal/total/placement/total/line/amount | /RegistroSesion/Totales/Participacion/Total/Linea/Cantidad |
| /CasinoRecord/sessionTotal/total/placement/total/line/unit | /RegistroSesion/Totales/Participacion/Total/Linea/Unidad |
| /CasinoRecord/sessionTotal/total/placement/breakdown | /RegistroSesion/Totales/Participacion/Desglose |
| /CasinoRecord/sessionTotal/total/placement/breakdown/operatorId | /RegistroSesion/Totales/Participacion/Desglose/OperadorId |
| /CasinoRecord/sessionTotal/total/placement/breakdown/amount | /RegistroSesion/Totales/Participacion/Desglose/Importe |
| /CasinoRecord/sessionTotal/total/placement/breakdown/amount/line | /RegistroSesion/Totales/Participacion/Desglose/Importe/Linea |
| /CasinoRecord/sessionTotal/total/placement/breakdown/amount/line/amount | /RegistroSesion/Totales/Participacion/Desglose/Importe/Linea/Cantidad |
| /CasinoRecord/sessionTotal/total/placement/breakdown/amount/line/unit | /RegistroSesion/Totales/Participacion/Desglose/Importe/Linea/Unidad |
| /CasinoRecord/sessionTotal/total/refund | /RegistroSesion/Totales/ParticipacionDevolucion |
| /CasinoRecord/sessionTotal/total/refund/total | /RegistroSesion/Totales/ParticipacionDevolucion/Total |
| /CasinoRecord/sessionTotal/total/refund/total/line | /RegistroSesion/Totales/ParticipacionDevolucion/Total/Linea |
| /CasinoRecord/sessionTotal/total/refund/total/line/amount | /RegistroSesion/Totales/ParticipacionDevolucion/Total/Linea/Cantidad |
| /CasinoRecord/sessionTotal/total/refund/total/line/unit | /RegistroSesion/Totales/ParticipacionDevolucion/Total/Linea/Unidad |
| /CasinoRecord/sessionTotal/total/refund/breakdown | /RegistroSesion/Totales/ParticipacionDevolucion/Desglose |
| /CasinoRecord/sessionTotal/total/refund/breakdown/operatorId | /RegistroSesion/Totales/ParticipacionDevolucion/Desglose/OperadorId |
| /CasinoRecord/sessionTotal/total/refund/breakdown/amount | /RegistroSesion/Totales/ParticipacionDevolucion/Desglose/Importe |
| /CasinoRecord/sessionTotal/total/refund/breakdown/amount/line | /RegistroSesion/Totales/ParticipacionDevolucion/Desglose/Importe/Linea |
| /CasinoRecord/sessionTotal/total/refund/breakdown/amount/line/amount | /RegistroSesion/Totales/ParticipacionDevolucion/Desglose/Importe/Linea/Cantidad |
| /CasinoRecord/sessionTotal/total/refund/breakdown/amount/line/unit | /RegistroSesion/Totales/ParticipacionDevolucion/Desglose/Importe/Linea/Unidad |
| /CasinoRecord/sessionTotal/total/inKindPrizes | /RegistroSesion/Totales/PremiosEspecie |
| /CasinoRecord/sessionTotal/total/inKindPrizes/total | /RegistroSesion/Totales/PremiosEspecie/Total |
| /CasinoRecord/sessionTotal/total/inKindPrizes/total/line | /RegistroSesion/Totales/PremiosEspecie/Total/Linea |
| /CasinoRecord/sessionTotal/total/inKindPrizes/total/line/amount | /RegistroSesion/Totales/PremiosEspecie/Total/Linea/Cantidad |
| /CasinoRecord/sessionTotal/total/inKindPrizes/total/line/unit | /RegistroSesion/Totales/PremiosEspecie/Total/Linea/Unidad |
| /CasinoRecord/sessionTotal/total/inKindPrizes/breakdown | /RegistroSesion/Totales/PremiosEspecie/Desglose |
| /CasinoRecord/sessionTotal/total/inKindPrizes/breakdown/operatorId | /RegistroSesion/Totales/PremiosEspecie/Desglose/OperadorId |
| /CasinoRecord/sessionTotal/total/inKindPrizes/breakdown/amount | /RegistroSesion/Totales/PremiosEspecie/Desglose/Importe |
| /CasinoRecord/sessionTotal/total/inKindPrizes/breakdown/amount/line | /RegistroSesion/Totales/PremiosEspecie/Desglose/Importe/Linea |
| /CasinoRecord/sessionTotal/total/inKindPrizes/breakdown/amount/line/amount | /RegistroSesion/Totales/PremiosEspecie/Desglose/Importe/Linea/Cantidad |
| /CasinoRecord/sessionTotal/total/inKindPrizes/breakdown/amount/line/unit | /RegistroSesion/Totales/PremiosEspecie/Desglose/Importe/Linea/Unidad |
| /CasinoRecord/sessionTotal/total/cashWinnings | /RegistroSesion/Totales/Premios |
| /CasinoRecord/sessionTotal/total/cashWinnings/total | /RegistroSesion/Totales/Premios/Total |
| /CasinoRecord/sessionTotal/total/cashWinnings/total/line | /RegistroSesion/Totales/Premios/Total/Linea |
| /CasinoRecord/sessionTotal/total/cashWinnings/total/line/amount | /RegistroSesion/Totales/Premios/Total/Linea/Cantidad |
| /CasinoRecord/sessionTotal/total/cashWinnings/total/line/unit | /RegistroSesion/Totales/Premios/Total/Linea/Unidad |
| /CasinoRecord/sessionTotal/total/cashWinnings/breakdown | /RegistroSesion/Totales/Premios/Desglose |
| /CasinoRecord/sessionTotal/total/cashWinnings/breakdown/operatorId | /RegistroSesion/Totales/Premios/Desglose/OperadorId |
| /CasinoRecord/sessionTotal/total/cashWinnings/breakdown/amount | /RegistroSesion/Totales/Premios/Desglose/Importe |
| /CasinoRecord/sessionTotal/total/cashWinnings/breakdown/amount/line | /RegistroSesion/Totales/Premios/Desglose/Importe/Linea |
| /CasinoRecord/sessionTotal/total/cashWinnings/breakdown/amount/line/amount | /RegistroSesion/Totales/Premios/Desglose/Importe/Linea/Cantidad |
| /CasinoRecord/sessionTotal/total/cashWinnings/breakdown/amount/line/unit | /RegistroSesion/Totales/Premios/Desglose/Importe/Linea/Unidad |
| /CasinoRecord/sessionTotal/total/jackpot | /RegistroSesion/Totales/Botes |
| /CasinoRecord/sessionTotal/total/jackpot/total | /RegistroSesion/Totales/Botes/Total |
| /CasinoRecord/sessionTotal/total/jackpot/total/line | /RegistroSesion/Totales/Botes/Total/Linea |
| /CasinoRecord/sessionTotal/total/jackpot/total/line/amount | /RegistroSesion/Totales/Botes/Total/Linea/Cantidad |
| /CasinoRecord/sessionTotal/total/jackpot/total/line/unit | /RegistroSesion/Totales/Botes/Total/Linea/Unidad |
| /CasinoRecord/sessionTotal/total/jackpot/breakdown | /RegistroSesion/Totales/Botes/Desglose |
| /CasinoRecord/sessionTotal/total/jackpot/breakdown/jackpotId | /RegistroSesion/Totales/Botes/Desglose/BoteId |
| /CasinoRecord/sessionTotal/total/jackpot/breakdown/jackpotDesc | /RegistroSesion/Totales/Botes/Desglose/BoteDesc |
| /CasinoRecord/sessionTotal/total/jackpot/breakdown/amount | /RegistroSesion/Totales/Botes/Desglose/Movimiento |
| /CasinoRecord/sessionTotal/total/jackpot/breakdown/amount/line | /RegistroSesion/Totales/Botes/Desglose/Movimiento/Linea |
| /CasinoRecord/sessionTotal/total/jackpot/breakdown/amount/line/amount | /RegistroSesion/Totales/Botes/Desglose/Movimiento/Linea/Cantidad |
| /CasinoRecord/sessionTotal/total/jackpot/breakdown/amount/line/unit | /RegistroSesion/Totales/Botes/Desglose/Movimiento/Linea/Unidad |
| /CasinoRecord/sessionTotal/variant | /RegistroSesion/Variante |
| /CasinoRecord/sessionTotal/variant=21 | /RegistroSesion/Variante=21 |
| /CasinoRecord/sessionTotal/variant=American | /RegistroSesion/Variante=Americana |
| /CasinoRecord/sessionTotal/variant=AM | /RegistroSesion/Variante=AM |
| /CasinoRecord/sessionTotal/variant=CL | /RegistroSesion/Variante=CL |
| /CasinoRecord/sessionTotal/variant=French | /RegistroSesion/Variante=Francesa |
| /CasinoRecord/sessionTotal/variant=PO | /RegistroSesion/Variante=PO |
| /CasinoRecord/sessionTotal/variant=SU | /RegistroSesion/Variante=SU |
| /CasinoRecord/sessionTotal/commercialVariant | /RegistroSesion/VarianteComercial |
| /CasinoRecord/sessionTotal/roundsPlayed | /RegistroSesion/PartidasJugadas |
| /CasinoRecord/baccaraTotal | /RegistroPuntoBanca |
| /CasinoRecord/baccaraTotal/operatorId | /RegistroPuntoBanca/Cabecera/OperadorId |
| /CasinoRecord/baccaraTotal/recordId | /RegistroPuntoBanca/Cabecera/RegistroId |
| /CasinoRecord/baccaraTotal/date | /RegistroPuntoBanca/Cabecera/Fecha |
| /CasinoRecord/baccaraTotal/subRecordId | /RegistroPuntoBanca/Cabecera/SubregistroId |
| /CasinoRecord/baccaraTotal/subRecordTotal | /RegistroPuntoBanca/Cabecera/SubregistroTotal |
| /CasinoRecord/baccaraTotal/gameId | /RegistroPuntoBanca/JuegoId |
| /CasinoRecord/baccaraTotal/gameDesc | /RegistroPuntoBanca/JuegoDesc |
| /CasinoRecord/baccaraTotal/gameType | /RegistroPuntoBanca/TipoJuego |
| /CasinoRecord/baccaraTotal/startDate | /RegistroPuntoBanca/FechaInicio |
| /CasinoRecord/baccaraTotal/endDate | /RegistroPuntoBanca/FechaFin |
| /CasinoRecord/baccaraTotal/networkGame | /RegistroPuntoBanca/JuegoEnRed |
| /CasinoRecord/baccaraTotal/postponed | /RegistroPuntoBanca/JuegoAplazado |
| /CasinoRecord/baccaraTotal/suspended | /RegistroPuntoBanca/JuegoSuspendido |
| /CasinoRecord/baccaraTotal/canceled | /RegistroPuntoBanca/JuegoCancelado |
| /CasinoRecord/baccaraTotal/total | /RegistroPuntoBanca/Totales |
| /CasinoRecord/baccaraTotal/total/placement | /RegistroPuntoBanca/Totales/Participacion |
| /CasinoRecord/baccaraTotal/total/placement/total | /RegistroPuntoBanca/Totales/Participacion/Total |
| /CasinoRecord/baccaraTotal/total/placement/total/line | /RegistroPuntoBanca/Totales/Participacion/Total/Linea |
| /CasinoRecord/baccaraTotal/total/placement/total/line/amount | /RegistroPuntoBanca/Totales/Participacion/Total/Linea/Cantidad |
| /CasinoRecord/baccaraTotal/total/placement/total/line/unit | /RegistroPuntoBanca/Totales/Participacion/Total/Linea/Unidad |
| /CasinoRecord/baccaraTotal/total/placement/breakdown | /RegistroPuntoBanca/Totales/Participacion/Desglose |
| /CasinoRecord/baccaraTotal/total/placement/breakdown/operatorId | /RegistroPuntoBanca/Totales/Participacion/Desglose/OperadorId |
| /CasinoRecord/baccaraTotal/total/placement/breakdown/amount | /RegistroPuntoBanca/Totales/Participacion/Desglose/Importe |
| /CasinoRecord/baccaraTotal/total/placement/breakdown/amount/line | /RegistroPuntoBanca/Totales/Participacion/Desglose/Importe/Linea |
| /CasinoRecord/baccaraTotal/total/placement/breakdown/amount/line/amount | /RegistroPuntoBanca/Totales/Participacion/Desglose/Importe/Linea/Cantidad |
| /CasinoRecord/baccaraTotal/total/placement/breakdown/amount/line/unit | /RegistroPuntoBanca/Totales/Participacion/Desglose/Importe/Linea/Unidad |
| /CasinoRecord/baccaraTotal/total/refund | /RegistroPuntoBanca/Totales/ParticipacionDevolucion |
| /CasinoRecord/baccaraTotal/total/refund/total | /RegistroPuntoBanca/Totales/ParticipacionDevolucion/Total |
| /CasinoRecord/baccaraTotal/total/refund/total/line | /RegistroPuntoBanca/Totales/ParticipacionDevolucion/Total/Linea |
| /CasinoRecord/baccaraTotal/total/refund/total/line/amount | /RegistroPuntoBanca/Totales/ParticipacionDevolucion/Total/Linea/Cantidad |
| /CasinoRecord/baccaraTotal/total/refund/total/line/unit | /RegistroPuntoBanca/Totales/ParticipacionDevolucion/Total/Linea/Unidad |
| /CasinoRecord/baccaraTotal/total/refund/breakdown | /RegistroPuntoBanca/Totales/ParticipacionDevolucion/Desglose |
| /CasinoRecord/baccaraTotal/total/refund/breakdown/operatorId | /RegistroPuntoBanca/Totales/ParticipacionDevolucion/Desglose/OperadorId |
| /CasinoRecord/baccaraTotal/total/refund/breakdown/amount | /RegistroPuntoBanca/Totales/ParticipacionDevolucion/Desglose/Importe |
| /CasinoRecord/baccaraTotal/total/refund/breakdown/amount/line | /RegistroPuntoBanca/Totales/ParticipacionDevolucion/Desglose/Importe/Linea |
| /CasinoRecord/baccaraTotal/total/refund/breakdown/amount/line/amount | /RegistroPuntoBanca/Totales/ParticipacionDevolucion/Desglose/Importe/Linea/Cantidad |
| /CasinoRecord/baccaraTotal/total/refund/breakdown/amount/line/unit | /RegistroPuntoBanca/Totales/ParticipacionDevolucion/Desglose/Importe/Linea/Unidad |
| /CasinoRecord/baccaraTotal/total/inKindPrizes | /RegistroPuntoBanca/Totales/PremiosEspecie |
| /CasinoRecord/baccaraTotal/total/inKindPrizes/total | /RegistroPuntoBanca/Totales/PremiosEspecie/Total |
| /CasinoRecord/baccaraTotal/total/inKindPrizes/total/line | /RegistroPuntoBanca/Totales/PremiosEspecie/Total/Linea |
| /CasinoRecord/baccaraTotal/total/inKindPrizes/total/line/amount | /RegistroPuntoBanca/Totales/PremiosEspecie/Total/Linea/Cantidad |
| /CasinoRecord/baccaraTotal/total/inKindPrizes/total/line/unit | /RegistroPuntoBanca/Totales/PremiosEspecie/Total/Linea/Unidad |
| /CasinoRecord/baccaraTotal/total/inKindPrizes/breakdown | /RegistroPuntoBanca/Totales/PremiosEspecie/Desglose |
| /CasinoRecord/baccaraTotal/total/inKindPrizes/breakdown/operatorId | /RegistroPuntoBanca/Totales/PremiosEspecie/Desglose/OperadorId |
| /CasinoRecord/baccaraTotal/total/inKindPrizes/breakdown/amount | /RegistroPuntoBanca/Totales/PremiosEspecie/Desglose/Importe |
| /CasinoRecord/baccaraTotal/total/inKindPrizes/breakdown/amount/line | /RegistroPuntoBanca/Totales/PremiosEspecie/Desglose/Importe/Linea |
| /CasinoRecord/baccaraTotal/total/inKindPrizes/breakdown/amount/line/amount | /RegistroPuntoBanca/Totales/PremiosEspecie/Desglose/Importe/Linea/Cantidad |
| /CasinoRecord/baccaraTotal/total/inKindPrizes/breakdown/amount/line/unit | /RegistroPuntoBanca/Totales/PremiosEspecie/Desglose/Importe/Linea/Unidad |
| /CasinoRecord/baccaraTotal/total/cashWinnings | /RegistroPuntoBanca/Totales/Premios |
| /CasinoRecord/baccaraTotal/total/cashWinnings/total | /RegistroPuntoBanca/Totales/Premios/Total |
| /CasinoRecord/baccaraTotal/total/cashWinnings/total/line | /RegistroPuntoBanca/Totales/Premios/Total/Linea |
| /CasinoRecord/baccaraTotal/total/cashWinnings/total/line/amount | /RegistroPuntoBanca/Totales/Premios/Total/Linea/Cantidad |
| /CasinoRecord/baccaraTotal/total/cashWinnings/total/line/unit | /RegistroPuntoBanca/Totales/Premios/Total/Linea/Unidad |
| /CasinoRecord/baccaraTotal/total/cashWinnings/breakdown | /RegistroPuntoBanca/Totales/Premios/Desglose |
| /CasinoRecord/baccaraTotal/total/cashWinnings/breakdown/operatorId | /RegistroPuntoBanca/Totales/Premios/Desglose/OperadorId |
| /CasinoRecord/baccaraTotal/total/cashWinnings/breakdown/amount | /RegistroPuntoBanca/Totales/Premios/Desglose/Importe |
| /CasinoRecord/baccaraTotal/total/cashWinnings/breakdown/amount/line | /RegistroPuntoBanca/Totales/Premios/Desglose/Importe/Linea |
| /CasinoRecord/baccaraTotal/total/cashWinnings/breakdown/amount/line/amount | /RegistroPuntoBanca/Totales/Premios/Desglose/Importe/Linea/Cantidad |
| /CasinoRecord/baccaraTotal/total/cashWinnings/breakdown/amount/line/unit | /RegistroPuntoBanca/Totales/Premios/Desglose/Importe/Linea/Unidad |
| /CasinoRecord/baccaraTotal/total/jackpot | /RegistroPuntoBanca/Totales/Botes |
| /CasinoRecord/baccaraTotal/total/jackpot/total | /RegistroPuntoBanca/Totales/Botes/Total |
| /CasinoRecord/baccaraTotal/total/jackpot/total/line | /RegistroPuntoBanca/Totales/Botes/Total/Linea |
| /CasinoRecord/baccaraTotal/total/jackpot/total/line/amount | /RegistroPuntoBanca/Totales/Botes/Total/Linea/Cantidad |
| /CasinoRecord/baccaraTotal/total/jackpot/total/line/unit | /RegistroPuntoBanca/Totales/Botes/Total/Linea/Unidad |
| /CasinoRecord/baccaraTotal/total/jackpot/breakdown | /RegistroPuntoBanca/Totales/Botes/Desglose |
| /CasinoRecord/baccaraTotal/total/jackpot/breakdown/jackpotId | /RegistroPuntoBanca/Totales/Botes/Desglose/BoteId |
| /CasinoRecord/baccaraTotal/total/jackpot/breakdown/jackpotDesc | /RegistroPuntoBanca/Totales/Botes/Desglose/BoteDesc |
| /CasinoRecord/baccaraTotal/total/jackpot/breakdown/amount | /RegistroPuntoBanca/Totales/Botes/Desglose/Movimiento |
| /CasinoRecord/baccaraTotal/total/jackpot/breakdown/amount/line | /RegistroPuntoBanca/Totales/Botes/Desglose/Movimiento/Linea |
| /CasinoRecord/baccaraTotal/total/jackpot/breakdown/amount/line/amount | /RegistroPuntoBanca/Totales/Botes/Desglose/Movimiento/Linea/Cantidad |
| /CasinoRecord/baccaraTotal/total/jackpot/breakdown/amount/line/unit | /RegistroPuntoBanca/Totales/Botes/Desglose/Movimiento/Linea/Unidad |
| /CasinoRecord/gameDetails | /RegistroJUD |
| /CasinoRecord/gameDetails/operatorId | /RegistroJUD/Cabecera/OperadorId |
| /CasinoRecord/gameDetails/recordId | /RegistroJUD/Cabecera/RegistroId |
| /CasinoRecord/gameDetails/date | /RegistroJUD/Cabecera/Fecha |
| /CasinoRecord/gameDetails/subRecordId | /RegistroJUD/Cabecera/SubregistroId |
| /CasinoRecord/gameDetails/subRecordTotal | /RegistroJUD/Cabecera/SubregistroTotal |
| /CasinoRecord/gameDetails/gameId | /RegistroJUD/JuegoId |
| /CasinoRecord/gameDetails/gameType | /RegistroJUD/<used in batch file path> |
| /CasinoRecord/gameDetails/player | /RegistroJUD/Jugador |
| /CasinoRecord/gameDetails/player/playerID | /RegistroJUD/Jugador/ID |
| /CasinoRecord/gameDetails/player/playerID/operatorId | /RegistroJUD/Jugador/ID/OperadorId |
| /CasinoRecord/gameDetails/player/playerID/playerId | /RegistroJUD/Jugador/ID/JugadorId |
| /CasinoRecord/gameDetails/player/placement | /RegistroJUD/Jugador/Participacion |
| /CasinoRecord/gameDetails/player/placement/line | /RegistroJUD/Jugador/Participacion/Linea |
| /CasinoRecord/gameDetails/player/placement/line/amount | /RegistroJUD/Jugador/Participacion/Linea/Cantidad |
| /CasinoRecord/gameDetails/player/placement/line/unit | /RegistroJUD/Jugador/Participacion/Linea/Unidad |
| /CasinoRecord/gameDetails/player/refund | /RegistroJUD/Jugador/ParticipacionDevolucion |
| /CasinoRecord/gameDetails/player/refund/line | /RegistroJUD/Jugador/ParticipacionDevolucion/Linea |
| /CasinoRecord/gameDetails/player/refund/line/amount | /RegistroJUD/Jugador/ParticipacionDevolucion/Linea/Cantidad |
| /CasinoRecord/gameDetails/player/refund/line/unit | /RegistroJUD/Jugador/ParticipacionDevolucion/Linea/Unidad |
| /CasinoRecord/gameDetails/player/cashWinnings | /RegistroJUD/Jugador/Premios |
| /CasinoRecord/gameDetails/player/cashWinnings/line | /RegistroJUD/Jugador/Premios/Linea |
| /CasinoRecord/gameDetails/player/cashWinnings/line/amount | /RegistroJUD/Jugador/Premios/Linea/Cantidad |
| /CasinoRecord/gameDetails/player/cashWinnings/line/unit | /RegistroJUD/Jugador/Premios/Linea/Unidad |
| /CasinoRecord/gameDetails/player/inKindPrizes | /RegistroJUD/Jugador/PremiosEspecie |
| /CasinoRecord/gameDetails/player/inKindPrizes/line | /RegistroJUD/Jugador/PremiosEspecie/Linea |
| /CasinoRecord/gameDetails/player/inKindPrizes/line/amount | /RegistroJUD/Jugador/PremiosEspecie/Linea/Cantidad |
| /CasinoRecord/gameDetails/player/inKindPrizes/line/unit | /RegistroJUD/Jugador/PremiosEspecie/Linea/Unidad |
| /CasinoRecord/gameDetails/player/inKindPrizesBreakdown | /RegistroJUD/Jugador/DesgloseEspecie |
| /CasinoRecord/gameDetails/player/inKindPrizesBreakdown/description | /RegistroJUD/Jugador/DesgloseEspecie/Descripcion |
| /CasinoRecord/gameDetails/player/inKindPrizesBreakdown/amount | /RegistroJUD/Jugador/DesgloseEspecie/Valoracion |
| /CasinoRecord/gameDetails/player/inKindPrizesBreakdown/amount/line | /RegistroJUD/Jugador/DesgloseEspecie/Valoracion/Linea |
| /CasinoRecord/gameDetails/player/inKindPrizesBreakdown/amount/line/amount | /RegistroJUD/Jugador/DesgloseEspecie/Valoracion/Linea/Cantidad |
| /CasinoRecord/gameDetails/player/inKindPrizesBreakdown/amount/line/unit | /RegistroJUD/Jugador/DesgloseEspecie/Valoracion/Linea/Unidad |
| /CasinoRecord/gameDetails/player/betId | /RegistroJUD/Jugador/TicketApuesta |
| /CasinoRecord/gameDetails/player/betDate | /RegistroJUD/Jugador/FechaApuesta |
| /CasinoRecord/gameDetails/player/betExchange | /RegistroJUD/Jugador/DesgloseCruzadas |
| /CasinoRecord/gameDetails/player/betExchange/challenge | /RegistroJUD/Jugador/DesgloseCruzadas/Reto |
| /CasinoRecord/gameDetails/player/betExchange/exchange | /RegistroJUD/Jugador/DesgloseCruzadas/Cruces |
| /CasinoRecord/gameDetails/player/betExchange/exchange/layOrBack | /RegistroJUD/Jugador/DesgloseCruzadas/Cruces/LayBack |
| /CasinoRecord/gameDetails/player/betExchange/exchange/ticketId | /RegistroJUD/Jugador/DesgloseCruzadas/Cruces/Ticket |
| /CasinoRecord/gameDetails/player/slotsSessionLimits | /RegistroJUD/Jugador/PlanificacionAzar |
| /CasinoRecord/gameDetails/player/slotsSessionLimits/durationLimit | /RegistroJUD/Jugador/PlanificacionAzar/DuracionLimite |
| /CasinoRecord/gameDetails/player/slotsSessionLimits/placementLimit | /RegistroJUD/Jugador/PlanificacionAzar/ParticipacionLimite |
| /CasinoReplacement/previous | /RegistroSesion/Cabecera/Rectificacion |
| /CasinoReplacement/previous/operatorId | <used for validation> |
| /CasinoReplacement/previous/recordId | /RegistroSesion/Cabecera/Rectificacion/RegistroId |
| /CasinoReplacement/previous/date | /RegistroSesion/Cabecera/Rectificacion/RegistroFecha |
| /CasinoReplacement/previous | /RegistroPuntoBanca/Cabecera/Rectificacion |
| /CasinoReplacement/previous/operatorId | <used for validation> |
| /CasinoReplacement/previous/recordId | /RegistroPuntoBanca/Cabecera/Rectificacion/RegistroId |
| /CasinoReplacement/previous/date | /RegistroPuntoBanca/Cabecera/Rectificacion/RegistroFecha |
| /CasinoReplacement/previous | /RegistroJUD/Cabecera/Rectificacion |
| /CasinoReplacement/previous/operatorId | <used for validation> |
| /CasinoReplacement/previous/recordId | /RegistroJUD/Cabecera/Rectificacion/RegistroId |
| /CasinoReplacement/previous/date | /RegistroJUD/Cabecera/Rectificacion/RegistroFecha |
| /CasinoReplacement/current |  |
| /CasinoReplacement/current/sessionTotal | /RegistroSesion |
| /CasinoReplacement/current/sessionTotal/operatorId | /RegistroSesion/Cabecera/OperadorId |
| /CasinoReplacement/current/sessionTotal/recordId | /RegistroSesion/Cabecera/RegistroId |
| /CasinoReplacement/current/sessionTotal/date | /RegistroSesion/Cabecera/Fecha |
| /CasinoReplacement/current/sessionTotal/subRecordId | /RegistroSesion/Cabecera/SubregistroId |
| /CasinoReplacement/current/sessionTotal/subRecordTotal | /RegistroSesion/Cabecera/SubregistroTotal |
| /CasinoReplacement/current/sessionTotal/gameId | /RegistroSesion/JuegoId |
| /CasinoReplacement/current/sessionTotal/gameDesc | /RegistroSesion/JuegoDesc |
| /CasinoReplacement/current/sessionTotal/gameType | /RegistroSesion/TipoJuego |
| /CasinoReplacement/current/sessionTotal/startDate | /RegistroSesion/FechaInicio |
| /CasinoReplacement/current/sessionTotal/endDate | /RegistroSesion/FechaFin |
| /CasinoReplacement/current/sessionTotal/networkGame | /RegistroSesion/JuegoEnRed |
| /CasinoReplacement/current/sessionTotal/postponed | /RegistroSesion/JuegoAplazado |
| /CasinoReplacement/current/sessionTotal/suspended | /RegistroSesion/JuegoSuspendido |
| /CasinoReplacement/current/sessionTotal/canceled | /RegistroSesion/JuegoCancelado |
| /CasinoReplacement/current/sessionTotal/total | /RegistroSesion/Totales |
| /CasinoReplacement/current/sessionTotal/total/placement | /RegistroSesion/Totales/Participacion |
| /CasinoReplacement/current/sessionTotal/total/placement/total | /RegistroSesion/Totales/Participacion/Total |
| /CasinoReplacement/current/sessionTotal/total/placement/total/line | /RegistroSesion/Totales/Participacion/Total/Linea |
| /CasinoReplacement/current/sessionTotal/total/placement/total/line/amount | /RegistroSesion/Totales/Participacion/Total/Linea/Cantidad |
| /CasinoReplacement/current/sessionTotal/total/placement/total/line/unit | /RegistroSesion/Totales/Participacion/Total/Linea/Unidad |
| /CasinoReplacement/current/sessionTotal/total/placement/breakdown | /RegistroSesion/Totales/Participacion/Desglose |
| /CasinoReplacement/current/sessionTotal/total/placement/breakdown/operatorId | /RegistroSesion/Totales/Participacion/Desglose/OperadorId |
| /CasinoReplacement/current/sessionTotal/total/placement/breakdown/amount | /RegistroSesion/Totales/Participacion/Desglose/Importe |
| /CasinoReplacement/current/sessionTotal/total/placement/breakdown/amount/line | /RegistroSesion/Totales/Participacion/Desglose/Importe/Linea |
| /CasinoReplacement/current/sessionTotal/total/placement/breakdown/amount/line/amount | /RegistroSesion/Totales/Participacion/Desglose/Importe/Linea/Cantidad |
| /CasinoReplacement/current/sessionTotal/total/placement/breakdown/amount/line/unit | /RegistroSesion/Totales/Participacion/Desglose/Importe/Linea/Unidad |
| /CasinoReplacement/current/sessionTotal/total/refund | /RegistroSesion/Totales/ParticipacionDevolucion |
| /CasinoReplacement/current/sessionTotal/total/refund/total | /RegistroSesion/Totales/ParticipacionDevolucion/Total |
| /CasinoReplacement/current/sessionTotal/total/refund/total/line | /RegistroSesion/Totales/ParticipacionDevolucion/Total/Linea |
| /CasinoReplacement/current/sessionTotal/total/refund/total/line/amount | /RegistroSesion/Totales/ParticipacionDevolucion/Total/Linea/Cantidad |
| /CasinoReplacement/current/sessionTotal/total/refund/total/line/unit | /RegistroSesion/Totales/ParticipacionDevolucion/Total/Linea/Unidad |
| /CasinoReplacement/current/sessionTotal/total/refund/breakdown | /RegistroSesion/Totales/ParticipacionDevolucion/Desglose |
| /CasinoReplacement/current/sessionTotal/total/refund/breakdown/operatorId | /RegistroSesion/Totales/ParticipacionDevolucion/Desglose/OperadorId |
| /CasinoReplacement/current/sessionTotal/total/refund/breakdown/amount | /RegistroSesion/Totales/ParticipacionDevolucion/Desglose/Importe |
| /CasinoReplacement/current/sessionTotal/total/refund/breakdown/amount/line | /RegistroSesion/Totales/ParticipacionDevolucion/Desglose/Importe/Linea |
| /CasinoReplacement/current/sessionTotal/total/refund/breakdown/amount/line/amount | /RegistroSesion/Totales/ParticipacionDevolucion/Desglose/Importe/Linea/Cantidad |
| /CasinoReplacement/current/sessionTotal/total/refund/breakdown/amount/line/unit | /RegistroSesion/Totales/ParticipacionDevolucion/Desglose/Importe/Linea/Unidad |
| /CasinoReplacement/current/sessionTotal/total/inKindPrizes | /RegistroSesion/Totales/PremiosEspecie |
| /CasinoReplacement/current/sessionTotal/total/inKindPrizes/total | /RegistroSesion/Totales/PremiosEspecie/Total |
| /CasinoReplacement/current/sessionTotal/total/inKindPrizes/total/line | /RegistroSesion/Totales/PremiosEspecie/Total/Linea |
| /CasinoReplacement/current/sessionTotal/total/inKindPrizes/total/line/amount | /RegistroSesion/Totales/PremiosEspecie/Total/Linea/Cantidad |
| /CasinoReplacement/current/sessionTotal/total/inKindPrizes/total/line/unit | /RegistroSesion/Totales/PremiosEspecie/Total/Linea/Unidad |
| /CasinoReplacement/current/sessionTotal/total/inKindPrizes/breakdown | /RegistroSesion/Totales/PremiosEspecie/Desglose |
| /CasinoReplacement/current/sessionTotal/total/inKindPrizes/breakdown/operatorId | /RegistroSesion/Totales/PremiosEspecie/Desglose/OperadorId |
| /CasinoReplacement/current/sessionTotal/total/inKindPrizes/breakdown/amount | /RegistroSesion/Totales/PremiosEspecie/Desglose/Importe |
| /CasinoReplacement/current/sessionTotal/total/inKindPrizes/breakdown/amount/line | /RegistroSesion/Totales/PremiosEspecie/Desglose/Importe/Linea |
| /CasinoReplacement/current/sessionTotal/total/inKindPrizes/breakdown/amount/line/amount | /RegistroSesion/Totales/PremiosEspecie/Desglose/Importe/Linea/Cantidad |
| /CasinoReplacement/current/sessionTotal/total/inKindPrizes/breakdown/amount/line/unit | /RegistroSesion/Totales/PremiosEspecie/Desglose/Importe/Linea/Unidad |
| /CasinoReplacement/current/sessionTotal/total/cashWinnings | /RegistroSesion/Totales/Premios |
| /CasinoReplacement/current/sessionTotal/total/cashWinnings/total | /RegistroSesion/Totales/Premios/Total |
| /CasinoReplacement/current/sessionTotal/total/cashWinnings/total/line | /RegistroSesion/Totales/Premios/Total/Linea |
| /CasinoReplacement/current/sessionTotal/total/cashWinnings/total/line/amount | /RegistroSesion/Totales/Premios/Total/Linea/Cantidad |
| /CasinoReplacement/current/sessionTotal/total/cashWinnings/total/line/unit | /RegistroSesion/Totales/Premios/Total/Linea/Unidad |
| /CasinoReplacement/current/sessionTotal/total/cashWinnings/breakdown | /RegistroSesion/Totales/Premios/Desglose |
| /CasinoReplacement/current/sessionTotal/total/cashWinnings/breakdown/operatorId | /RegistroSesion/Totales/Premios/Desglose/OperadorId |
| /CasinoReplacement/current/sessionTotal/total/cashWinnings/breakdown/amount | /RegistroSesion/Totales/Premios/Desglose/Importe |
| /CasinoReplacement/current/sessionTotal/total/cashWinnings/breakdown/amount/line | /RegistroSesion/Totales/Premios/Desglose/Importe/Linea |
| /CasinoReplacement/current/sessionTotal/total/cashWinnings/breakdown/amount/line/amount | /RegistroSesion/Totales/Premios/Desglose/Importe/Linea/Cantidad |
| /CasinoReplacement/current/sessionTotal/total/cashWinnings/breakdown/amount/line/unit | /RegistroSesion/Totales/Premios/Desglose/Importe/Linea/Unidad |
| /CasinoReplacement/current/sessionTotal/total/jackpot | /RegistroSesion/Totales/Botes |
| /CasinoReplacement/current/sessionTotal/total/jackpot/total | /RegistroSesion/Totales/Botes/Total |
| /CasinoReplacement/current/sessionTotal/total/jackpot/total/line | /RegistroSesion/Totales/Botes/Total/Linea |
| /CasinoReplacement/current/sessionTotal/total/jackpot/total/line/amount | /RegistroSesion/Totales/Botes/Total/Linea/Cantidad |
| /CasinoReplacement/current/sessionTotal/total/jackpot/total/line/unit | /RegistroSesion/Totales/Botes/Total/Linea/Unidad |
| /CasinoReplacement/current/sessionTotal/total/jackpot/breakdown | /RegistroSesion/Totales/Botes/Desglose |
| /CasinoReplacement/current/sessionTotal/total/jackpot/breakdown/jackpotId | /RegistroSesion/Totales/Botes/Desglose/BoteId |
| /CasinoReplacement/current/sessionTotal/total/jackpot/breakdown/jackpotDesc | /RegistroSesion/Totales/Botes/Desglose/BoteDesc |
| /CasinoReplacement/current/sessionTotal/total/jackpot/breakdown/amount | /RegistroSesion/Totales/Botes/Desglose/Movimiento |
| /CasinoReplacement/current/sessionTotal/total/jackpot/breakdown/amount/line | /RegistroSesion/Totales/Botes/Desglose/Movimiento/Linea |
| /CasinoReplacement/current/sessionTotal/total/jackpot/breakdown/amount/line/amount | /RegistroSesion/Totales/Botes/Desglose/Movimiento/Linea/Cantidad |
| /CasinoReplacement/current/sessionTotal/total/jackpot/breakdown/amount/line/unit | /RegistroSesion/Totales/Botes/Desglose/Movimiento/Linea/Unidad |
| /CasinoReplacement/current/sessionTotal/variant | /RegistroSesion/Variante |
| /CasinoReplacement/current/sessionTotal/variant=21 | /RegistroSesion/Variante=21 |
| /CasinoReplacement/current/sessionTotal/variant=American | /RegistroSesion/Variante=Americana |
| /CasinoReplacement/current/sessionTotal/variant=AM | /RegistroSesion/Variante=AM |
| /CasinoReplacement/current/sessionTotal/variant=CL | /RegistroSesion/Variante=CL |
| /CasinoReplacement/current/sessionTotal/variant=French | /RegistroSesion/Variante=Francesa |
| /CasinoReplacement/current/sessionTotal/variant=PO | /RegistroSesion/Variante=PO |
| /CasinoReplacement/current/sessionTotal/variant=SU | /RegistroSesion/Variante=SU |
| /CasinoReplacement/current/sessionTotal/commercialVariant | /RegistroSesion/VarianteComercial |
| /CasinoReplacement/current/sessionTotal/roundsPlayed | /RegistroSesion/PartidasJugadas |
| /CasinoReplacement/current/baccaraTotal | /RegistroPuntoBanca |
| /CasinoReplacement/current/baccaraTotal/operatorId | /RegistroPuntoBanca/Cabecera/OperadorId |
| /CasinoReplacement/current/baccaraTotal/recordId | /RegistroPuntoBanca/Cabecera/RegistroId |
| /CasinoReplacement/current/baccaraTotal/date | /RegistroPuntoBanca/Cabecera/Fecha |
| /CasinoReplacement/current/baccaraTotal/subRecordId | /RegistroPuntoBanca/Cabecera/SubregistroId |
| /CasinoReplacement/current/baccaraTotal/subRecordTotal | /RegistroPuntoBanca/Cabecera/SubregistroTotal |
| /CasinoReplacement/current/baccaraTotal/gameId | /RegistroPuntoBanca/JuegoId |
| /CasinoReplacement/current/baccaraTotal/gameDesc | /RegistroPuntoBanca/JuegoDesc |
| /CasinoReplacement/current/baccaraTotal/gameType | /RegistroPuntoBanca/TipoJuego |
| /CasinoReplacement/current/baccaraTotal/startDate | /RegistroPuntoBanca/FechaInicio |
| /CasinoReplacement/current/baccaraTotal/endDate | /RegistroPuntoBanca/FechaFin |
| /CasinoReplacement/current/baccaraTotal/networkGame | /RegistroPuntoBanca/JuegoEnRed |
| /CasinoReplacement/current/baccaraTotal/postponed | /RegistroPuntoBanca/JuegoAplazado |
| /CasinoReplacement/current/baccaraTotal/suspended | /RegistroPuntoBanca/JuegoSuspendido |
| /CasinoReplacement/current/baccaraTotal/canceled | /RegistroPuntoBanca/JuegoCancelado |
| /CasinoReplacement/current/baccaraTotal/total | /RegistroPuntoBanca/Totales |
| /CasinoReplacement/current/baccaraTotal/total/placement | /RegistroPuntoBanca/Totales/Participacion |
| /CasinoReplacement/current/baccaraTotal/total/placement/total | /RegistroPuntoBanca/Totales/Participacion/Total |
| /CasinoReplacement/current/baccaraTotal/total/placement/total/line | /RegistroPuntoBanca/Totales/Participacion/Total/Linea |
| /CasinoReplacement/current/baccaraTotal/total/placement/total/line/amount | /RegistroPuntoBanca/Totales/Participacion/Total/Linea/Cantidad |
| /CasinoReplacement/current/baccaraTotal/total/placement/total/line/unit | /RegistroPuntoBanca/Totales/Participacion/Total/Linea/Unidad |
| /CasinoReplacement/current/baccaraTotal/total/placement/breakdown | /RegistroPuntoBanca/Totales/Participacion/Desglose |
| /CasinoReplacement/current/baccaraTotal/total/placement/breakdown/operatorId | /RegistroPuntoBanca/Totales/Participacion/Desglose/OperadorId |
| /CasinoReplacement/current/baccaraTotal/total/placement/breakdown/amount | /RegistroPuntoBanca/Totales/Participacion/Desglose/Importe |
| /CasinoReplacement/current/baccaraTotal/total/placement/breakdown/amount/line | /RegistroPuntoBanca/Totales/Participacion/Desglose/Importe/Linea |
| /CasinoReplacement/current/baccaraTotal/total/placement/breakdown/amount/line/amount | /RegistroPuntoBanca/Totales/Participacion/Desglose/Importe/Linea/Cantidad |
| /CasinoReplacement/current/baccaraTotal/total/placement/breakdown/amount/line/unit | /RegistroPuntoBanca/Totales/Participacion/Desglose/Importe/Linea/Unidad |
| /CasinoReplacement/current/baccaraTotal/total/refund | /RegistroPuntoBanca/Totales/ParticipacionDevolucion |
| /CasinoReplacement/current/baccaraTotal/total/refund/total | /RegistroPuntoBanca/Totales/ParticipacionDevolucion/Total |
| /CasinoReplacement/current/baccaraTotal/total/refund/total/line | /RegistroPuntoBanca/Totales/ParticipacionDevolucion/Total/Linea |
| /CasinoReplacement/current/baccaraTotal/total/refund/total/line/amount | /RegistroPuntoBanca/Totales/ParticipacionDevolucion/Total/Linea/Cantidad |
| /CasinoReplacement/current/baccaraTotal/total/refund/total/line/unit | /RegistroPuntoBanca/Totales/ParticipacionDevolucion/Total/Linea/Unidad |
| /CasinoReplacement/current/baccaraTotal/total/refund/breakdown | /RegistroPuntoBanca/Totales/ParticipacionDevolucion/Desglose |
| /CasinoReplacement/current/baccaraTotal/total/refund/breakdown/operatorId | /RegistroPuntoBanca/Totales/ParticipacionDevolucion/Desglose/OperadorId |
| /CasinoReplacement/current/baccaraTotal/total/refund/breakdown/amount | /RegistroPuntoBanca/Totales/ParticipacionDevolucion/Desglose/Importe |
| /CasinoReplacement/current/baccaraTotal/total/refund/breakdown/amount/line | /RegistroPuntoBanca/Totales/ParticipacionDevolucion/Desglose/Importe/Linea |
| /CasinoReplacement/current/baccaraTotal/total/refund/breakdown/amount/line/amount | /RegistroPuntoBanca/Totales/ParticipacionDevolucion/Desglose/Importe/Linea/Cantidad |
| /CasinoReplacement/current/baccaraTotal/total/refund/breakdown/amount/line/unit | /RegistroPuntoBanca/Totales/ParticipacionDevolucion/Desglose/Importe/Linea/Unidad |
| /CasinoReplacement/current/baccaraTotal/total/inKindPrizes | /RegistroPuntoBanca/Totales/PremiosEspecie |
| /CasinoReplacement/current/baccaraTotal/total/inKindPrizes/total | /RegistroPuntoBanca/Totales/PremiosEspecie/Total |
| /CasinoReplacement/current/baccaraTotal/total/inKindPrizes/total/line | /RegistroPuntoBanca/Totales/PremiosEspecie/Total/Linea |
| /CasinoReplacement/current/baccaraTotal/total/inKindPrizes/total/line/amount | /RegistroPuntoBanca/Totales/PremiosEspecie/Total/Linea/Cantidad |
| /CasinoReplacement/current/baccaraTotal/total/inKindPrizes/total/line/unit | /RegistroPuntoBanca/Totales/PremiosEspecie/Total/Linea/Unidad |
| /CasinoReplacement/current/baccaraTotal/total/inKindPrizes/breakdown | /RegistroPuntoBanca/Totales/PremiosEspecie/Desglose |
| /CasinoReplacement/current/baccaraTotal/total/inKindPrizes/breakdown/operatorId | /RegistroPuntoBanca/Totales/PremiosEspecie/Desglose/OperadorId |
| /CasinoReplacement/current/baccaraTotal/total/inKindPrizes/breakdown/amount | /RegistroPuntoBanca/Totales/PremiosEspecie/Desglose/Importe |
| /CasinoReplacement/current/baccaraTotal/total/inKindPrizes/breakdown/amount/line | /RegistroPuntoBanca/Totales/PremiosEspecie/Desglose/Importe/Linea |
| /CasinoReplacement/current/baccaraTotal/total/inKindPrizes/breakdown/amount/line/amount | /RegistroPuntoBanca/Totales/PremiosEspecie/Desglose/Importe/Linea/Cantidad |
| /CasinoReplacement/current/baccaraTotal/total/inKindPrizes/breakdown/amount/line/unit | /RegistroPuntoBanca/Totales/PremiosEspecie/Desglose/Importe/Linea/Unidad |
| /CasinoReplacement/current/baccaraTotal/total/cashWinnings | /RegistroPuntoBanca/Totales/Premios |
| /CasinoReplacement/current/baccaraTotal/total/cashWinnings/total | /RegistroPuntoBanca/Totales/Premios/Total |
| /CasinoReplacement/current/baccaraTotal/total/cashWinnings/total/line | /RegistroPuntoBanca/Totales/Premios/Total/Linea |
| /CasinoReplacement/current/baccaraTotal/total/cashWinnings/total/line/amount | /RegistroPuntoBanca/Totales/Premios/Total/Linea/Cantidad |
| /CasinoReplacement/current/baccaraTotal/total/cashWinnings/total/line/unit | /RegistroPuntoBanca/Totales/Premios/Total/Linea/Unidad |
| /CasinoReplacement/current/baccaraTotal/total/cashWinnings/breakdown | /RegistroPuntoBanca/Totales/Premios/Desglose |
| /CasinoReplacement/current/baccaraTotal/total/cashWinnings/breakdown/operatorId | /RegistroPuntoBanca/Totales/Premios/Desglose/OperadorId |
| /CasinoReplacement/current/baccaraTotal/total/cashWinnings/breakdown/amount | /RegistroPuntoBanca/Totales/Premios/Desglose/Importe |
| /CasinoReplacement/current/baccaraTotal/total/cashWinnings/breakdown/amount/line | /RegistroPuntoBanca/Totales/Premios/Desglose/Importe/Linea |
| /CasinoReplacement/current/baccaraTotal/total/cashWinnings/breakdown/amount/line/amount | /RegistroPuntoBanca/Totales/Premios/Desglose/Importe/Linea/Cantidad |
| /CasinoReplacement/current/baccaraTotal/total/cashWinnings/breakdown/amount/line/unit | /RegistroPuntoBanca/Totales/Premios/Desglose/Importe/Linea/Unidad |
| /CasinoReplacement/current/baccaraTotal/total/jackpot | /RegistroPuntoBanca/Totales/Botes |
| /CasinoReplacement/current/baccaraTotal/total/jackpot/total | /RegistroPuntoBanca/Totales/Botes/Total |
| /CasinoReplacement/current/baccaraTotal/total/jackpot/total/line | /RegistroPuntoBanca/Totales/Botes/Total/Linea |
| /CasinoReplacement/current/baccaraTotal/total/jackpot/total/line/amount | /RegistroPuntoBanca/Totales/Botes/Total/Linea/Cantidad |
| /CasinoReplacement/current/baccaraTotal/total/jackpot/total/line/unit | /RegistroPuntoBanca/Totales/Botes/Total/Linea/Unidad |
| /CasinoReplacement/current/baccaraTotal/total/jackpot/breakdown | /RegistroPuntoBanca/Totales/Botes/Desglose |
| /CasinoReplacement/current/baccaraTotal/total/jackpot/breakdown/jackpotId | /RegistroPuntoBanca/Totales/Botes/Desglose/BoteId |
| /CasinoReplacement/current/baccaraTotal/total/jackpot/breakdown/jackpotDesc | /RegistroPuntoBanca/Totales/Botes/Desglose/BoteDesc |
| /CasinoReplacement/current/baccaraTotal/total/jackpot/breakdown/amount | /RegistroPuntoBanca/Totales/Botes/Desglose/Movimiento |
| /CasinoReplacement/current/baccaraTotal/total/jackpot/breakdown/amount/line | /RegistroPuntoBanca/Totales/Botes/Desglose/Movimiento/Linea |
| /CasinoReplacement/current/baccaraTotal/total/jackpot/breakdown/amount/line/amount | /RegistroPuntoBanca/Totales/Botes/Desglose/Movimiento/Linea/Cantidad |
| /CasinoReplacement/current/baccaraTotal/total/jackpot/breakdown/amount/line/unit | /RegistroPuntoBanca/Totales/Botes/Desglose/Movimiento/Linea/Unidad |
| /CasinoReplacement/current/gameDetails | /RegistroJUD |
| /CasinoReplacement/current/gameDetails/operatorId | /RegistroJUD/Cabecera/OperadorId |
| /CasinoReplacement/current/gameDetails/recordId | /RegistroJUD/Cabecera/RegistroId |
| /CasinoReplacement/current/gameDetails/date | /RegistroJUD/Cabecera/Fecha |
| /CasinoReplacement/current/gameDetails/subRecordId | /RegistroJUD/Cabecera/SubregistroId |
| /CasinoReplacement/current/gameDetails/subRecordTotal | /RegistroJUD/Cabecera/SubregistroTotal |
| /CasinoReplacement/current/gameDetails/gameId | /RegistroJUD/JuegoId |
| /CasinoReplacement/current/gameDetails/gameType | /RegistroJUD/<used in batch file path> |
| /CasinoReplacement/current/gameDetails/player | /RegistroJUD/Jugador |
| /CasinoReplacement/current/gameDetails/player/playerID | /RegistroJUD/Jugador/ID |
| /CasinoReplacement/current/gameDetails/player/playerID/operatorId | /RegistroJUD/Jugador/ID/OperadorId |
| /CasinoReplacement/current/gameDetails/player/playerID/playerId | /RegistroJUD/Jugador/ID/JugadorId |
| /CasinoReplacement/current/gameDetails/player/placement | /RegistroJUD/Jugador/Participacion |
| /CasinoReplacement/current/gameDetails/player/placement/line | /RegistroJUD/Jugador/Participacion/Linea |
| /CasinoReplacement/current/gameDetails/player/placement/line/amount | /RegistroJUD/Jugador/Participacion/Linea/Cantidad |
| /CasinoReplacement/current/gameDetails/player/placement/line/unit | /RegistroJUD/Jugador/Participacion/Linea/Unidad |
| /CasinoReplacement/current/gameDetails/player/refund | /RegistroJUD/Jugador/ParticipacionDevolucion |
| /CasinoReplacement/current/gameDetails/player/refund/line | /RegistroJUD/Jugador/ParticipacionDevolucion/Linea |
| /CasinoReplacement/current/gameDetails/player/refund/line/amount | /RegistroJUD/Jugador/ParticipacionDevolucion/Linea/Cantidad |
| /CasinoReplacement/current/gameDetails/player/refund/line/unit | /RegistroJUD/Jugador/ParticipacionDevolucion/Linea/Unidad |
| /CasinoReplacement/current/gameDetails/player/cashWinnings | /RegistroJUD/Jugador/Premios |
| /CasinoReplacement/current/gameDetails/player/cashWinnings/line | /RegistroJUD/Jugador/Premios/Linea |
| /CasinoReplacement/current/gameDetails/player/cashWinnings/line/amount | /RegistroJUD/Jugador/Premios/Linea/Cantidad |
| /CasinoReplacement/current/gameDetails/player/cashWinnings/line/unit | /RegistroJUD/Jugador/Premios/Linea/Unidad |
| /CasinoReplacement/current/gameDetails/player/inKindPrizes | /RegistroJUD/Jugador/PremiosEspecie |
| /CasinoReplacement/current/gameDetails/player/inKindPrizes/line | /RegistroJUD/Jugador/PremiosEspecie/Linea |
| /CasinoReplacement/current/gameDetails/player/inKindPrizes/line/amount | /RegistroJUD/Jugador/PremiosEspecie/Linea/Cantidad |
| /CasinoReplacement/current/gameDetails/player/inKindPrizes/line/unit | /RegistroJUD/Jugador/PremiosEspecie/Linea/Unidad |
| /CasinoReplacement/current/gameDetails/player/inKindPrizesBreakdown | /RegistroJUD/Jugador/DesgloseEspecie |
| /CasinoReplacement/current/gameDetails/player/inKindPrizesBreakdown/description | /RegistroJUD/Jugador/DesgloseEspecie/Descripcion |
| /CasinoReplacement/current/gameDetails/player/inKindPrizesBreakdown/amount | /RegistroJUD/Jugador/DesgloseEspecie/Valoracion |
| /CasinoReplacement/current/gameDetails/player/inKindPrizesBreakdown/amount/line | /RegistroJUD/Jugador/DesgloseEspecie/Valoracion/Linea |
| /CasinoReplacement/current/gameDetails/player/inKindPrizesBreakdown/amount/line/amount | /RegistroJUD/Jugador/DesgloseEspecie/Valoracion/Linea/Cantidad |
| /CasinoReplacement/current/gameDetails/player/inKindPrizesBreakdown/amount/line/unit | /RegistroJUD/Jugador/DesgloseEspecie/Valoracion/Linea/Unidad |
| /CasinoReplacement/current/gameDetails/player/betId | /RegistroJUD/Jugador/TicketApuesta |
| /CasinoReplacement/current/gameDetails/player/betDate | /RegistroJUD/Jugador/FechaApuesta |
| /CasinoReplacement/current/gameDetails/player/betExchange | /RegistroJUD/Jugador/DesgloseCruzadas |
| /CasinoReplacement/current/gameDetails/player/betExchange/challenge | /RegistroJUD/Jugador/DesgloseCruzadas/Reto |
| /CasinoReplacement/current/gameDetails/player/betExchange/exchange | /RegistroJUD/Jugador/DesgloseCruzadas/Cruces |
| /CasinoReplacement/current/gameDetails/player/betExchange/exchange/layOrBack | /RegistroJUD/Jugador/DesgloseCruzadas/Cruces/LayBack |
| /CasinoReplacement/current/gameDetails/player/betExchange/exchange/ticketId | /RegistroJUD/Jugador/DesgloseCruzadas/Cruces/Ticket |
| /CasinoReplacement/current/gameDetails/player/slotsSessionLimits | /RegistroJUD/Jugador/PlanificacionAzar |
| /CasinoReplacement/current/gameDetails/player/slotsSessionLimits/durationLimit | /RegistroJUD/Jugador/PlanificacionAzar/DuracionLimite |
| /CasinoReplacement/current/gameDetails/player/slotsSessionLimits/placementLimit | /RegistroJUD/Jugador/PlanificacionAzar/ParticipacionLimite |
| /CasinoCancellation/previous |  |
| /CasinoCancellation/previous/operatorId | /<used in batch name> |
| /CasinoCancellation/previous/recordId | /RegistroAnulador/Cabecera/Rectificacion/RegistroId |
| /CasinoCancellation/previous/date | /RegistroAnulador/Cabecera/Rectificacion/RegistroFecha |
| /CasinoCancellation/previous/recordType | /<used in batch name> |
| /CasinoCancellation/previous/recordType=PlayerRegistrationDetails | /<used in batch name>=RUD |
| /CasinoCancellation/previous/recordType=PlayerRegistrationTotal | /<used in batch name>=RUT |
| /CasinoCancellation/previous/recordType=NetworkPlayerRegistration | /<used in batch name>=RUR |
| /CasinoCancellation/previous/recordType=WinnerRegistrationDetails | /<used in batch name>=RUG |
| /CasinoCancellation/previous/recordType=PlayerAccountDetails | /<used in batch name>=CJD |
| /CasinoCancellation/previous/recordType=PlayerAccountTotal | /<used in batch name>=CJT |
| /CasinoCancellation/previous/recordType=OperatorAccountTotal | /<used in batch name>=OPT |
| /CasinoCancellation/previous/recordType=NetworkOperatorAccountTotal | /<used in batch name>=ORT |
| /CasinoCancellation/previous/recordType=JackpotTotal | /<used in batch name>=BOT |
| /CasinoCancellation/previous/recordType=GameDetails | /<used in batch name>=JUD |
| /CasinoCancellation/previous/recordType=GameTotal | /<used in batch name>=JUT |
| /CasinoCancellation/previous/recordType=BetAdjustment | /<used in batch name>=JUA |
| /CasinoCancellation/previous/recordType=EventCatalog | /<used in batch name>=CEV |
| /CasinoCancellation/previous/gameType | /<used in batch name> |
| /CasinoCancellation/previous/periodicity | /<used in batch name> |
| /CasinoCancellation/previous/periodicity=PerDay | /<used in batch name>=Diaria |
| /CasinoCancellation/previous/periodicity=PerMonth | /<used in batch name>=Mensual |
| /CasinoCancellation/cancellation | /RegistroAnulador |
| /CasinoCancellation/cancellation/operatorId | /RegistroAnulador/Cabecera/OperadorId |
| /CasinoCancellation/cancellation/recordId | /RegistroAnulador/Cabecera/RegistroId |
| /CasinoCancellation/cancellation/date | /RegistroAnulador/Cabecera/Fecha |

OT-MORPHO RESTRICTED

D3S Online Gaming Spain Edition  
Functional Specification

Réf. : Dictao_D3S_JEL_FunctionalSpec_ES version 2.1 du 2011/10/218 110/110  
Communication, reproduction ou utilisation interdites sauf autorisation préalable de OT-Morpho