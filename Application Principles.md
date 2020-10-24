**Contents**  
General Principles
12_Factor
Beyond 12_Factor
Containerization		
===========================
General Principles

PRINCIPLE 01 – Reuse before buy, before build
Statement:	Business applications, system components and data will be reused
wherever possible, purchased as commodity solutions if necessary and
only built if there is a unique requirement that cannot otherwise be fulfilled.
Rationale:	Reuse will provide value for money by simplifying the ICT landscape, reducing data duplication and adopting common business processes
Implications:	Funding of projects will need to cater for cross project delivery (shared services) to avoid unnecessary duplication of BizSolutions services (silos). To maximize value and reduce complexity requirements for shared services should be captured cross project.



PRINCIPLE 02 – Seek architecture approval
Statement:	All projects will be subject to architectural approval at key stages throughout the delivery lifecycle.
Rationale:	To ensure that projects collectively move in the technology direction that is required by the Highways EA. To control and prevent divergence from strategic intent and to understand the trade-offs around any divergence.
Implications:	Changes to the architecture need to be formally managed so that divergence is controlled.



Principle 03: DRY
Statement:	Don’t repeat yourself 
Rational: When the DRY principle is applied successfully, a modification of any single element of a system does not require a change in other logically unrelated elements. Additionally, elements that are logically related all change predictably and uniformly and are thus kept in sync. 
Implications:	Besides using methods and subroutines in their code, rely on code generators, automatic build systems, and scripting languages to observe the DRY principle across layers.


Principle 04: KISS
Statement:	Keep it simple and straightforward
Rational:	The KISS principle states that most systems work best if they are kept simple rather than made complicated; therefore.
Implications:	simplicity should be a key goal in design, and unnecessary complexity should be avoided 


Principle 05: YAGNI
Statement:	You aren’t going to need it
Rational:	a programmer should not add functionality until deemed necessary
Implications:	Always implement things when you actually need them, never when you just foresee that you need them 


Principle 06: SoC
Statement:	Separation of concerns
Rational:	Separating the application into distinct sections, so each section addresses a separate concern. 
The overall goal of separation of concerns is to establish a well-organized system where each part fulfills a meaningful and intuitive role while maximizing its ability to adapt to change.
Implications:	Separation of concerns is achieved by the establishment of boundaries. A boundary is any logical or physical constraint which delineates a given set of responsibilities. Some examples of boundaries would include the use of methods, objects, components, and services to define core behavior within an application; projects, solutions, and folder hierarchies for source organization; application layers and tiers for processing organization.


Principle 07: SOLID
Statement	SOLID is stand for five object-oriented principles as follows:
1.	Single-responsibility principle
2.	Open–closed
3.	Liskov substitution
4.	Interface segregation
5.	Dependency inversion
Rational	SOLID is a mnemonic acronym for five design principles intended to make software designs more understandable, flexible and maintainable. Mainly related to object-oriented design.
Implications	1.	Single-responsibility principle
A class should only have a single responsibility, that is, only changes to one part of the software's specification should be able to affect the specification of the class.
2.	Open–closed
"Software entities ... should be open for extension, but closed for modification."
3.	Liskov substitution
"Objects in a program should be replaceable with instances of their subtypes without altering the correctness of that program." See also design by contract.
4.	Interface segregation
"Many client-specific interfaces are better than one general-purpose interface.
5.	Dependency inversion
One should "depend upon abstractions, [not] concretions 

1	Information Principles 

PRINCIPLE 01 – Manage data as an asset
Element	Description
Statement	All projects will be subject to architectural approval at key stages throughout the delivery lifecycle.

Rationale
	Thiqah Information and its application data needs to be managed properly. Accurate, timely data is critical to deliver information and support informed business decisions.
Implications	There must be an Information Asset Owner (IAO) that is responsible for assuring that information is properly managed. All projects that handle a significant amount of data must have a data management plan and information asset register to describe the data used and the security classification of the data.

Metrics	

PRINCIPLE 02 –
 Make data accessible
