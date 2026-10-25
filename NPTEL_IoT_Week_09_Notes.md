# NPTEL IoT – Week 9 Exam Notes (Improved)
## Assignment Priority + Complete Lecture Coverage + Mock-Exam Cross-Check

**Course:** Introduction to Internet of Things  
**Week:** 9  
**Exam style:** MCQ/MSQ  
**Priority:** Assignment first, then ALL Week 9 lecture/PPT topics, then cumulative mock-exam patterns.

> **Update rule:** The original Week 9 notes are preserved. This update adds only exam-relevant cross-checks and traps found in the uploaded cumulative mock exams. No images are generated or added.

# 1. WEEK 9 ULTRA-QUICK REVISION

## OpenStack
- OpenStack = open-source software for creating cloud infrastructure.
- Launched in **2010** as a joint project of **Rackspace Hosting + NASA**.
- Can be used for public or private clouds.
- **Horizon** → dashboard / GUI.
- **Nova** → compute / launch instances.
- **Glance** → image service.
- **Swift** → object storage.
- **Neutron** → networking.
- **Cinder** → block storage.
- **Heat** → orchestration.
- **Ceilometer** → billing/usage measurement in the lecture.
- **Keystone** → identity, authentication, authorization.
- DevStack installation → configure `local.conf`, then run `./stack.sh`.

## Sensor-Cloud
- More than simply combining WSN + cloud.
- Core idea → **virtualization of sensor nodes**.
- Pay-per-use.
- One physical sensor/network can appear as many virtual resources.
- Acts as a stratum between sensor nodes and end-users.
- Traditional WSN → dedicated to one WSN-user.
- Sensor-cloud → can serve multiple applications/users.
- Actors:
  - End-user
  - Sensor-owner
  - Sensor-Cloud Service Provider (SCSP)
- Traditional WSN responsibility:
  - WSN-user owns/deploys/redeploys/maintains/uses.
- Sensor-cloud:
  - Sensor-owner → ownership + deployment
  - SCSP → redeployment + maintenance + overhead
  - End-user → usage
- Virtual sensor:
  - **CoV-I** → homogeneous nodes, same geographical region.
  - **CoV-II** → heterogeneous nodes, multiple geographical regions → Virtual Sensor Group.
- Caching:
  - **IC (Internal Cache)** → handles end-user request and decides direct serving/re-cache from EC.
  - **EC (External Cache)** → periodically re-caches data.
- Adaptive caching saves energy when environmental conditions change slowly.
- Pricing:
  - `pH` → hardware/physical sensor-node usage.
  - `pI` → sensor-cloud infrastructure.
  - Goal → maximize SCSP profit + sensor-owner profit + end-user satisfaction.

## Fog Computing
- Term **fog computing/fogging** coined by **CISCO**.
- Extends cloud closer to IoT devices.
- Fog = intermediate layer between cloud and devices.
- Main cloud problems for IoT:
  - **Volume**
  - **Latency**
  - **Bandwidth**
- Fog nodes:
  - transient storage,
  - computing facility,
  - network connectivity.
- Fog nodes can be:
  - routers,
  - embedded servers,
  - switches,
  - video-surveillance cameras.
- Data processing:
  - Very time-sensitive → nearest fog node, fraction-of-second decision.
  - Less time-sensitive → aggregate fog node, seconds/minutes.
  - Non-time-sensitive → cloud, hours/days/weeks.
- Fog advantages:
  - lower latency,
  - lower bandwidth consumption,
  - better privacy,
  - local processing,
  - mobility support,
  - remote/harsh-environment deployment.
- Fog challenges:
  - power consumption,
  - distributed security,
  - reliability,
  - fault tolerance,
  - real-time analysis,
  - programming/scalability.

---

# 2. ASSIGNMENT-FIRST: ALL 15 QUESTIONS

## Q1. OpenStack was launched in 2010 as a joint project between Rackspace Hosting and which organization?

**Answer: C — NASA**

### Explanation
OpenStack is open-source cloud-infrastructure software. The lecture states that it was launched in **2010** as a joint project of **Rackspace Hosting and NASA**.

### Trap
Do not confuse the companies that later contributed to OpenStack with the original joint-project partners.

**Memory:** **2010 → Rackspace + NASA**

---

## Q2. Which OpenStack component provides the dashboard (GUI)?

**Answer: C — Horizon**

### Explanation
**Horizon** is the dashboard component:
- provides the GUI,
- gives an overview of other OpenStack components.

### Trap
- Keystone = identity/authentication/authorization.
- Nova = compute.
- Swift = object storage.

**Memory:** **Horizon = GUI**

---

## Q3. Which OpenStack component is the compute service where instances are launched?

**Answer: A — Nova**

### Explanation
**Nova** is OpenStack's compute service and is where instances are launched.

### Related components
- Glance → image service
- Cinder → block storage
- Neutron → networking

**Memory:** **Nova = compute**

---

## Q4. Which script/tool is used in the lecture to install OpenStack?

**Answer: A — `stack.sh` via DevStack**

### Installation flow
```text
Install git
   ↓
Clone DevStack
   ↓
cd devstack
   ↓
Configure local.conf
   ↓
./stack.sh
```

### Password/IP entries
The lecture shows:
- `ADMIN_PASSWORD`
- `DATABASE_PASSWORD`
- `RABBIT_PASSWORD`
- `SERVICE_PASSWORD`
- `HOST_IP`

### Uninstallation
```bash
./unstack.sh
```

### Trap
`stack.sh` is the script; **DevStack** is the installation/deployment toolset.

---

## Q5. What does sensor-cloud fundamentally provide beyond merely integrating sensors with cloud computing?

**Answer: B — Virtualization of sensor nodes, offered on a pay-per-use basis**

### Explanation
Sensor-cloud is **not** simply:
- connecting sensors to cloud,
- dumping sensor data into cloud.

Its key idea is:
- virtualize sensor nodes,
- provide virtualized sensing as a service,
- use pay-per-use access,
- act as a stratum between physical sensor nodes and end-users.

**Memory:** **Sensor-cloud = sensor virtualization + pay-per-use**

---

## Q6. In a traditional WSN, who is responsible for redeployment of sensor nodes?

**Answer: C — WSN-user**

### Traditional WSN
The WSN-user handles:
- ownership,
- deployment,
- redeployment,
- maintenance,
- overhead,
- usage.

### Sensor-cloud
Responsibilities shift:
- Sensor-owner → ownership/deployment
- SCSP → redeployment/maintenance/overhead
- End-user → usage

### Trap
Do not use SCSP for traditional WSN redeployment.

---

## Q7. In sensor-cloud, which actor purchases physical sensor devices and lends them to the sensor-cloud?

**Answer: B — Sensor-owner**

### Explanation
The sensor-owner:
- purchases physical sensor devices,
- deploys them over different geographical locations,
- lends them to the sensor-cloud,
- plays a business role.

### Memory
**Sensor-owner = owns physical sensors**

---

## Q8. Which is a major limitation of traditional WSNs motivating sensor-cloud?

**Answer: B — Difficulty adapting to a change of requirement**

### Example
A WSN designed for:
- agriculture

may later need to support:
- smart-home sensing.

