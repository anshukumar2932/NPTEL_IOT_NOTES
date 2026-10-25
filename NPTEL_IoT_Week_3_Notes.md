# NPTEL Introduction to Internet of Things — Week 3 Notes

> **Study rule for this file:** Assignment questions are given **highest priority**, but all topics from the Week-3 lecture PDF are covered after the assignment section.
>
> **Sources used:** Week-3 lecture PDF and Assignment-Week 3 Solution PDF supplied by the student.

---

# ⭐ 1. ASSIGNMENT-FIRST REVISION

The Week-3 assignment contains **15 MCQ/True-False questions for 15 marks**. These are the highest-priority facts to memorize.

## Q1. Wired HART Network Layer

**Question:** There is no network layer in Wired HART.

**Answer:** **True**

**Why?**
- Wired HART lacks a network layer.
- The main differences between wired and WirelessHART occur in the physical, data-link and network-related functions.

**Exam trap:**  
Do not confuse **Wired HART** with **WirelessHART**. WirelessHART uses network functionality for mesh routing.

**PPT reference:** Lecture Part III, page 4.

---

## Q2. Z-Wave Operating Frequency

**Question:** Z-Wave operates at ______ MHz in the US and ______ MHz in Europe.

**Answer:** **908.42 MHz, 868.42 MHz**

**Memorize:**

| Region | Frequency |
|---|---:|
| US | **908.42 MHz** |
| Europe | **868.42 MHz** |

**PPT reference:** Z-Wave section, page 44.

---

## Q3. Dumb Behavior of Sensor Nodes

**Question:** Dumb behavior of sensor nodes is ______ in nature because it depends on environmental conditions.

**Answer:** **Temporal**

**Why?**
- Under adverse environmental conditions such as high temperature, rainfall or fog, communication range can shrink.
- A node may temporarily sense its surroundings but fail to transmit the sensed data.
- When environmental conditions become favorable, the node can work normally again.

**Key word:** `Dumb behavior = Temporal`

**PPT reference:** Sensor Networks Part II, page 87.

---

## Q4. Interference-Affected Channels

**Question:** The process of identifying channels consistently affected by interference and removing them from use is known as ______.

Options:
- Channel Trimming
- Channel Flushing
- Both
- None

**Answer:** **None of these**

**Correct term:** **Channel Blacklisting**

**Meaning:** Channel blacklisting identifies channels consistently affected by interference and removes them from use.

**Exam trap:**  
If the options do not contain **Channel Blacklisting**, choose **None of these**.

**PPT reference:** WirelessHART Data Link Layer, page 6.

---

## Q5. NFC Full Form

**Question:** Full form of NFC?

**Answer:** **Near Field Communication**

**Memorize exactly:** `NFC = Near Field Communication`

---

## Q6. NFC Working Principle

**Question:** NFC works on the principle of magnetic induction.

**Answer:** **True**

**Why?**
- A reader produces a small electric current.
- This creates a magnetic field.
- The field couples with a coil in the other device and enables communication.

**Key word:** `NFC → Magnetic Induction`

---

## Q7. NFC Supermarket Tags

**Question:** NFC tags found in supermarket products are examples of active NFC.

**Answer:** **False**

**Correct concept:** They are examples of **passive NFC**.

**Passive NFC:**
- Contains information readable by another device.
- Does not independently read information.
- Uses energy from the reader for its response.

**Active NFC:**
- Can collect and transmit information.
- Smartphones are an example of active devices.

---

## Q8. Bluetooth Network

**Question:** Bluetooth is based on ______.

Options include Nanonets/Binarynets.

**Answer:** **None of these**

**Correct term:** **Piconets**

**Memorize:**
- Bluetooth → **Piconet**
- Multiple linked piconets → **Scatternet**

---

## Q9. NFC Reader

**Question:** In NFC, a ______ emits a small electric current that creates the magnetic field bridging the devices.

**Answer:** **Reader**

**Why?**
- The reader generates the magnetic field.
- The receiving coil converts the field into electrical impulses used for communication.

---

## Q10. Bluetooth Ad-Hoc Technology

**Question:** Bluetooth technology is based on Ad-hoc network technology.

**Answer:** **True**

**More specifically:** Bluetooth uses **Ad-hoc Piconets**.

---

## Q11. Z-Wave Modulation and Encoding

**Question:** Z-Wave utilizes GFSK modulation and Hongkong channel encoding.

**Answer:** **False**

**Correct:**
- Modulation = **GFSK**
- Channel encoding = **Manchester**

**Memorize:** `Z-Wave → GFSK + Manchester`

---

## Q12. Z-Wave Dead-Spot Bypassing