Element	Description
Statement	Data must be easy to find and retrieve and present a single version of
the truth.
Rationale	Data must come from a single authorized source that can be directly referenced.
Implications	The way information is accessed and displayed must be sufficiently
adaptable to meet a wide range of users and their corresponding
methods of access

Metrics	
2	Application Principles

PRINCIPLE 01 –
 Use existing services
Element	Description
Statement	Avoid doing everything yourself, consume and use existing Application
Program Interfaces (APIs). The functionality needed could be provided
by an existing service.
Rationale	Modern applications (digital services) are built on top of a wide range of APIs. Eliminating the effort designing and implementing a duplicate service will reduce projects costs and shorten the time to deliver them.
Implications	Technical teams should understand what services exists, are being built and planned. A service catalogue needs to be developed and maintained as the source of this information. There must be a single service catalogue supporting ITSM and EA. This needs to communicate a pipeline of services to clearly show those proposed, under development, in operation and being retired.

Metrics	

 
PRINCIPLE 02 –
 Build Reusable Services not applications
Element	Description
Statement	Applications will be built as a collection of services that expose an Application Program Interface (API) enabling them to be combined to deliver users what they need.
Rationale	This facilitates reuse, interoperability and the ability to scale by reducing tight dependencies between components
Implications	Cloud-services and COTS products are expected to have well-defined APIs. An overlap of functionality can exist within multiple Cloud solutions. This must be managed to prevent unnecessary duplication of services. 
Service Design will need to cover Supplier Management, Availability Management, Capacity Management, Information Security Management and Service Continuity Management.

Metrics	

PRINCIPLE 03 –
 Design applications to meet user needs
Element	Description
Statement	User needs will be discovered from direct participation with users and
evidence gathered on existing services usage.
Rationale	Understanding user needs and what functions and features are regularly used by them in existing services helps to prioritize and plan the delivery of new services and make changes to existing ones.
Implications	A business team will be required consisting of stakeholders and technical staff. Expertise in User Experience (UX) consultancy will be required.

Metrics	

PRINCIPLE 04 –
 Pilot new applications and services
Element	Description
Statement	Build a prototype, test it with users and learn from it.
Rationale	It is impossible to accurately predict everything upfront. Prototypes enable users to provide early feedback about the design of the solution.
Implications	Projects must be open to investing and testing new products and services on a small scale in order to de-risk large scale delivery projects. 
Metrics	

Cloud Native Services and Containerization Principles

12_Factor

Principle 01: Code Base 
Element 	Description
Statement	A single code base for each application, stored in its own repository tracked with version control.
Rational	If there are multiple codebases, it’s not an app – it’s a distributed system. Each component in a distributed system is an app, and each can individually comply with twelve-factor.
Multiple apps sharing the same code is a violation of twelve-factor. The solution here is to factor shared code into libraries which can be included through the dependency manager.
Implications	There is only one codebase per app, but there will be many deploys of the app. A deploy is a running instance of the app. This is typically a production site, and one or more staging sites. Additionally, every developer has a copy of the app running in their local development environment, each of which also qualifies as a deploy
Metrics	One codebase per each application


Principle 02: Dependencies
Element	Description
Statement	Each service/microservice isolates and packages its own dependencies, embracing changes without impacting the entire system.
Rational	Most programming languages offer a packaging system for distributing support libraries, such as Nuget for .NET or Rubygems for Ruby. Libraries installed through a packaging system can be installed system-wide (known as “site packages”) or scoped into the directory containing the app (known as “vendoring” or “bundling”).
One benefit of explicit dependency declaration is that it simplifies setup for developers new to the app. The new developer can check out the app’s codebase onto their development machine, requiring only the language runtime and dependency manager installed as prerequisites.
Implications	Build process must be rely on packaging system which manage the dependences agnostic from the environment 
Metrics	All dependencies in the build configuration file of the app, must be managed by a packaging system


