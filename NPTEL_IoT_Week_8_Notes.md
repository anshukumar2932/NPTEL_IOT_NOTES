# NPTEL IoT – Week 8 Exam Notes
## Assignment Priority + Complete Lecture Coverage

**Course:** Introduction to Internet of Things  
**Week:** 8  
**Exam style:** MCQ/MSQ  
**Assignment:** 15 questions / 15 marks

> **Priority rule:** The assignment is the first and highest-priority section. After that, these notes cover the complete Week 8 lecture material: Recent Advances of SDN in IoT, Cloud Computing Fundamentals, Cloud Service Models, Cloud Service Management & Security, and Cloud Computing Case Studies.

---

# 1. WEEK 8 ULTRA-QUICK REVISION

## SDN for IoT – Recent Advances
- Traditional mobile networks are:
  - difficult to scale,
  - difficult to manage,
  - inflexible,
  - cost-expensive.
- SDN mobile networking:
  - flow-table paradigm,
  - logically centralized control,
  - path management,
  - network virtualization.
- SDWMN use cases:
  - interference management,
  - mobile traffic management / offloading.
- Access-device rule placement challenges:
  - normal OpenFlow does not directly support wireless,
  - mobile users cause frequent rule changes,
  - heterogeneous devices.
- Approaches:
  - **ODIN**
  - **Ubi-Flow**
  - **Mobi-Flow**
- ODIN:
  - Odin agent → physical/access point side,
  - Odin master → controller side,
  - LVAP = Light Virtual AP.
- Mobi-Flow:
  - predicts next user location,
  - proactively places rules at relevant APs,
  - uses an **order-K Markov predictor**,
  - can use linear programming for optimal AP selection,
  - reduces control-message overhead and energy consumption.
- Backbone:
  - load balancing is important,
  - dynamic resource allocation can be integrated.
- Data center:
  - mice-flow → wildcard rules,
  - elephant-flow → exact-match rules,
  - classify flows before inserting rules.
- Anomaly detection:
  - monitor flows,
  - monitor switch port statistics.
- Wireless experimentation:
  - **Mininet-WiFi** → wired Ethernet + Wi-Fi/IEEE 802.11,
  - **ONOS** → controller placement.

## Cloud Fundamentals
- NIST definition: convenient, on-demand network access to a shared pool of **configurable computing resources**.
- Essential characteristics:
  1. On-demand self-service
  2. Broad network access
  3. Resource pooling
  4. Rapid elasticity
  5. Measured service
- Service models:
  - **IaaS**
  - **PaaS**
  - **SaaS**
- Deployment models:
  - Public
  - Private
  - Hybrid
  - Community
  - Also discussed: Distributed, Multi-cloud, Inter-cloud.
- Cloud advantages:
  - low upfront infrastructure cost,
  - real-time availability,
  - better utilization,
  - usage-based costing,
  - faster time-to-market.

## Service Models
- IaaS → infrastructure: compute, storage, network, OS.
- PaaS → platform/middleware for application development and deployment.
- SaaS → completed application delivered as a service.
- IaaS virtualization → **hypervisor** allows multiple VMs on physical hardware.
- PaaS removes the need to manage underlying hardware/OS.
- SaaS is commonly accessed through a browser/thin client and is provider-managed.

## Service Management + Security
- SLA → defines non-functional requirements expected from provider.
- Service accounting → obtains resource-usage records.
- Billing → uses accounting records + resource prices + billing rules.
- Cloud security:
  - network level,
  - host level,
  - application level.
- Data security objectives:
  - confidentiality,
  - integrity,
  - availability.
- Security mechanisms:
  - identity management,
  - encryption,
  - access control.
- IAM → legitimate users access legitimate resources at legitimate times for legitimate reasons.
- Trust vs reputation:
  - trust → expectation between entities in a context/time,
  - reputation → community belief about an entity's standing.

## Cloud Simulation
- Simulation → reliable, scalable, repeatable pre-deployment evaluation.
- CloudSim:
  - Java-based,
  - developed at CLOUDS Lab, University of Melbourne,
  - models data centers, VMs, applications, users, network topology.
- CloudAnalyst → GUI-based tool built on CloudSim.
- GreenCloud → energy-aware cloud data-center simulation, based on NS2 extension.
- OpenStack → open-source cloud platform, mainly associated with IaaS in the lecture.
- AWS EC2 → virtual computing environments with dynamic scaling and pay-per-use.

---

# 2. ASSIGNMENT-FIRST: ALL 15 QUESTIONS

## Q1. Which is a problem in traditional (non-SDN) mobile networks?

**Answer: D — Difficult to scale due to static, over-provisioned networks**

### Explanation
Traditional mobile networks are:
- difficult to scale,
- difficult to manage,
- inflexible,
- cost-expensive.

Static, over-provisioned infrastructure is inflexible when mobile traffic demand becomes high.

### Trap
Do not choose “too flexible hardware architecture.” The problem is the opposite: **inflexibility**.

**Memory:** Traditional mobile → **static + over-provisioned + difficult to scale**

---

## Q2. In ODIN, what does the Odin agent do?

**Answer: C — It is placed with the physical devices to communicate with the controller**

ODIN has two major components:

| Component | Location |
|---|---|
| **Odin agent** | With physical/access devices |
| **Odin master** | Controller side |

### Trap
The agent is NOT the controller-side master.

**Memory:** Agent → device side; Master → controller side.

---

## Q3. What is the primary goal of Mobi-Flow's proactive rule placement?

**Answer: B — Predict users' future location and place flow-rules at APs accordingly**

Mobi-Flow:
1. observes the user's current location at time `t`,
2. predicts the user's location at `t+1`,
3. places rules at APs likely to serve the user.

### Predictor
Uses an **order-K Markov predictor**.

### Trap
Mobi-Flow does not eliminate the controller and does not intentionally increase PACKET-IN messages.

**Memory:** Mobi-Flow = **mobility prediction + proactive rule placement**

---

## Q4. Which simulation tool supports both wired and wireless IEEE 802.11 networks?

**Answer: D — Mininet-WiFi**

### Mininet-WiFi
Supports:
- wired Ethernet,
- wireless Wi-Fi / IEEE 802.11.

The lecture also states **ONOS** can be used to place controllers.

### Trap
Do not confuse Mininet-WiFi with CloudSim. CloudSim is for cloud-computing simulation.

---

## Q5. According to NIST, cloud computing provides on-demand network access to a shared pool of what?

**Answer: B — Configurable computing resources**

NIST definition emphasizes:

> convenient, on-demand network access to a shared pool of configurable computing resources.