**Question:** The process of bypassing radio dead-spots is done using a message called ______ in Z-Wave.

**Answer:** **Healing**

**Concept:**
- Z-Wave uses source-routed mesh networking.
- If devices are not directly in range, messages can be routed through other nodes.
- The process for bypassing radio dead-spots is called **Healing**.

---

## Q13. Sensor Node Battery Life

**Question:** Sensor nodes have unlimited battery life.

**Answer:** **False**

**Correct:** Sensor nodes have **limited battery life**.

**Why important?**
Energy is one of the major constraints in Wireless Sensor Networks.

---

## Q14. Bluetooth Link Manager Protocol

**Question:** The Link Manager Protocol in Bluetooth manages establishment, authentication and link configuration.

**Answer:** **True**

**Memorize:**  
`LMP → establishment + authentication + link configuration`

---

## Q15. ZigBee Data Rate

**Question:** ZigBee commonly uses ______ data rate.

**Answer:** **250 kbps**

**Trap:** It is **kbps**, not Mbps.

---

# 🔥 2. ASSIGNMENT-DERIVED MUST-MEMORIZE LIST

These are the highest-priority Week-3 facts because they are directly tested in the assignment:

1. **Wired HART has no network layer.**
2. **WirelessHART uses mesh networking.**
3. **WirelessHART uses TDMA and channel hopping.**
4. **Channel blacklisting removes interference-prone channels.**
5. **NFC = Near Field Communication.**
6. **NFC works using magnetic induction.**
7. **Supermarket NFC tags = passive NFC.**
8. **NFC reader creates the magnetic field.**
9. **Bluetooth = Ad-hoc Piconets.**
10. **Piconet = Bluetooth short-range network.**
11. **Z-Wave US = 908.42 MHz; Europe = 868.42 MHz.**
12. **Z-Wave = GFSK + Manchester encoding.**
13. **Z-Wave dead-spot bypass = Healing.**
14. **Sensor nodes have limited battery life.**
15. **Dumb behavior = temporal.**
16. **Bluetooth LMP manages establishment, authentication and link configuration.**
17. **ZigBee commonly uses 250 kbps.**

---

# 📚 3. COMPLETE WEEK-3 PPT COVERAGE

# 3.1 WirelessHART

## What is HART?

**HART = Highway Addressable Remote Transducer**

- HART was developed for networked smart field devices.
- WirelessHART is the wireless version/latest release described in the lecture.
- Wireless communication makes HART implementation cheaper and allows devices to be placed in difficult locations.

### Why WirelessHART?

WirelessHART makes device placement easier in locations such as:
- Top of reaction tanks
- Inside pipes
- Widely separated warehouses

### Wired HART vs WirelessHART

| Feature | Wired HART | WirelessHART |
|---|---|---|
| Network layer | **Absent** | Present |
| Physical/data link | Wired | Wireless |
| Routing | Limited by wired structure | Mesh-based |
| Device forwarding | Not the main wireless mechanism | Nodes forward packets |
| Deployment | Cabling required | Easier placement |

---

## WirelessHART Physical Layer

According to the lecture:

- Derived from **IEEE 802.15.4**
- Operates in the **2.4 GHz ISM band**
- Uses **15 channels** to improve reliability

---

## WirelessHART Data Link Layer

Important concepts:

### TDMA
**Time Division Multiple Access** provides deterministic communication by allocating time slots.

### Superframes
- Superframes contain grouped **10 ms time slots**.
- They control transmission timing.
- This supports collision-free and reliable communication.

### Channel Hopping
Nodes change channels to reduce the effect of interference.

### Channel Blacklisting
Channels consistently affected by interference are identified and removed from use.

**Assignment connection:** Q4 directly tests channel blacklisting.

---

## WirelessHART Network and Transport Functions

These functions handle:
- Traffic
- Routing
- Session creation
- Security

WirelessHART uses a **mesh network**.

Each device can forward packets from other devices.

Each device maintains an updated network graph/topology to assist routing.

### Important mapping

`HART network layer = OSI Network + Transport + Session functions`

---

## WirelessHART Application Layer

Responsible for:
- Communication between gateways and devices
- Command and response messages
- Extracting commands
- Executing commands
- Generating responses

The application layer is common/seamless between wired and wireless versions.

---

## WirelessHART Congestion Control

Lecture points:
- Operates in the 2.4 GHz ISM band.
- Channel 26 is removed because of restricted usage in certain areas.
- Interference-prone channels are avoided by switching channels after transmissions.
- Transmission is synchronized using **10 ms slots**.
- Multiple channels can be used during a slot, allowing propagation of multiple packets and reducing collisions.

