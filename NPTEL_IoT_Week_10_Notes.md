# NPTEL Introduction to Internet of Things — Week 10
## Assignment-First + Complete Lecture Coverage + Cumulative Mock Cross-Check

> **Exam priority rule:** Assignment questions are the highest priority. Learn the exact answer mappings first, then the related lecture concepts. This file covers all Week-10 lecture topics from the uploaded `Week-10.pdf` and all 15 questions from `Assignment_10(1).pdf`.
>
> **No images added.**

---

# PART A — ASSIGNMENT 10: HIGHEST PRIORITY

## Assignment answer lock

| Q | Answer | Must remember |
|---|---|---|
| 1 | **C** | Sensors & Tags → Sensory Organs |
| 2 | **A** | Six smart-city focus areas include Smart Economy |
| 3 | **D** | Smart Parking Lots → empty-slot routing/detection |
| 4 | **C** | Multi-tenancy data leakage → Security & Privacy |
| 5 | **B** | Data fusion → precise/accurate data for better decisions |
| 6 | **C** | Same sensor type gives different data at same location → Conflicts |
| 7 | **D** | Sensor-node/local-network fusion → Signal level |
| 8 | **A** | Smart parking layers include Information Collection |
| 9 | **D** | Intentionally deployed nearby energy source → Dedicated harvesting |
| 10 | **C** | IEEE 802.15.4 PHY/MAC + low-cost/low-energy → Zigbee |
| 11 | **D** | Power-line home control → X-10 |
| 12 | **A** | TCP/IP V2X limitation → endpoint/location-oriented communication |
| 13 | **B** | ICV spectrum → 75 MHz, 5850–5925 MHz |
| 14 | **B** | 4G LTE/DSRC intelligent transportation → Phase-2 |
| 15 | **D** | Mobile OBUs + static RSUs, V2V/V2I → Ad-hoc domain |

These answers and explanations are taken directly from the uploaded Week-10 assignment. fileciteturn104file0L25-L61 fileciteturn104file0L75-L114 fileciteturn104file0L125-L167 fileciteturn104file0L178-L219 fileciteturn104file0L227-L270 fileciteturn104file0L278-L322 fileciteturn104file0L330-L397

---

## Q1. Human ↔ Smart City analogy

**Question:** In the lecture analogy, what do **Sensors and Tags** correspond to?

**Answer: C — Sensory Organs**

### Full analogy

| Human | Smart city |
|---|---|
| Skeleton | Buildings, Industries, People |
| Skin | Transportation, Logistics |
| Organs | Hospitals, Police, Banks, Schools |
| Brain | Ubiquitously embedded intelligence |
| Nerves | Digital telecommunication networks |
| **Sensory organs** | **Sensors, Tags** |
| Cognition | Software |

**Exam trap:**  
- Sensors/Tags ≠ nerves.
- Digital telecommunication networks = **nerves**.
- Ubiquitously embedded intelligence = **brain**.

The lecture gives this analogy explicitly. fileciteturn104file1L445-L454

---

## Q2. Six smart-city Application Focus Areas

**Answer: A — Smart Economy**

Memorize all six:

1. **Smart Economy** → competitiveness
2. **Smart Governance** → citizen participation
3. **Smart People** → social and human capital
4. **Smart Mobility** → transport and ICT
5. **Smart Environment** → natural resources
6. **Smart Living** → quality of life

**Trap:** Smart Bandwidth, Smart Voltage, Smart Currency are distractors.

Source: assignment and lecture. fileciteturn104file0L49-L70 fileciteturn104file1L458-L470

---

## Q3. Smart Parking Lots

**Answer: D — Smart Parking Lots**

The lecture lists these functions:

- Auto-routing vehicles to empty slots
- Auto-charging for services
- Detecting vacant slots

### Memory hook
**Parking = find slot + route + charge + detect vacancy.**

The assignment explicitly ties these functions to Smart Parking Lots. fileciteturn104file0L75-L93

---

## Q4. Multi-tenancy and data leakage

**Answer: C — Security and Privacy**

Smart-city security/privacy challenges include:

- Exposure to attacks
- Exposure to vulnerabilities
- **Multi-tenancy → risk of data leakage**

### Trap
If the question says **data leakage because multiple tenants share infrastructure**, choose **Security and Privacy**, not heterogeneity.

The lecture separately defines heterogeneity as integration of varying hardware, radio and software platforms and varying user requirements. fileciteturn104file1L599-L613

---

## Q5. Purpose of data fusion

**Answer: B — Make large incoming data volume precise and accurate for better decision making**

Data fusion:

- Combines data from multiple sources/platforms.
- Improves the precision and accuracy of available data.
- Helps decision-making.
- Enables optimum use of massive multi-source data.

The lecture says that data precision/accuracy directly affects decision quality. fileciteturn104file1L678-L687

### Trap
Data fusion does **not** mean:
- deleting redundant sensors,
- replacing sensors,
- intentionally increasing latency.

---

## Q6. Same sensor type gives different values at same location

**Answer: C — Conflicts**

Data-fusion challenges:

| Challenge | Meaning |
|---|---|
| **Imperfection** | Inaccurate or uncertain WSN sensor data |
| **Ambiguity** | Outliers, missing data |
| **Conflicts** | Same sensor type reports different data for same location |
| **Alignment** | Sensor data frames converted to a singular frame before transmission |
| **Trivial features** | Processing trivial features may reduce overall system accuracy |

Source: lecture and assignment. fileciteturn104file1L708-L723

**Very high-probability trap:**  
**Different values from same sensor type at same location = CONFLICTS.**

---

## Q7. Fusion at sensor node/local network

**Answer: D — Signal level**

### Four stages of data fusion

| Level | What happens |
|---|---|
| **Signal level** | Fusion at sensor node / within local network |
| **Pixel level** | Fusion at imaging-device level |
| **Feature level** | Fusion of information before decision making |
| **Decision level** | Ensemble of decisions |

The lecture defines these stages directly. fileciteturn104file1L744-L755

### Memory order
**Signal → Pixel → Feature → Decision**

Do not confuse:
- **Signal** = closest to sensor/network.
- **Decision** = output/decision stage.

---

## Q8. Functional layers of smart parking

**Answer: A — Information Collection**

Three functional layers:

1. **Information Collection**
2. **System Deployment**
3. **Service Dissemination**

### Information Collection
Sources shown in the lecture:

- Sensors
- Parking meters
- Sensor networks
- Crowd sensing

### System Deployment
Includes:

- Software system
- Information management
- E-parking
- Guidance
- Data analytics

### Service Dissemination
Includes:

- Dynamic pricing strategies
- Infrastructure-based information
- Infrastructure-free information
- Parking choice
- Vehicular activities

Sources: fileciteturn104file1L812-L823 fileciteturn104file1L828-L855 fileciteturn104file1L860-L874

---

## Q9. Dedicated energy harvesting

**Answer: D — Dedicated energy harvesting**

### Ambient vs dedicated

**Ambient energy harvesting**
- Uses energy already available in the environment.
- Examples listed:
  - RF
  - Wind
  - Sun
  - Heat
  - Vibration

**Dedicated energy harvesting**
- Energy source is **intentionally deployed near the IoT source/device**.
- Harvested energy depends on:
  1. Sensitivity of harvesting circuit
  2. Distance between device and source
  3. Environment

Source: fileciteturn104file1L898-L943

**Trap:** "intentionally deployed near IoT devices" = **Dedicated**.

---

## Q10. Zigbee and IEEE 802.15.4

**Answer: C — Zigbee**

The lecture states:

- Zigbee has four layers:
  1. Physical
  2. MAC
  3. Network
  4. Application
- **IEEE 802.15.4 defines Physical + MAC**
- Zigbee defines Network + Application
- Target: **low-cost, low-energy devices**

Source: fileciteturn104file1L1151-L1164

### Exam distinction

**IEEE 802.15.4**
→ PHY + MAC

**Zigbee**
→ Network + Application on top of 802.15.4

---

## Q11. X-10

**Answer: D — X-10**

X-10:

- Enables remote control of compliant transmitters/receivers.
- Uses existing power lines/electrical wiring.
- Adopted by GE and Philips according to the lecture.
- Low-speed and low-data-rate.
- Used mainly for:
  - Lighting control
  - Appliance networks
  - Security sensors

Source: fileciteturn104file1L1169-L1182

### Trap
**Power-line home control + lighting/appliances = X-10.**

---

## Q12. Why traditional TCP/IP struggles with V2X

**Answer: A**

According to the lecture, TCP/IP:

- Was designed mainly for information exchange between a **single pair of entities**.
- Is dependent on the **location of data**.
- Identifies **endpoint addresses**, which alone is not sufficient for content distribution.
- The highly mobile environment creates additional problems.

Source: fileciteturn104file1L1357-L1367

### Core contrast

**Traditional IP approach**
→ "Where is the endpoint/data?"

**Content-centric approach**
→ "What data/content do I need?"

This leads to **CCN / Information-Centric Networking** concepts later in the lecture.

---

## Q13. ICV dedicated spectrum

**Answer: B — 75 MHz (5850–5925 MHz)**

Memorize:

> **ICV / DSRC → 75 MHz → 5850–5925 MHz**

The lecture states that the US Department of Transport and FCC allocated this dedicated spectrum for ICVs, based on DSRC. fileciteturn106file0L176-L185

---

## Q14. ICV development phase

**Answer: B — Phase-2**

| Phase | Main idea | Technology |
|---|---|---|
| **Phase-1** | Infotainment + remote information processing | 2G/3G |
| **Phase-2** | Intelligent transportation services | 4G LTE or DSRC |
| **Phase-3** | Vehicles connected to cloud | Cloud connectivity |

Source: fileciteturn106file1L231-L243

**Trap:** 4G LTE/DSRC + intelligent transportation = **Phase-2**.

---

## Q15. VANET domain classification

**Answer: D — Ad-hoc Domain**

The **Ad-hoc Domain** contains:

- Vehicles / OBUs → mobile
- RSUs → static
- V2V communication
- V2I communication
- DSRC stack / IEEE 802.11p

Source: fileciteturn106file1L301-L313

### Domain comparison

| Domain | Key idea |
|---|---|
| **In-Vehicle** | Internal vehicle components/OBUs, sensors, actuators |
| **Ad-hoc** | Vehicles + RSUs; V2V/V2I |
| **Infrastructure** | RSUs + gateways + Internet/cellular connectivity |
| Cloud | Backend/cloud services |

---

# PART B — COMPLETE WEEK-10 LECTURE NOTES

# 1. Smart Cities

## 1.1 Definition

A **Smart City** is an urban system that:

- Uses **Information & Communication Technology (ICT)**.
- Makes infrastructure more:
  - Interactive
  - Accessible
  - Efficient

### Why smart cities?

The lecture identifies major motivations:

- Rapidly growing urban population
- Fast depletion of natural resources
- Environmental and climate changes

Source: fileciteturn104file1L430-L443

---

# 2. Human ↔ Smart City Analogy

This is a major memory table.

| Human body | Smart city |
|---|---|
| Skeleton | Buildings, industries, people |
| Skin | Transportation, logistics |
| Organs | Hospitals, police, banks, schools |
| Brain | Ubiquitously embedded intelligence |
| Nerves | Digital telecommunication networks |
| Sensory organs | Sensors, tags |
| Cognition | Software |

### Exam trigger words

- **Sensors/Tags** → sensory organs
- **Digital telecom** → nerves
- **Embedded intelligence** → brain
- **Software** → cognition
- **Buildings/industries/people** → skeleton

---

# 3. Six Smart-City Application Focus Areas

### 1. Smart Economy
Focus: competitiveness.

### 2. Smart Governance
Focus: citizen participation.

### 3. Smart People
Focus: social and human capital.

### 4. Smart Mobility
Focus: transport and ICT.

### 5. Smart Environment
Focus: natural resources.

### 6. Smart Living
Focus: quality of life.

Source: fileciteturn104file1L458-L475

### One-line recall
**Economy – Governance – People – Mobility – Environment – Living**

---

# 4. Current Smart-City Focus Areas

## Smart Homes

Lecture examples:

- Health monitoring
- Conservation of electricity, water and fuel
- Security and safety

## Smart Parking Lots

- Auto-routing to empty slots
- Auto charging
- Vacancy detection

## Smart Vehicles

- Driver assistance during bad weather/low visibility
- Detection of bad driving patterns
- Detection of driving under influence
- Crash alerts
- Self-diagnostics

## Smart Health

- Low-cost portable at-home diagnosis
- Remote check-ups and diagnosis
- On-body sensors
- Emergency medical alerts

