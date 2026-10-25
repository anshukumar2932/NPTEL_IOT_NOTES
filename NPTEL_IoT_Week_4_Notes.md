# NPTEL Introduction to Internet of Things — Week 4 Notes

> **Priority rule:** Assignment questions are the highest priority. After the assignment, all major topics from the Week-4 lecture PDF are covered so that no lecture topic is skipped.
>
> **Materials used:** Week-4 Assignment + Week-4 lecture PDF (Sensor Networks Part III, Part IV, Part V, UAV Networks, Machine-to-Machine Communication).

---

# ⭐ 1. ASSIGNMENT-FIRST REVISION

## Q1. Ultrasonic Sensor in AID

**Question:** What does the ultrasonic sensor measure generally in the AID system?

**Answer: B — Distance of the object**

### Concept
In the **Agricultural Intrusion Detection (AID)** system:
- **PIR sensor** detects an intruder entering the field.
- **Ultrasonic sensor** measures the distance at which the detected object is located.

**Exam memory:** `AID → PIR detects → Ultrasonic measures distance`

---

## Q2. Data Processing in AID

**Question:** Which component processes data received from sensors?

**Answer: C — Microcontroller**

### Concept
The microcontroller receives/processes sensor data in the AID system.

**Memory:** `Sensors → Microcontroller → further action/communication`

---

## Q3. Communication of Nanodevices

**Question:** How can standard nanodevices communicate?

**Answer: A and B**
- **Electromagnetic communication**
- **Molecular communication**

### Trap
- Wired Ethernet ❌
- ZigBee communication ❌

**Memory:** `Nanonetworks → EM + Molecular`

---

## Q4. Coverage Guarantees Connectivity

**Question:** When does sensing coverage guarantee network connectivity?

**Answer: A — Transmission range ≥ 2 × sensing range**

### Formula
\[
r_t \geq 2r_s
\]

where:
- `r_t` = transmission range
- `r_s` = sensing range

### Important theorem
If the transmission range is at least twice the sensing range, **coverage implies connectivity**.

---

## Q5. Coverage Problem in Static WSN

**Question:** Which is a coverage problem in a static WSN?

**Answer: A — Area coverage**

### Three important static-WSN coverage problems
1. **Area coverage**
2. **Point coverage**
3. **Barrier coverage**

---

## Q6. Forest-Fire Reporting

**Question:** Which reporting method is used for forest-fire monitoring?

**Answer: A — Event-driven reporting**

### Why?
The sensor network reports when a relevant event occurs, such as a fire.

### Compare
- Forest fire → **Event-driven**
- Inventory control → **On-demand**

**Memory:** `Fire → Event`

---

## Q7. Data Mule

**Question:** What does a data mule do?

**Answer: C — Collects data and carries it to the sink**

### Concept
A **data mule** is a mobile entity that:
1. Visits sensor nodes.
2. Collects their data.
3. Moves toward the sink.
4. Delivers the collected data.

**Memory:** `Data Mule = Collect + Carry + Deliver`

---

## Q8. Failure of Critical Stationary Node

**Question:** What may happen if a critical stationary sensor node fails?

**Answer: A — The network may be partitioned**

### Why?
Stationary nodes cannot automatically move to repair a broken topology. Failure of a critical node can split the network into disconnected parts.

**Memory:** `Stationary node failure → possible network partition`

---

## Q9. Human-Centric Sensing

**Question:** A person who provides sensing information acts as a:

**Answer: D — Data source**

### Human-centric sensing roles
1. **Sensing target** — the human is being sensed.
2. **Sensor operator** — the human operates sensors/apps.
3. **Data source** — the human provides/disseminates information.

**Assignment trap:** A person providing information is specifically a **data source**.

---

## Q10. Advantage of Stationary WSN

**Question:** Which is an advantage of a stationary wireless sensor network?

**Answer: A — Easy topology maintenance**

### Why?
Nodes remain fixed, so topology/deployment is comparatively easier.

### Important contrast
Stationary WSN:
- Easy deployment/topology maintenance
- Node failure can partition the network
- Topology cannot automatically change through node movement

---

## Q11. UAV Topology Changes

**Statement:** In a UAV network, topology may change frequently because UAVs are mobile.