That change can require:
- different sensor types,
- different deployment area,
- different topology,
- redesign/redeployment.

### Other traditional WSN issues
- procurement,
- price,
- selecting vendor,
- sensor types,
- deployment,
- maintenance,
- battery lifetime.

---

## Q9. In Optimal Composition of Virtual Sensors, what does CoV-I refer to?

**Answer: B — Composition of virtual sensors using only homogeneous nodes within the same geographic region**

### CoV-I
- homogeneous sensor nodes,
- same geographical boundary,
- form a Virtual Sensor (VS).

### CoV-II
- heterogeneous physical sensor nodes,
- different geographical locations,
- form a Virtual Sensor Group (VSG).

### Memory
**CoV-I = Same region + homogeneous**  
**CoV-II = Multiple regions + heterogeneous + VSG**

---

## Q10. Which cache handles end-user requests and decides whether to serve data directly or re-cache from another source?

**Answer: D — Internal Cache (IC)**

### Internal Cache
- receives end-user requests,
- decides whether data can be supplied directly,
- or whether it needs to re-cache from External Cache (EC).

### External Cache
- re-caches data after certain intervals,
- initially sends selected data toward IC.

**Memory:** **IC = user-facing decision point**

---

## Q11. Why is dynamic/adaptive data caching useful in sensor-cloud?

**Answer: D — Unnecessary sensing during slow environmental change wastes energy**

### Explanation
If the environment changes slowly:
- sensed data remains largely unchanged,
- repeated sensing is unnecessary,
- repeated sensing wastes sensor energy.

Adaptive caching can therefore reduce unnecessary sensing.

### Trap
Caching is not intended to remove virtualization or eliminate the sensor-owner.

---

## Q12. Which company coined the term "fog computing"?

**Answer: C — CISCO**

### Explanation
The Week 9 lecture explicitly states:
- fog computing/fogging was coined by **CISCO**,
- the idea is to extend cloud closer to IoT devices.

**Memory:** **Fog → CISCO**

---

## Q13. Which key issue with traditional cloud motivates fog computing?

**Answer: B — Volume, latency, and bandwidth limitations**

### Three-letter memory
**V-L-B**
- **Volume** → too much IoT data.
- **Latency** → cloud round trip can be too slow.
- **Bandwidth** → sending all IoT data to cloud consumes huge bandwidth.

### Trap
Do not choose “excess bandwidth.” Fog is motivated partly because bandwidth is insufficient for massive IoT traffic.

---

## Q14. Where is the fog layer positioned?

**Answer: B — Between the cloud and IoT devices**

### Architecture
```text
        Cloud
          ↑
          │
         Fog
          ↑
          │
       Devices
```

Fog:
- processes data closer to source,
- reduces latency,
- saves bandwidth,
- reduces cloud storage burden.

---

## Q15. Which is NOT a required characteristic of a fog node?

**Answer: D — Permanent, unlimited archival storage**

### Fog node requirements
1. **Transient storage**
2. **Computing facility**
3. **Network connectivity**

Permanent, unlimited archival storage belongs conceptually to the cloud, not as a required fog-node characteristic.

### Memory
**Fog = compute + transient storage + connectivity**

---

# 3. OPENSTACK – COMPLETE LECTURE COVERAGE

## 3.1 What is OpenStack?

OpenStack is:
- software for creating cloud infrastructure,
- open source,
- usable for public/private clouds,
- supported by a large community.

### Important history
- **2010**
- Rackspace Hosting + NASA
- later many organizations contributed.

Examples listed in the lecture:
- IBM
- Cisco
- HP
- Dell
- VMware
- Red Hat
- SUSE
- Rackspace Hosting

---

# 4. OPENSTACK COMPONENTS

## Keystone
**Identity service**

Provides:
- authentication,
- authorization.

### Memory
**Keystone = identity**

---

## Horizon
**Dashboard**

Provides:
- GUI,
- overview of other components.

### Assignment connection
Q2 → Horizon.

---

## Nova
**Compute service**

Used to:
- launch instances.

### Assignment connection
Q3 → Nova.

---

## Glance
**Image service**

Used for:
- discovering,
- registering,
- retrieving VM images,
- snapshots.

### Memory
**Glance = images**

---

## Swift
**Object storage**

Used for:
- safe,
- cheap,
- efficient data storage.

### Memory
**Swift = objects**

---

## Neutron
**Networking service**

Provides:
- networking,
- communication between services,
- user-created networks.

### Memory
**Neutron = network**

---

## Cinder
**Block storage**

Virtualizes management of block storage.

### Memory
**Cinder = blocks**

---

## Heat
**Orchestration**

Used to coordinate/deploy resources according to defined templates/workflows.

### Memory
**Heat = orchestration**

---

## Ceilometer
The lecture associates Ceilometer with:
- billing,
- what service is being used,
- how long it is being used.

### Memory
**Ceilometer = usage/billing measurement in this lecture**

---

# 5. OPENSTACK COMPONENT MEMORY TABLE

| Component | Remember |
|---|---|
| Keystone | Identity, authentication, authorization |
| Horizon | Dashboard / GUI |
| Nova | Compute / instances |
| Glance | Images / VM images / snapshots |
| Swift | Object storage |
| Neutron | Networking |
| Cinder | Block storage |
| Heat | Orchestration |
| Ceilometer | Billing / usage measurement |

### Highest-priority seven
**Nova – Glance – Swift – Neutron – Cinder – Keystone – Horizon**

---

# 6. OPENSTACK INSTALLATION WITH DEVSTACK

## Steps

### 1. Install Git
```bash
sudo apt-get install git
```

### 2. Clone DevStack
```bash
git clone https://git.openstack.org/openstack-dev/devstack
```

### 3. Enter directory
```bash
cd devstack
```

### 4. Configure `local.conf`

The lecture shows:
```text
ADMIN_PASSWORD=<YOUR PASSWORD>
DATABASE_PASSWORD=<YOUR PASSWORD>
RABBIT_PASSWORD=<YOUR PASSWORD>
SERVICE_PASSWORD=<YOUR PASSWORD>
HOST_IP=<the IP of your PC>
```

### 5. Install
```bash
./stack.sh
```

### 6. Uninstall
```bash
./unstack.sh
```

### Assignment trap
Question asks for the **script/tool** used to install OpenStack:
- Tool → **DevStack**
- Script → **`stack.sh`**

---

# 7. SENSOR-CLOUD – INTRODUCTION

## 7.1 What sensor-cloud is NOT

Sensor-cloud is not merely:
- integration of sensor networks and cloud computing,
- dumping sensor data into cloud.

## 7.2 Core idea

Sensor-cloud provides:
- virtualization of sensor nodes,
- pay-per-use,
- one physical sensor/network appearing as many virtual resources,
- a stratum between sensor nodes and end-users.

### Mental model

```text
Physical Sensor Nodes
        ↓
Sensor-Cloud / Virtualization
        ↓
Virtual Sensors / Services
        ↓
Multiple End-Users / Applications
```

---

# 8. WSN RECAP

A Wireless Sensor Network contains sensor nodes that:
- sense physical phenomena,
- communicate sensed data wirelessly,
- send data toward a sink,
- may use single-hop or multi-hop communication,
- have a sink that further processes data.