## Pollution and Calamity Monitoring

- Weather/man-made calamity monitoring
- Above-threshold pollutant alerts
- Resource reallocation and service rerouting

## Smart Energy

- Smart metering
- Smart allocation/distribution
- Traditional + renewable energy in the same grid

## Smart Agriculture

- Plant water-stress detection
- Crop-health monitoring
- Crop-infection detection
- Automatic fertilizer/pesticide application
- Harvest scheduling and transfer planning

Source: fileciteturn104file1L524-L582

---

# 5. Technological Focus Areas

The lecture groups smart-city technology into four major activities:

| Area | Examples |
|---|---|
| **Data Collection** | Mobile devices, sensors, architecture |
| **Data Transmission** | Radios, networking, topologies |
| **Data Storage** | Local storage, data warehouses |
| **Data Processing** | Data cleaning, analytics, prediction |

Source: fileciteturn104file1L584-L597

### Easy sequence
**Collect → Transmit → Store → Process**

---

# 6. IoT Challenges in Smart Cities

## 6.1 Security and Privacy

Problems:

- Attacks
- Vulnerabilities
- Multi-tenancy → data leakage

## 6.2 Heterogeneity

Need to integrate:

- Different hardware platforms/specifications
- Different radio specifications
- Different software platforms
- Different user requirements

## 6.3 Reliability

- Unreliable communication because of vehicle mobility
- Device failures

## 6.4 Large Scale

- Deployment-scale delay
- Mobility-induced delay
- Device distribution affects monitoring

## 6.5 Legal and Social Aspects

- Services using user-provided information may be subject to laws.
- Informed individual consent is required when humans are used as data sources.

## 6.6 Big Data

- Huge-volume transfer/storage/maintenance is expensive.
- Data cleaning is time-consuming.
- Analytics on huge data volumes is processing-intensive.

## 6.7 Sensor Networks

Important concerns:

- Appropriate sensor selection
- Energy planning
- Device placement
- Network architecture
- Communication medium

Source: fileciteturn104file1L599-L660

### MCQ mapping

- Data leakage from multi-tenancy → **Security & Privacy**
- Different hardware/radio/software → **Heterogeneity**
- Vehicle mobility → **Reliability**
- Huge-volume processing → **Big Data**
- Human data source consent → **Legal/Social**

---

# 7. Data Fusion

## 7.1 Why data fusion?

Smart cities periodically produce enormous data volumes.

The problem is not just "more data"; the challenge is obtaining **precise and accurate information** from the incoming data.

Data fusion:

- Uses data from multiple sources.
- Works across multiple platforms.
- Improves the information available for decisions.
- Enables optimum utilization of massive data.

Source: fileciteturn104file1L678-L687

---

# 8. Multi-Sensor Data Fusion

Multi-sensor fusion:

- Combines information from multiple sensor sources.
- Lets decision systems consider many variables.
- Can produce better inferences than a single sensor type.
- Heterogeneous sensor information gives better understanding of surroundings.

Source: fileciteturn104file1L693-L702

### Exam idea
**Many imperfect sensors + fusion → better collective information.**

---

# 9. Data-Fusion Challenges

Memorize this table exactly.

| Challenge | Meaning |
|---|---|
| **Imperfection** | Inaccurate/uncertain WSN sensor data |
| **Ambiguity** | Outliers, missing data |
| **Conflicts** | Same sensor type reports different data for same location |
| **Alignment** | Convert sensor data frames into a singular frame before transmission |
| **Trivial features** | Processing trivial features may reduce whole-system accuracy |

Source: fileciteturn104file1L708-L723

### High-value trap
**Same sensor type + same location + different readings = Conflicts.**

---

# 10. Opportunities of Data Fusion

The lecture lists:

- Collective data is richer than single-source data.
- Optimal amalgamation of data.
- Increased collective information content from multiple low-power/low-precision sensors.
- Ability to hide critical data sources and semantics in contexts such as military/medical applications.

Source: fileciteturn104file1L729-L738

---

# 11. Stages of Data Fusion

| Stage | Meaning |
|---|---|
| **Signal level** | Fusion at sensor node / local network |
| **Pixel level** | Fusion at imaging-device level |
| **Feature level** | Fusion before decision making |
| **Decision level** | Ensemble of decisions |

Source: fileciteturn104file1L744-L755

### Memory ladder
**Signal → Pixel → Feature → Decision**

### Assignment lock
If question says **"at sensor node/local network"** → **Signal level**.

---

# 12. Mathematical Methods of Data Fusion

The lecture groups methods into:

## Probability-based
- Bayesian analysis
- Statistics
- Recursive methods

## AI-based
- ANN
- Machine Learning
- CNN

## Theory-of-Evidence-based
- Belief functions
- Transferable belief models

Source: fileciteturn104file1L761-L773

---

# 13. AI in IoT Decision Making

Conceptual flow:

**Sensors → AI / intelligent processing → highly accurate decision → Actuator**

Without intelligence, raw sensor inputs can create a decision-making gap.

The lecture's AI-in-IoT slide explicitly contrasts decision-making without intelligence with an AI-assisted architecture. fileciteturn103file7L812-L821

### Exam idea
AI helps convert multi-source sensor information into more accurate decisions that can drive actuators.

---

# 14. Data Fusion for Autonomous Vehicles

Data fusion is especially important in vehicles because a vehicle may need to combine information from multiple sensing modalities and sources before taking decisions.

Think:

**Sensors → fusion → decision → vehicle action**

This connects Week 10's data-fusion section with the later connected-vehicle section.

---

# 15. Smart Parking

## Benefits

Smart parking can:

- Shorten parking-search time.
- Reduce traffic congestion.
- Reduce pollution from unnecessary vehicle circulation.
- Reduce fuel consumption/cost.
- Increase urban mobility.
- Increase parking-related revenue because less time is spent searching.

Source: fileciteturn104file1L797-L807

---

# 16. Smart Parking Functional Layers

Three layers:

1. **Information Collection**
2. **System Deployment**
3. **Service Dissemination**

### Information Collection
- Sensors
- Parking meters
- Sensor networks
- Crowd sensing

### System Deployment
- Software system
- Information management
- E-parking
- Guidance
- Data analytics

### Service Dissemination
- Dynamic pricing strategies
- Infrastructure-based information
- Infrastructure-free information
- Parking choice
- Vehicular activities