**Answer: TRUE**

### Why?
UAV movement changes:
- Relative positions
- Communication links
- Network topology

**Memory:** `UAV mobility → dynamic topology`

---

## Q12. Common UAV Issue

**Question:** Which is a common issue in UAV networks?

**Answer: A — Frequent topology changes**

Other important UAV issues:
- UAV malfunction
- Intermittent links
- Lack of suitable routing algorithms

---

## Q13. M2M vs Traditional SCADA

**Question:** Compared with traditional SCADA, M2M supports:

**Answer: D — Cross-platform integration**

### Key difference
- Traditional SCADA → commonly isolated systems using proprietary solutions.
- M2M → designed for **cross-platform integration**.

**Memory:** `SCADA → isolated/proprietary | M2M → cross-platform`

---

## Q14. Stationary WSN Nodes Moving After Failure

**Statement:** In a stationary WSN, sensor nodes can automatically move to restore connectivity after node failure.

**Answer: FALSE**

### Why?
Stationary sensor nodes are fixed. They cannot physically move to repair connectivity.

**Memory:** `Stationary = fixed`

---

## Q15. Definition of M2M

**Question:** Which statement best describes M2M communication?

**Answer: A — Devices can exchange data without direct human control**

### Definition
M2M is communication between machines/devices with computing and communication facilities, designed to operate without direct human intervention.

Human intervention may still be needed for:
- Maintenance
- Operational stability
- Sustainability

---

# 🔥 2. ASSIGNMENT-DERIVED MUST-MEMORIZE FACTS

1. **AID:** PIR detects intruder; ultrasonic sensor measures distance.
2. **Microcontroller:** processes AID sensor data.
3. **Nanonetwork communication:** electromagnetic + molecular.
4. **Coverage ⇒ connectivity:** `r_t ≥ 2r_s`.
5. Static WSN coverage problems = **area, point, barrier**.
6. Forest-fire monitoring = **event-driven reporting**.
7. Inventory control = **on-demand reporting**.
8. Data mule = **collects data and carries it to sink**.
9. Critical stationary-node failure → **network partition**.
10. Human providing information = **data source**.
11. Stationary WSN advantage = **easy topology maintenance**.
12. Stationary WSN nodes **do not move automatically**.
13. UAVs → **frequent topology changes**.
14. M2M → **cross-platform integration**.
15. M2M → machine/device communication without direct human control.

---

# 📚 3. COMPLETE PPT / LECTURE COVERAGE

# 3.1 Target Tracking in Sensor Networks

The lecture presents three target-tracking formulations.

### Push-based
- Sensor nodes compute the position of the target.
- Nodes periodically notify the sink.
- A **cluster structure** is commonly used.

### Poll-based
- Nodes register the presence of the target.
- A low-cost query can be issued.
- Data is sent toward the sink only when a query needs to be answered.
- A **tree structure** is commonly used.

### Guided
- Beacon nodes define a trajectory toward the target.
- The tracker follows the trail to intercept the target.
- A **face structure** is often used.

### Memory
`Push → periodic reports`
`Poll → report when queried`
`Guided → beacon-defined trajectory`

---

# 3.2 WSNs in Agriculture — AID

**AID = Agricultural Intrusion Detection**

A set of sensor nodes is deployed across an agricultural field.

Each board uses:
- **PIR sensor**
- **Ultrasonic sensor**

### Operation
1. Intruder enters the field boundary.
2. PIR detects the object.
3. Ultrasonic sensor measures object distance.
4. Microcontroller processes sensor information.
5. Information can be communicated through the network.

**Exam focus:** Q1 + Q2.

---

# 3.3 Wireless Multimedia Sensor Networks (WMSNs)

WMSNs add low-cost cameras to wireless sensor nodes.

## Camera Sensor (CS) Nodes
- Capture multimedia data:
  - Video
  - Audio
  - Scalar information
- More expensive/resource hungry.
- Directional sensing range.

## Scalar Sensor (SS) Nodes
- Sense scalar data:
  - Temperature
  - Light
  - Vibration
- Omni-directional sensing range.
- Lower cost.

### Typical WMSN composition
- Smaller number of CS nodes.
- Larger number of SS nodes.