Examples:
- networks,
- servers,
- storage,
- applications.

### Memory
**Cloud = on-demand + shared pool + configurable resources**

---

## Q6. Which is an essential characteristic of cloud computing?

**Answer: A — Rapid elasticity**

NIST's five essential characteristics are:

1. On-demand self-service
2. Broad network access
3. Resource pooling
4. Rapid elasticity
5. Measured service

### Trap
Manual resource allocation is not an essential cloud characteristic.

---

## Q7. Which deployment model is for the exclusive use of one organization?

**Answer: B — Private cloud**

Private cloud:
- functions for a single organization,
- can be managed on-premises by the organization,
- or off-premises by a third party.

### Memory
**Private = one organization**

---

## Q8. Which is an example of a public cloud provider?

**Answer: A — Amazon Web Services (AWS)**

Lecture examples:
- AWS
- Google Compute Engine
- Microsoft Azure

### Trap
An organization's internal private data center is not a public cloud.

---

## Q9. Which cloud service model provides servers, storage, network and operating-system access?

**Answer: C — IaaS**

IaaS = **Infrastructure-as-a-Service**

Provides access to:
- compute/servers,
- storage,
- network,
- operating system.

### Memory
**IaaS = infrastructure**

---

## Q10. What allows multiple VMs to share the same physical hardware in IaaS?

**Answer: D — Hypervisor**

Concept:

```text
Physical Hardware
       ↓
   Hypervisor
   ↙       ↘
 VM1       VM2
 OS1       OS2
```

The hypervisor manages multiple virtual machines on virtualized physical hardware.

### Trap
DNS server, load balancer and firewall are not the virtualization layer.

---

## Q11. Which service model is application middleware offered as a service to developers?

**Answer: C — PaaS**

PaaS = **Platform-as-a-Service**

It:
- abstracts infrastructure,
- supports application development/deployment,
- removes the need to manage underlying hardware and OS.

### Memory
**PaaS = platform for developers**

---

## Q12. What is the main purpose of an SLA?

**Answer: B — Define the non-functional requirements expected from the service provider**

SLA provides:
- clearly defined deliverables,
- quality expectations,
- utility,
- warranty/service guarantees.

### Trap
SLA is not primarily a hardware-vendor list or programming-language agreement.

**Memory:** SLA → **service quality/requirements/guarantees**

---

## Q13. What does service accounting primarily obtain?

**Answer: A — Resource usage information, typically in the form of records**

Accounting obtains usage information through monitoring and metric measurements.

Billing then uses:
- accounting records,
- resource prices,
- billing rules.

### Memory
**Accounting = usage records; Billing = price calculation**

---

## Q14. Why use cloud simulators such as CloudSim before deployment?

**Answer: D — Reliable, scalable and repeatable pre-deployment performance evaluation**

Simulation provides:
- controlled environment,
- low/no deployment cost,
- repeatable tests,
- pre-detection of performance issues,
- opportunity to design countermeasures.

### Trap
A simulator does not permanently replace real cloud infrastructure.

---

## Q15. Where was CloudSim developed and in which language?

**Answer: B — CLOUDS Lab, University of Melbourne; Java**

CloudSim:
- models cloud environments,
- is Java-based,
- was developed at the **CLOUDS Lab, University of Melbourne**.

### Memory
**CloudSim → Melbourne + Java**

---

# 3. RECENT ADVANCES OF SDN IN IoT

## 3.1 Traditional Mobile Network Problems

The lecture identifies four major problems:

### 1. Difficult to scale
Static, over-provisioned networks are inflexible when traffic demand becomes high.

### 2. Difficult to manage
Complexity can lead to misconfigurations.

### 3. Inflexible
Introducing a new service can take too much time because hardware architecture is inflexible.

### 4. Cost-expensive
Both:
- CapEx (capital expenditure),
- OpEx (operational expenditure)

can be high.

---

# 4. SDN FOR MOBILE NETWORKING

## 4.1 Flow-table paradigm

SDN's flow-table approach is suitable for end-to-end communication across multiple technologies such as:
- Wi-Fi,
- 3G,
- 4G.

## 4.2 Logically centralized control

A logically centralized controller can coordinate base stations.

This is particularly useful for:
- base-station coordination,
- inter-cell interference management.

---

# 5. PATH MANAGEMENT

SDN allows data to be routed based on **service requirements** without depending entirely on core routing policies.

### Exam idea
Traditional routing policies → less flexible.

SDN path management → application/service-aware routing.

---

# 6. NETWORK VIRTUALIZATION

Network virtualization:
- abstracts physical resources from network services,
- supports seamless connectivity,
- supports service differentiation among users.

### Memory
**Virtualization = abstract physical resources from services**

---

# 7. SDWMN USE CASES

## 7.1 Interference Management

The lecture's SDWMN diagram contrasts:

### Traditional mobile network
Interfering signals can reduce signal quality.

### Software-defined mobile network
A virtualized radio resource management function + SDN controller + OpenFlow-enabled switches can coordinate resources so that signals from one eNodeB do not adversely affect another.

### Exam idea
SDN can centrally coordinate radio/network resources to reduce interference.

---

## 7.2 Mobile Traffic Management

The lecture shows:
- mobile traffic offloading,
- OpenFlow,
- ANDSF (Access Network Discovery and Selection Function).

### Memory
Mobile traffic management → **offloading + OpenFlow**

---

# 8. KEY BENEFITS OF SDN IN MOBILE/IoT NETWORKS

The lecture lists:
- Centralized control of devices from multiple vendors.
- Higher rate of integration of new services.
- Abstracted network control and management.
- Network abstraction from the user.

### Assignment connection
These benefits explain why SDN is useful for dynamic IoT/mobile environments.

---

# 9. RULE PLACEMENT AT ACCESS DEVICES

## Challenges

### Challenge 1: Wireless support
General OpenFlow does not directly support wireless networks.

Therefore a **modified version of OpenFlow** is required.

### Challenge 2: Mobility
Users are mobile.

Therefore:
- the network changes dynamically,
- flow-rule placement must change frequently.

### Challenge 3: Heterogeneity
IoT networks contain heterogeneous devices.

The system must support heterogeneous devices on a common platform.

---

# 10. ODIN

ODIN is one approach for programmable wireless/SDN environments.

## Components

### Odin agent
Placed with physical devices/access points.

### Odin master
Placed at the controller end.

```text
Physical/AP side
      ↓
Odin Agent
      ↕
Controller
      ↑
Odin Master
```

## Other ODIN concept
**LVAP = Light Virtual AP**