Principle 03: Configuration
Element	Description
Statement	Configuration information is moved out of the microservice and externalized through a configuration management tool outside of the code. 
Rational	The same deployment can propagate across environments with the correct configuration applied.
Implications	Application must be developed with the concept of fetching configuration from environment configuration service, e.g. ConfigMap in Kubernetes or something like web service hosted by the target environment.
The use of web.config or appsettings.json files in .NET must be limited as possible.
Metrics	App configuration is managed by the hosting environments. 


Principle 04: Backing Services 
Element	Description
Statement	Ancillary resources (data stores, caches, message brokers) should be exposed via an addressable URL. 
Rational	Doing so decouples the resource from the application, enabling it to be interchangeable.

A deploy of the twelve-factor app should be able to swap out a local MySQL database with one managed by a third party (such as Amazon RDS) without any changes to the app’s code. Likewise, a local SMTP server could be swapped with a third-party SMTP service (such as Postmark) without code changes. In both cases, only the resource handle in the config needs to change.
Implications	The code for a twelve-factor app makes no distinction between local and third-party services to the app, both are attached resources, accessed via a URL or other locator/credentials stored in the config
Metrics	Loosely coupled services


Principle 05: Build, Release, Run
Element	Description
Statement	Each release must enforce a strict separation across the build, release, and run stages. Each should be tagged with a unique ID and support the ability to roll back. Modern CI/CD systems help fulfill this principle.
Rational	Deployment tools typically offer release management tools, most notably the ability to roll back to a previous release. For example, the Capistrano deployment tool stores releases in a subdirectory named releases, where the current release is a symlink to the current release directory. Its rollback command makes it easy to quickly roll back to a previous release.

Implications	Every release should always have a unique release ID, such as a timestamp of the release (such as 2011-04-06-20:32:17) or an incrementing number (such as v100). Releases are an append-only ledger and a release cannot be mutated once it is created. Any change must create a new release.
Metrics	Strict separation between the build, release, and run


Principle 06: Processes
Element	Description
Statement	Execute the app as one or more stateless processes.
processes are stateless and share-nothing. Any data that needs to persist must be stored in a stateful backing service, typically a database.
Rational	The twelve-factor app never assumes that anything cached in memory or on disk will be available on a future request or job – with many processes of each type running, chances are high that a future request will be served by a different process. Even when running only one process, a restart (triggered by code deploy, config change, or the execution environment relocating the process to a different physical location) will usually wipe out all local (e.g., memory and filesystem) state.
Implications	Some web systems rely on “sticky sessions” – that is, caching user session data in memory of the app’s process and expecting future requests from the same visitor to be routed to the same process. Sticky sessions are a violation of twelve-factor and should never be used or relied upon. Session state data is a good candidate for a datastore that offers time-expiration, such as Memcached or Redis.
Metrics	No sticky session(s) managed by the app


Principle 07: Port Binding
Element	Description
Statement	Export services via port binding

Each service should be self-contained with its interfaces and functionality exposed on its own port. Doing so provides isolation from other microservices.
Rational	App is completely self-contained and does not rely on runtime injection of a webserver into the execution environment to create a web-facing service
Implications	This is typically implemented by using dependency declaration to add a webserver library to the app, such as Tornado for Python, Thin for Ruby, or Jetty for Java and other JVM-based languages. This happens entirely in user space, that is, within the app’s code. The contract with the execution environment is binding to a port to serve requests.
Metrics	Slef-contained app


Principle 08: Concurrency
Element	Description
Statement	Services scale out across a large number of small identical processes (copies) as opposed to scaling-up a single large instance on the most powerful machine available. 
Rational	In the twelve-factor app, processes are a first-class citizen. Processes in the twelve-factor app take strong cues from the unix process model for running service daemons. 
Implications	Using this model, the developer can architect their app to handle diverse workloads by assigning each type of work to a process type. For example, HTTP requests may be handled by a web process, and long-running background tasks handled by a worker process.
Metrics	Applying single responsibility per each process  