### Applications
- Security surveillance
- Wild-habitat monitoring
- Environmental monitoring

### Why combine CS + SS?
Scalar nodes are cheaper and energy-efficient, while camera nodes can provide more precise information. Combining both can improve sensing and network lifetime.

---

# 3.4 WMSN Topology Management

Video data is:
- Larger in size.
- More bandwidth demanding.
- Higher in battery consumption.

The lecture highlights three important metrics:
1. **Coverage**
2. **Connectivity**
3. **Network lifetime**

A distributed topology-management approach uses **Coalition Formation Game** between CS and SS nodes for event coverage.

---

# 3.5 Nanonetworks

A **nanodevice** contains components with dimensions on the order of nanometers.

The lecture identifies two main communication options:

### 1. Electromagnetic communication
- Uses electromagnetic effects at nanoscale.
- The lecture places EM nanonetwork communication around the **0.1–10 THz** channel range.
- Surface Plasmon Polariton (SPP) is discussed.

### 2. Molecular communication
- Molecules carry information.
- Information can be packed into vesicles.
- Gap junctions can act as mediators between cells and vesicles.

**Assignment focus:** Q3.

---

# 3.6 Underwater Acoustic Sensor Networks

Underwater acoustic networks face special propagation conditions.

### Internal Solitons
In shallow oceanic regions:
- Non-linear internal waves called **solitons** can scatter underwater sound.
- Acoustic communication can interact with these solitons.
- Network performance can be significantly affected.

### Oceanic Forces
Realistic underwater nodes may move due to oceanic forces.

The lecture describes an **Oceanic Forces Mobility Model (OFMM)**:
- Models realistic oceanic forces.
- Allows nodes to move in a **3D ocean column**.

---

# 3.7 3D Localization in Underwater Networks

The lecture discusses localization approaches for mobile underwater sensor networks.

### MobiL
- Silent and energy-efficient.
- Iterative approach.
- Requires fewer anchor/initiator nodes.
- Uses mobility prediction to improve accuracy.
- Lecture highlights **3 surface anchor nodes**.

### HASL
**High-Speed AUV-Based Silent Localization**

Main sequence:
1. Get GPS information.
2. Start dead-reckoning.
3. Broadcast beacon at a constant interval.
4. Nodes silently listen.
5. Receive effective beacon message.
6. Use trilateration.
7. Obtain depth (`z`) from pressure.
8. Estimate sensor location.

---

# 3.8 Opportunistic Localization

Objectives:
- Unlocalized nodes → minimize localization delay.
- Localized nodes → choose transmission power so that the maximum number of nodes can be localized with minimum energy consumption.

This is discussed using a game-theoretic topology-control perspective.

---

# 3.9 Self-Organizing Underwater Architecture

The lecture introduces **Tic-Tac-Toe-Arch**:
- Self-organizing virtual architecture for underwater sensor networks.
- Uses dynamic formation of a virtual topology.
- Calculates duration of connectivity between underwater nodes.

### Virtual topology formation
1. Broadcast `REQ`.
2. Receive `RPLY`.
3. Find neighbors.
4. Calculate connectivity duration `t_d`.
5. Select the best neighbor.
6. Set selected node to active mode for `t_d`.
7. Set duty cycle.
8. Continue the process.

---

# 3.10 WSN Coverage

### Coverage
The area of interest is satisfactorily monitored.

### Connectivity
All nodes are connected so that sensed data can reach the sink.

Sensor coverage studies:
- Where sensors should be deployed.
- Which sensors should be activated.
- How mobile sensor trajectories should be planned.

Two broad cases:
- Static sensors
- Mobile sensors

---

# 3.11 Coverage vs Connectivity

Define:
- `r_s` = sensing range
- `r_t` = transmission range

Important relationship:

\[
r_t \geq 2r_s
\]

When this condition holds:

**Coverage implies connectivity.**

This is one of the most important formulas in Week 4.

---

# 3.12 Reporting in WSNs

The lecture identifies two reporting modes:

## Event-driven
Data is reported when an event occurs.

**Example:** Forest-fire monitoring.

## On-demand
Data is reported when requested.

**Example:** Inventory-control system.

### Design objective
Use a minimum number of sensors while maximizing network lifetime.

---