## Major sensor-node components
- Sensing unit
- Processing unit
- Communication unit

## Applications
- Target tracking
- Wildlife monitoring
- Healthcare
- Industrial applications
- Smart home
- Smart city
- Agriculture

---

# 9. CLOUD COMPUTING RECAP

Cloud computing:
- provides on-demand computing resources.

Advantages from the lecture:
- **Elasticity** → scale up/down.
- **Pay-per-use** → pay according to resource requirement.
- **Self-service** → resources can be accessed by the user.

## Service models
- SaaS
- PaaS
- IaaS

---

# 10. SENSOR-CLOUD VS TRADITIONAL WSN

| Attribute | Traditional WSN | Sensor-cloud |
|---|---|---|
| User scope | Dedicated to single user | Multiple applications/users |
| Ownership | WSN-user | Sensor-owner |
| Deployment | WSN-user | Sensor-owner |
| Redeployment | WSN-user | SCSP |
| Maintenance | WSN-user | SCSP |
| Overhead | WSN-user | SCSP |
| Usage | WSN-user | End-user |

### High-priority
The **actor/role table** is a very likely MCQ source.

---

# 11. SENSOR-CLOUD ACTORS

## End-user
- enjoys Sensor-as-a-Service,
- selects applications/templates according to requirements,
- does not need to know which physical sensor is allocated.

## Sensor-owner
- business actor,
- purchases physical sensor devices,
- deploys them geographically,
- lends them to sensor-cloud.

## Sensor-Cloud Service Provider (SCSP)
- business/managerial actor,
- manages sensor-cloud infrastructure,
- charges end-users according to Se-aaS usage.

---

# 12. SENSOR-CLOUD ARCHITECTURE

## End-users
- register,
- select templates,
- request applications.

## Sensor-owner
Deploys:
- heterogeneous/homogeneous physical sensor nodes,
- at different geographic locations.

## SCSP
- managerial role.

### Important architecture concepts
- Web portal
- Browser interface
- XML interpretation
- Template specification
- Dynamic scaling
- On-demand physical sensor scheduling
- Vast data storage
- Specialized processing
- Energy management
- QoS
- Application-specific real-time data aggregation
- On-demand sensor data

---

# 13. SENSOR-CLOUD WORKFLOW

Important components:

```text
User Organization
      ↓
SensorML Interpreter
      ↓
Virtual Sensor Manager
      ↓
Virtual Sensor Controller
      ↓
Resource Manager
      ↓
Sensor Resource Pool / WSN
```

## Operations
- Request
- Create virtual sensor instance
- Manage operations
- Data aggregation
- Data retrieval
- Sensor scheduling
- Allocation
- Deallocation
- Delete virtual sensor
- Release instance
- Release resource

## Metadata/templates
The resource manager can work with:
- physical sensor definition,
- virtual sensor group definition,
- client information,
- metadata,
- templates.

---

# 14. SENSOR-CLOUD CASE STUDY: TARGET TRACKING

### Traditional WSN problem
If a WSN owner refuses to share sensing information:
- another organization must deploy its own WSN,
- long-term investment is required,
- setup and maintenance are expensive.

### Sensor-cloud solution
The organization can:
- use the same tracking application,
- obtain the tracking service,
- without owning the WSN.

### Exam idea
**Sensor-cloud converts ownership-heavy WSN deployment into service-based sensing.**

---

# 15. SENSOR-CLOUD MANAGEMENT ISSUES

Three major management issues:

1. **Optimal composition of virtual sensor nodes**
2. **Data caching**
3. **Optimal pricing**

These are the major Part II topics.

---

# 16. OPTIMAL COMPOSITION OF VIRTUAL SENSORS

## Why needed?
- sensor nodes are resource constrained,
- sensor conditions can change dynamically,
- virtual-sensor composition is non-traditional.

---

# 17. CoV-I

**Composition of Virtual Sensor – I**

### Conditions
- homogeneous sensor nodes,
- within the same geographical boundary.

### Output
Formation of a **Virtual Sensor (VS)**.

```text
Homogeneous nodes
   + same region
        ↓
       VS
```

### Assignment
Q9 → **CoV-I = homogeneous + same region**

---

# 18. CoV-II

**Composition of Virtual Sensor – II**

### Conditions
- heterogeneous physical sensor nodes,
- across different geographical locations.

### Output
**Virtual Sensor Group (VSG)**.

```text
Heterogeneous nodes
+ multiple regions
        ↓
       VSG
```

### Assignment trap
CoV-II is NOT the same as CoV-I.

---

# 19. DYNAMIC AND ADAPTIVE DATA CACHING

## Why caching?

End-users request sensed information through a web interface.

Meanwhile:
- physical sensors continuously sense,
- data is transmitted to sensor-cloud,
- virtualization and sensor allocation consume resources.

If environmental change is slow:
- data remains largely unchanged,
- repeated sensing is wasteful,
- energy is unnecessarily consumed.

### Goal
Use cached data when appropriate instead of repeatedly sensing unchanged conditions.

---

# 20. INTERNAL CACHE (IC)

The **Internal Cache**:
- handles end-user requests,
- checks whether cached data can be served,
- decides whether to return data directly,
- or re-cache from External Cache.

### Memory
**IC = interacts with end-user request**

---

# 21. EXTERNAL CACHE (EC)

The **External Cache**:
- re-caches data after a certain interval,
- supplies data toward IC.

### Memory
**EC = periodic upstream re-cache**

---

# 22. CACHE ARCHITECTURE

### Existing architecture
Applications → sensor-cloud resource pool.

### Cache-enabled architecture
Applications → sensor-cloud → **IC + EC** → resource pool.

### Key benefit
Reduced unnecessary sensing/resource consumption.

---

# 23. DYNAMIC OPTIMAL PRICING

The lecture discusses pricing for heterogeneous Sensor-Cloud infrastructure.

## Existing issue
Traditional pricing schemes often assume homogeneous service types such as:
- IaaS,
- SaaS.

The lecture highlights the absence of an equivalent scheme for **Se-aaS**.

---

# 24. TWO PRICING COMPONENTS

## Hardware price: `pH`
Deals with:
- usage of physical sensor nodes.

## Infrastructure price: `pI`
Deals with:
- sensor-cloud infrastructure price.

### Goals
Maximize:
- SCSP profit,
- sensor-owner profit,
- end-user satisfaction.

### Memory
**pH = hardware; pI = infrastructure**

---

# 25. FOG COMPUTING – INTRODUCTION

## Definition
Fog computing, or fogging:
- term coined by **CISCO**,
- extends cloud nearer to IoT devices,
- creates an intermediate layer between cloud and devices.

### Architecture

```text
Cloud
  ↑
Fog
  ↑
IoT Devices
```

### Assignment
Q12 + Q14 directly test this.

---

# 26. WHY FOG COMPUTING?

IoT generates enormous amounts of data.

The lecture highlights:
- huge data volume,
- time-sensitive decisions,
- massive bandwidth requirements.

The current cloud model is insufficient for all IoT requirements.

### Three core problems
**Volume + Latency + Bandwidth**

---