---

## WirelessHART Network Manager

The Network Manager:
- Supervises network nodes.
- Determines when and where packets should be sent.
- Helps achieve collision-free and timely delivery.
- Maintains neighbor and signal-strength information.
- Determines who sends/listens and which frequency is used in a time slot.
- Handles code-based network security.
- Prevents unauthorized nodes from joining.

---

# 3.2 WirelessHART vs ZigBee

| Topic | WirelessHART | ZigBee |
|---|---|---|
| Channel hopping | Hops after every message | Does not hop per message |
| MAC access | **TDMA** | **CSMA/CA** |
| Topology emphasized | True mesh | Tree topology in the lecture comparison |
| Router behavior | Every node can act as router | Trunk nodes can become critical |
| Back compatibility | Devices described as back compatible | ZigBee variants are otherwise incompatible according to lecture |

### Very important exam distinction

`WirelessHART → TDMA + channel hopping + true mesh`

`ZigBee → CSMA/CA + no per-message hopping`

---

# 3.3 NFC — Near Field Communication

## Definition

NFC is an offshoot of **RFID** designed for communication between devices in close proximity.

Types mentioned:
- Type A
- Type B
- FeliCa

**FeliCa is commonly found in Japan.**

---

## NFC Active vs Passive

### Passive NFC
- Contains information.
- Can be read by another device.
- Cannot independently read information.
- Uses energy from the reader to encode its response.
- Example: supermarket NFC tags.

### Active NFC
- Can collect information.
- Can transmit information.
- Has its own power source in the lecture's description.
- Example: smartphones.

---

## NFC Working Principle

**Principle = Magnetic Induction**

Process:

1. Reader emits a small electric current.
2. Current creates a magnetic field.
3. Magnetic field bridges the physical space.
4. A coil in the client device receives the field.
5. The field is converted back into electrical impulses.
6. Information is communicated.

### Assignment connection
- Q5 → Full form
- Q6 → Magnetic induction
- Q7 → Passive supermarket tags
- Q9 → Reader

---

## NFC Specifications

| Parameter | Value |
|---|---:|
| Frequency | **13.56 MHz** |
| Data rates | **106, 212, 424 kbps** |
| Typical tag storage | **96–512 bytes** |
| Communication range | **< 20 cm** |

---

## NFC Modes

### 1. Peer-to-peer
Two smartphones/devices exchange data.

### 2. Read/Write
An active device reads information from a passive device/tag.

### 3. Card Emulation
An NFC device behaves like a contactless payment/card device.

---

## NFC Applications

- Smartphone-based payments
- Parcel tracking
- Information tags in posters/advertisements
- Computer-game synchronized toys
- Low-power home automation

---

# 3.4 Bluetooth

## Introduction

Bluetooth is:
- Short-range wireless communication technology.
- Intended to replace cables between portable units.
- Designed with security features.
- Based on **Ad-hoc Piconets**.

**Assignment connection:** Q8 and Q10.

---

## Bluetooth Frequency and Hopping

According to the lecture:
- Operates in unlicensed **2.4–2.485 GHz ISM band**.
- Uses spread-spectrum hopping.
- Nominal hopping rate = **1600 hops/sec**.

Lecture examples:
- Version 1.2 → **1 Mbps**
- Version 2.0 → **3 Mbps**

---

## Bluetooth Range Classes

| Class | Approx. range | Typical use |
|---|---:|---|
| Class 3 | **1 m** | Shortest range |
| Class 2 | **10 m** | Common mobile devices |
| Class 1 | **100 m** | Industrial use |

---

## Bluetooth Connection Establishment

### Inquiry
Used to discover nearby Bluetooth devices.

### Paging
Used to establish a connection between two Bluetooth devices.

### Connection
After connection, the device can participate actively or enter a low-power state.

---

## Bluetooth Modes

### Active
Device actively transmits/receives.

### Sniff
Device sleeps and listens only at a defined interval.

### Hold
Power-saving mode where the device sleeps for a defined period and later returns to active mode.

### Park
Slave becomes inactive until the master instructs it to become active again.

---

# 3.5 Bluetooth Protocol Stack

Important components shown in the lecture include:

- Application
- Audio
- Baseband
- L2CAP
- RFCOMM
- SDP
- Other protocol/adaptation components

## Baseband

Baseband is the physical layer of Bluetooth.

Functions:
- Manages physical channels and links
- Error correction
- Data whitening
- Hop selection
- Bluetooth security
- Manages asynchronous and synchronous links
- Handles packets, paging and inquiry

---

## L2CAP