Source: fileciteturn104file1L812-L874

---

# 17. Information Sensing in Smart Parking

Two broad sensing approaches:

## Stationary sensing
- Large number of sensors
- Detects presence/absence in place

## Mobile sensing
- Fewer sensors
- Collects information along a route

Source: fileciteturn104file1L879-L892

### Trap
Do not automatically assume "mobile" means more sensors. The lecture specifically contrasts **stationary = many sensors** and **mobile = fewer sensors**.

---

# 18. Energy Management in Smart Cities

## Energy-efficient solutions

Lecture examples:

- Lightweight protocols
- Scheduling optimization
- Predictive models for energy consumption
- Cloud-based approach
- Low-power transceivers
- Cognitive management framework

Source: fileciteturn104file1L898-L912

---

# 19. Energy Harvesting

## Ambient energy harvesting

Environmental sources listed:

- RF
- Wind
- Sun
- Heat
- Vibration

## Dedicated energy harvesting

- Energy source intentionally deployed near IoT source.
- Harvested amount depends on:
  1. Harvesting-circuit sensitivity
  2. Device-source distance
  3. Environment

Source: fileciteturn104file1L914-L943

### One-line exam rule
**Ambient = already around. Dedicated = deliberately placed nearby.**

---

# 20. Smart Home

## Smart-home infrastructure

Consists of:

- Intelligent networking-device infrastructure
- Seamless integration of devices using wired/wireless technologies

Goals include:

- Ease of use
- Personalized home space
- Safe home environment

The lecture notes corporations such as GE, Cisco, Google and Microsoft as examples of organizations involved in smart-home systems. fileciteturn104file1L965-L978

---

# 21. Smart Home Goals

A smart home provides:

- Productive and cost-efficient environment
- Better effectiveness for occupants
- Efficient management
- Minimum lifetime cost of hardware/facilities
- Optimization of:
  - Structures
  - Systems
  - Services/management
  - Interrelationships among them

Source: fileciteturn104file1L980-L994

---

# 22. Home Area Networks (HANs)

A **HAN** is a network contained within a home.

It enables:

- Remote access
- Remote control
- Integration of systems such as:
  - Security
  - Home automation
  - Personal media
  - Communication

Source: fileciteturn104file1L1007-L1022

---

# 23. HAN Elements

## Internet Protocol / Multi-protocol gateway

A multi-protocol gateway:

- Bridges non-IP networks to IP networks.
- Allows technologies with different networking approaches to interact.
- May require new mapping for new technologies/networks.

Source: fileciteturn104file1L1024-L1039

---

# 24. Wired vs Wireless HAN

## Wired HAN

Advantages/features:

- Easy integration with existing house infrastructure.
- Low cost.
- Can use:
  - Power lines
  - Coaxial cables
  - Telephone lines
  - Optical fibers
  - Other wired technologies

## Wireless HAN

Can use:

- Wi-Fi
- ZigBee
- 6LoWPAN

Wireless implementation can be easier.

Source: fileciteturn104file1L1041-L1071

---

# 25. HAN Medium Classification

The lecture classifies HAN communication into:

## Wired
Examples shown include:
- HomePlug
- Ethernet
- Insteon
- X-10

## Wireless — Battery Operated
Examples:
- Z-Wave
- Wi-Fi
- 6LoWPAN
- ZigBee

## Wireless — Battery Free
Uses:
- Energy harvesting
- Example: EnOcean

**Exam association:**  
**Battery-free wireless → energy harvesting → EnOcean.**

---

# 26. HAN Standards

## 26.1 UPnP — Universal Plug and Play

- Application-layer technology.
- Mainly web-based.
- TCP/IP supports lower layers.
- Enables seamless integration.
- Supports zero-configuration networking.
- Automatic device discovery.

Source: fileciteturn104file1L1080-L1096

### Memory
**UPnP = plug + play + zero configuration + discovery.**

---

## 26.2 DLNA

- Trade organization created by Sony, Intel and Microsoft.
- Connects cable-based and wireless networks for sharing media/control/access.
- Supports domestic network-media sharing.

Source: fileciteturn104file1L1098-L1113

### Memory
**DLNA = home media/resource sharing.**

---

## 26.3 Konnex / KNX

- Open important standard for home/building networks.
- Can use:
  - Power lines
  - Coaxial cables
  - Twisted pair
  - RF
- Must be set up/configured through software before proper use.

Source: fileciteturn104file1L1115-L1131

### Memory
**KNX = configurable home/building network standard.**

---

## 26.4 LonWorks

Each device includes:

- Neuron chip
- Transceiver
- Application electronics

Neuron chip is a system-on-chip containing:

- Multiple microprocessors
- RAM
- ROM
- I/O interface ports

Source: fileciteturn104file1L1133-L1149

### Memory
**LonWorks = Neuron chip.**

---

## 26.5 ZigBee

Four layers:

1. Physical
2. MAC
3. Network
4. Application

- IEEE 802.15.4 → PHY + MAC
- ZigBee → Network + Application
- Low-cost, low-energy devices

Source: fileciteturn104file1L1151-L1164

### Memory
**ZigBee = 802.15.4 PHY/MAC + ZigBee Network/Application.**

---

## 26.6 X-10

- Uses existing power wiring.
- Remote control of compliant devices.
- Low speed/low data rate.
- Lighting/appliance/security use.

Source: fileciteturn104file1L1169-L1182

### Memory
**X-10 = power-line home control.**

---

# 27. HAN Architectures

## DomoNet

Lecture points:

- XML for description.
- Web services for control.
- Service-Oriented Architecture (SOA).
- Not tied to a particular software/language/architecture.
- Central gateway connects different technologies.
- Technology manager for each technology provides web services.

Source: fileciteturn104file1L1187-L1203

## Jini

- Connects devices sharing resources.
- Auto-configuration and auto-installation.
- Java environment.
- Associated with Sun Microsystems (now Oracle).
- Federation without a central node.
- Applications use bytecode on JVM.
- Object-oriented paradigm.

Source: fileciteturn104file1L1205-L1222

### DomoNet vs Jini
- **DomoNet** → XML, web services, SOA, central gateway.
- **Jini** → Java, JVM bytecode, federation, no central node.

---

# 28. HAN Initiatives

## HYDRA

A middleware approach for embedded intelligent systems.

Key ideas:

- Connects a Service-Oriented Architecture network.
- Targets constrained connected devices.
- Devices may have limited:
  - Processing power
  - Memory
  - Energy
- Each device has an embedded HYDRA client acting as a proxy between device and middleware.

Source: fileciteturn104file1L1224-L1240

## Amigo

Aimed at:

- Ambient intelligent systems
- Networked home systems

Features:

- User-friendly interfaces
- Interoperability
- Automatic discovery of devices/services

Source: fileciteturn104file1L1253-L1266

---

# 29. Connected Vehicles

Vehicles can be equipped with:

- Sensors
- Networking devices
- Communication devices

They can communicate:

- Within the vehicle
- With other vehicles
- With fixed infrastructure

Source: fileciteturn104file1L1284-L1297

---

# 30. Connected-Vehicle Challenges

Memorize:

- Security
- Privacy
- Scalability
- Reliability
- Quality of service
- Lack of global standards

Source: fileciteturn104file1L1299-L1307

---

# 31. V2X — Vehicle-to-Everything

V2X is a major component of future Intelligent Transportation Systems.

Vehicles can share information with:

- Other vehicles
- Pedestrians
- Fixed infrastructure
- Mobile towers
- Parking meters

Benefits include:

- Traffic management
- On-road/off-road safety
- Mobility

Source: fileciteturn104file1L1324-L1340

### V2X types to remember

- **V2V** → Vehicle to Vehicle
- **V2I** → Vehicle to Infrastructure
- **V2P** → Vehicle to Pedestrian
- **V2X** → Vehicle to Everything

---

# 32. V2X Architecture / Information Distribution

The lecture describes V2X as:

- Distributed
- Not restricted to a single information provider
- Designed for highly mobile environments
- Able to share information locally and remotely
- Useful for travel efficiency and safety
- A network primarily used for information sharing/dissemination

Source: fileciteturn104file1L1342-L1355

---

# 33. Why TCP/IP Is a Poor Fit for Some V2X Requirements

Lecture limitations:

1. Mainly single-pair information exchange.
2. Data exchange depends on data location.
3. Endpoint addresses alone are insufficient for content distribution.
4. Increasing wireless-device numbers can restrict mobility.

Source: fileciteturn104file1L1357-L1370

### Assignment lock
If the wording resembles:
> "single pair + location dependent + endpoint address"

→ **TCP/IP limitation in V2X**.

---

# 34. Content-Centric Networking (CCN)

CCN is derived from Information-Centric Networking (ICN).

Core ideas:

- Focuses on **data/content**, not its physical location.
- Uses hierarchically named data.
- Data is transmitted directly rather than being tied to a conventional conversation.
- Supports scalable and efficient data dissemination.
- In-network caching reduces traffic.
- Works well in highly mobile environments.

Source: fileciteturn104file1L1372-L1385

### TCP/IP vs CCN

| TCP/IP-style idea | CCN idea |
|---|---|
| Endpoint/location oriented | Content oriented |
| Endpoint addresses | Hierarchical content names |
| Location matters | Content name matters |
| Conventional routing | Content-name forwarding |
| Less natural for highly mobile content distribution | Designed to work well in highly mobile environments |

---

# 35. VANETs

**VANET = Vehicular Ad-hoc Network**

The lecture connects VANETs with:

- DSRC
- WAVE
- Routing protocols derived from MANETs

Lecture-stated characteristics include:

- High throughput in mobile environments
- Low latency in mobile environments

Source: fileciteturn104file1L1387-L1403

---

# 36. VANET Features

## High dynamic topology
Vehicles move rapidly, causing constant changes in:

- Network partitioning
- Topology

## High transmission and computation capability
Vehicle energy sources and computational capability reduce the restrictions that commonly affect tiny sensor nodes.

## Unstable connectivity
Links are short-lived because of highly dynamic movement.

## Large scale
Can scale to include vehicles across roads.

Source: fileciteturn104file1L1405-L1414

### Exam trap
VANET is **not** a static sensor network:
- topology is highly dynamic,
- links can be short-lived,
- vehicles are mobile.

---

# 37. VANET Applications

## Safety
- Emergency braking
- Lane-change warning
- Collision avoidance
- Hazard notification

## Efficiency
- Congestion management
- Electronic toll collection
- Parking availability

## Commercial
- Internet access
- Multimedia streaming

## Comfort
- Weather information
- Autonomous driving
- Journey-time estimation

Source: fileciteturn106file0L11-L27

### Memory
**Safety – Efficiency – Commercial – Comfort**

---

# 38. CCN for VANETs — Routing

CCN forwarding/routing:

- Based on **content name**, not location.
- Routers advertise content-name prefixes.
- Builds a **Forwarding Information Base (FIB)**.
- Content name remains globally unique.
- Avoids traditional IP-address-management/address-exhaustion issues.
- Communication is not dependent on node speed/direction in the same way as location-oriented routing.

Source: fileciteturn106file0L32-L45

---

# 39. CCN for VANETs — Scalability

Each router can have an in-network cache.

### Content Store (CS)

- Stores uniquely named data chunks.
- Acts as a cache.
- Later requests can be served from the cache.
- Same named data can be reused.
- Reduces network load as network size increases.

Source: fileciteturn106file0L47-L61

### Important terms

**FIB** → forwarding based on content-name prefixes.

**CS** → cached content/data chunks.

---

# 40. Body-and-Brain Architecture

An in-vehicle networking architecture with three layers:

1. **Sense and Execution** → Body
2. **Network and Transmission** → Nervous system
3. **Decision** → Brain

The body contains intelligent networking nodes (INNs) that continually collect vehicle information; the brain manages central coordination.

Source: fileciteturn106file0L63-L80

### Human analogy
**Body → Nervous system → Brain**
=
**Sense/Execution → Network/Transmission → Decision**

---

# 41. Intelligent Networking Nodes (INN)

The lecture classifies INNs by types such as:

## Resistor type
- Open
- Close

## Motor type
- Clockwise
- Counter-clockwise
- Stop

## Switch type
- Knob
- Pneumatic
- Electromagnetic

## Sensor type
- Rheostatic
- Transformer
- Transducer

The lecture also distinguishes assembled/separate electronic control in the shown classification.

Source: fileciteturn106file0L89-L109

---

# 42. Sense-and-Execution Layer

This layer represents the vehicle's sensing and action components.

Think:

**Sensors + actuators + physical vehicle functions**