The lecture also mentions conversion of 802.11.

### Assignment memory
**Agent → physical devices**

---

# 11. UBI-FLOW

Ubi-Flow addresses mobility management in Software-Defined IoT.

### Features
- Scalable control of APs.
- Fault tolerance.
- Flow scheduling.

Flow scheduling includes:
- network partition,
- network matching,
- load balancing.

### Memory
**Ubi-Flow = mobility + scalable AP control + fault tolerance + flow scheduling**

---

# 12. MOBI-FLOW

Mobi-Flow focuses on **mobility-aware flow-rule placement**.

## Proactive placement

Instead of waiting until the user reaches a new AP:

```text
Current location t
      ↓
Predict t+1
      ↓
Identify likely APs
      ↓
Place rules in advance
```

## Location prediction
Uses an **order-K Markov predictor**.

It uses recent location instances to predict the next location.

## Rule placement
Linear programming can be used to select the optimal AP.

## Benefit
Compared with conventional placement schemes, Mobi-Flow can significantly reduce:
- control-message overhead,
- network energy consumption.

### High-priority memory
**Mobi-Flow = prediction → proactive rules → lower overhead + lower energy**

---

# 13. RULE PLACEMENT AT BACKBONE NETWORK

Existing wired-network rule-placement schemes can be used.

### Important issue
**Load balancing** is important because IoT traffic/network conditions are dynamic.

### Additional concept
Dynamic resource allocation can be integrated.

---

# 14. DATA CENTER NETWORKING

Two flow types:

## Mice flow
Small/short-lived flow.

Lecture:
- **wildcard rules** can be placed for mice flows.

## Elephant flow
Large/high-volume flow.

Lecture:
- **exact-match rules** are useful.

### Important sequence
Before inserting flow rules:

```text
Classify flows
     ↓
Choose suitable rule
     ↓
Insert flow-rule
```

---

# 15. ANOMALY DETECTION IN IoT NETWORKS

SDN/OpenFlow can monitor network behavior.

## Monitoring methods

### 1. Flow monitoring
Monitor each flow in the network.

### 2. Port statistics
Collect switch port statistics.

### Why?
An anomaly can generate a large number of packets.

Monitoring traffic patterns can reveal abnormal behavior.

---

# 16. EXPERIMENTING WITH WIRELESS SDN

## Mininet-WiFi

Mininet-WiFi can deploy:
- wired networks,
- wireless networks.

### Wired
Ethernet.

### Wireless
Wi-Fi / **IEEE 802.11**.

## ONOS
The lecture states ONOS can be used to place controllers.

### Assignment
Wireless SDN simulation → **Mininet-WiFi**

---

# 17. CLOUD COMPUTING FUNDAMENTALS

## 17.1 Recent trends in computing

Cloud computing builds on trends such as:
- shared pools of configurable resources,
- ubiquitous dynamic on-demand access,
- packaged computing/storage resources,
- heterogeneous distributed computing nodes,
- loosely/tightly connected homogeneous nodes.

---

# 18. EVOLUTION OF CLOUD COMPUTING

Lecture timeline:

| Period/Year | Development |
|---|---|
| 1950s | Time-shared mainframe computers |
| 1969 | ARPANET |
| 1970s | Virtual machines by IBM |
| 1990s | Internet expansion + VPNs |
| 1996–97 | “Cloud computing” term |
| 1999 | Salesforce.com |
| 2002 | Amazon Web Services |
| 2006 | Amazon EC2 |
| 2008 | Google App Engine / Microsoft Azure |

### Exam caution
The timeline is lecture-specific; memorize the major milestones rather than assuming every cloud-history source uses identical dates.

---

# 19. NIST DEFINITION OF CLOUD COMPUTING

NIST defines cloud computing as a model enabling:

- convenient,
- on-demand,
- network access,
- to a shared pool,
- of configurable computing resources.

Examples:
- networks,
- servers,
- storage,
- applications.

### Key phrase
**On-demand + shared pool + configurable resources**

---

# 20. BUSINESS ADVANTAGES OF CLOUD

Lecture lists:
- Nearly zero upfront infrastructure investment.
- Real-time infrastructure availability.
- More efficient resource utilization.
- Usage-based costing.
- Reduced time to market.

---

# 21. GENERAL CLOUD CHARACTERISTICS

- Improved agility in resource provisioning.
- Ubiquitous access independent of device/location.
- Multitenancy.
- Dynamic load balancing.
- High reliability and scalability.
- Low cost and low maintenance.
- Improved security and access control.

---

# 22. NIST'S FIVE ESSENTIAL CHARACTERISTICS

## 1. Broad Network Access

Cloud resources:
- are available over a network,
- use standard access mechanisms,
- support heterogeneous clients.

Clients can include:
- mobile phones,
- laptops,
- PDAs,
- thin clients,
- thick clients.

---

## 2. Rapid Elasticity

Resources can be:
- rapidly allocated,
- rapidly released,
- dynamically scaled.

Two directions:

```text
Scale-out → add resources
Scale-in  → remove resources
```

The consumer should experience the resource pool as if it were nearly infinite.

---

## 3. Measured Service

Resource usage should be:
- recorded,
- monitored,
- dynamically controlled/optimized.

Usage measurement should be transparent between provider and consumer.

### Assignment connection
Service accounting depends on usage monitoring and measurement.

---

## 4. On-Demand Self-Service

Users can automatically obtain:
- server time,
- network storage,
- other resources

without requiring human interaction with the provider.

---

## 5. Resource Pooling

Provider resources are pooled.

The same pool can serve multiple users using:
- multitenancy,
- dynamic allocation according to demand.

---

# 23. CLOUD COMPONENTS

Lecture lists:

1. **Clients / end-users**
   - thick,
   - thin,
   - mobile.

2. **Services**
   - identity,
   - mapping,
   - search, etc.

3. **Applications**
   - web apps,
   - SaaS.

4. **Platform**
   - application/web hosting,
   - PaaS.

5. **Storage**
   - databases,
   - DSaaS.

6. **Infrastructure**
   - virtualization,
   - IaaS,
   - EC2.

### Memory
```text
Client
Services
Applications
Platform
Storage
Infrastructure
```

---

# 24. CLOUD SERVICE MODELS

Three core models:

```text
SaaS → finished application
PaaS → application platform
IaaS → infrastructure
```

---

# 25. IaaS

**Infrastructure-as-a-Service**

## Provides
- servers/compute,
- storage,
- network,
- operating system.

## User control
User can:
- deploy software,
- execute software,
- control operating systems,
- control applications.