**L2CAP = Logical Link Control and Adaptation Protocol**

Functions:
- Sits over Baseband.
- Resides in the data-link layer.
- Multiplexes multiple logical connections.
- Supports connection-oriented and connectionless services.
- Protocol multiplexing.
- Segmentation and reassembly.
- Group abstractions.

---

## RFCOMM

**RFCOMM = Radio Frequency Communications**

Functions:
- Cable replacement protocol.
- Generates a virtual serial data stream.
- Provides binary data transport.
- Emulates EIA-232/RS-232 control signals.
- Acts as serial-port emulation.
- Provides a simple reliable stream similar to TCP.
- Lecture states support for up to **60 simultaneous connections between two Bluetooth devices**.

---

## SDP

**SDP = Service Discovery Protocol**

Functions:
- Allows applications to discover available services and features.
- Handles dynamic Bluetooth environments.
- Uses a request/response model.
- Can operate over reliable packet transfer.

---

# 3.6 Piconets and Scatternets

## Piconet

A Bluetooth short-range ad-hoc network.

Basic structure:
- One master
- Up to **7 slaves** clustered around the master

The device that initiates establishment becomes the master.

The master controls transmission using time slots.

### Important Piconet facts

- Master clock and unique **48-bit address** determine timing and hopping sequence.
- No direct slave-to-slave connection.
- Communication occurs master-to-slave or slave-to-master.
- Slaves transmit after being polled by the master.
- A device can participate in multiple piconets.

---

## Scatternet

A collection of linked piconets.

A device can:
- Be a slave in one piconet.
- Be a master in another piconet.
- It cannot be a master in more than one piconet according to the lecture.

Devices connecting adjacent piconets can form a larger physically extensible network called a **Scatternet**.

### Memory

`Piconet = one Bluetooth ad-hoc network`

`Scatternet = linked piconets`

---

## Bluetooth Applications

- Audio players
- Home automation
- Smartphones
- Toys
- Hands-free headphones
- Sensor networks

---

# 3.7 Z-Wave

## Introduction

Z-Wave is a protocol for communication among devices used in **home automation**.

Features:
- Uses RF for signaling/control.
- Uses mesh topology.
- Lecture states support for **232 nodes** in a network.

### Assignment frequency

- US → **908.42 MHz**
- Europe → **868.42 MHz**

---

## Z-Wave Global Frequencies

The lecture gives several regional values:

| Region | Frequency mentioned |
|---|---|
| India | **865.2 MHz** |
| Malaysia | **868.1 MHz** |
| Europe | **868.42 / 869.85 MHz** |
| China/Korea | **868.4 MHz** |
| Russia | **869.0 MHz** |
| USA | **908.4 / 916.0 MHz** |
| Israel | **915.0–926.0 MHz** |
| Hong Kong | **919.8 MHz** |
| Australia/New Zealand | **921.4 / 919.8 MHz** |
| Japan | **922.0–926.0 MHz** |

For the exam, **memorize the assignment values first: US 908.42 MHz, Europe 868.42 MHz.**

---

## Z-Wave Modulation and Network IDs

### Modulation
**GFSK = Gaussian Frequency Shift Keying**

### Encoding
**Manchester encoding**

**Assignment connection:** Q11.

### Network

A central network controller:
- Sets up the network.
- Manages the network.

Each logical network has:
- One **Home/Network ID**
- Multiple **Node IDs**

Nodes with different Home IDs cannot communicate.

ID lengths:
- Network ID = **4 bytes**
- Node ID = **1 byte**

---

## GFSK

**GFSK = Gaussian Frequency Shift Keying**

Basic idea:
- Baseband pulses pass through a Gaussian filter before modulation.
- Filtering smooths the pulse stream.
- This is called **pulse shaping**.
- Pulse shaping limits the modulated spectrum width.

---

## Z-Wave Routing and Healing

Z-Wave uses source-routed mesh topology with one primary controller.

If devices are in range:
- They communicate directly.

If devices are not in range:
- Messages can be routed through other nodes.
- This helps bypass obstructions created by household appliances/layout.

### Healing
The process of bypassing radio dead-spots is called **Healing**.

**Assignment connection:** Q12.

The lecture describes Z-Wave as a static network, so mobile devices are excluded and static devices are considered.

---

## Z-Wave vs ZigBee

The lecture emphasizes:

| Z-Wave | ZigBee |
|---|---|
| User-friendly | More customizable for technical users |
| Simple setup/maintenance | Open-standard ecosystem |
| Described as more expensive | Described as cheaper |
| Used for secure/easy home automation | Low-power operation emphasized |
| Source-routed mesh | ZigBee uses its own networking approaches |