# 27. IMPORTANT LECTURE NUMBERS

The lecture contains historical projections such as:
- 40% of world data from sensors alone by 2020.
- 90% of world data generated during the previous two years.
- 2.5 quintillion bytes/day.
- IoT expenditure of $1.7 trillion by 2020.
- 250 million connected vehicles by 2020.
- more than 30 billion IoT devices.
- another slide uses an approximately 50-billion-device projection by 2020.

### Exam advice
These numbers are lecture-specific projections. If an MCQ quotes one, match it to the lecture wording rather than applying today's real-world numbers.

---

# 28. FOG PROBLEM 1 — DATA VOLUME

IoT devices:
- generate huge amounts of data,
- increase device density,
- can produce exabytes of data.

Cloud problems:
- processing burden,
- storage burden.

### Solution
Filter/process data closer to the source before sending everything to cloud.

---

# 29. FOG PROBLEM 2 — LATENCY

### Definition
Latency is the time associated with data communication, including the **round-trip** concept emphasized in the lecture.

### Why it matters
For time-sensitive applications:
- cloud analysis can take too long,
- an action may arrive after the dangerous event.

### Example
If a device needs an immediate decision:
```text
Device → Cloud → Analysis → Action → Device
```

The delay may be unacceptable.

### Fog solution
```text
Device → Nearby Fog → Immediate Action
```

---

# 30. FOG PROBLEM 3 — BANDWIDTH

If all IoT data is sent to cloud:
- traffic becomes enormous,
- available bandwidth can be heavily consumed.

### Fog solution
Process/filter/summarize data locally and send only useful information upward.

---

# 31. OTHER REASONS FOR FOG

The lecture also highlights:
- confidential data may not be desirable to send online,
- data should be processed at an appropriate location,
- geographically distributed devices require local coordination.

---

# 32. REQUIREMENTS OF IoT THAT FOG ADDRESSES

## 1. Reduce latency
Analyze close to data source.

## 2. Data security
- protect IoT data,
- monitor continuously,
- take action before attacks cause major harm.

## 3. Operation reliability
- integrity,
- availability,
- uninterrupted use of important IoT data.

## 4. Process at the suitable place
Data has different time sensitivities.

## 5. Monitor large geographical areas
Examples:
- railway tracks across a state/country,
- harsh environments.

---

# 33. THREE TYPES OF IoT DATA

## Type 1 — Very time-sensitive
Must be analyzed:
- near the data source,
- within a fraction of a second.

## Type 2 — Less time-sensitive
Can be analyzed:
- after seconds or minutes.

Use:
- aggregate fog node.

## Type 3 — Non-time-sensitive
Can wait:
- hours,
- days,
- weeks.

Send to:
- cloud.

### Golden rule
**The more time-sensitive the data, the closer processing should be to the device.**

---

# 34. WHEN SHOULD WE USE FOG?

Use fog when:
- data must be analyzed within a fraction of a second,
- there are huge numbers of devices,
- devices are spread over large geographical distances,
- devices operate in extreme/harsh conditions.

---

# 35. FOG ARCHITECTURE

## Core idea
Fog extends cloud services to IoT devices.

Fog:
- lies between cloud and devices,
- can contain many fog nodes,
- processes sensor data before cloud transmission.

### Benefits
- lower latency,
- bandwidth savings,
- cloud-storage savings.

---

# 36. FOG NODE CHARACTERISTICS

A fog node needs:

## 1. Storage
**Transient storage**

Not unlimited permanent archival storage.

## 2. Computing facility
Used to:
- process data,
- take quick decisions.

## 3. Network connectivity
Connects:
- IoT devices,
- other fog nodes,
- cloud.

### Assignment
Q15 tests this directly.

---

# 37. EXAMPLES OF FOG NODES

The lecture gives examples:
- routers,
- embedded servers,
- switches,
- video-surveillance cameras.

### Important
Fog nodes can be:
- deployed anywhere inside the network,
- arranged with aggregate fog nodes.

---

# 38. WORKING OF FOG

## Step 1
Nearest fog node **ingests data** from devices.

## Step 2
Classify data by time sensitivity.

### Very time-sensitive
- analyze at nearest fog node,
- take immediate action,
- send summary to cloud for historical analysis/storage.

### Less time-sensitive
- send to aggregate fog node,
- analyze there,
- send action back through nearest fog node,
- send summary to cloud.

### Non-time-sensitive
- send to cloud,
- store for future analysis.

---

# 39. FOG PROCESSING HIERARCHY

| Location | Analysis duration | Storage duration | Geographic coverage |
|---|---|---|---|
| Nearest fog node | Fraction of second | Transient | Very local |
| Aggregate fog node | Seconds to minutes | Hours/days | Wider |
| Cloud | Hours to weeks | Months/years | Global |

### Very important
This table is one of the best ways to solve scenario-based MCQs.

---

# 40. FOG ADVANTAGES

## Security
- better security,
- same security policy can be used by fog nodes.

## Low operation cost
- local processing,
- lower bandwidth consumption.

## Accident reduction
- lower latency,
- quick decisions.

## Better privacy
- local industry data can be analyzed locally,
- confidential information can remain local,
- only shareable information goes to cloud.

## Business agility
Fog applications can:
- be developed with available tools,
- be deployed where needed,
- be programmed according to customer requirements.

## Mobility support
- fog nodes can be mobile,
- nodes can join/leave the network.

## Remote/harsh deployment
Possible in:
- undersea environments,
- railway tracks,
- vehicles,
- factory floors.

## Better data handling
- less bandwidth,
- local analysis,
- lower latency risk.

---

# 41. FOG APPLICATIONS

## 1. Real-time health analysis
Examples:
- chronic illness monitoring,
- stroke patients.

Features:
- real-time analysis,
- emergency alerts to doctors,
- historical data can help predict future danger.

---

## 2. Intelligent power-efficient systems
Fog can:
- monitor power consumption,
- produce daily power reports,
- suggest economical power-use plans.

---

## 3. Real-time railway monitoring
Fog nodes can be deployed along railway tracks.

Benefits:
- real-time track monitoring,
- fast analysis,
- improved safety/reliability,
- useful for high-speed trains where cloud round-trip is inefficient.

---

## 4. Pipeline optimization
Gas/oil pipelines require monitoring of:
- pressure,
- flow,
- compressors.

Problems:
- huge data volume,
- cloud processing delay,
- unacceptable latency.

Fog enables local processing.

---

## 5. Windmill/turbine analysis
Real-time analysis of:
- wind direction,
- wind speed.

Can improve:
- monitoring,
- power output.

---

# 42. FOG CHALLENGES

## 1. Power consumption
Adding fog nodes increases energy consumption compared with a centralized cloud.

## 2. Data security
Distributed data-generating nodes make security harder.

## 3. Reliability
Need:
- authentication,
- authorization,
- data integrity,
- availability,
- resilience to node failures.

## 4. Fault tolerance
Failure of an individual node should:
- be fixed quickly,
- not affect the whole system.

## 5. Real-time analysis
Real-time processing is required to:
- minimize latency,
- reduce danger,
- improve output.

But monitoring huge numbers of nodes is difficult.