In some cases the user can control selected networking components such as host firewalls.

### Examples from lecture
- Amazon EC2
- GoGrid
- iland
- Rackspace Cloud Servers

---

# 26. IaaS WORKING METHODOLOGY

```text
Physical Hardware
       ↓
   Hypervisor
   ↙       ↘
 VM1       VM2
 OS1       OS2
   ↘       ↙
Applications
```

The user rents computing infrastructure/resources.

The cloud provider handles:
- physical infrastructure,
- resource management,
- virtualization.

### Assignment
Multiple VMs sharing physical hardware → **Hypervisor**

---

# 27. WHY IaaS?

Useful when:
- a new business does not want to purchase hardware,
- workload grows rapidly,
- computing demand fluctuates,
- a new business model needs testing,
- capital expenditure must be minimized.

Example:
- festival-season demand for large e-commerce systems.

---

# 28. IaaS CHARACTERISTICS

## Scalability and elasticity
Dynamic allocation/release of infrastructure resources.

## Manageability and interoperability
- virtualized infrastructure can be controlled,
- resources can be preconfigured,
- resource status can be monitored,
- usage/billing records can be generated.

## Availability and reliability
- data should be retrievable,
- computing resources should remain accessible,
- computation/communication should be uninterrupted.

## Performance and optimization
- high physical-resource utilization,
- parallel processing,
- dynamic configuration of virtual infrastructure.

## Accessibility and portability
- easier control/access,
- reallocation,
- duplication of allocated resources.

---

# 29. IaaS CATEGORIES

### Public IaaS
Shared infrastructure available for self-service.

### Private IaaS
Private infrastructure with access control.

### Hybrid IaaS
Blend of public and private infrastructure.

---

# 30. IaaS CHALLENGES

- Regulations may prevent outsourcing sensitive data.
- Example: medical records.
- Network latency can degrade performance.
- Automated job scheduling may be needed.
- Seamless scaling must work despite traffic variation.
- Developers may still need to focus on lower-level system details.

---

# 31. PAAS

**Platform-as-a-Service**

PaaS removes the need to manage:
- underlying hardware,
- underlying operating systems.

It allows developers to focus on:
- application development,
- deployment,
- application management.

### Key definition
**PaaS = application middleware offered as a service to developers.**

### Examples
- Windows Azure
- Google App Engine

---

# 32. PaaS FEATURES

A PaaS offering can provide:
- operating system,
- server-side scripting environment,
- database management system,
- server software,
- support,
- storage,
- network access,
- design/development tools,
- hosting.

---

# 33. PaaS WORKING MODEL

Users:
- create applications using offered tools,
- subscribe to preconfigured features,
- receive infrastructure/application-management support.

Services are regularly updated with new features.

### Benefit
Developers do not need to manage underlying infrastructure complexity.

---

# 34. SAAS

**Software-as-a-Service**

SaaS delivers a completed application as a service.

## Characteristics
- provider runs/manages application,
- accessed through different clients,
- commonly through a web browser,
- provider handles operation/maintenance/technical support,
- supports pay-as-you-go,
- multi-tenant delivery.

### Examples from lecture
- Google Apps
- Salesforce
- Learn.com

---

# 35. SaaS VS TRADITIONAL SOFTWARE

| Traditional software | SaaS |
|---|---|
| Customer installs/manages/maintains | Provider manages |
| Runs on organization's systems | Runs as Internet service |
| Separate installations | One-to-many/multi-tenant |
| Cross-platform concerns | Less client-platform concern |
| Less frequent updates | More frequent updates |
| Separate upgrade costs | Usually service-based pricing |
| More piracy exposure | Less vulnerable to piracy |

---

# 36. SaaS ARCHITECTURE

Important concepts:

## Scalability
Maximize:
- application concurrency,
- sharing of threads,
- network connections/resources.

## Multi-tenancy
One application can serve users from multiple organizations.

Need:
- resource sharing,
- tenant separation,
- transparent operation.

## Configurability
A single application can serve several customers while providing separate data spaces.

### Trap
Changing configuration for one customer may affect the application behavior for others if the architecture is not carefully isolated.

---

# 37. SaaS LIMITATIONS

Lecture lists:
- Centralized control.
- Switching cost.
- Limited flexibility.
- Data security and privacy concerns.

---

# 38. SERVICE MODEL COMPARISON

| Layer | IaaS | PaaS | SaaS |
|---|---|---|---|
| Applications | User | User | **Provider** |
| Data | User | User | Provider-managed service |
| Runtime | User | Provider | Provider |
| Middleware | User | Provider | Provider |
| OS | User | Provider | Provider |
| Virtualization | Provider | Provider | Provider |
| Servers | Provider | Provider | Provider |
| Storage | Provider | Provider | Provider |
| Networking | Provider | Provider | Provider |

### Easy memory
- **IaaS:** You manage the most.
- **PaaS:** Provider manages infrastructure; you manage your app.
- **SaaS:** Provider manages almost everything; you use the application.

---

# 39. CLOUD DEPLOYMENT MODELS

## Public Cloud
- available for general use,
- typically owned by a cloud provider,
- examples: AWS, Google Compute Engine, Microsoft Azure.

### Advantages
- low setup cost,
- provider covers hardware/application/bandwidth,
- scalable,
- pay-per-use.

---

## Private Cloud
- exclusive to one organization,
- on-premises or off-premises,
- more control,
- lower security concern from the lecture comparison,
- requires regular maintenance.

### Assignment
Single organization → **Private cloud**

---

## Public vs Private

| Public | Private |
|---|---|
| Publicly shared resources | Privately shared |
| Multiple customer types | Limited customer scope |
| Internet | Internet/private network |
| Lower control/security in lecture comparison | Higher control/security |

---

## Hybrid Cloud
Constructed from two or more different cloud types:
- public,
- private,
- community.

Supports:
- data portability,
- application portability,
- load balancing between clouds.

---

## Community Cloud
Shared by organizations with common concerns such as:
- security,
- compliance,
- jurisdiction.

---

## Distributed Cloud
Scattered computing devices at different locations connected through one network.

Two types mentioned:
- public-resource computing,
- volunteer cloud.

---

## Multi-cloud
Multiple cloud services through one heterogeneous architecture.

Benefits:
- fault tolerance,
- flexibility.

---

## Inter-cloud
A unified global **“cloud of clouds”** over the Internet.

Focus:
- interoperability between cloud providers.

---

# 40. CLOUD SERVICE MANAGEMENT

Cloud service management aims to ensure:
- optimal performance,
- efficiency,
- on-demand service,
- desired customer outcomes.