**Exam strategy:** Do not memorize every descriptive comparison before the assignment facts. Prioritize frequency, GFSK, Manchester, Home ID/Node ID and Healing.

---

# 3.8 ISA 100.11A

## Introduction

**ISA = International Society of Automation**

ISA 100.11A is designed mainly for:
- Large-scale industrial complexes
- Industrial plants

The lecture describes support for:
- Native and tunneled application layers
- Reliable transport
- Best-effort transport
- Real-time services

---

## ISA 100.11A Protocol Structure

### Network and Transport
Based on:
- **TCP or UDP / IPv6**

### Data Link
Supports:
- Mesh routing
- Frequency hopping

### Physical and MAC
Based on:
- **IEEE 802.15.4**

### Supported topologies
- Star/tree
- Mesh

### Permitted network types
- Radio link
- ISA over Ethernet
- Field buses

---

## Application Support Layer

Provides communication services to:
- User processes
- Management processes

Supports native objects such as:
- Methods
- Attributes

Also supports tunneling for legacy data.

---

## Device Types

The lecture diagram uses:
- **RD** = Routing Device
- **NRD** = Non-Routing Device
- **H** = Handheld Device
- **B** = Backbone Device

---

## ISA 100.11A Features

- Flexibility
- Multiple protocol support
- Open standards
- Multiple application support
- Reliability
- Error detection
- Channel hopping
- Determinism
- TDMA
- QoS support
- Security

---

## ISA 100.11A Security

Security is built into the standard.

Includes:
- Authentication
- Confidentiality
- Network security manager for key management/distribution

Two security steps:
1. Data-link layer encrypts each hop.
2. Transport layer secures peer-to-peer communication.

---

## ISA 100.11A Usage Classes

| Class | Category/application |
|---:|---|
| 0 | Emergency action — always critical |
| 1 | Closed-loop regulatory control — often critical |
| 2 | Closed-loop control — usually non-critical |
| 3 | Supervisory control |
| 4 | Open-loop control / alerting |
| 5 | Logging/downloading — no immediate operational consequence |

---

# 3.9 Wireless Sensor Networks (WSNs)

## Definition

A WSN consists of a large number of sensor nodes densely deployed over an area.

Sensor nodes:
- Collaborate with one another.
- Measure environmental conditions.
- Examples: light, temperature, sound, vibration.
- Convert sensed measurements into digital signals.
- Process the measurements to reveal properties of surrounding phenomena.

Because radio transmission range is short:
- Intermediate nodes act as relays.
- Data reaches a **sink node** through a **multi-hop path**.

---

## Basic Components of a Sensor Node

The lecture diagram shows:

- **Location Finding Unit**
- **Sensing Unit**
- **Transceiver**
- **Processor**
- **Storage**
- **Power**

### Remember the architecture

`Sense → Process → Store/Communicate → Power support`

The exact lecture diagram also includes a **Location Finding Unit**.

---

## Sensor Node Characteristics

Sensor nodes are:
- Multifunctional
- Application-dependent in number
- Short-range
- Often run an OS such as **TinyOS**
- Battery-powered
- Limited in lifetime

**Assignment connection:** Q13.

---

## Constraints on Sensor Nodes

- Very small size, typically less than a cubic centimeter
- Extremely low power consumption
- Unattended operation
- Dense deployment
- Low production cost
- Dispensable
- Autonomous
- Adaptive to the environment

---

## WSN Applications

The lecture gives examples including:
- Temperature measurement
- Humidity
- Lighting condition
- Air pressure
- Soil makeup
- Noise level
- Vibration

---

# 3.10 WSN Detection Scenarios

The lecture illustrates different combinations of sources and objects:

### Single Source — Single Object
One source detects one object.

### Single Source — Multiple Objects
One source detects multiple objects.

### Multiple Sources — Single Object
Multiple sources observe one object.

### Multiple Sources — Multiple Objects
Multiple sources observe multiple objects.

These diagrams emphasize that WSN sensing can involve different combinations of sensing sources and detected objects.

---

# 3.11 Challenges in WSNs

## Scalability

A network must provide acceptable service even with a large number of nodes.

The lecture gives the relationship:

`Throughput ≈ 1/N`

where `N` is the number of nodes.

---

## Quality of Service (QoS)

QoS may require guarantees for:
- Bandwidth
- Delay
- Jitter
- Packet-loss probability

Challenges:
- Limited bandwidth
- Unpredictable RF channel characteristics

---

## Energy Efficiency

- Nodes have limited battery power.
- Nodes cooperate to relay information.
- Relaying consumes energy.

---

## Security