The exact detailed diagram is visual in the uploaded lecture, but the core architectural placement is the **Body / Sense and Execution** layer.

---

# 43. Network-and-Transmission Layer

Purpose:

- Communication
- Transmission of information among vehicle components/nodes.

In the body-brain architecture, it acts as the **nervous-system equivalent**.

---

# 44. Decision Layer

The lecture shows two decision-layer roles:

- **Administrative Node** → monitoring
- **Supervisory Node** → control of sensors

Information is transmitted upward from the network/transmission layer and commands can be transmitted downward.

### Memory
**Administrative = monitoring**  
**Supervisory = control**

---

# 45. Intelligent Connected Vehicles (ICVs)

ICV architecture brings together:

- Intelligent transportation
- Transport infrastructure
- Pedestrians
- Communication channel

The lecture presents ICVs as part of the broader intelligent-transportation ecosystem.

---

# 46. ICV Technological Background

The lecture states:

- US Department of Transport + FCC allocated **75 MHz**.
- Spectrum: **5850–5925 MHz**
- Dedicated for ICVs.
- Based on **DSRC**.
- IEEE developed:
  - IEEE 802.11p
  - IEEE 1609 family
- SAE developed:
  - SAE J2735
  - SAE J2945

Source: fileciteturn106file0L176-L185

### Number lock
**75 MHz = 5850–5925 MHz**

---

# 47. IEEE 1609 Family

Important associations:

| Standard | Lecture association |
|---|---|
| IEEE P1609.0 | WAVE architecture |
| IEEE 1609.1-2006 | WAVE resource manager |
| IEEE 1609.2-2006 | Security services for applications/management messages |
| IEEE 1609.3-2007 | Networking services |
| IEEE 1609.4-2006 | Multi-channel operations |
| IEEE P1609.11 | Over-the-air data exchange protocol for ITS |

Source: fileciteturn106file0L191-L207

### High-yield pairings
- **1609.2 → Security**
- **1609.3 → Networking**
- **1609.4 → Multi-channel**
- **1609.1 → Resource manager**

---

# 48. ICV Development Phases

## Phase-1
- Infotainment
- Remote information processing
- 2G/3G

## Phase-2
- Intelligent transportation services
- 4G LTE or DSRC

## Phase-3
- Vehicles connected to cloud

Source: fileciteturn106file1L231-L243

### Assignment trap
**4G LTE or DSRC + intelligent transportation = Phase-2.**

---

# 49. Forward Collision Warning and Vulnerable Road Users

The lecture includes examples of:

- **Forward Collision Warning (V2V)**
- **Vulnerable Road User Safety (V2P)**

### Memory
- Collision warning between vehicles → **V2V**
- Vulnerable road user safety → **V2P**

---

# 50. VANET Domain Classification

Three domains shown:

1. **In-Vehicle Domain**
2. **Ad-hoc Domain**
3. **Infrastructure Domain**

---

## 50.1 In-Vehicle Domain

Contains:

- One or more OBUs
- ADAS sensors such as:
  - Cameras
  - Proximity sensors
  - Engine sensors
  - Radars
  - Actuators

Communication mainly through:

- CAN
- Vehicular Powerline Networks (VPLN)
- Ethernet

Source: fileciteturn106file1L284-L300

---

## 50.2 Ad-hoc Domain

Contains:

- Vehicles / OBUs → mobile
- RSUs → static

Communication:

- V2V
- V2I

Technology:

- DSRC stack
- IEEE 802.11p

Source: fileciteturn106file1L304-L317

### Assignment lock
**Mobile OBUs + static RSUs + V2V/V2I = Ad-hoc Domain.**

---

## 50.3 Infrastructure Domain

- RSUs connect to Internet through gateways.
- Vehicles can communicate with Internet through RSUs/V2I.
- If RSUs are absent, vehicles may communicate with one another or Internet through:
  - 3G/4G
  - LTE
  - Cellular networks

Source: fileciteturn106file1L321-L335

---

# 51. V2X Advantages

Lecture lists:

- Increased traffic safety
- Increased driver safety
- Optimized travel time
- Better fuel-consumption efficiency
- Secure travel
- Easier driving in low visibility/unfavorable weather

Source: fileciteturn106file1L341-L353

---

# 52. V2X Disadvantages / Privacy

Lecture lists:

- Privacy violation
- Loss of data control
- Collection of personal data
- Second use of data
- Data use by unauthorized entities
- Tracking of movements
- Localization of position

Source: fileciteturn110file7L637-L646

### Cumulative mock cross-check
A cumulative mock exam asks about the major privacy concern in V2X and identifies **tracking vehicle movements/location** as a significant concern. fileciteturn107file6L597-L614

### Exam trap
If a question asks for a V2X privacy issue:
**tracking + location + personal data + unauthorized use** are all lecture-supported concerns.

---

# PART C — HAN STANDARD COMPARISON

| Standard | Key exam identity |
|---|---|
| **UPnP** | Zero-config networking + automatic discovery |
| **DLNA** | Home media/resource sharing |
| **KNX/Konnex** | Open home/building network standard; configurable |
| **LonWorks** | Neuron chip |
| **ZigBee** | Low-cost/low-energy; 802.15.4 PHY/MAC |
| **X-10** | Power-line lighting/appliance/security control |

---

# PART D — DATA-FUSION TRAP BANK

## Trap 1
**Same sensor type + same location + different readings**

→ **Conflicts**

## Trap 2
**Outliers + missing data**

→ **Ambiguity**

## Trap 3
**Inaccurate/uncertain WSN data**

→ **Imperfection**

## Trap 4
**Convert multiple sensor frames into one frame**

→ **Alignment**

## Trap 5
**Fusion at sensor node/local network**

→ **Signal level**

## Trap 6
**Ensemble of decisions**

→ **Decision level**

## Trap 7
**Fusion at imaging device**

→ **Pixel level**

## Trap 8
**Fusion before decision making**

→ **Feature level**

---

# PART E — CONNECTED-VEHICLE TRAP BANK

## TCP/IP vs CCN

- TCP/IP → endpoint/location-oriented.
- CCN → content-oriented.

## ICV spectrum

- **75 MHz**
- **5850–5925 MHz**
- DSRC

## ICV phases

- Phase-1 → 2G/3G + infotainment
- **Phase-2 → 4G LTE/DSRC + intelligent transportation**
- Phase-3 → cloud-connected vehicles