## 6. Programming architecture
Fog nodes may:
- move,
- join,
- leave.

Static processing frameworks may not provide sufficient:
- scalability,
- flexibility.

---

# 43. FOG VS CLOUD

| Cloud | Fog |
|---|---|
| Farther from devices | Nearer to devices |
| Global processing/storage | Local/intermediate processing |
| Higher round-trip latency | Lower latency |
| Large centralized storage | Transient/local storage |
| Good for non-time-sensitive data | Good for time-sensitive data |
| Global coverage | Local/wider intermediate coverage |
| More bandwidth needed for raw IoT data | Reduces bandwidth by local processing |

### One-line memory
**Cloud = global + long-term; Fog = local + fast.**

---

# 44. FOG VS EDGE

For this lecture, remember the operational idea rather than overcomplicating terminology:

- Fog places a computing layer between devices and cloud.
- It can contain many intermediate nodes.
- It emphasizes distributed/local processing and coordination.
- Edge computing is a broader related idea of processing near the source.

For NPTEL Week 9, prioritize the **Cloud → Fog → Device** model used in the slides.

---

# 45. VISUAL/DIAGRAM-BASED EXAM NOTES

## Assignment/lecture diagram: Cloud–Fog–Device
The early fog diagram shows:

```text
Cloud
  ↓
Fog
  ↓
Device
```

**Exam meaning:** Fog is the intermediate layer.

---

## Fog working diagram
The Week 9 lecture's working diagram shows:
- devices ingest data into the nearest fog node,
- immediate action for highly time-sensitive data,
- less time-sensitive data moving toward an aggregate fog node,
- summaries sent to cloud,
- non-time-sensitive data sent to cloud.

**Exam meaning:** Processing location depends on time sensitivity.

---

## Sensor-cloud architecture
The sensor-cloud architecture diagram shows:
- end-user applications,
- web portal/browser,
- templates,
- dynamic scaling,
- on-demand sensor scheduling,
- heterogeneous sensor pool,
- real-time data aggregation,
- QoS/energy management.

**Exam meaning:** Sensor-cloud hides the complexity of physical sensor allocation from end-users.

---

## Sensor-cloud workflow
The workflow diagram connects:
- User organization,
- SensorML interpreter,
- Virtual Sensor Manager,
- Virtual Sensor Controller,
- Resource Manager,
- physical sensor resource pool.

**Exam meaning:** Requests are translated into virtual-sensor operations and physical resource allocation.

---

## OpenStack architecture diagram
The OpenStack component visual groups:
- Horizon/dashboard,
- Nova,
- Glance,
- Swift,
- Neutron,
- Cinder,
- Heat,
- Ceilometer,
- Keystone.

**Exam meaning:** Learn the function of each named component.

---

# 46. HIGH-PRIORITY COMPARISONS

## OpenStack components

| Component | Function |
|---|---|
| Horizon | GUI/dashboard |
| Nova | Compute |
| Glance | Images |
| Swift | Object storage |
| Neutron | Network |
| Cinder | Block storage |
| Heat | Orchestration |
| Ceilometer | Billing/usage measurement |
| Keystone | Identity/authentication/authorization |

---

## WSN vs Sensor-cloud

| WSN | Sensor-cloud |
|---|---|
| Single-user orientation | Multiple applications/users |
| User owns sensors | Sensor-owner owns sensors |
| User deploys | Sensor-owner deploys |
| User redeploys | SCSP redeploys |
| User maintains | SCSP maintains |
| User bears overhead | SCSP bears overhead |
| User consumes data | End-user consumes service |
| Fixed/dedicated resource | Virtualized resource |

---

## CoV-I vs CoV-II

| CoV-I | CoV-II |
|---|---|
| Homogeneous nodes | Heterogeneous nodes |
| Same geographic region | Multiple regions |
| Virtual Sensor (VS) | Virtual Sensor Group (VSG) |

---

## IC vs EC

| Internal Cache | External Cache |
|---|---|
| Handles end-user request | Periodically re-caches |
| Decides direct serving vs re-cache | Supplies refreshed data |
| User-facing cache logic | Upstream/external cache |

---

## Fog vs Cloud

| Fog | Cloud |
|---|---|
| Near devices | Remote/global |
| Low latency | Higher round-trip delay |
| Local processing | Centralized/global processing |
| Transient storage | Long-term storage |
| Time-sensitive decisions | Non-time-sensitive analysis |
| Saves bandwidth | Raw-data transfer can consume bandwidth |

---

# 47. MCQ/MSQ TRAPS

1. OpenStack launched in 2010 → **Rackspace + NASA**.
2. Horizon → **dashboard/GUI**.
3. Nova → **compute/instances**.
4. Glance → image service.
5. Swift → object storage.
6. Neutron → networking.
7. Cinder → block storage.
8. Keystone → identity/authentication/authorization.
9. Heat → orchestration.
10. Ceilometer → billing/usage measurement in lecture.
11. OpenStack install → **DevStack + `stack.sh`**.
12. Sensor-cloud ≠ simply dumping data into cloud.
13. Sensor-cloud key concept → **sensor-node virtualization**.
14. Sensor-cloud → **pay-per-use**.
15. Traditional WSN redeployment → WSN-user.
16. Sensor-owner → purchases/lends physical sensors.
17. SCSP → managerial/service provider role.
18. CoV-I → homogeneous + same region.
19. CoV-II → heterogeneous + multiple regions.
20. IC → handles end-user requests.
21. EC → periodic re-cache.
22. Adaptive caching → saves energy when environment changes slowly.
23. Fog term → **CISCO**.
24. Fog layer → **between cloud and devices**.
25. Fog motivation → **volume + latency + bandwidth**.
26. Fog node storage → **transient**, not unlimited permanent storage.
27. Fog node must compute for quick decisions.
28. Very time-sensitive → nearest fog.
29. Less time-sensitive → aggregate fog.
30. Non-time-sensitive → cloud.
31. Fog reduces latency and bandwidth consumption.
32. Fog can improve privacy by local processing.
33. Fog can support mobile nodes.
34. Fog challenge → higher power consumption due to extra nodes.
35. Fog security is harder because nodes are distributed.
36. Fog fault tolerance → individual node failure should not collapse the whole scenario.

---

# 48. IMPORTANT NUMBERS / NAMES / COMMANDS

| Item | Remember |
|---|---|
| OpenStack launch | **2010** |
| OpenStack original partners | **Rackspace + NASA** |
| Git install | `sudo apt-get install git` |
| DevStack clone | `git clone https://git.openstack.org/openstack-dev/devstack` |
| Enter directory | `cd devstack` |
| Install | `./stack.sh` |
| Uninstall | `./unstack.sh` |
| Fog term coined by | **CISCO** |
| Fog location | **Cloud ↔ Fog ↔ Device** |
| CoV-I | Same region + homogeneous |
| CoV-II | Multiple regions + heterogeneous |
| IC | Internal Cache |
| EC | External Cache |
| pH | Hardware/physical sensor-node price |
| pI | Infrastructure price |
| Fog very time-sensitive | Fraction of second |
| Fog less time-sensitive | Seconds/minutes |
| Fog non-time-sensitive | Hours/days/weeks |

---