WSNs use an open medium.

Nodes can be vulnerable to:
- Malicious attacks
- Infiltration
- Eavesdropping
- Interference

---

# 3.12 Sensor Web

The lecture introduces **Sensor Web** and service-oriented sensor-web concepts.

Important service terms shown:

- **WNS** = Web Notification Services
- **SCS** = Sensor Collection Services
- **SPS** = Sensor Planning Services
- **SensorML** = Sensor Modeling Language

---

## Sensor Web Entanglement

Important components:
- O&M = Observations & Measurements
- SensorML = Sensor Model Language
- TML = Transducer Model Language
- SOS = Sensor Observation Service
- SPS = Sensor Planning Service
- SAS = Sensor Alert Service
- WNS = Web Notification Services

---

# 3.13 Cooperation in Wireless Ad-Hoc and Sensor Networks

Nodes communicate with other nodes using intermediate nodes.

Intermediate nodes act as **relays**.

Important characteristics:
- Wireless nodes are energy-constrained.
- Nodes may cooperate or may not cooperate.

---

## Two Extremes of Cooperation

### Total Cooperation
All relay requests are accepted.

Problem:
- Nodes quickly exhaust limited energy.

### Total Non-Cooperation
No relay requests are accepted.

Problem:
- Network throughput falls rapidly.

### Core tradeoff

`Node lifetime ↔ Network throughput`

Other issues:
- Selfishness
- Self-interest
- Symbiotic dependence

---

# 3.14 Security Challenges in Cooperation

Security challenges include:
- Open/shared radio medium
- Dynamically changing node positions
- Lack of centralized management/certification authority
- Malicious nodes
- Infiltration
- Eavesdropping
- Interference
- Node capture/compromise
- False routing information
- Attacks against cooperating nodes

A compromised node can potentially send false routing information and disrupt the network.

---

# 3.15 Node Behavior in WSNs

The lecture classifies nodes into:

```text
Node
├── Normal
└── Misbehaving
    ├── Unintentional
    │   ├── Failed
    │   └── Badly Failed
    └── Intentional
        ├── Selfish
        └── Malicious
```

## Normal Node
Works correctly under ideal environmental conditions.

## Failed Node
Unable to perform an operation, possibly because of:
- Power failure
- Environmental events

## Badly Failed Node
Shows failure characteristics and may also send false routing messages.

## Selfish Node
Unwilling to cooperate when cooperation has a personal cost.

Main attack mentioned:
- **Packet dropping**

## Malicious Node
Intentionally tries to disrupt correct routing operation and deny network service.

---

# 3.16 Dynamic Misbehavior — Dumb Behavior

This is an important assignment topic.

### What happens?

Under adverse environmental conditions:
- Temperature may be high.
- Rainfall/fog may occur.
- Communication range shrinks.
- A sensor may still sense the environment.
- It may temporarily be unable to transmit sensed information.

When favorable conditions return:
- The node works normally again.

### Key property

**Dumb behavior is temporal in nature.**

### Why?

Because it depends on environmental conditions and can disappear when those conditions improve.

---

# 3.17 Detection and Connectivity Re-establishment

Dumb nodes can reduce overall network performance.

Therefore:
1. Detect dumb nodes.
2. Re-establish connectivity.
3. Restore useful information flow.

The lecture mentions two schemes:
- **CoRD**
- **CoRAD**

These are used for re-establishing connectivity between dumb nodes and other network nodes.

---

# 3.18 Event-Aware Topology Management

Main objectives:

1. Timely detection of an event of interest.
2. Monitoring the event.
3. Disseminating event data to the sink.
4. Adapting to changes in event state.

Important event properties:
- Event location
- Event area
- Event duration

---

# 3.19 Information Theoretic Self-Management (InTSeM)

A WSN is deployed to acquire information.

The sensed information is transmitted as packets.

**Information Theoretic Self-Management (InTSeM)** controls the transmission rate of a node by adjusting its **sleep time**.

### Benefits

- Reduces transmission energy consumption of transmitters.
- Reduces receiving energy consumption of relay nodes.

### General framework

The lecture's framework uses questions such as:
- Is the currently sensed data more informative?
- Are neighboring nodes providing more informative data?

Based on this, the node can adjust its transmission rate toward a minimum or maximum rate.

**Exam idea:**  
`InTSeM → transmission-rate control → sleep-time adjustment → energy saving`

---

# 3.20 Social Sensing in WSNs

Topic:
**Social Sensing-based Duty Cycle Management for Monitoring Rare Events**

### Problem

WSNs are energy-constrained.

For rare-event monitoring:
- Sensors may continue sensing even when no event is present.
- This causes ineffective sensing and energy waste.