## Objectives
- Standard services.
- Clear service descriptions.
- Usage monitoring and billing.
- High network/connectivity availability.
- Ease of access.
- Service-selection portals.
- Rapid resource fulfillment/decommissioning.
- Service guarantees.
- Secure computing/storage.

---

# 41. SLA

**SLA = Service Level Agreement**

### Purpose
Defines the **non-functional requirements** expected from the provider.

It provides:
- roadmap,
- clearly defined deliverables,
- quality,
- utility,
- warranty/service expectations.

### Assignment
SLA → **non-functional requirements**

---

# 42. ACCOUNTING AND BILLING

## Service Accounting
Obtains:
- resource usage information,
- usually in record form.

It depends on:
- infrastructure monitoring,
- service monitoring,
- metric measurements.

## Billing
Provider calculates billing using:
1. accounting records,
2. resource prices,
3. billing rules.

### Memory
```text
Monitoring
   ↓
Usage records
   ↓
Accounting
   ↓
Price + billing rules
   ↓
Bill
```

---

# 43. TRADITIONAL VS CLOUD SCALING

## Traditional data center
- heterogeneous hardware,
- networked computing,
- remote servers.

## Cloud
- off-premises,
- virtual hosting,
- heterogeneous hardware/software/networks.

### Major differences
- resilience,
- elasticity,
- flexibility,
- scalability,
- automation,
- running costs,
- security.

---

# 44. ECONOMICS OF CLOUD SCALING

Lecture gives four customer-population metrics:
1. Number of unique customer sets.
2. Duty cycles of customer sets.
3. Relative displacement duty cycle.
4. Load of customer set.

Economic incentives:
- lower cost,
- CapEx-free computing,
- faster project deployment,
- innovation,
- scale as needed,
- lower maintenance,
- resiliency/redundancy.

---

# 45. MANAGING DATA IN THE CLOUD

## Database-manager evaluation
Consider:
- type of application,
- data-asset protection,
- business intelligence,
- e-commerce,
- public vs private cloud suitability,
- development factors.

## Cloud DBMS demands
- efficiency,
- fault tolerance,
- adaptability to heterogeneity,
- operation on encrypted data,
- interoperability with other products/solutions.

---

# 46. DATABASE-AS-A-SERVICE

**DBaaS = Database-as-a-Service**

Examples mentioned:
- Microsoft Azure SQL Database
- Amazon DynamoDB
- Amazon Relational Database Service
- Google Cloud SQL
- Google App Engine Datastore
- ClearDB
- Database.com

---

# 47. CLOUD SECURITY

## Main problem
On public cloud, users may lose direct control over their information.

## Security concerns
- data loss,
- account seizing,
- service traffic hindrance,
- vulnerable APIs.

### Goal
Protect against:
- theft,
- leakage,
- deletion,

using secure policies.

---

# 48. INFRASTRUCTURE SECURITY

Security applies to:
- public/private cloud,
- SaaS,
- PaaS,
- IaaS.

Three levels:

```text
Network-level security
        ↓
Host-level security
        ↓
Application-level security
```

---

# 49. NETWORK-LEVEL SECURITY

Concerns:
- access control,
- confidentiality of data in transit,
- integrity of data in transit,
- availability of Internet resources to genuine users.

### Public-cloud point
A small network change can severely affect network topology.

---

# 50. HOST-LEVEL SECURITY

## PaaS/SaaS
- host OS is hidden from end users,
- security responsibilities move toward provider.

## IaaS
- primary goal is securing allocated hosts,
- example threat: **Blue Pill attack on hypervisor**.

### Trap
IaaS exposes more infrastructure control to the customer, so customer-side security responsibilities are greater.

---

# 51. APPLICATION-LEVEL SECURITY

Both:
- cloud service provider,
- customer

have responsibilities.

### SaaS
Provider:
- secures deliverable applications.

### PaaS
Provider:
- secures PaaS platform,
- secures deployed customer applications within the provider's responsibility.

### IaaS
Application-level security is not generally provided by IaaS itself; customers arrange their own application security mechanisms.

---

# 52. DATA SECURITY

## Objectives
- **Confidentiality**
- **Integrity**
- **Availability**

## Security mechanisms
- Identity management.
- Encryption.
- Access control.

## Data-security aspects shown in lecture
- Data in transit.
- Data at rest.
- Data provenance.
- Data remanence.
- Data lineage.
- Data involving multitenancy.

---

# 53. IAM

**IAM = Identity and Access Management**

Purpose:
Allow legitimate persons to access legitimate resources at:
- legitimate time,
- for legitimate reasons.

IAM manages:
- identities,
- access permissions,
- authentication,
- authorization,
- user evaluation according to roles/conditions.

## IAM features
- single access-control interface,
- increased security,
- resource-level access control,
- improved operational efficiency,
- improved regulatory compliance.

### Memory
**IAM = Who can access what, when, and under which conditions?**

---

# 54. ACCESS CONTROL LAYERS

Cloud access control can cover:

1. Cloud access.
2. Server access.
3. Service access.
4. Database access.
5. VM access.
6. Objects inside a VM.

Responsibility depends on:
- provider,
- consumer,
- deployment/service model.

---

# 55. TRUST VS REPUTATION

## Trust
Independent expectancy between two entities in a specific context at a given time.

## Reputation
Community's belief about an entity's standing.

Both help a customer select an appropriate cloud provider.

---

# 56. TRUST ESTABLISHMENT

Lecture mentions:
- accomplishment of SLA,
- audit standards,
- measurements and ratings,
- questionnaires for self-assessment.

---

# 57. RISK ASSESSMENT

Risk-assessment methodologies can be categorized as:

- Formal vs informal.
- Qualitative vs quantitative.
- Consequence vs cause analysis.
- Inductive vs deductive techniques.

### Qualitative
Uses categories such as:
- high,
- moderate,
- low.

### Quantitative
Uses numerical measures.

---

# 58. AUTHENTICATION IN CLOUD

Lecture focuses on user authentication between:
- new users,
- service provider.

### Important points
- Authentication can be attacked.
- A successful attack can expose confidential information to fake users.
- Lecture places user authentication at the **PaaS layer**.

---

# 59. CLOUD COMPUTING CASE STUDIES

## Why simulation?

Cloud simulators provide:
- reliable environment,
- scalable environment,
- repeatable experiments,
- pre-deployment testing,
- low/no real deployment cost,
- controlled environment,
- pre-detection of performance issues,
- countermeasure design.

---

# 60. CLOUD SIMULATORS