# 49. CODE/CONCEPT RECOGNITION DRILL

## If question says:
**“OpenStack GUI/dashboard.”**

→ **Horizon**

## If question says:
**“Launch cloud instances.”**

→ **Nova**

## If question says:
**“Identity + authentication + authorization.”**

→ **Keystone**

## If question says:
**“Object storage.”**

→ **Swift**

## If question says:
**“Block storage.”**

→ **Cinder**

## If question says:
**“Networking service.”**

→ **Neutron**

## If question says:
**“OpenStack installation script.”**

→ **`stack.sh`**

## If question says:
**“Virtualize physical sensor nodes and provide pay-per-use sensing.”**

→ **Sensor-cloud**

## If question says:
**“Homogeneous sensors in same region.”**

→ **CoV-I**

## If question says:
**“Heterogeneous sensors across multiple regions.”**

→ **CoV-II / VSG**

## If question says:
**“End-user request cache.”**

→ **Internal Cache**

## If question says:
**“Term coined by CISCO.”**

→ **Fog computing**

## If question says:
**“Intermediate layer between cloud and IoT devices.”**

→ **Fog**

## If question says:
**“Fraction-of-second analysis.”**

→ **Nearest fog node**

## If question says:
**“Hours/days/weeks delay is acceptable.”**

→ **Cloud**

---

# 50. ONE-PAGE FINAL REVISION

## OPENSTACK

```text
2010
Rackspace + NASA
        ↓
OpenStack
```

### Components
```text
Keystone  → Identity
Horizon   → Dashboard
Nova      → Compute
Glance    → Image
Swift     → Object
Neutron   → Network
Cinder    → Block
Heat      → Orchestration
Ceilometer→ Billing/usage
```

### Install
```text
git
 ↓
clone DevStack
 ↓
cd devstack
 ↓
local.conf
 ↓
./stack.sh
```

---

## SENSOR-CLOUD

```text
Physical Sensors
       ↓
Virtualization
       ↓
Sensor-cloud
       ↓
Multiple applications/users
```

### Actors
```text
Sensor-owner → owns/deploys
SCSP         → redeploys/maintains/manages
End-user     → uses service
```

### Composition
```text
CoV-I
→ homogeneous
→ same region
→ VS

CoV-II
→ heterogeneous
→ multiple regions
→ VSG
```

### Caching
```text
End-user
   ↓
IC
   ↓
EC / sensor data
```

---

## FOG

```text
Cloud
  ↑
Fog
  ↑
Devices
```

### Why?
```text
Volume
Latency
Bandwidth
```

### Processing
```text
Very time-sensitive
→ nearest fog
→ fraction second

Less time-sensitive
→ aggregate fog
→ seconds/minutes

Non-time-sensitive
→ cloud
→ hours/days/weeks
```

### Fog node
```text
Transient storage
+ Computing
+ Network connectivity
```

### Advantages
```text
Low latency
Bandwidth saving
Privacy
Quick decisions
Mobility
Remote deployment
```

### Challenges
```text
Power
Security
Reliability
Fault tolerance
Real-time monitoring
Scalability/flexible programming
```

---

# 51. LAST-MINUTE 15-ANSWER DRILL

1. OpenStack's original joint-project partner with Rackspace?  
   **NASA**

2. OpenStack dashboard?  
   **Horizon**

3. OpenStack compute service?  
   **Nova**

4. OpenStack installation script?  
   **`stack.sh` via DevStack**

5. Sensor-cloud's key innovation?  
   **Virtualization of sensor nodes + pay-per-use**

6. Traditional WSN redeployment responsibility?  
   **WSN-user**

7. Physical sensor purchaser/lender?  
   **Sensor-owner**

8. CoV-I?  
   **Homogeneous nodes in same geographic region**

9. End-user cache?  
   **Internal Cache (IC)**

10. Why adaptive caching?  
    **Avoid unnecessary sensing/energy consumption**

11. Fog term coined by?  
    **CISCO**

12. Main cloud limitations motivating fog?  
    **Volume, latency, bandwidth**

13. Fog layer location?  
    **Between cloud and IoT devices**

14. Fog-node storage type?  
    **Transient**

15. Very time-sensitive data should be processed where?  
    **Nearest fog node**

---

# 52. EXAM STRATEGY

## Priority 1 — Memorize all 15 assignment answers
These are the highest-probability Week 9 concepts.

## Priority 2 — Memorize the role tables
Especially:
- OpenStack components.
- WSN vs sensor-cloud actors.
- CoV-I vs CoV-II.
- IC vs EC.
- Fog processing hierarchy.

## Priority 3 — Memorize the three fog keywords
**Volume – Latency – Bandwidth**

## Priority 4 — Memorize scenario logic
- Need GUI → Horizon.
- Need compute instance → Nova.
- Need image → Glance.
- Need object storage → Swift.
- Need network → Neutron.
- Need block storage → Cinder.
- Need identity → Keystone.
- Need homogeneous same-region virtual sensor → CoV-I.
- Need heterogeneous multi-region sensor group → CoV-II.
- Need end-user cache decision → IC.
- Need fraction-of-second action → nearest fog.
- Need long-term/global analysis → cloud.

---

# 53. FINAL MEMORY LINE

**Week 9 = OpenStack + Sensor-Cloud + Fog Computing:**  
**OpenStack 2010 = Rackspace + NASA; Horizon = dashboard; Nova = compute; DevStack `stack.sh` = installation; Sensor-cloud = sensor-node virtualization + pay-per-use; WSN-user owns/deploys/redeploys/maintains traditional WSN; Sensor-owner owns/deploys physical sensors in sensor-cloud; SCSP manages/redeploys/maintains; CoV-I = homogeneous same-region VS; CoV-II = heterogeneous multi-region VSG; IC = end-user cache; EC = periodic re-cache; adaptive caching saves energy; Fog = CISCO + intermediate cloud/device layer; motivation = Volume + Latency + Bandwidth; very time-sensitive data → nearest fog; less time-sensitive → aggregate fog; non-time-sensitive → cloud; fog node = transient storage + compute + connectivity.**


---

# 54. UPDATE — CUMULATIVE MOCK-EXAM CROSS-CHECK

This section is based on the uploaded cumulative Mock Exams 1–5. It does **not** replace the Week 9 assignment or lecture notes above. It identifies which Week 9 ideas are repeatedly tested and how the mock questions phrase the traps.

## 54.1 Highest-Priority Mock-Exam Patterns

### A. Fog computing is repeatedly tested

Across the mocks, the same three ideas recur:

1. **Latency**
   - Fog processes data closer to the source.
   - This reduces the round-trip delay for time-sensitive IoT applications.
   - Mock wording: *main advantage of fog over traditional cloud for time-sensitive applications* → **reduced latency**.

2. **Bandwidth**
   - Fog can **filter, aggregate, and preprocess** data locally.
   - Only relevant/summarized information needs to be sent to the cloud.
   - Mock wording: *how fog addresses cloud-centric bandwidth limitations* → **local filtering/aggregation/preprocessing**.

3. **Different time-sensitivity classes**
   - **Very time-sensitive** → nearest fog node → immediate action.
   - **Less time-sensitive** → aggregate fog node → analysis in seconds/minutes.
   - **Non-time-sensitive** → cloud → long-term storage/future analysis.