Example from lecture:
- Submarine monitoring / underwater surveillance.

---

## Duty-Cycle Management

Approaches mentioned:
- SMAC
- DutyCon
- PW-MAC

### Limitations mentioned

These approaches may:
- Fail to distinguish rare events from regular events.
- Have ineffective wake-up/sensing behavior for rare-event scenarios.

---

## Probabilistic Duty Cycle (PDC)

The lecture's proposed contribution:
- Distinguish rare and regular events.
- Adapt duty cycle according to event occurrence probability.
- Use social-media information to estimate the possibility of rare events.
- Adjust sensor-node duty cycles using weak estimation learning automata.

---

# 3.21 WSN Application — Mines

Example:
**Fire Monitoring and Alarm System for Underground Coal Mines**

The lecture describes a WSN-based system for Bord-and-Pillar coal mines.

Capabilities:
- Real-time fire monitoring
- Alarm generation
- Identification of exact fire location
- Determination of spreading direction
- Continuous gathering, analysis and storage of real-time information

---

# 3.22 WSN Application — Healthcare

## Wireless Body Area Networks (WBANs)

WBANs provide:
- Continuous monitoring of physiological parameters.
- Cost-effective monitoring.
- User-friendly healthcare support.

Applications mentioned:
- Cardiovascular disease monitoring
- Diabetes monitoring
- Elderly-person activity monitoring

---

## Cloud-Assisted WBAN — Post-Disaster Healthcare

Lecture concepts:
- Remote patient-health monitoring.
- Ambulatory healthcare while a patient is being moved to an emergency healthcare center.
- Fair aggregation so eligible elements are not unjustly ignored.
- Pseudo-clusters to avoid aggregation bias toward leader nodes.
- Data aggregation among LDPUs using social-choice theory.
- Mobile aggregation centers to improve scalability.
- Dynamic gateway allocation after aggregation.

---

## Payload Tuning in WBANs

Health assessment can be influenced by external parameters such as:
- Age
- Height
- Weight
- Sex

The lecture notes that crisp set theory has difficulty representing degrees such as:
- Low
- Moderate
- High

A dynamic decision model is needed to optimize energy consumption.

The lecture mentions:
- **Fuzzy Inference System (FIS)**
- **Markov Decision Process (MDP)**

for energy optimization.

---

## Priority-Based Time-Slot Allocation in WBANs

During medical emergencies:
- Critical health data must be distinguished from regular data.

A problem with frequency-division transmission in a multisource/single-sink network is:
- Sink receiver buffer flooding
- Packet loss
- Retransmission

### PATS

**Priority-Based Allocation of Time Slots (PATS)** uses a fitness parameter.

Fitness can depend on:
- Criticality of health data
- Energy dissipation
- Time since last successful transmission

Higher-fitness LDPUs receive higher transmission preference while trying to maintain a minimum waiting time between transmissions.

---

# 🧠 4. HIGH-PRIORITY COMPARISONS

## WirelessHART vs ZigBee

| Feature | WirelessHART | ZigBee |
|---|---|---|
| MAC | **TDMA** | **CSMA/CA** |
| Channel behavior | Hops after every message | No per-message hopping |
| Topology emphasized | True mesh | Tree in lecture comparison |
| Routing | Every node can act as router | Trunk nodes may be critical |

---

## NFC Active vs Passive

| Feature | Passive NFC | Active NFC |
|---|---|---|
| Own power | No | Yes, according to lecture |
| Can collect information | No | Yes |
| Can transmit | Response using reader energy | Yes |
| Example | Supermarket tag | Smartphone |

---

## Piconet vs Scatternet

| Piconet | Scatternet |
|---|---|
| Single Bluetooth ad-hoc network | Multiple linked piconets |
| One master | Multiple piconets |
| Up to 7 slaves around master | Physically extensible network |

---

## Z-Wave Key Facts

| Parameter | Value |
|---|---|
| Main use | Home automation |
| US frequency | **908.42 MHz** |
| Europe frequency | **868.42 MHz** |
| Modulation | **GFSK** |
| Encoding | **Manchester** |
| Topology | Mesh |
| Network controller | Central controller |
| Network ID | 4 bytes |
| Node ID | 1 byte |
| Maximum nodes stated | 232 |
| Dead-spot bypass | **Healing** |

---

# ⚠️ 5. MCQ / MSQ TRAPS

### Trap 1
**Wired HART has a network layer** → ❌ False

### Trap 2
**Channel trimming/flushing = interference channel removal** → ❌  
Correct term = **Channel Blacklisting**