# 3.13 Coverage Algorithm Types

### Distributed
Nodes compute their positions/decisions using communication with neighbors.

### Centralized
Data is collected at a central point and a global map is computed.

### Localized
A special distributed approach where only a subset of nodes participate in sensing, communication and computation.

### Deployment methods
- Deterministic
- Random

---

# 3.14 Static WSN Coverage Problems

Three major types:

## Area Coverage
Cover an entire area.

Important concepts:
- Random coverage
- Connected random coverage

A network is connected when active nodes can communicate with one another.

### Key theorem
`R_c ≥ 2R_s → coverage implies connectivity`

---

## Point Coverage
Objective:
- Cover a specified set of points.

Two forms:
- Random point coverage
- Deterministic point coverage

---

## Barrier Coverage
Ensures that movement through a monitored region encounters sufficient sensors.

Types:
- **1-barrier** → at least 1 sensor
- **2-barrier** → at least 2 sensors
- **K-barrier** → at least K sensors

---

# 3.15 Coverage Maintenance and Crossings

A continuous region is considered covered when:
- Crossings exist in the region.
- Every crossing is covered.

### Crossing
An intersection point:
- Between sensor coverage-disk boundaries, or
- Between monitored-space boundary and a coverage-disk boundary.

A crossing is covered if it lies inside at least one sensor's coverage disk.

---

# 3.16 Optimality Conditions

For minimizing overlap while covering crossings, the lecture gives geometric conditions.

If A and B are fixed:
- Node C should be positioned such that `OR = OQ`.

If A, B and C can all move:
- `OP = OR = OQ`.

If all nodes have the same sensing range:
- Distance between them is `√3 × r_s`.

---

# 3.17 OGDC — Optimal Geographical Density Control

OGDC is a distributed/localized coverage algorithm.

### Basic process
1. A node volunteers as a starting node.
2. It broadcasts an ideal direction.
3. Another node close to the desired distance/angle becomes active.
4. Nodes continue covering uncovered crossings.
5. Nodes causing minimum overlap are preferred.
6. A node sleeps if its coverage area is already completely covered.
7. Process repeats for subsequent rounds.

### Starting node selection
- Each node participates with probability `p`.
- Chooses a random back-off time.
- If it hears nothing from neighbors, it declares itself the starting node.
- It announces position and preferred direction.

### Memory
`OGDC → choose starting node → optimal distance/angle → cover crossings → sleep redundant nodes`

---

# 3.18 Stationary Wireless Sensor Networks

### Characteristics
Sensor nodes are static.

### Advantages
- Easy deployment.
- Nodes can be placed at optimized distances.
- Can reduce total number of nodes.
- Easy topology maintenance.

### Disadvantages
- Node failure can partition the network.
- Topology cannot automatically change through movement.

**Assignment focus:** Q8, Q10, Q14.

---

# 3.19 Mobile Wireless Sensor Networks (MWSNs)

MWSN can be viewed as a combination of:
- Mobile networking ideas from MANETs.
- Sensor-network sensing capabilities.

MANET properties recalled in the lecture:
- Self-configure
- Self-heal
- Self-optimize
- Self-protect

---

# 3.20 Components of MWSN

## Mobile Sensor Nodes
- Sense physical parameters.
- When they come close to the sink, they deliver data.

## Mobile Sink
- Moves to collect data from sensor nodes.
- Movement is based on an algorithm.

## Data Mule
- Mobile entity.
- Collects data from sensor nodes.
- Travels to the sink.
- Delivers collected data.

**Assignment focus:** Q7.

---

# 3.21 Types of MWSNs

## Underwater MWSNs
- Sensors operate under water/sea.
- Can connect with AUVs.
- Applications:
  - Marine-life monitoring
  - Water-quality monitoring

## Terrestrial MWSNs
- Nodes deployed on land.
- Can connect with UAVs.
- Applications:
  - Wildlife monitoring
  - Surveillance
  - Object tracking

## Aerial MWSNs
- Nodes fly in the air.
- UAVs are the typical example.
- Applications:
  - Surveillance
  - Multimedia data gathering

---

# 3.22 Mobile Entities in Daily Life

### Humans
- Mobility is difficult to predict.
- Smartphones can gather information and deliver it to access points.