Lecture mentions:
- CloudSim
- CloudAnalyst
- GreenCloud
- iCanCloud
- GroudSim
- DCSim

---

# 61. CLOUDSIM

CloudSim is a simulation framework.

## Models
- data centers,
- virtual machines,
- applications,
- users,
- network topology.

## Key facts
- Java-based environment.
- Developed at **CLOUDS Lab, University of Melbourne**.
- Supports dynamic addition/removal of resources.
- Allows performance evaluation of application services.

### Assignment
CloudSim → **CLOUDS Lab + University of Melbourne + Java**

---

# 62. ADVANTAGES OF CLOUDSIM

- Time effectiveness.
- Minimum implementation time/effort.
- Flexibility.
- Applicability to diverse cloud environments.
- Modeling of application services in different environments.

---

# 63. CLOUDSIM FEATURES

- Multiple cloud data centers.
- Different data-center network topologies.
- Message-passing applications.
- Virtualized server hosts.
- VM allocation.
- User-defined VM resource-allocation policies.
- Energy-aware computational resources.
- Dynamic addition/removal of components.
- Stop/resume simulation.

---

# 64. CLOUDSIM ARCHITECTURE

Three main layers:

## Top: User Code
Specifies:
- machine specifications,
- application specifications,
- user requirements,
- scheduling policies,
- cloud scenarios.

Entities include:
- users,
- physical machines,
- virtual machines,
- applications/services,
- scheduling policies.

## Middle: CloudSim
Provides:
- cloud environment,
- modeling,
- simulation,
- management interfaces,
- memory/storage/bandwidth/VM modeling.

## Bottom: Core Simulation Engine
Handles:
- event scheduling,
- entity creation,
- component interaction,
- clock management.

### Memory
```text
User Code
   ↓
CloudSim
   ↓
Core Simulation Engine
```

---

# 65. CLOUDSIM RESOURCE MANAGEMENT

The architecture includes:
- VM provisioning,
- CPU allocation,
- memory allocation,
- storage allocation,
- bandwidth allocation,
- network topology,
- message-delay calculation,
- cloud data-center coordination.

---

# 66. CLOUDANALYST

CloudAnalyst:
- is based on CloudSim,
- provides a GUI,
- supports geographically distributed large-scale cloud applications,
- studies application behavior under deployment configurations.

## Features
- easy to use,
- highly configurable,
- flexible component addition,
- repeatable experiments,
- graphical charts/tables,
- extendable using Java Swing.

---

# 67. CLOUDANALYST COMPONENTS

The lecture architecture includes:
- GUI package,
- simulation,
- UserBase,
- DataCenterController,
- Internet,
- InternetCharacteristics,
- VmLoadBalancer,
- CloudAppServiceBroker.

### Memory
CloudAnalyst = **CloudSim + GUI + geographically distributed analysis**

---

# 68. GREENCLOUD

GreenCloud focuses on **energy-aware cloud data centers**.

## Why?
Data-center computing capacity and energy consumption contribute significantly to operational cost.

## What?
Operational cost includes energy used by:
- computing units,
- communication units.

## How?
GreenCloud monitors energy consumption of:
- servers,
- switches,
- other data-center components.

### Important fact
GreenCloud was developed as an extension of **NS2**.

---

# 69. GREENCLOUD FEATURES

- User-friendly GUI.
- Open source.
- Monitors energy consumption.
- Simulates cloud network components.
- Monitors individual-component energy.
- Supports improved power-management schemes.
- Dynamic device management/configuration.

### Memory
**GreenCloud = energy**

---

# 70. OPEN-SOURCE VS COMMERCIAL CLOUDS

| Open-source clouds | Commercial clouds |
|---|---|
| OpenStack, CloudStack, Eucalyptus | AWS, Microsoft Azure, Google App Engine |
| Mostly IaaS in lecture | IaaS/PaaS/SaaS subscriptions |
| Security implemented by user | Security implemented by provider |
| Private/on-premise | Public/off-premise/hosted-private |

---

# 71. OPENSTACK

OpenStack:
- collection of open-source technologies,
- managed by OpenStack Foundation,
- supports scalable cloud systems,
- preconfigured software suite,
- provides multiple cloud services,
- considered IaaS in the lecture.

## Components

| Component | Function |
|---|---|
| **Nova** | Compute |
| **Neutron** | Networking |
| **Cinder** | Block storage |
| **Keystone** | Identity |
| **Glance** | Image |
| **Swift** | Object storage |
| **Horizon** | Dashboard |
| **Trove** | Database |
| **Sahara** | Elastic MapReduce |
| **Manila** | Shared file system |
| **Designate** | DNS |
| **Searchlight** | Search |
| **Barbican** | Key manager |

## Features
- create/deploy VMs,
- create cloud-management environments,
- horizontal scaling,
- dynamically add/remove instances,
- open source.

### High-priority
**Nova = compute, Neutron = network, Cinder = block storage, Keystone = identity, Glance = image, Swift = object storage, Horizon = dashboard.**

---

# 72. MICROSOFT AZURE

Lecture states:
- formerly Windows Azure,
- supports IaaS and PaaS,
- supports many services,
- supports many programming languages/frameworks,
- available through Microsoft-managed worldwide data centers.

## Azure services
- Compute
- Mobile services
- Storage
- Data management
- Messaging
- Media
- CDN
- Developer
- Management
- Machine Learning

---

# 73. AZURE AS PAAS

PaaS model:
- platform provided to clients,
- clients develop/deploy software,
- clients focus on application rather than infrastructure,
- low cost,
- easier movement to new tools,
- addresses many OS/server/network management issues.

---

# 74. AZURE AS IAAS

IaaS model:
- total control of OS/application stack,
- data-center access/management/monitoring,
- useful when complete control is required,
- supports custom configurations.

### Easy distinction
- Azure PaaS → **focus on application development**.
- Azure IaaS → **more infrastructure/OS control**.

---

# 75. AMAZON EC2

**EC2 = Elastic Compute Cloud**

It is a web service for:
- launching server instances,
- managing instances,
- dynamic computation scaling.

### Business model
- pay-per-use,
- avoids large hardware purchases.

---

# 76. EC2 INSTANCE TYPES

Lecture examples:

### General purpose
- T2
- M4
- M3

### Compute optimized
- C4
- C3

### Memory optimized
- X1
- R4
- R3

### Accelerated computing
- P2
- G2
- F1

### Trap
These are **instance categories/examples**, not cloud service models.

---

# 77. EC2 FEATURES

## Operating systems
Supports different OS types and custom Amazon Machine Images.