### Trap 3
**NFC supermarket tags are active** → ❌  
They are **passive**.

### Trap 4
**NFC works through ordinary electrical contact** → ❌  
Lecture: **magnetic induction**.

### Trap 5
**Bluetooth = Nanonet/Binarynet** → ❌  
Correct = **Piconet**.

### Trap 6
**Bluetooth is not ad-hoc** → ❌  
Lecture: Bluetooth is based on **Ad-hoc Piconets**.

### Trap 7
**Z-Wave uses Hongkong encoding** → ❌  
Correct = **Manchester encoding**.

### Trap 8
**Z-Wave dead-spot bypass = Ping** → ❌  
Correct = **Healing**.

### Trap 9
**Dumb behavior is spatial** → ❌  
Assignment answer = **Temporal**.

### Trap 10
**Sensor nodes have unlimited battery life** → ❌  
They have **limited battery life**.

### Trap 11
**Bluetooth LMP only handles data transmission** → ❌  
It handles establishment, authentication and link configuration.

### Trap 12
**ZigBee commonly uses 250 Mbps** → ❌  
Correct = **250 kbps**.

---

# 🔥 6. NUMBERS TO MEMORIZE

## WirelessHART
- 2.4 GHz ISM
- 15 channels
- 10 ms time slots
- Channel 26 removed in the lecture's congestion-control discussion

## NFC
- 13.56 MHz
- 106 / 212 / 424 kbps
- 96–512 bytes
- <20 cm

## Bluetooth
- 2.4–2.485 GHz
- 1600 hops/sec
- Version 1.2 → 1 Mbps
- Version 2.0 → 3 Mbps
- Class 3 → 1 m
- Class 2 → 10 m
- Class 1 → 100 m
- Piconet → up to 7 slaves

## Z-Wave
- US → 908.42 MHz
- Europe → 868.42 MHz
- Network ID → 4 bytes
- Node ID → 1 byte
- Network → up to 232 nodes

## ZigBee
- Common data rate → **250 kbps**

---

# 🚀 7. ONE-PAGE FINAL REVISION

### WirelessHART
`IEEE 802.15.4 → 2.4 GHz → 15 channels → TDMA → 10 ms slots → channel hopping → blacklisting → mesh`

### NFC
`Near Field Communication → magnetic induction → 13.56 MHz → <20 cm → passive tags + active smartphones`

### Bluetooth
`Ad-hoc → Piconet → master + up to 7 slaves → hopping → Baseband → L2CAP → RFCOMM → SDP → Scatternet`

### Z-Wave
`Home automation → mesh → 908.42 MHz US → 868.42 MHz Europe → GFSK → Manchester → Home ID + Node ID → Healing`

### ISA 100.11A
`Industrial automation → TCP/UDP/IPv6 → IEEE 802.15.4 PHY/MAC → mesh/frequency hopping → TDMA/QoS/security`

### WSN
`Many small sensor nodes → short range → multi-hop → relay nodes → sink → limited battery → scalability/QoS/energy/security challenges`

### Node Behavior
`Normal / Failed / Badly Failed / Selfish / Malicious`

### Dumb Behavior
`Environmental condition → temporary communication failure → temporal behavior → detect → re-establish connectivity`

### WSN Self-Management
`InTSeM → adjust sleep time → control transmission rate → reduce energy`

### Rare Events
`Social sensing → probabilistic duty cycle → adapt sensing to event probability`

### Healthcare
`WBAN → physiological monitoring → emergency priority → PATS`

---

# ⭐ 8. FINAL EXAM PRIORITY ORDER

If revision time is short, study in this order:

1. **All 15 assignment questions**
2. WirelessHART architecture + TDMA + channel hopping + blacklisting
3. NFC active/passive + magnetic induction + specifications
4. Bluetooth piconet/scatternet + protocol stack + LMP
5. Z-Wave frequency + GFSK + Manchester + Healing
6. WSN sensor-node characteristics + components + constraints
7. WSN node behavior + dumb behavior
8. WSN challenges: scalability, QoS, energy, security
9. ISA 100.11A architecture and security
10. Sensor Web + cooperation
11. InTSeM + event-aware topology management
12. Social sensing + rare-event duty cycle
13. WSN applications: mines and healthcare

---

# 📌 SOURCE-BASED NOTE

This file follows the supplied NPTEL Week-3 lecture material and Assignment-Week 3 Solution. Where a fact is presented as an exam point, it is based on the supplied material rather than being silently replaced with outside information.

**Assignment:** 15 questions, 15 marks.  
**Lecture:** Connectivity Technologies Parts III–V + Sensor Networks Parts I–II.