### Vehicles
- Can carry sensors.
- Sense data at different geographical locations.
- Can transmit to Road Side Units (RSUs).

### Mobile Robots
- Controllable sensor nodes.
- Collect data according to predefined instructions.
- Deliver data to a specified unit.

---

# 3.23 Human-Centric Sensing

Modern smartphones/PDAs contain sensors such as:
- Accelerometer
- Gyroscope

This enables:
- Participatory sensing
- People-centric sensing
- Opportunistic sensing

### Basic idea
1. Humans carry sensor-equipped devices.
2. Devices move through the environment.
3. Embedded sensors collect readings.
4. Readings are transmitted.

---

## Three Human Roles

### 1. Sensing Target
Human is being sensed.

Example:
- Personal health monitoring.

### 2. Sensor Operator
Human operates sensors/apps.

### 3. Data Source
Human provides or disseminates information without necessarily using a sensor.

Example:
- Social-network updates.

**Assignment:** Q9 → **Data source**

### Challenges
- Device energy
- Participant selection
- User privacy

---

# 3.24 Participatory Sensing

Proposed by Burke et al. in 2006.

It is distributed sensing using devices carried by people.

Goals:
- Collect information.
- Allow ordinary people to access data.
- Allow knowledge sharing.

Data can provide:
- Quantitative measurements, e.g. CO₂ level.
- Authenticity/verification through geo-tagging and timestamps.

---

# 3.25 Delay-Tolerant WSNs

Delay-tolerant networks may experience:
- No end-to-end communication path.
- High latency.
- Asymmetric data rates.
- Erroneous channels.

Data mules can help move information physically between disconnected parts of a network.

### Memory
`No continuous path + store/carry/forward → delay-tolerant networking`

---

# 3.26 UAV Networks

UAV networks use unmanned aerial vehicles as network nodes.

## Important features
- Mesh or star networks.
- Flexible deployment.
- SDN can support service management.
- Routing should be adaptive.
- Large coverage area.
- Multi-tasking.
- Easy reconfiguration for different missions.
- Can contribute to greener networking.

---

# 3.27 UAV Network Issues

Major issues:
1. Frequent topology changes.
2. Changing relative UAV positions.
3. UAV malfunction.
4. Intermittent links.
5. Lack of suitable routing algorithms.

### UAV constraints
- Frequent link breakages.
- Malfunction risk.
- High power requirements.
- High complexity.
- Environmental effects such as wind and rain.

### UAV advantages
- High reliability.
- High survivability.
- More tolerant of a single malfunction.
- Cost-effective.
- Efficient.
- Faster missions.

**Assignment focus:** Q11 + Q12.

---

# 3.28 UAV Topologies

## Star Configuration
- UAV directly connected to ground station.
- Centralized.
- Single-hop.
- Highly dependent on ground station.
- Can have high latency.

## Multi-star
- Multiple star groups.
- One node from each group connects to ground station.

## Flat Mesh
- Nodes interconnected.
- Flexible.
- Reliable.
- Multi-hop.

## Hierarchical Mesh
- Layered mesh structure.
- More structured communication.

### Star vs Mesh

| Star | Mesh |
|---|---|
| Central control point | May be decentralized/ad hoc |
| Single hop | Multi-hop |
| Less self-configuring | Self-configuring |
| More dependent on central point | Nodes relay traffic |
| Infrastructure-based | Infrastructure or ad hoc |

---

# 3.29 FANET — Flying Ad Hoc Networks

FANETs form networks using UAVs.

### Benefits
- Longer communication range.
- Better line-of-sight propagation.
- More environment-resilient communication.

UAVs can operate:
- In the same plane.
- At different altitudes.

Each UAV must be aware of other UAVs to reduce collision risk.

### Applications
- Disaster-time networking.
- Post-disaster emergency communication.

---

## FANET Communication Types

- Inter-plane communication.
- Intra-plane communication.
- FANET ↔ ground station.
- FANET ↔ ground sensors.
- FANET ↔ VANET.

---

# 3.30 Ad-Hoc FANETs

UAV-to-UAV links are called **A2A links**.

Possible radio interfaces:
- XBee-PRO / IEEE 802.15.4
- Wi-Fi / IEEE 802.11