### B. Sensor-Cloud pricing is a hard-trap area

The mocks repeatedly ask the distinction:

- **PH / pH** → pricing attributed to **hardware**, i.e. use of physical sensor nodes.
- **PI / pI** → pricing attributed to **infrastructure**, i.e. underlying sensor-cloud infrastructure.

Do not confuse:
- PH with “price per hour”.
- PI with “processing intensity”.
- Sensor-owner payment with infrastructure payment.

The lecture's stated goals of the pricing scheme are:
- maximize SCSP profit,
- maximize sensor-owner profit,
- maintain end-user satisfaction.

The lecture also explains why a dedicated sensor-cloud pricing model is useful: the service involves heterogeneous physical sensor hardware and infrastructure, unlike ordinary homogeneous cloud-service assumptions.

### C. Internal Cache vs External Cache

Mock wording repeatedly targets this exact distinction:

| Component | What to remember |
|---|---|
| **Internal Cache (IC)** | Handles end-user requests; decides whether to serve directly or re-cache from EC |
| **External Cache (EC)** | Re-caches/refreshes data at intervals; supplies data toward IC |

**Trap:** IC is NOT simply “real-time cache” and EC is NOT simply “historical cache.”

### D. Cloud service-model recognition still appears

Although the main focus of Week 9 is OpenStack + Sensor-Cloud + Fog, the cumulative mocks still test:

- **IaaS** → infrastructure resources.
- **PaaS** → platform for developing/running applications.
- **SaaS** → ready-to-use software/application over the Internet.

**Trap:** If the question says “ready-to-use application hosted by provider,” answer **SaaS**, not PaaS.

### E. OpenStack role recognition

The Week 9 assignment itself is the strongest source for OpenStack, and the exam-style pattern is a direct role-matching question:

| If the question asks for... | Answer |
|---|---|
| Dashboard / GUI | **Horizon** |
| Compute / launch instances | **Nova** |
| VM image service | **Glance** |
| Object storage | **Swift** |
| Networking | **Neutron** |
| Block storage | **Cinder** |
| Orchestration | **Heat** |
| Identity / authentication / authorization | **Keystone** |
| Billing / usage measurement in the lecture | **Ceilometer** |

---

# 55. MOCK-EXAM QUESTION → ANSWER LOCK

## Fog

### Mock pattern 1
**Question:** What is the main advantage of fog computing over traditional cloud computing for time-sensitive IoT applications?

**Answer:** **Reduced latency by processing data closer to the source.**

**Trap:** Fog does not eliminate centralized/cloud processing. It complements cloud by moving suitable processing closer to devices.

### Mock pattern 2
**Question:** How does fog address cloud-centric bandwidth limitations?

**Answer:** **Filtering, aggregating, and preprocessing data locally, then sending relevant/summarized information to the cloud.**

**Trap:** Fog does not mean permanently storing all raw data at the edge.

### Mock pattern 3
**Question:** How does fog address high latency?

**Answer:** **Extend cloud-like capabilities closer to the data source so local processing can happen before cloud round trips.**

### Mock pattern 4
**Question:** How should data with different time sensitivities be handled?

**Answer:**
- Very time-sensitive → nearest fog node.
- Less time-sensitive → aggregate fog node.
- Non-time-sensitive → cloud.

---

## Sensor-Cloud

### Mock pattern 5
**Question:** What is the difference between PH and PI?

**Answer:**
- **PH/pH** → hardware / physical sensor-node usage.
- **PI/pI** → underlying sensor-cloud infrastructure.

### Mock pattern 6
**Question:** Why is dynamic pricing needed instead of simply using traditional IaaS/PaaS/SaaS pricing?

**Answer:** The sensor-cloud model must account for the heterogeneous sensor hardware and infrastructure involved in providing Sensor-as-a-Service.

### Mock pattern 7
**Question:** What is the functional difference between internal and external cache?

**Answer:**
- **IC** → directly handles end-user request and decides whether to serve or re-cache.
- **EC** → periodically re-caches data.

---

# 56. WEEK 9 MOCK-EXAM TRAP BANK

## Trap 1 — Fog is not “replacement of cloud”

**Wrong idea:** Fog replaces cloud completely.

**Correct idea:** Fog is an **intermediate layer** that extends cloud services nearer to IoT devices.

---

## Trap 2 — Fog node storage is transient

The assignment explicitly asks what is **NOT** a required fog-node characteristic.

Required:
- transient storage,
- computing facility,
- network connectivity.

NOT required:
- permanent, unlimited archival storage.

Permanent/global long-term storage belongs to the cloud role described in the lecture.

---

## Trap 3 — Time-sensitive ≠ cloud-first

For data that must be processed within a fraction of a second:

**Device → nearest fog node → immediate action**

Do **not** choose a distant cloud-first path when the question emphasizes immediate response.

---

## Trap 4 — Less time-sensitive ≠ always cloud

The lecture distinguishes three classes:

| Data class | Processing location |
|---|---|
| Very time-sensitive | Nearest fog node |
| Less time-sensitive | Aggregate fog node |
| Non-time-sensitive | Cloud |

This three-level hierarchy is highly testable.

---

## Trap 5 — Sensor-cloud ≠ “dump sensor data into cloud”

The lecture explicitly says sensor-cloud is more than integration of WSN and cloud.

Core concept:

**Sensor-node virtualization + pay-per-use + service layer between physical sensors and end-users**

---

## Trap 6 — CoV-I vs CoV-II

| Feature | CoV-I | CoV-II |
|---|---|---|
| Physical sensor nodes | Homogeneous | Heterogeneous |
| Geography | Same region | Multiple regions |
| Result | Virtual Sensor (VS) | Virtual Sensor Group (VSG) |

**Memory:**  
**I = In one region + Identical/homogeneous nodes**  
**II = multiple regions + heterogeneous group**

---

## Trap 7 — Traditional WSN vs Sensor-Cloud actor responsibilities

### Traditional WSN
**WSN-user** handles:
- ownership,
- deployment,
- redeployment,
- maintenance,
- overhead,
- usage.

### Sensor-cloud
- **Sensor-owner** → ownership + deployment.
- **SCSP** → redeployment + maintenance + overhead.
- **End-user** → usage.

---

## Trap 8 — OpenStack component confusion

- Horizon ≠ compute → **Horizon = dashboard**
- Nova ≠ image service → **Nova = compute**
- Glance ≠ block storage → **Glance = image**
- Swift ≠ networking → **Swift = object storage**
- Neutron ≠ block storage → **Neutron = networking**
- Cinder ≠ object storage → **Cinder = block storage**
- Keystone ≠ dashboard → **Keystone = identity/authentication/authorization**

---

# 57. WEEK 9 PRIORITY RANKING FOR THE EXAM

## 🔴 MUST MEMORIZE

