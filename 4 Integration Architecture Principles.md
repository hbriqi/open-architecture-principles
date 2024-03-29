![Integration Services](https://github.com/hisham-elbreky/open-architecture-principles/blob/main/Diagrams/Integration%20Services%20Model.png)

# Integration Platform – Design Principles 

## PRINCIPLE 01 – Integration Use Cases 

#### Statement 
The platform can fit with different integration use-cases

#### Rationale  
The platform has the capability to be used to implement integration solution for the well-known integration use-case, and can be configured easily to fit with the special use-case  
  
#### Implications  
Platform supported with the runtimes which support  
Master data management: Synchronizing master data repositories and communicating changes — for example, taking customer data from CRM and ERP systems and creating a master record of that data, then pushing any changes back to the individual systems. 
Application data sync: Synchronizing data between application stores — for example, between two microservice features that need a common view of product data or replicating customer data between a CRM and ERP system. 

Business intelligence and reporting: Creating semantic layers in reporting platforms, where it will be used to generate analytics and insights used by line-of-business managers — for example, generating daily sales reports. 

Machine learning and analytics data pipelines: Delivering bulk datasets that will be used by data scientists to perform their analytic tradecraft; gathering data for training sets is a combination of one-off and recurring data delivery activities — for example, gathering customer purchase data to train a machine learning model for a recommendation engine and then keeping it up-to-date to ensure it reflects current buying habits. 

Streaming analytics: Delivering streams of data, where the position of an event in the stream and the content of nearby events is as important as the integrity of individual data items — for example, the ordering and timing of messages in the stream must be maintained, and you may need to pause, rewind and replay parts of the stream. (Streaming analytics often involves looking for patterns within a stream of data, such as potentially fraudulent activity in a stream of financial transactions).

Business-to-business integration: Exchanging information with external organizations and business partners — for example, submitting requisitions as part of a digital supply chain. 

Application composition: Creating new applications by orchestrating a set of calls to existing services — for example, creating a customer check-out application that calls existing inventory management, payment processing, logistics and CRM applications. 

Digital process automation: Automating business processes, with a goal of improving process speed, compliance and accuracy — for example, automating the process of provisioning IT accounts, building access and payroll for new employees.tion platform -at least- support the following use-case: 
   
  
 
 
## PRINCIPLE 02 – Integration Approaches 
 
#### Statement

The platform supports all standard integration approaches  
Rationale  
Many of integration use-case can be applied 
  
  
#### Implications  
Integration spectrums can be identified by: 
Data integration  
Event-driven integration  
Application integration 
The integration platform must provide different approaches for each integration spectrum as follows: 
Data integration approaches 
 ETL 
Managed file transfer 
Data virtualization  
Data capture  
Event-driven integration approaches 
Message-driven (message broker) 
Stream processing 
Application integration approaches  
API Mediation  
SOA 
  
  
 
## PRINCIPLE 03 – Platform Maturity 
Element  
Description  
 Statement  
Platform enable organization to meet with the planned maturity level  
Rationale  
Maturity level must be identified to set the expectation  
 Implications  
Measure the capability of integration environment and keep continues improvement 
 Metrics  
  
Note: maturity model to be identified internally, aligned with agile maturity model.  
PRINCIPLE 04 – Agile Integration  
Element  
Description  
Statement  
Distributed Ownership of Integration Environment 
Rationale  
Many organizations would have preferred the application teams own the creation of their own services, but the technology and infrastructure of the time didn’t enable that. 
The move to fine-grained integration deployment opens a door such that ownership of the creation and maintenance of integrations can be distributed 
 
Implications  
Enable DevOps pipelines to have access on the integration environment without limiting development team to deploy the required integration services 
  
  
 
## PRINCIPLE 5 – Monitoring and Administration  
Element  
Description  
Statement  
Integration environment is full monitored and controlled through automated tools and human admins 
Rationale  
The critical role of integration environment, demand to be robustness and flexibility to react to the issues in real-time basis, and provide secure access to the administrators to configure the environment as required   
Implications  
Provide dashboard and ticketing system to handle the issues and environment configuration 
  
  
 
 
## PRINCIPLE 06 – Scalable Platform  
Element  
Description  
Statement  
Scalable environment  
Rationale  
Elastic environment which can be scaled up or down   
Implications  
Efficient utilization of infrastructure  
   
  
 
 
# Application Integration Principles  
## PRINCIPLE 01 – Integration Interface Standard 
Element  
Description  
 Statement  
Interfaces to systems that are managed as APIs, with a defined contract and independent life cycle. 
Rationale  
A well-defined contract between services/applications is required for consistent communication   
 Implications  
Standard communication contract must be identified is in-prior to development e.g. WSDL, REST Specification, or gRPC contract  
  
 
 
## PRINCIPLE 02 – Supported Protocols of Integration Interface 
Element  
Description  
 Statement  
APIs can be exposed using a variety of protocols, not just REST (e.g., gRPC, GraphQL or WebSockets). 
Rationale  
Each communication protocol is fit with specific use case  
 Implications  
Selecting the communication protocol must consider the use case, for example when a fast and light communication is required so gRPC or REST have to be considered, and when a solid contract (or communication with legacy SOAP services) so SOAP communication is required 
 Metrics  
  
 
## PRINCIPLE 03 – Aggregation API 
Element  
Description  
 Statement  
Integration flows that create composite services or data are themselves services and should be called via an API. 
Rationale  
Data Aggregation is done through APIs make it safe for future updates to take place on different data sources  
 
Implications  
Separate the concern between services which make it extendable and maintainable  
Data aggregation to be done on the level of API to make it data source agnostic    
  
 
 
# Event-based integration Principles  
## PRINCIPLE 01 – Event Documentation 
Element  
Description  
 Statement  
Message Broker events must be documented, showing the producers and consumers dependencies 
Rationale  
Event must be well-defined with a proper name and description which reflect the business function 
Implications  
Event must be declared with the owner application(s)/producer(s) and the subscribers/consumers so it can be developed, deployed, monitored, and maintained smoothly without interrupting the business     
  
 
 
## PRINCIPLE 02 – Event Security 
Element  
Description  
 Statement  
Events are secured so producers and subscribers are the only authorized entities to deal with the pre-defined and configured events. 
Rationale  
 Secure the event in the area of its scope and prevent unauthorized entities from dealing with the event. 
Implications  
System accounts must be identified per each app for triggering or consuming events  
Each system account must be configured to be authorized with specific actions on the message broker system.   
  
 
 
## PRINCIPLE 03 – Event Sourcing  
Element  
Description  
 Statement  
Note: Event Sourcing is that of ensuring every change to the state of an application is captured in an event object, and that these event objects are themselves stored in the sequence they were applied for the same lifetime as the application state itself. 
Event sourcing is the best implementation for message brokering when the series of events history must be maintained (e.g. data auditing, data processing or event replay)  
Rationale  
In some business cases like auditing, the history of events flow must be retained for future querying/reposts   
Replaying event for monitoring (or simulation)  
When 100% of message delivery is required for the asynchronous communication 
Implications   
 
 
 
## PRINCIPLE 04 – Using Event Driven  
Element  
Description  
 Statement  
Event driven approach must be wisely used in specific cases to avoid any complexity in development and operation  
Rationale  
Event-driven is a dynamic implementation for the decoupled communication between services, that requires to identify when to go with event-driven to avoid fall in chaos which could lead to business interruption 
 
Implications  
To use event driven pattern(s) when: 
Asynchronous one-to-one communication of long-term process (in the case of the absence of workflow engine) 
Asynchronous one-to-many communication, when more than one system is interested with the event 
Asynchronous many-to-many or many-to-one communication. In some cases, the event is triggered based a aggregating events from more than one system 
Event-sourcing e.g. auditing  
Real-time processing 
Integration of heterogeneous systems e.g. systems running on different stacks    
 Metrics  
  
 
 
## PRINCIPLE 04 – Choreography Pattern  
Element  
Description  
 Statement  
Each component of the system participates in the decision-making process about the workflow of a business transaction, instead of relying on a central point of control 
Rationale  
An alternative to strict orchestration of tasks is choreography, where an event-driven approach is used to combine processes. Rather than having the platform drive the sequence of steps, a choreography approach has the platform observe a set of events (such as a record appearing in a database). By observing the events, the platform can provide the monitoring and optimization benefits associated with an iBPMS while not having to drive the process. Choreography also allows the platform to execute compensating actions (that is, reversing changes already made) if an observed event indicates that a task has failed. When adopting a choreography approach, the platform acts not as the driving force behind the process, but as an observer, prompting next steps or changes in direction as required.  
Implications  
Use the choreography pattern if you expect to update, remove, or add new services frequently. The entire app can be modified with lesser effort and minimal disruption to existing services. 
Consider this pattern if you experience performance bottlenecks in the central orchestrator. 
This pattern is a natural model for the serverless architecture where all services can be short lived, or event driven. Services can spin up because of an event, do their task, and are removed when the task is finished.   
  
 
 
 
#Data Integration Principles 
## PRINCIPLE 01 – Data Virtualization 
Element  
Description  
 Statement  
Data Virtualization help in efficient aggregating data from heterogenous data sources 
Rationale  
Aggregating data from heterogeneous data sources with the need of best performance without requiring technical detail, that demand to rely on data vitiation technique 
 
Implications  
Implementing data virtualization requires a big scale environment, so it is considered that it is part of big data implementation      
  
 
 
## PRINCIPLE 02 – Data Synchronization 
Element  
Description  
 Statement  
Data synchronization is a basic part of application integration which is almost done asynchrony between systems using either ETL or data streaming techniques  
Rationale  
The change of the state of data could affect in other systems which require that change to be synched to other interested systems  
Implications  
Data sync between systems could be done either on the level of data system (e.g. MS SQL Integration Service) or as part of application event sourcing (Kafka data streaming). 
Selecting the technique should consider data source and destination systems. Also, a hybrid technique could be used as required. 
  
  
 
 
 
 