Ground networks may include:
- Stationary WSNs.
- VANETs.
- Control stations.

UAV–WSN links support:
- Collaborative sensing.
- Data muling.

UAV–VANET links can support:
- Visual guidance.
- Data muling.
- Coverage enhancement.

---

# 3.31 Gateway Selection in FANETs

Important communication requirements:
1. Send sensor data back.
2. Receive control commands.
3. Cooperative trajectory planning.
4. Dynamic task assignment.

Too many UAV-ground connections can cause interference.

Therefore:
- Select a reduced number of UAVs as gateways.
- Gateways connect UAVs to ground infrastructure.

### Selection process
1. Divide coverage area into sub-areas.
2. Adjust sub-area sizes dynamically.
3. Use UAV interconnections and derived metrics.
4. Optimize metrics over iterations.
5. Start by selecting a stable node.
6. Optimize partition parameters.
7. Each UAV can acquire information about UAVs within two hops.

---

# 3.32 Layered Gateway in FANET

In multi-layer UAV topology:
- One gateway may be selected per layer.
- Gateways forward information between layers and ground control.

### Limitation
More layers can increase delay between ground control and higher layers.

Therefore it is not suitable for highly time-critical relaying.

---

# 3.33 Trajectory Control for UAV Throughput

UAVs with queue occupancy above a threshold can experience:
- Congestion
- Communication delay

The control station can:
- Instruct UAVs to change trajectory centers.
- Base commands on traffic at busy links.
- Change trajectory radius to improve coverage.

**Memory:** `Congestion → trajectory adjustment → better throughput/delay`

---

# 3.34 Machine-to-Machine Communication (M2M)

## Definition
M2M is communication between machines/devices with computing and communication capabilities, generally without direct human intervention.

### Relation to SCADA
- SCADA → often isolated/proprietary systems.
- M2M → cross-platform integration.

**Assignment focus:** Q13 + Q15.

---

# 3.35 M2M Overview

The lecture's M2M flow can be remembered as:

`Sensors → Network → Information Extraction → Processing → Actuation`

This represents the path from sensing physical information to taking an action.

---

# 3.36 M2M Applications

Important application areas:
- Environmental monitoring
- Civil protection
- Public safety
- Supply Chain Management (SCM)
- Energy and utility distribution / smart grid
- Intelligent Transport Systems (ITS)
- Healthcare
- Building automation
- Military
- Agriculture
- Home networks

---

# 3.37 M2M Features

- Large number of devices.
- Low cost.
- Energy efficiency.
- Small traffic per individual device.
- Large collective quantity of data.
- Communication without direct human intervention.
- Human intervention may still be needed for operational stability and sustainability.

---

# 3.38 M2M Node Types

Three broad categories:

## Low-End Sensor Nodes
- Cheap.
- Low capability.
- Static.
- Energy efficient.
- Simple.
- High-density deployment can improve lifetime/survivability.
- Resource constrained.
- No IP support.
- Basic functions:
  - Data aggregation
  - Auto-configuration
  - Power saving
- Commonly used for environmental monitoring.

## Mid-End Sensor Nodes
- More expensive than low-end nodes.
- May be mobile.
- Fewer complexity/energy constraints.
- May support:
  - Localization
  - QoS
  - TCP/IP
  - Power control
  - Traffic control
- Applications:
  - Home networks
  - SCM
  - Asset management
  - Industrial automation

## High-End Sensor Nodes
- Low-density deployment.
- Can handle multimedia/video with QoS requirements.
- Mobility is essential.
- Example: Smartphones.
- Applications:
  - ITS
  - Military
  - Bio/medical

---

# 3.39 M2M Ecosystem

Main entities:
1. Device Providers
2. Internet Service Providers (ISPs)
3. Platform Providers
4. Service Providers
5. Service Users

---

# 3.40 M2M Service Platform (M2SP)

The M2M service-platform architecture separates major functions across:
- Device
- User
- Application
- Access
- Core network

### Device-side functions
- Device profile management
- M2M area-network management
- Device searching

### User-side functions
- User profile management
- Authentication
- Charging

### Application-side functions
- Data collection
- Data control
- Service management
- Connection management

### Access-side functions
- App management
- App searching
- Web portal