## VANET domains

- In-Vehicle → inside vehicle
- **Ad-hoc → OBUs + RSUs, V2V/V2I**
- Infrastructure → RSUs + gateways + Internet/cellular

## Privacy

- Movement tracking
- Position localization
- Personal-data collection
- Loss of data control

---

# PART F — HIGH-PRIORITY MEMORY LIST

If time is short, memorize these first:

1. Sensors & Tags → **Sensory Organs**
2. Smart-city six focus areas:
   **Economy, Governance, People, Mobility, Environment, Living**
3. Smart Parking → empty-slot routing + charging + vacancy detection
4. Multi-tenancy leakage → **Security & Privacy**
5. Data fusion → precise/accurate information for decision making
6. Imperfection → inaccurate/uncertain data
7. Ambiguity → outliers/missing data
8. Conflicts → same sensor type, same location, different data
9. Alignment → singular frame
10. Signal-level fusion → sensor node/local network
11. Pixel-level → imaging device
12. Feature-level → before decision
13. Decision-level → ensemble of decisions
14. Dedicated energy harvesting → intentionally deployed nearby source
15. Ambient harvesting → RF/wind/sun/heat/vibration
16. ZigBee → IEEE 802.15.4 PHY/MAC + ZigBee Network/Application
17. X-10 → power-line home control
18. UPnP → zero-config + discovery
19. DLNA → media sharing
20. LonWorks → Neuron chip
21. DomoNet → XML + web services + SOA + central gateway
22. Jini → Java + JVM + federation
23. HYDRA → middleware + embedded client/proxy
24. V2X → vehicle shares information with vehicles/pedestrians/infrastructure
25. TCP/IP V2X limitation → endpoint/location orientation
26. CCN → content-centric, hierarchical names, caching
27. VANET → DSRC/WAVE + MANET-derived routing
28. ICV spectrum → **75 MHz, 5850–5925 MHz**
29. Phase-2 → **4G LTE/DSRC + intelligent transportation**
30. Ad-hoc domain → **mobile OBUs + static RSUs + V2V/V2I**
31. In-Vehicle → CAN/VPLN/Ethernet
32. Infrastructure → RSU + gateway + Internet/cellular
33. V2X privacy → tracking/location/personal data
34. IEEE 1609.2 → security
35. IEEE 1609.3 → networking
36. IEEE 1609.4 → multi-channel
37. IEEE 1609.1 → resource manager

---

# PART G — NUMBERS / STANDARDS TO MEMORIZE

| Item | Value / association |
|---|---|
| ICV dedicated spectrum | **75 MHz** |
| ICV spectrum range | **5850–5925 MHz** |
| ICV technology | **DSRC** |
| Wireless access in vehicular environments | **WAVE** |
| Vehicular radio standard | **IEEE 802.11p** |
| ZigBee lower layers | **IEEE 802.15.4 PHY + MAC** |
| ICV Phase-1 | **2G/3G** |
| ICV Phase-2 | **4G LTE / DSRC** |
| ICV Phase-3 | **Cloud-connected vehicles** |

---

# PART H — CUMULATIVE MOCK-STYLE PATTERNS

The uploaded cumulative mocks repeatedly favor **short association questions**. For Week 10, the strongest directly supported mock pattern found is V2X privacy: movement/location tracking is a major concern. fileciteturn107file6L597-L614

### Likely question forms

**1.** Sensors and Tags in smart-city analogy correspond to:
→ **Sensory Organs**

**2.** Multi-tenancy data leakage belongs to:
→ **Security & Privacy**

**3.** Same sensor type reports different data at same location:
→ **Conflicts**

**4.** Fusion at sensor node:
→ **Signal level**

**5.** Energy source intentionally deployed near device:
→ **Dedicated energy harvesting**

**6.** IEEE 802.15.4 PHY/MAC + low-cost/low-energy:
→ **ZigBee**

**7.** Power-line home automation:
→ **X-10**

**8.** TCP/IP V2X limitation:
→ **Single-pair/location/endpoints**

**9.** ICV spectrum:
→ **75 MHz, 5850–5925 MHz**

**10.** 4G LTE/DSRC intelligent transportation:
→ **Phase-2**

**11.** OBUs + RSUs + V2V/V2I:
→ **Ad-hoc domain**

**12.** V2X privacy:
→ **Tracking/location/personal data**

---

# PART I — 25-QUESTION RAPID SELF-TEST

Try answering without looking.

1. Sensors and Tags correspond to what in the smart-city analogy?
2. Name all six smart-city application focus areas.
3. Which smart-city area routes vehicles to empty parking slots?
4. Which challenge includes multi-tenancy data leakage?
5. What is the main purpose of data fusion?
6. What does imperfection mean?
7. What does ambiguity mean?
8. What does conflicts mean?
9. What does alignment mean?
10. Which fusion level occurs at the sensor node/local network?
11. Which fusion level is an ensemble of decisions?
12. What are the three smart-parking functional layers?
13. What is dedicated energy harvesting?
14. Which HAN standard uses IEEE 802.15.4 PHY/MAC and targets low-cost/low-energy devices?
15. Which HAN standard uses existing electrical wiring?
16. What is the main V2X problem with endpoint/location-oriented TCP/IP?
17. What does CCN focus on?
18. What is VANET based on?
19. What are the four broad VANET application categories in the lecture?
20. What is the ICV spectrum?
21. What technology is associated with that spectrum?
22. Which ICV phase uses 4G LTE/DSRC for intelligent transportation?
23. What is in the Ad-hoc domain?
24. What is the role of RSUs in the infrastructure domain?
25. Name two V2X privacy concerns.

## Answers

1. Sensory organs.
2. Smart Economy, Smart Governance, Smart People, Smart Mobility, Smart Environment, Smart Living.
3. Smart Parking Lots.
4. Security and Privacy.
5. Make incoming large data volumes more precise/accurate for better decisions.
6. Inaccurate/uncertain sensor data.
7. Outliers/missing data.
8. Same sensor type gives different data for same location.
9. Converting sensor frames to a singular frame.
10. Signal level.
11. Decision level.
12. Information Collection, System Deployment, Service Dissemination.
13. Energy source intentionally deployed near IoT source/device.
14. ZigBee.
15. X-10.
16. It is mainly endpoint/location-oriented and is less suited to content distribution in highly mobile V2X.
17. Data/content rather than physical location.
18. DSRC/WAVE; routing derived from MANETs.
19. Safety, Efficiency, Commercial, Comfort.
20. 75 MHz, 5850–5925 MHz.
21. DSRC.
22. Phase-2.
23. Mobile OBUs + static RSUs, V2V/V2I.
24. Connect vehicles to infrastructure/Internet through gateways and V2I.
25. Movement tracking, position localization, personal-data collection, loss of data control, unauthorized use.