Principle 09: Disposability
Element	Description
Statement	Service instances should be disposable, favoring fast startups to increase scalability opportunities and graceful shutdowns to leave the system in a correct state. Docker containers along with an orchestrator inherently satisfy this requirement.
Rational	Processes should strive to minimize startup time. Ideally, a process takes a few seconds from the time the launch command is executed until the process is up and ready to receive requests or jobs. Short startup time provides more agility for the release process and scaling up; and it aids robustness, because the process manager can more easily move processes to new physical machines when warranted.

Processes shut down gracefully when they receive a SIGTERM signal from the process manager. For a web process, graceful shutdown is achieved by ceasing to listen on the service port (thereby refusing any new requests), allowing any current requests to finish, and then exiting. Implicit in this model is that HTTP requests are short (no more than a few seconds), or in the case of long polling, the client should seamlessly attempt to reconnect when the connection is lost.
Implications	app’s processes are disposable, meaning they can be started or stopped at a moment’s notice. This facilitates fast elastic scaling, rapid deployment of code or config changes, and robustness of production deploys.
Metrics	Restart time and graceful shutdown 



Principle 10: Dev/Prod Parity
Element	Description
Statement	Keep environments across the application lifecycle as similar as possible, avoiding costly shortcuts. Here, the adoption of containers can greatly contribute by promoting the same execution environment.
Rational	Historically, there have been substantial gaps between development (a developer making live edits to a local deploy of the app) and production (a running deploy of the app accessed by end users). These gaps manifest in three areas:
1.	The time gap: A developer may work on code that takes days, weeks, or even months to go into production.
2.	The personnel gap: Developers write code, ops engineers deploy it.
3.	The tools gap: Developers may be using a stack like Nginx, SQLite, and OS X, while the production deploy uses Apache, MySQL, and Linux.
Implications	The twelve-factor app is designed for continuous deployment by keeping the gap between development and production small. Looking at the three gaps described above:
1.	Make the time gap small: a developer may write code, and have it deployed hours or even just minutes later.
2.	Make the personnel gap small: developers who wrote code are closely involved in deploying it and watching its behavior in production.
3.	Make the tools gap small: keep development and production as similar as possible.
Metrics	Difference between dev and prod environments


Principle 11: Logging
Element	Description
Statement	Treat logs generated by services as event streams. Process them with an event aggregator and propagate the data to data-mining/log management tools like Azure Monitor or Splunk and eventually long-term archival.
Rational	Logs provide visibility into the behavior of a running app. In server-based environments they are commonly written to a file on disk (a “logfile”); but this is only an output format.

Logs are the stream of aggregated, time-ordered events collected from the output streams of all running processes and backing services. Logs in their raw form are typically a text format with one event per line (though back traces from exceptions may span multiple lines). Logs have no fixed beginning or end but flow continuously as long as the app is operating.
Implications	app never concerns itself with routing or storage of its output stream. It should not attempt to write to or manage logfiles. Instead, each running process writes its event stream, unbuffered, to stdout. During local development, the developer will view this stream in the foreground of their terminal to observe the app’s behavior.
Metrics	Streamed logs



Principle 12: Admin Processes
Element	Description
Statement	Run administrative/management tasks as one-off processes. Tasks can include data cleanup and pulling analytics for a report. Tools executing these tasks should be invoked from the production environment, but separately from the application.
Rational	The process formation is the array of processes that are used to do the app’s regular business (such as handling web requests) as it runs. Separately, developers will often wish to do one-off administrative or maintenance tasks for the app, such as:
1.	Running database migrations 
2.	Running a console (also known as a REPL shell) to run arbitrary code or inspect the app’s models against the live database. 
3.	Running one-time scripts committed into the app’s repo 
Implications	One-off admin processes should be run in an identical environment as the regular long-running processes of the app. They run against a release, using the same codebase and config as any process run against that release. Admin code must ship with application code to avoid synchronization issues.
Metrics	

Beyond 12_Factor
Principle 13: API First
Element	Description
Statement	Make everything a service. Assume your code will be consumed by a front-end client, gateway, or another service.
Rational	Planning on building a service as part of a larger
Ecosystem. 