---

# 3.41 M2M Device Platform

Functions:
- Provides access to Internet-connected devices.
- Maintains registered-device information.
- Manages device profiles:
  - Location
  - Device type
  - Address
  - Description
- Authentication/authorization key management.
- Monitors device and M2M-area status.
- Controls devices according to status.

---

# 3.42 M2M User Platform

Functions:
- User registration.
- User modification.
- Charging.
- Inquiry.
- Access restriction management.
- Interoperability with device platform.
- Device/network/service administration.

---

# 3.43 M2M Application Platform

Functions:
- Provides integrated services from device data.
- Merges heterogeneous data from multiple devices.
- Creates new services.
- Collects control/processing log data.
- Supports connection management with appropriate networks.

---

# 3.44 M2M Access Platform

Functions:
- Provides application/web access.
- Redirects applications/links to service providers.
- Provides services to M2M devices.
- Manages smart-device applications.
- Registers applications.
- Maps applications to appropriate devices.

---

# 3.45 Non-IP vs IP-Based M2M

## Non-IP M2M
Devices/area networks may use non-IP technologies internally.

## IP-Based M2M
The lecture shows an IP network with:
- Application layer
- Transport layer: TCP/UDP
- Network layer: IP
- MAC/PHY

### Memory
`IP-based M2M → Application + TCP/UDP + IP + MAC/PHY`

---

# 3.46 M2M Area Network Management

Important requirements:
- Fault tolerant.
- Scalable.
- Low cost.
- Low complexity.
- Energy efficient.
- Dynamic configuration.
- Minimized management traffic.

Application dependence includes:
- Data-centric applications.
- Emergency applications.
- Real-time applications.

---

# ⚠️ 4. MCQ/MSQ TRAPS

1. **Ultrasonic sensor detects the intruder itself** → ❌ In AID, PIR detects the intruder; ultrasonic measures distance.
2. **Microcontroller measures ultrasonic distance directly as the sensor** → ❌ It processes sensor data.
3. **Nanodevices use ZigBee as the two lecture communication methods** → ❌ EM + molecular.
4. **Coverage implies connectivity whenever ranges are equal** → ❌ Important condition is `r_t ≥ 2r_s`.
5. **Only area coverage exists in static WSN** → ❌ Area + point + barrier.
6. **Forest fire = on-demand reporting** → ❌ Event-driven.
7. **Data mule repairs sensors** → ❌ Collects and carries data.
8. **Stationary node failure automatically causes node movement** → ❌ Stationary nodes do not move.
9. **Person providing information = sensor operator** → ❌ Assignment answer: data source.
10. **UAV networks have fixed topology** → ❌ UAV mobility causes frequent changes.
11. **Traditional SCADA is cross-platform by default** → ❌ Lecture contrasts SCADA's isolated/proprietary approach with M2M cross-platform integration.
12. **M2M means humans never intervene for any reason** → ❌ Direct communication can be automatic, but human intervention may be needed for maintenance/stability.
13. **Piconet/scatternet concepts from earlier weeks should be mixed into FANET** → ❌ FANET = Flying Ad Hoc Network.
14. **Star UAV topology is multi-hop by definition** → ❌ Star is centered on a ground/control point; mesh supports multi-hop.
15. **Data mule and mobile sink are identical** → ❌ Both are mobile, but their roles differ: mobile sink moves to collect; data mule collects and carries data to the sink.

---

# 🧠 5. NUMBERS / FORMULAS TO MEMORIZE

| Topic | Fact |
|---|---|
| Coverage-connectivity | **`r_t ≥ 2r_s`** |
| Nanonetwork EM communication | **0.1–10 THz** |
| Static coverage types | **Area, Point, Barrier** |
| Barrier coverage | 1-barrier / 2-barrier / K-barrier |
| OGDC | Participation probability `p`, back-off based selection |
| Underwater localization | Lecture highlights **3 surface anchor nodes** for MobiL |
| FANET gateway | UAV obtains information within **2 hops** in the described selection process |

---

# 🔥 6. HIGH-PRIORITY COMPARISONS

## Event-Driven vs On-Demand

| Event-driven | On-demand |
|---|---|
| Reports when event occurs | Reports when requested |
| Forest fire | Inventory control |
| Event triggers communication | Query/request triggers communication |