---

# PART J — 60-SECOND WEEK-10 RECALL

> **Smart City** = ICT-enabled urban system.  
> **Analogy:** Sensors/Tags = sensory organs; telecom = nerves; embedded intelligence = brain; software = cognition.  
> **Six areas:** Economy, Governance, People, Mobility, Environment, Living.  
> **Challenges:** security/privacy, heterogeneity, reliability, scale, legal/social, big data, sensor networks.  
> **Data fusion:** combine multi-source data for better precision/accuracy.  
> **Fusion traps:** imperfection / ambiguity / conflicts / alignment.  
> **Levels:** signal → pixel → feature → decision.  
> **Parking:** information collection → deployment → service dissemination.  
> **Energy:** ambient vs dedicated.  
> **HAN:** UPnP, DLNA, KNX, LonWorks, ZigBee, X-10; remember ZigBee = 802.15.4 PHY/MAC, X-10 = power lines.  
> **V2X:** vehicles communicate with vehicles, pedestrians and infrastructure.  
> **TCP/IP issue:** endpoint/location-oriented.  
> **CCN:** content-centric + hierarchical names + caching.  
> **VANET:** DSRC/WAVE, dynamic topology, unstable connectivity.  
> **ICV:** 75 MHz / 5850–5925 MHz / DSRC.  
> **Phases:** 1 = 2G/3G infotainment, 2 = 4G LTE/DSRC intelligent transport, 3 = cloud-connected vehicles.  
> **Domains:** in-vehicle, ad-hoc, infrastructure.  
> **Ad-hoc:** OBUs mobile + RSUs static + V2V/V2I.  
> **V2X privacy:** tracking, localization, personal data, loss of control.

---

# PART K — FINAL EXAM STRATEGY

## Priority 1 — Learn the 15 assignment answers

Do not merely memorize letters. Memorize the **concept-to-answer mapping**:

- Sensory organs
- Smart Economy
- Smart Parking
- Security & Privacy
- Data fusion
- Conflicts
- Signal level
- Information Collection
- Dedicated harvesting
- ZigBee
- X-10
- TCP/IP limitation
- 75 MHz
- Phase-2
- Ad-hoc domain

## Priority 2 — Master comparison tables

Especially:

- Smart-city challenges
- Data-fusion challenges
- Data-fusion levels
- HAN standards
- TCP/IP vs CCN
- ICV phases
- VANET domains

## Priority 3 — Memorize numbers and standards

**75 MHz, 5850–5925 MHz, DSRC, IEEE 802.11p, IEEE 1609, 2G/3G, 4G LTE/DSRC.**

## Priority 4 — Scenario recognition

If question says:

- **Multi-tenancy leakage** → Security & Privacy
- **Different sensor values at same place** → Conflicts
- **Sensor-node fusion** → Signal level
- **Intentional nearby energy source** → Dedicated
- **Power-line home control** → X-10
- **4G LTE/DSRC intelligent transport** → Phase-2
- **OBUs + RSUs + V2V/V2I** → Ad-hoc
- **Tracking vehicle movement** → V2X privacy
- **Content instead of location** → CCN

---

# PART L — SOURCE BASIS

This Week-10 file is grounded in the uploaded course materials:

1. **Assignment_10(1).pdf** — all 15 assignment questions, answer keys, and assignment explanations. fileciteturn104file0L10-L21
2. **Week-10.pdf** — Smart Cities and Smart Homes Parts I–III and Connected Vehicles Parts I–II, including smart-city concepts, data fusion, HANs, energy harvesting, V2X, CCN, VANETs, ICVs, IEEE 1609, and domain classifications. fileciteturn104file1L415-L475
3. **Cumulative mock exams available in the uploaded files** — used only for directly supported Week-10-style cross-checks, notably V2X privacy/movement tracking. fileciteturn107file6L597-L614

> **Important:** No outside web research or invented questions were used to fill unsupported gaps. Where the lecture is primarily diagrammatic, the notes preserve the terminology and concepts explicitly supported by the uploaded material.

---

# FINAL ONE-PAGE REVISION

## Smart City
**ICT + interactive + accessible + efficient**

## Analogy
**Sensors/Tags → Sensory organs**  
**Telecom → Nerves**  
**Embedded intelligence → Brain**  
**Software → Cognition**

## Six focus areas
**Economy – Governance – People – Mobility – Environment – Living**

## Data fusion
**Purpose:** precision + accuracy + better decisions

**Challenges:**
- Imperfection
- Ambiguity
- Conflicts
- Alignment
- Trivial features

**Levels:**
- Signal → sensor/local network
- Pixel → imaging device
- Feature → before decision
- Decision → ensemble

## Smart parking
**Information Collection → System Deployment → Service Dissemination**

## Energy
**Ambient:** RF/wind/sun/heat/vibration  
**Dedicated:** intentionally deployed source near IoT device

## HAN
**UPnP:** discovery/zero config  
**DLNA:** media sharing  
**KNX:** home/building network  
**LonWorks:** Neuron chip  
**ZigBee:** 802.15.4 PHY/MAC  
**X-10:** power lines

## V2X
**V2V + V2I + V2P + infrastructure**

## TCP/IP problem
**Single-pair + location/endpoint orientation**

## CCN
**Content-centric + hierarchical naming + caching**

## VANET
**DSRC/WAVE + dynamic topology + unstable connectivity**

## ICV
**75 MHz = 5850–5925 MHz**  
**DSRC**

## ICV phases
**1:** 2G/3G + infotainment  
**2:** 4G LTE/DSRC + intelligent transport  
**3:** cloud-connected

## VANET domains
**In-Vehicle:** inside vehicle  
**Ad-hoc:** mobile OBUs + static RSUs + V2V/V2I  
**Infrastructure:** RSUs + gateways + Internet/cellular

## V2X privacy
**Tracking + localization + personal data + loss of control**

---

**END OF WEEK 10 NOTES**