By designing API first, you can facilitate discussion with
your stakeholders (your internal team, customers, or possibly other
teams within your organization who want to consume your API)
well before you might have coded yourself past the point of no
return. This collaboration then allows you to build user stories,
mock your API, and generate documentation that can be used to
further socialize the intent and functionality of the service you’re
building.
Implications	Collaboration between business and design teams to provide the high-level manifest of the new business services APIs
Metrics	



Principle 14: Telemetry
Element	Description
Statement	On a workstation, you have deep visibility into your application and its behavior. In the cloud, you don’t. 
Rational	Auditing and monitoring cloud applications are often overlooked
but are perhaps some of the most important things to plan and do
properly for production deployments. If you wouldn’t blindly
launch a satellite into orbit with no way to monitor it, you shouldn’t
do the same to your cloud application.
There are generally a few different categories of data for application monitoring:
1.	Application performance monitoring (APM)
2.	Domain-specific telemetry
3.	Health and system logs
Implications	Make sure your design includes the collection of monitoring, domain-specific, and health/system data:
1.	Application have to expose the required probes to be used by the hosting environment for checking app health 
2.	Application must stream the required logs data so it can by manipulated in real-time basis by the target monitoring system
Metrics	


Principle 15: Authentication/ Authorization
Element	Description
Statement	Implement identity from the start. Consider RBAC (role-based access control) features available in public clouds.

Rational	Security is a vital part of any application and cloud environment.
Security should never be an afterthought.
A cloud-native application is a secure application. Your code,
whether compiled or raw, is transported across many data centers,
executed within multiple containers, and accessed by countless clients some legitimate, most nefarious.
Implications	With tools like OAuth2, OpenID Connect, various SSO servers and
standards, as well as a near infinite supply of language-specific
authentication and authorization libraries, security should be something
that is baked into the application’s development from day one,
and not added as a bolt-on project after an application is running in
production.
Metrics	





Containerization 
Principle 01: Single Concern
Element	Description
Statement	The main motivation for Single Concern Principle is container image reuse and replaceability
Rational	Creating a container that addresses a single concern, the chances are higher of container image reuse in different application contexts.
And, in case of multiple concerns are managed by the container, it can use patterns such as sidecar and init-containers to combine multiple containers into a single deployment unit (pod), where each container still handles a single concern.
Implications	Container have to be designed to manage single concern as possible
Metrics	Number of business concerns are managed by the container


Principle 02: High Observability
Element	Description
Statement	The container exposes a set of APIs used by the hosting environment to observe and manage the application e.g. metrics, tracing, logs, process health, readiness, and liveness.

The application should log important events into the standard error (STDERR) and standard output (STDOUT) for log aggregation by tools such as Fluentd and Logstash and integrate with tracing and metrics-gathering libraries such as OpenTracing, Prometheus, and others.
Rational	This is a fundamental prerequisite for automating container updates and life cycles in a unified way, which in turn improves the system’s resilience and user experience.
Implications	Container must provide application programming interfaces (APIs) for the runtime environment to observe the container health and act accordingly
Metrics	Percent of observation APIs provided by the container 


Principle 03: Life Cycle Conformance
Element	Description
Statement	Container provide APIs for the platform to read from, as the application have a way to read the events coming from the container management platform e.g. PostStart, PreStop, SIGTERM, and SIGKILL
Rational	The application/service have a way to read the events coming from the platform.

There are all kind of events coming from the managing platform that are intended to help in managing the life cycle of the container. It is up to the application to decide which events to handle and whether to react to those events or not.

But some events are more important than others. For example, any application that requires a clean shutdown process needs to catch signal: terminate (SIGTERM) messages and shut down as quickly as possible. This is to avoid the forceful shutdown through a signal: kill (SIGKILL) that follows a SIGTERM.
Implications	The application/service have to be designed and developed to handle the required events raised by container platform e.g. SIGTREM
Metrics	All required events which raised by the container platform are handled by the application