---

## Stationary WSN vs MWSN

| Stationary WSN | MWSN |
|---|---|
| Nodes fixed | Nodes/mobile entities can move |
| Easy topology maintenance | Dynamic topology |
| Failure can partition network | Mobility can help reposition/collect |
| Cannot automatically move | Mobile sensors/sink/data mules possible |

---

## Mobile Sink vs Data Mule

| Mobile Sink | Data Mule |
|---|---|
| Sink itself moves | Mobile entity carries collected data |
| Moves to collect data | Collects from nodes then travels to sink |
| Movement based on algorithm | Store/carry/deliver role |

---

## Star vs Mesh UAV Network

| Star | Mesh |
|---|---|
| Central control point | Interconnected nodes |
| Single-hop | Multi-hop |
| Highly dependent on central point | More flexible/reliable |
| Not self-configuring | Self-configuring |
| Less suitable for autonomous ad hoc behavior | Supports ad hoc operation |

---

## Low-End vs Mid-End vs High-End M2M Nodes

| Low-end | Mid-end | High-end |
|---|---|---|
| Cheap | More expensive | High capability |
| Static | May be mobile | Mobility essential |
| Resource constrained | QoS/TCP-IP possible | Multimedia |
| No IP support | More functionality | Smartphones example |
| Environment monitoring | Home/SCM/industrial | ITS/military/biomedical |

---

# 🚀 7. ONE-PAGE FINAL REVISION

### AID
`PIR → detects intruder`
`Ultrasonic → measures distance`
`Microcontroller → processes sensor data`

### Nanonetworks
`Nanodevices → Electromagnetic + Molecular communication`

### Coverage
`rt ≥ 2rs → coverage implies connectivity`

### Static WSN
`Area + Point + Barrier coverage`

### Reporting
`Forest fire → Event-driven`
`Inventory → On-demand`

### Data Mule
`Sensor nodes → Data mule → Sink`

### Stationary WSN
`Fixed nodes → easy topology maintenance → failure may partition network`

### MWSN
`Mobile sensor nodes + mobile sink + data mule`

### Human-centric sensing
`Target + Operator + Data Source`

### UAV
`Mobility → frequent topology changes`
`Issues → link breakage + malfunction + intermittent links + routing`
`Topologies → Star / Mesh`
`FANET → Flying Ad Hoc Network`

### M2M
`Machines/devices communicate automatically`
`SCADA → isolated/proprietary`
`M2M → cross-platform`
`Sensors → Network → Information Extraction → Processing → Actuation`

### M2M node levels
`Low-end → cheap/static/resource constrained`
`Mid-end → more functionality/QoS/TCP-IP`
`High-end → mobile/multimedia/smartphones`

---

# ⭐ 8. FINAL EXAM PRIORITY ORDER

If time is short, revise in this order:

1. **All 15 assignment questions**
2. `rt ≥ 2rs` coverage-connectivity condition
3. Static WSN coverage: area/point/barrier
4. Event-driven vs on-demand reporting
5. Stationary WSN failure and topology
6. Data mule
7. AID: PIR + ultrasonic + microcontroller
8. Human-centric sensing roles
9. UAV topology and frequent topology changes
10. FANET basics
11. M2M definition and SCADA comparison
12. M2M node types
13. M2M service/device/user/application/access platforms
14. Nanonetwork communication
15. WMSN and underwater sensor-network concepts

---

# 📌 SOURCE / PAGE GUIDE

- **Lecture Part III:** Week-4 PDF pages 1–20 — AID, WMSN, nanonetworks, underwater networks, localization.
- **Lecture Part IV:** pages 21–41 — WSN coverage, coverage-connectivity, reporting, static coverage and OGDC.
- **Lecture Part V:** pages 42–65 — stationary WSNs, MWSNs, data mules, human-centric sensing, participatory sensing and delay-tolerant networks.
- **UAV Networks:** pages 66–86 — UAV issues, topologies, FANETs, gateways and trajectory control.
- **M2M:** pages 87–107 — M2M definition, applications, node types, ecosystem, platforms, IP/non-IP networks and management.

**Week-4 assignment:** 15 questions, 15 marks.