## Persistent/storage options
- temporary local Instance Store,
- Amazon EBS,
- Amazon S3.

## Automated scaling
- rule-based,
- schedule-based.

## Availability zones
Multiple availability zones improve fault tolerance.

## Security groups
Only predefined:
- protocols,
- ports,
- source IP ranges

can reach instances.

## Elastic IP
Maps an IP address to a user's VM/instance.

## CloudWatch
Monitors:
- CPU,
- disk,
- network resource utilization.

## Key-pair security
Public/private key pair improves instance security.

## VPC
Virtual Private Cloud:
- logically separated from the rest of AWS,
- can optionally connect to user's own network.

---

# 78. HIGH-PRIORITY COMPARISONS

## IaaS vs PaaS vs SaaS

| | IaaS | PaaS | SaaS |
|---|---|---|---|
| Main idea | Infrastructure | Platform | Finished software |
| User focuses on | OS/app/software | Application | Usage |
| Hardware managed by | Provider | Provider | Provider |
| OS managed by | User | Provider | Provider |
| App managed by | User | User | Provider |
| Typical user | System/admin/developer | Developer | End user |

### One-line memory
**IaaS = infrastructure, PaaS = platform, SaaS = software.**

---

## Public vs Private vs Hybrid

| Public | Private | Hybrid |
|---|---|---|
| General users/industries | Single organization | Combination |
| Provider-owned | Organization/third-party managed | Two+ cloud types |
| Low setup cost | More control | Portability/load balancing |
| Pay-per-use | Maintenance needed | Multiple deployment models |

---

## Traditional Mobile vs SDN Mobile

| Traditional | SDN |
|---|---|
| Static/over-provisioned | Dynamic/software-controlled |
| Difficult to scale | Easier dynamic control |
| Difficult to manage | Centralized/logical control |
| Inflexible | Programmable |
| Cost-expensive | Better resource abstraction |
| Limited coordination | Flow-table + controller coordination |

---

## CloudSim vs CloudAnalyst vs GreenCloud

| Tool | Main focus |
|---|---|
| **CloudSim** | General cloud simulation/modeling |
| **CloudAnalyst** | GUI + geographically distributed cloud applications |
| **GreenCloud** | Energy-aware data-center simulation |

---

## ODIN vs Ubi-Flow vs Mobi-Flow

| Approach | Key idea |
|---|---|
| **ODIN** | Agent/master + programmable WLAN/LVAP |
| **Ubi-Flow** | Mobility management, AP scalability, fault tolerance, flow scheduling |
| **Mobi-Flow** | Mobility prediction + proactive flow-rule placement |

---

# 79. MCQ/MSQ TRAPS

1. Traditional mobile problem → **static, over-provisioned, difficult to scale**.
2. ODIN agent → **physical/access-device side**.
3. Odin master → controller side.
4. Mobi-Flow → **predict future location**.
5. Mobi-Flow predictor → **order-K Markov**.
6. Mobi-Flow → proactive rule placement.
7. Mininet-WiFi → wired + wireless.
8. Wireless protocol in Mininet-WiFi lecture → **IEEE 802.11**.
9. ONOS → controller placement.
10. NIST cloud resource pool → **configurable computing resources**.
11. NIST essential characteristics → five.
12. Rapid elasticity → cloud characteristic.
13. Private cloud → one organization.
14. Public cloud example → AWS.
15. IaaS → infrastructure.
16. Hypervisor → multiple VMs on physical hardware.
17. PaaS → middleware/platform for developers.
18. SaaS → finished application.
19. SLA → non-functional requirements.
20. Accounting → usage records.
21. Billing → records + prices + billing rules.
22. Cloud simulator → repeatable pre-deployment evaluation.
23. CloudSim → Java.
24. CloudSim → CLOUDS Lab, University of Melbourne.
25. GreenCloud → energy-aware.
26. GreenCloud → NS2 extension.
27. OpenStack → open source.
28. Nova → compute.
29. Neutron → networking.
30. Cinder → block storage.
31. Keystone → identity.
32. Glance → image.
33. Swift → object storage.
34. Horizon → dashboard.
35. EC2 → compute instances.
36. EC2 billing → pay-per-use.
37. IAM → identity + permissions.
38. Data security objectives → confidentiality, integrity, availability.
39. IaaS security includes hypervisor concerns.
40. SaaS limitation → switching cost / limited flexibility / privacy.
41. Multi-cloud → multiple cloud services.
42. Inter-cloud → cloud of clouds.
43. Community cloud → shared concerns.
44. Distributed cloud → scattered devices connected to one network.

---

# 80. IMPORTANT NUMBERS / NAMES / DATES

| Item | Remember |
|---|---|
| Cloud NIST definition source version | **2009, version 15** |
| Cloud history – Salesforce.com | **1999** |
| Amazon Web Services | **2002** |
| Amazon EC2 | **2006** |
| Google App Engine / Azure milestone | **2008** |
| Mobi-Flow predictor | **Order-K Markov** |
| Wireless standard in Mininet-WiFi | **IEEE 802.11** |
| CloudSim language | **Java** |
| CloudSim institution | **CLOUDS Lab, University of Melbourne** |
| GreenCloud base | **NS2 extension** |
| OpenStack compute | **Nova** |
| OpenStack network | **Neutron** |
| OpenStack block storage | **Cinder** |
| OpenStack identity | **Keystone** |
| OpenStack image | **Glance** |
| OpenStack object storage | **Swift** |
| OpenStack dashboard | **Horizon** |

---

# 81. CODE/CONCEPT RECOGNITION DRILL

## If question says:
**“Predict user's next location and place rules beforehand.”**

→ **Mobi-Flow**

## If question says:
**“Agent at AP/physical device communicates with controller.”**

→ **ODIN / Odin agent**

## If question says:
**“Wired Ethernet + wireless IEEE 802.11 simulation.”**

→ **Mininet-WiFi**

## If question says:
**“On-demand access to shared configurable resources.”**

→ **Cloud computing / NIST**

## If question says:
**“Servers + storage + network + OS.”**

→ **IaaS**

## If question says:
**“Application middleware for developers.”**

→ **PaaS**

## If question says:
**“Completed application delivered over Internet.”**

→ **SaaS**

## If question says:
**“Multiple VMs share physical hardware.”**

→ **Hypervisor**

## If question says:
**“Non-functional service requirements.”**

→ **SLA**

## If question says:
**“Resource usage records.”**

→ **Service accounting**

## If question says:
**“Java cloud simulator from Melbourne.”**

→ **CloudSim**