Principle 04: Image Immutability
Element	Description
Statement	Containerized applications are meant to be immutable, and once built are not expected to change between different environments
Rational	That, allows practices such as automatic roll-back and roll-forward during application updates, which is an important aspect of cloud-native automation
Implications	This implies the use of an external means of storing the runtime data and relying on externalized configurations that vary across environments, rather than creating or modifying containers per environment. Any change in the containerized application should result in building a new container image and reusing it across all environments
Metrics	


Principle 05: Process Disposability
Element	Description
Statement	Container is disposable as required for the purposes of maintenance, migration, and scaling-down   
Rational	One of the primary motivations for moving to containerized applications is that containers need to be as ephemeral as possible and ready to be replaced by another container instance at any point in time
Implications	Containerized application must be designed and developed to disposable as mentioned in the 12 factor principles.
Container management system must be able replace and scale the hosted applications
Metrics	


Principle 06: Self-Containment
Element	Description
Statement	The Container should contain everything it needs at build time.
Rational	The container should rely only on the presence of the Linux kernel and have any additional libraries added into it at the time the container is built. In addition to the libraries, it should also contain things such as the language runtime, the application platform if required, and other dependencies needed to run the containerized application
Implications	Image build process must wrap all required libraries at runtime 
Metrics	


Principle 07: Runtime Confinement
Element	Description
Statement	Every container declares its resource requirements and pass that information to the platform
Rational	Container is not just a single-dimensional black box of one size on the disk. Containers have multiple dimensions at runtime, such as memory usage dimension, CPU usage dimension, and other resource consumption dimensions.
Implications	The build process of container image must be configured well with the required resources on different environments (dev, test, preprod, and prod)
Metrics	


Principle 08: Container Security
Element	Description
Statement	Container is run with a limited privilege account and communicate securely with the internal/external environments.
Rational	Container must be secure to prevent any vulnerability on the environment and business.
Implications	Do not run containers as root user. 
Deploy containers with signed images. 
Patch vulnerabilities by deploying new container versions. 
Encrypt traffic between containers. 
Do not store credentials in containers. 
Update base operating systems regularly. 
Ensure containers access only needed resources. 
Monitor applications instead of just infrastructure.
Metrics	


Technology Principles

PRINCIPLE 01 –
 Use Open Standards and Open Source
Element	Description
Statement	Open standards should be used where applicable in solution designs to enable interoperability. Open source software must be compared and considered alongside commercial software when selecting technology solutions.
Rationale	Closed proprietary standards restrict reuse, reduce interoperability and can create vendor lock-in that leads to unforeseen financial costs.
Implications	Exit, rebid and rebuild costs must be taken into consideration during procurement decisions for best value for money comparisons, between open source and proprietary solutions.
Open Source is not necessarily free to use. Many independent software vendors use open source technology within proprietary for-profit services. Other companies provide commercial service management wrappers around open source products. 
Commercial software needs to be considered alongside open source equivalents from a total cost of ownership perspective.
Metrics	

PRINCIPLE 02 –
  Manage technical debt and obsolescence
Element	Description
Statement	The development process for the company must make changes easier. Any
tactical decisions that introduce technical debt (quick but messy
solutions) will only be endorsed if there is a recognized actionable plan to
address both technically and financially.
Rationale	Unaddressed technical debt increases the complexity and costs of maintaining systems making it harder to upgrade software, transition services and deliver solutions that meet users’ needs
Implications	Reducing technical debt must become part of the company’s culture. Applications and services need to be designed and delivered to be as technology independent as possible. An increased level of service-based architecture will be required.
Delivery projects adopting an Agile delivery method will need to have an Architecture Owner to safeguard against adding new technical debt into the Thiqah systems.
Software and hardware assets (non-Cloud) must be recorded and managed in a configuration management system.
Metrics	

PRINCIPLE 03 –
 Exploit the Cloud
Element	Description
Statement	Solutions will be assessed to determine the benefits of migration to
Cloud-based service models for infrastructure, platform and software as applicable.
Rationale	Assessment of architectures, workloads, finance, operations and security will determine if a solution can be re-hosted (IaaS), rebuilt (PaaS), replaced (SaaS) or refactored as a hybrid solution.
Implications	Not all Thiqah services will be appropriate for delivery via the cloud. Evaluation criteria need to be created to provide the basis for an assessment model that can be used to justify architecture decisions. 
Cloud Service Providers must evidence the ITSM best practices, security and data protection standards followed.
Metrics	
Quality Principles
 