1. **OpenStack 2010 = Rackspace + NASA**
2. **Horizon = dashboard/GUI**
3. **Nova = compute / instances**
4. **DevStack → `./stack.sh`**
5. **Sensor-cloud = virtualization + pay-per-use**
6. **Traditional WSN → WSN-user**
7. **Sensor-cloud → Sensor-owner / SCSP / End-user roles**
8. **CoV-I = homogeneous + same geographical region**
9. **CoV-II = heterogeneous + multiple regions**
10. **IC = end-user request handler**
11. **EC = periodic re-cache**
12. **Adaptive caching = avoids unnecessary sensing/energy consumption**
13. **Fog term coined by CISCO**
14. **Fog = between cloud and IoT devices**
15. **Fog motivation = Volume + Latency + Bandwidth**
16. **Very time-sensitive = nearest fog**
17. **Less time-sensitive = aggregate fog**
18. **Non-time-sensitive = cloud**
19. **Fog node = transient storage + compute + connectivity**
20. **PH = hardware pricing; PI = infrastructure pricing**

## 🟠 HIGH PRIORITY

- Cloud service models: IaaS / PaaS / SaaS.
- Fog advantages: security, low operation cost, quick decisions, privacy, business agility, mobility, remote deployment, better data handling.
- Fog applications: healthcare, energy-efficient systems, railway monitoring, pipeline optimization, wind-turbine analysis.
- Fog challenges: power consumption, security, reliability, fault tolerance, real-time analysis, programming architecture.
- OpenStack component roles: Glance, Swift, Neutron, Cinder, Heat, Ceilometer, Keystone.

---

# 58. IMPORTANT NUMBERS / TERMS SHEET

## OpenStack
- **2010** → OpenStack launched as Rackspace + NASA joint project.
- **DevStack** → practical installation method used in lecture.
- `local.conf` → configure passwords + `HOST_IP`.
- `./stack.sh` → install.
- `./unstack.sh` → uninstall.

## Fog lecture figures

The lecture includes the following historical/context figures:
- **40%** of the world's data from sensors alone by 2020.
- **90%** of the world's data generated during the last two years (as stated in the lecture).
- **2.5 quintillion bytes/day** of data.
- **$1.7 trillion** total IoT-device expenditure by 2020.
- **250 million** connected vehicles worldwide by 2020.
- The lecture also states **more than 30 billion IoT devices** and, in the cloud-limitations discussion, uses a **50-billion-device** projection.

> **Exam advice:** These are lecture-era figures. Memorize them only if your instructor/mock pattern uses numerical recall. The conceptual triad **Volume–Latency–Bandwidth** is more important.

## Sensor-Cloud terms
- **Se-aaS** → Sensor-as-a-Service.
- **SCSP** → Sensor-Cloud Service Provider.
- **VS** → Virtual Sensor.
- **VSG** → Virtual Sensor Group.
- **CoV-I** → same-region homogeneous sensor composition.
- **CoV-II** → multi-region heterogeneous sensor composition.
- **IC** → Internal Cache.
- **EC** → External Cache.
- **PH/pH** → hardware pricing.
- **PI/pI** → infrastructure pricing.

---

# 59. 60-SECOND RECALL — WEEK 9

Say this without looking:

> **OpenStack = 2010, Rackspace + NASA. Horizon dashboard, Nova compute, Glance image, Swift object storage, Neutron network, Cinder block, Heat orchestration, Keystone identity, Ceilometer billing/usage. DevStack uses local.conf and stack.sh. Sensor-cloud = virtualization of sensor nodes + pay-per-use. WSN-user handles traditional WSN ownership/deployment/redeployment/maintenance/usage. Sensor-owner owns/deploys physical sensors; SCSP redeploys/maintains/manages overhead; end-user uses the service. CoV-I = homogeneous same-region VS; CoV-II = heterogeneous multi-region VSG. IC handles end-user requests; EC re-caches. Adaptive caching saves energy. Fog = CISCO, between cloud and IoT devices. Why fog? Volume, latency, bandwidth. Very time-sensitive → nearest fog; less time-sensitive → aggregate fog; non-time-sensitive → cloud. Fog node = transient storage + compute + connectivity. PH = hardware; PI = infrastructure.**

---

# 60. RAPID 20-QUESTION SELF-TEST

1. OpenStack was launched with Rackspace and which organization?  
   **NASA**

2. OpenStack dashboard?  
   **Horizon**

3. OpenStack compute service?  
   **Nova**

4. OpenStack image service?  
   **Glance**

5. OpenStack object storage?  
   **Swift**

6. OpenStack networking?  
   **Neutron**

7. OpenStack block storage?  
   **Cinder**

8. OpenStack identity service?  
   **Keystone**

9. OpenStack installation script in the lecture?  
   **`./stack.sh` via DevStack**

10. Sensor-cloud's defining concept?  
    **Virtualization of sensor nodes + pay-per-use**

11. Who redeploys a traditional WSN?  
    **WSN-user**

12. CoV-I?  
    **Homogeneous nodes in the same geographical region**

13. Which cache handles end-user requests?  
    **Internal Cache (IC)**

14. Why adaptive caching?  
    **To avoid unnecessary sensing and save energy when environmental conditions change slowly**

15. Fog computing term coined by?  
    **CISCO**

16. Three cloud limitations motivating fog?  
    **Volume, Latency, Bandwidth**

17. Where is fog placed?  
    **Between cloud and IoT devices**

18. Where is very time-sensitive data analyzed?  
    **Nearest fog node**

19. What does a fog node require?  
    **Transient storage + computing + network connectivity**

20. PH vs PI?  
    **PH = hardware; PI = infrastructure**

---

# 61. FINAL EXAM STRATEGY — UPDATED

### If the question is about OpenStack
Think:

**Horizon → Nova → Glance → Swift → Neutron → Cinder → Heat → Keystone → Ceilometer**

### If the question is about Sensor-Cloud
Think:

**Virtualization → Pay-per-use → Actors → CoV → Caching → Pricing**

### If the question is about Fog
Think:

**CISCO → Cloud/Fog/Device → Volume/Latency/Bandwidth → Time sensitivity → Fog-node characteristics → Advantages/Applications/Challenges**

### If the question gives a scenario

- “Need GUI” → **Horizon**
- “Launch instance” → **Nova**
- “VM image” → **Glance**
- “Object storage” → **Swift**
- “Network service” → **Neutron**
- “Block storage” → **Cinder**
- “Identity/authentication” → **Keystone**
- “Same region + homogeneous sensors” → **CoV-I**
- “Multiple regions + heterogeneous sensors” → **CoV-II**
- “End-user request/cache decision” → **IC**
- “Periodic re-cache” → **EC**
- “Fraction-of-second response” → **nearest fog**
- “Seconds/minutes” → **aggregate fog**
- “Hours/days/weeks” → **cloud**
- “Hardware pricing” → **PH**
- “Infrastructure pricing” → **PI**

---

# 62. SOURCE BASIS FOR THIS UPDATE

This improved file is grounded in the uploaded course materials:

- **Assignment_9.pdf** — all 15 Week 9 assignment questions and their provided solutions.
- **Week-9.pdf** — Cloud Computing Practical, Sensor-Cloud Part I, Sensor-Cloud Part II, Fog Computing Part I, and Fog Computing Part II.
- **Uploaded Mock Exams 1–5** — cumulative exam patterns used only for cross-checking and identifying repeated traps.

**No image was generated or added.**