## If question says:
**“Energy consumption of cloud data centers.”**

→ **GreenCloud**

---

# 82. VISUAL/DIAGRAM-BASED EXAM NOTES

## Week 8 PDF pages 6–7: SDWMN
The diagrams compare traditional mobile networking with software-defined mobile networking.

### What to see
- Traditional side → interference/problem in radio environment.
- SDN side → virtualized radio resource management + SDN controller + OpenFlow-enabled switches.

**Exam takeaway:** SDN can coordinate interference and mobile traffic management centrally.

---

## Week 8 PDF page 28: NIST Visual Model
The diagram groups cloud computing into:

### Essential characteristics
- Broad network access
- Rapid elasticity
- Measured services
- On-demand self-service
- Resource pooling

### Service models
- SaaS
- PaaS
- IaaS

### Deployment models
- Public
- Private
- Hybrid
- Community

**This diagram is extremely important for MCQs.**

---

## Week 8 PDF page 52: Service Model Comparison
The stack diagram visually shows who manages:
- applications,
- data,
- runtime,
- middleware,
- OS,
- virtualization,
- servers,
- storage,
- networking.

**Exam takeaway:** As you move from IaaS → PaaS → SaaS, the provider manages more layers.

---

## Week 8 PDF page 109: CloudSim Architecture
Three layers:
1. User Code
2. CloudSim
3. Core Simulation Engine

**Exam takeaway:** User defines scenarios; CloudSim models the environment; core engine handles events/entities/clock.

---

## Week 8 PDF page 120: OpenStack Components
The diagram/list contains:
- Nova,
- Neutron,
- Cinder,
- Keystone,
- Glance,
- Swift,
- Horizon,
- Trove,
- Sahara,
- Manila,
- Designate,
- Searchlight,
- Barbican.

**High-priority first seven:** Nova, Neutron, Cinder, Keystone, Glance, Swift, Horizon.

---

# 83. ONE-PAGE FINAL REVISION

## SDN FOR IoT
```text
Traditional mobile
→ difficult scale
→ difficult manage
→ inflexible
→ expensive

SDN mobile
→ flow-table
→ logically centralized control
→ path management
→ virtualization
```

### Approaches
```text
ODIN
→ agent + master
→ LVAP

Ubi-Flow
→ mobility management
→ fault tolerance
→ flow scheduling

Mobi-Flow
→ predict t+1
→ order-K Markov
→ proactive rule placement
→ lower overhead + energy
```

### Wireless experiment
```text
Mininet-WiFi
→ Ethernet + IEEE 802.11

ONOS
→ controller placement
```

---

## CLOUD
```text
Cloud
= on-demand
+ network access
+ shared pool
+ configurable resources
```

### Five NIST characteristics
```text
1. On-demand self-service
2. Broad network access
3. Resource pooling
4. Rapid elasticity
5. Measured service
```

### Service models
```text
IaaS → infrastructure
PaaS → platform
SaaS → software
```

### Deployment
```text
Public
Private
Hybrid
Community
```

---

## SERVICE MANAGEMENT
```text
SLA
→ non-functional requirements

Accounting
→ usage records

Billing
→ records + prices + rules
```

---

## SECURITY
```text
Network
Host
Application
```

Data security:
```text
Confidentiality
Integrity
Availability
```

IAM:
```text
Identity
Authentication
Authorization
Permissions
```

---

## SIMULATION
```text
CloudSim
→ Java
→ CLOUDS Lab / Melbourne
→ general cloud simulation

CloudAnalyst
→ CloudSim-based
→ GUI
→ geographically distributed applications

GreenCloud
→ energy-aware
→ NS2 extension
```

---

# 84. LAST-MINUTE 15-ANSWER DRILL

1. Traditional mobile network scaling problem?  
   **Static, over-provisioned network**

2. ODIN agent location?  
   **Physical/access devices**

3. Mobi-Flow goal?  
   **Predict future user location + proactive rules**

4. Wireless SDN simulator?  
   **Mininet-WiFi**

5. NIST shared pool?  
   **Configurable computing resources**

6. Essential characteristic?  
   **Rapid elasticity**

7. Single-organization cloud?  
   **Private cloud**

8. Public provider?  
   **AWS**

9. Infrastructure service?  
   **IaaS**

10. Multiple VMs on hardware?  
   **Hypervisor**

11. Middleware for developers?  
   **PaaS**

12. SLA purpose?  
   **Non-functional requirements**

13. Service accounting?  
   **Resource usage records**

14. CloudSim purpose?  
   **Reliable/scalable/repeatable pre-deployment evaluation**

15. CloudSim institution/language?  
   **CLOUDS Lab, University of Melbourne + Java**

---

# 85. EXAM STRATEGY

## Priority 1 — Memorize all 15 assignment answers
The assignment is a direct map of high-probability Week 8 concepts.

## Priority 2 — Memorize these 20 keywords

**SDN side**
1. Traditional mobile problems
2. ODIN agent
3. Odin master
4. LVAP
5. Ubi-Flow
6. Mobi-Flow
7. Order-K Markov
8. Mininet-WiFi
9. ONOS

**Cloud side**
10. NIST
11. Five characteristics
12. IaaS
13. PaaS
14. SaaS
15. Private cloud
16. Public cloud
17. SLA
18. Accounting
19. IAM
20. CloudSim

## Priority 3 — Master the comparisons
- IaaS vs PaaS vs SaaS.
- Public vs private vs hybrid.
- ODIN vs Ubi-Flow vs Mobi-Flow.
- CloudSim vs CloudAnalyst vs GreenCloud.
- Traditional mobile vs SDN mobile.

## Priority 4 — Memorize the visual models
Especially:
- NIST cloud model.
- Service-model responsibility stack.
- CloudSim architecture.
- OpenStack component list.
- SDWMN interference diagram.

---

# 86. FINAL MEMORY LINE

**Week 8 = Recent SDN advances + Cloud Computing:**  
**Traditional mobile = static/over-provisioned/difficult to scale; ODIN agent = physical side; Mobi-Flow = predict future location + proactive rules using order-K Markov; Mininet-WiFi = Ethernet + IEEE 802.11; NIST cloud = on-demand shared configurable resources; five characteristics = on-demand self-service, broad network access, resource pooling, rapid elasticity, measured service; IaaS = infrastructure, PaaS = platform, SaaS = software; hypervisor = multiple VMs; private = one organization; SLA = non-functional requirements; accounting = usage records; IAM = identity/access; CloudSim = Java + CLOUDS Lab University of Melbourne; GreenCloud = energy + NS2; OpenStack = open source.**