PRINCIPLE 01 – SECURITY
Element	Description
Statement	The architecture should ensure confidentiality, authenticity, and reproducibility, and
comply with legislation
Rationale	Government security, confidentiality, and privacy policies and laws are adhered to Information is protected against unauthorized access, denial of service, and Intentional/accidental modification.
Appropriate levels of access to information while maintaining tight security against unauthorized access.
Implications	Clear, well-communicated security policies
Security considerations at all levels of the architecture
A robust regime of security testing from both internal and external perspectives Proactive management of security systems
Metrics	Number of security incidents

PRINCIPLE 02 – AVAILABILITY
Element	Description
Statement	Systems should be capable and highly available
Rationale	Permanently available applications are reliable and trustworthy and encourage residents and businesses to use e-Government Changing working patterns and citizen expectations are supported.
Implications	Clear settings, No single point of failure in the architecture Proactive planning for the downtime of essential services.
Metrics	Availability against downtime.


PRINCIPLE 03 – FAULT AND ERROR TOLERANCE
Element	Description
Statement	Systems should be capable of handling unforeseen and invalid system states
Rationale	Unpredictable system behavior negatively affects the adoption of services Potential for data loss or corruption.
Implications	Clear, well-communicated design and coding standards Robust integration and testing regime Integrated system help center and guidance features
Metrics	The number of issues raised on live services as a result of system crashes and unexpected outcomes.
 
PRINCIPLE 04 – PERFORMANCE AND SCALABILITY
Element	Description
Statement	Systems should have response times that encourage widespread adoption within their user communities. The system should be scalable to allow additional capacity/bandwidth/volume of users.
Rationale	Successful use of an application is contingent upon user-friendly, performance-driven provision of data. 
With centrally operated applications, the number of users is often unknown, cost-effective scalability must be ensured as the number of public entities and users increases.
Without easy scalability, systems risk quickly requiring major costly upgrades and/or facing service disruptions.
Implications	Clear performance (and other non-functional requirements) must be stated. Agile teams must work together on predictions and capacity planning for service adoption and peak usage.

Performance modeling, testing, and monitoring disciplines should be established with appropriate responsibility.
Metrics	Transaction response times.

 
PRINCIPLE 05 – INTEROPERABILITY AND OPENNESS
Element	Description
Statement	The system should easily interface with other systems through APIs in a manner that allows multiple systems to operate within one environment
Rationale	Thiqah currently operate cost-intensive legacy systems. The openness of an application is crucial to its future successful use. Systems with limited interoperability risk requiring complex patching and interfaces for every new technology integrated.
Implications	Architectural interfaces should be well-designed and documented to enable simple integration of new and existing systems need education and training for solution design and development staff.
Metrics	Reduction in time and cost for system integration projects


PRINCIPLE 06 – AGILITY AND FLEXIBILITY
Element	Description
Statement	The architecture should be easily adjustable to new frames of reference as well as upgrades at a predictable cost.
Justification	Systems maintenance typically consumes more than high percent of many organizations’ overall budget. Well-maintained and -updated systems increase efficiency and reduce the potential for downtime
Implications	BioSolutions teams must plan, design, and construct to support the growth and expansion of services (known requirements).
Operating and updating systems should be as simple and cost-effective as possible to enable external experts to efficiently maintain and update them with a minimal learning curve.
Metrics	Percentage of overall budget spent on maintenance Speed of response to business change


PRINCIPLE 07 – COMPLETENESS
Element	Description
Statement	Provide a standard that yields a complete architecture if closely followed
Justification	Changes are minimized during the maintenance phase of systems built to follow the standards. Developed systems should have components that enable them to cover all business requirements
Implications	The standards must be constantly researched and updated to remain current with needed technologies.
A detailed agile project management process is needed to ensure changes are made known to entities as required
Metrics	


