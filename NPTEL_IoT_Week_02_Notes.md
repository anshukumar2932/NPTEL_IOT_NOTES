# NPTEL – Introduction to Internet of Things

## Week 2 Exam Preparation Notes

> **Source basis:** Week-2 assignment and the uploaded Week-2 lecture PDF covering 6LoWPAN, LOADng, RPL, RFID, MQTT, SMQTT, CoAP, XMPP, AMQP, IEEE 802.15.4 and ZigBee.
>
> **Exam strategy:** Memorize the **bold facts, protocol comparisons, mappings, and assignment answers** first. Then use the concept notes for understanding.

---

# 1. Week 2 – Quick Revision

## Core topics

## 🚨 Exam Priority Update — Assignment + Mock-Exam Cross-Check

**Your priority rule:**

1. **Assignment questions first** — all 15 Week-2 assignment questions remain the highest priority.
2. **Then all lecture/PPT topics** — do not skip topics that are not directly asked in the assignment.
3. **Then repeated mock-exam patterns** — especially concepts that appeared repeatedly across the uploaded Mock Exams 1–5.

### Week-2 topics repeatedly reinforced by the mock exams

| Topic                                    | Mock-exam pattern              | What to memorize                                                                  |
| ---------------------------------------- | ------------------------------ | --------------------------------------------------------------------------------- |
| **MQTT**                           | Repeated in Mock 1, 2, 3, 4, 5 | Broker, publish/subscribe, topic as routing information                           |
| **MQTT wildcards**                 | Mock 1                         | `+` = exactly one hierarchy level; `#` = multiple/remaining hierarchy levels  |
| **6LoWPAN**                        | Mock 2, 3, 4                   | IPv6 over low-power wireless; header compression; 802.15.4 packet-size constraint |
| **6LoWPAN Mesh Addressing Header** | Mock 3                         | Mesh forwarding; includes **Hops Left**                                     |
| **Passive RFID**                   | Mock 3                         | Powered inductively by the RFID reader; no internal battery                       |
| **IEEE 802.15.4**                  | Mock 1                         | Mainly PHY + MAC for LR-WPAN                                                      |
| **FFD/RFD**                        | Mock 2, 5                      | FFD can be coordinator/router/end device; RFD has limited functionality           |
| **CoAP**                           | Mock 5                         | Lightweight web-transfer protocol for constrained IoT; runs over UDP              |
| **AMQP**                           | Mock 3 / assignment            | **Exchange + Queue + Binding**; Flow frame controls message-flow rate       |

### ⚠️ Do NOT mix weeks

Some mock questions are useful only as cross-week context. For Week 2, focus on:

- MQTT
- 6LoWPAN
- RFID
- CoAP
- AMQP
- IEEE 802.15.4 / ZigBee

Bluetooth, WirelessHART, SDN, Arduino, Raspberry Pi, cloud, etc. belong mainly to other weeks and are **not added as Week-2 core material** merely because they appear in the mocks.

1. 6LoWPAN
2. 6LoWPAN addressing
3. 6LoWPAN packet/header concepts
4. LOADng routing
5. RPL routing
6. RFID
7. MQTT
8. MQTT topics and wildcards
9. Secure MQTT (SMQTT)
10. CoAP
11. CoAP messaging modes
12. XMPP
13. AMQP
14. AMQP frames, exchanges, queues and bindings
15. IEEE 802.15.4
16. IEEE 802.15.4 variants
17. Beacon and non-beacon networks
18. FFD and RFD
19. ZigBee
20. ZigBee device types and mesh networking

---

# 2. 6LoWPAN

## Meaning

**6LoWPAN = IPv6 over Low-Power Wireless Personal Area Networks.**

It allows very small devices with limited processing ability to communicate wirelessly using Internet protocols.

### Key ideas

- Low-power wireless personal area networks
- Uses IPv6
- Designed for constrained devices
- Enables low-power devices to connect to the Internet
- Developed through IETF work
- Useful for IoT, smart grids and M2M

---

# 3. Features of 6LoWPAN

6LoWPAN allows IEEE 802.15.4 radios to carry **128-bit IPv6 addresses**.

Because IEEE 802.15.4 has small packet sizes, 6LoWPAN uses techniques such as:

- Header compression
- Address translation / adaptation
- IPv6 packet compression and reformatting

### Memory point

> **6LoWPAN = IPv6 + IEEE 802.15.4 + low-power constrained devices**

---

# 4. 6LoWPAN Addressing

Two important address types:

| Address                           | Meaning                                   |
| --------------------------------- | ----------------------------------------- |
| **64-bit extended address** | Globally unique                           |
| **16-bit short address**    | PAN-specific; assigned by PAN coordinator |

### Important exam trap

Do **not** reverse these.

**64-bit → globally unique**

**16-bit → PAN-specific**

The assignment directly tests this distinction.

---

# 5. 6LoWPAN Packet Format

The lecture discusses adaptation between IEEE 802.15.4 frames and IPv6 packets.

Important fields/concepts include:

- Dispatch header
- Mesh addressing header
- Fragmentation header
- PAN ID
- Source and destination addresses
- IPv6 traffic class
- Payload length
- Flow label
- Next header
- Hop limit

## Dispatch header

The dispatch header:

- Initiates communication
- Identifies the dispatch type
- Indicates the type of next header

## Mesh Addressing Header

Contains information such as:

- Originator address
- Final destination address
- Hops Left

**Hops Left is decremented by each node before forwarding to the next hop.**

## Fragmentation Header

Used because an IPv6 packet may need to be divided to fit the smaller IEEE 802.15.4 frame format.

---

# 6. 6LoWPAN Routing

The lecture identifies two important routing approaches:

- **LOADng**
- **RPL**

### Easy memory

> **LOADng → on-demand route discovery**

> **RPL → IPv6 routing for Low-Power and Lossy Networks**

---

# 7. LOADng

**LOADng = Lightweight On-demand Ad hoc Distance-vector Routing Protocol – Next Generation.**

It is derived from **AODV** and adapted for IoT use.

## Basic operation

1. Originator generates a **Route Request (RREQ)**.
2. RREQ is forwarded through the network.
3. RREQ reaches the destination.
4. Destination generates a **Route Reply (RREP)**.
5. RREP travels hop-by-hop back to the originator.

## Route failure

If a route breaks:

- A **Route Error (RERR)** is returned to the originator.

## Very important rule

> **Only the destination is permitted to respond to an RREQ.**

An intermediate LOADng router **must not** respond to an RREQ even if it already has an active route to the destination.

This is a major Week 2 MCQ/True-False trap.

---

# 8. RPL

**RPL = IPv6 Routing Protocol for Low-Power and Lossy Networks.**

It is a distance-vector IPv6 routing protocol designed for low-power and lossy networks.

## Features

- Maintains routing topology using low-rate beaconing
- Beaconing can increase when inconsistencies are detected
- Routing information can be included in the datagram
- Proactive topology maintenance
- Reactive resolution of routing inconsistencies
- Supports confidentiality and integrity
- Supports data-path validation
- Supports loop detection

## Routing objectives

RPL can optimize for:

- Minimum energy
- Minimum latency
- Node power constraints
- Bandwidth constraints

### Important point

RPL operations require **bidirectional links**.

Reachability of a router must be verified before that router can be used as a parent.

---

# 9. RFID

**RFID = Radio-Frequency Identification.**

RFID stores digitally encoded data in tags that can be read by a reader.

It is somewhat similar to barcodes, but RFID has an important advantage:

> **RFID tags can be read without line-of-sight.**

## RFID components

- RFID tag / smart label
- RFID reader
- Antenna

## RFID tag

An RFID tag contains:

- Integrated circuit
- Antenna
- Protective material

---

# 10. Passive vs Active RFID

| Feature          | Passive RFID            | Active RFID                                 |
| ---------------- | ----------------------- | ------------------------------------------- |
| Own power supply | No                      | Yes                                         |
| Power source     | RFID reader             | Internal power supply                       |
| Transmission     | After reader powers tag | Uses its own power                          |
| Common use       | Very widely used        | Used when longer/active operation is needed |

### Critical exam fact

> **A passive RFID tag is powered inductively by the RFID reader before it can transmit information.**

---

# 11. RFID Applications

Important applications:

- Inventory management
- Asset tracking
- Personnel tracking
- Access control
- ID badging
- Supply chain management
- Counterfeit prevention
- Pharmaceutical industry tracking

---

# 12. IoT Protocol Organization

The lecture groups protocols by functionality.

| Function                  | Examples                          |
| ------------------------- | --------------------------------- |
| Connectivity              | 6LoWPAN, RPL                      |
| Identification            | EPC, uCode, IPv6, URIs            |
| Communication / Transport | Wi-Fi, Bluetooth, LPWAN           |
| Discovery                 | Physical Web, mDNS, DNS-SD        |
| Device Management         | TR-069, OMA-DM                    |
| Semantic                  | JSON-LD, Web Thing Model          |
| Data Protocols            | MQTT, CoAP, AMQP, WebSocket, Node |
| Multi-layer Frameworks    | AllJoyn, IoTivity, Weave, HomeKit |

---

# 13. MQTT

**MQTT = Message Queue Telemetry Transport.**

It is a lightweight, **publish-subscribe** messaging protocol designed for IoT and constrained/remote environments.

### Key characteristics

- Publish/subscribe architecture
- Lightweight
- Works with TCP/IP
- Uses a message broker
- Designed for remote connections
- Suitable for limited bandwidth
- Small code footprint

---

# 14. MQTT Architecture

Three major roles:

### Publisher

Produces and publishes data.

### Subscriber

Subscribes to topics and receives matching messages.

### Broker

Acts as the central communication point.

The broker:

- Connects publishers and subscribers
- Classifies data into topics
- Dispatches messages to matching subscribers

### Key concept

> Publishers and subscribers do **not** need to know each other directly. They communicate through topics and the broker.

---

# 15. MQTT Methods

Remember these five methods:

1. **Connect**
2. **Disconnect**
3. **Subscribe**
4. **Unsubscribe**
5. **Publish**

---

# 16. MQTT Topic

A topic is a string that can contain multiple hierarchy levels separated by `/`.

### Example

```text
house/living-room/temperature
```

A client can:

- Subscribe to an exact topic
- Subscribe using a wildcard

---

# 17. MQTT Wildcards

## `+` – Single-level wildcard

The plus sign matches an arbitrary value at **exactly one hierarchy level**.

Example:

```text
house/+/temperature
```

Can match:

```text
house/living-room/temperature
house/kitchen/temperature
```

It cannot replace multiple hierarchy levels.

## `#` – Multi-level wildcard

The hash sign matches the entire remaining topic hierarchy.

Example:

```text
house/#
```

matches topics beginning with:

```text
house/
```

### Exam trap

`house/#` does **not** mean only the exact topic `house`.

---

# 18. MQTT Routing

The **topic** contained in a published message is used by the broker as **routing information**.

### Memory

> MQTT message → Topic → Broker → Matching subscribers

---

# 19. Secure MQTT (SMQTT)

**SMQTT = Secure MQTT.**

It is an extension/proposed security enhancement for MQTT using lightweight attribute-based encryption.

## Four main stages

1. **Setup**
2. **Encryption**
3. **Publish**
4. **Decryption**

### Setup

Publishers and subscribers register with the broker and obtain the required master secret key.

### Publish

Data is encrypted and published.

### Subscriber

The subscriber receives the encrypted data and decrypts it using the appropriate key.

### Important trap

**Route discovery is NOT an SMQTT stage.**

---

# 20. CoAP

**CoAP = Constrained Application Protocol.**

It is a lightweight web-transfer protocol designed for:

- Constrained nodes
- Constrained networks
- IoT
- M2M applications
- Smart energy
- Building automation

CoAP uses a **request-response model**.

---

# 21. CoAP Transport Protocol

### Very important

> **CoAP operates over UDP.**

Why?

UDP helps keep the protocol lightweight for constrained IoT environments.

CoAP provides its own lightweight reliability mechanisms.

---

# 22. CoAP and REST

CoAP provides a lightweight **RESTful interface** for constrained devices.

REST/HTTP-style communication can introduce significant overhead and power consumption for tiny IoT devices.

CoAP is designed to provide REST-like services while meeting constrained-device requirements.

---

# 23. CoAP Architecture

CoAP has two major conceptual sub-layers:

### Messaging sub-layer

Responsible for:

- Reliability
- Duplication handling

### Request/Response sub-layer

Responsible for:

- Communication between endpoints

---

# 24. CoAP Message Modes

There are four important modes:

1. **Confirmable (CON)**
2. **Non-confirmable (NON)**
3. **Piggyback**
4. **Separate**

### Confirmable

Used for reliable transmission.

### Non-confirmable

Used for unreliable transmission.

---

# 25. Piggyback vs Separate Response

## Piggyback

The server response is included in the **acknowledgment**.

### Flow

```text
Client → Request
Server → ACK + Response
```

## Separate

The acknowledgment is sent first, and the server response is sent later as a **separate message**.

### Flow

```text
Client → Request
Server → ACK
Server → Response later
```

### Exam memory

> **Piggyback = response with ACK**

> **Separate = response after ACK**

---

# 26. CoAP Request Methods

As presented in the lecture:

| Method           | Purpose       |
| ---------------- | ------------- |
| **GET**    | Retrieve data |
| **PUT**    | Create data   |
| **PUSH**   | Update data   |
| **DELETE** | Delete data   |

### Exam note

Follow the mapping used in the NPTEL lecture/assignment for the exam.

---

# 27. CoAP Features

- Reduced overhead
- Reduced parsing complexity
- URL support
- Content-type support
- Resource discovery
- Subscription support
- Push notifications
- Simple caching

---

# 28. XMPP

**XMPP = Extensible Messaging and Presence Protocol.**

It is:

- A communication protocol for message-oriented middleware
- XML-based
- Designed for real-time exchange of structured data
- An open standard

## XMPP architecture/features

- Client-server architecture
- Decentralized model
- Service discovery
- Presence information
- Useful across diverse networks
- Useful for cloud environments
- Supports machine-to-machine and peer-to-peer communication

## Highlights

- Decentralization
- Open standards
- Security
- Flexibility/interoperability

---

# 29. XMPP Core Technologies

Important XMPP technologies:

- **Core** – XML streaming
- **Jingle** – multimedia signaling, voice, video, file transfer
- **Multi-user Chat** – multi-party communication
- **PubSub** – alerts and notifications/data syndication
- **BOSH** – HTTP binding for XMPP

---

# 30. XMPP Weaknesses

Important limitations:

- Does not support QoS
- Text-based communication causes higher network overhead
- Binary data must first be encoded using base64

---

# 31. XMPP Applications

- Publish-subscribe systems
- VoIP signaling
- Video
- File transfer
- Gaming
- IoT
- Smart grid
- Social networking services

---

# 32. AMQP

**AMQP = Advanced Message Queuing Protocol.**

It is an open standard for passing business messages between:

- Applications
- Organizations
- Systems
- Business processes

### Characteristics

- Binary application-layer protocol
- Basic data unit = frame
- ISO standard: ISO/IEC 19464
- Connects systems and business processes

---

# 33. AMQP Features

Remember:

- Security
- Reliability
- Interoperability
- Routing
- Queuing
- Open standard

Other important features:

- Targeted QoS
- Persistence
- Multiple consumers
- High-speed communication
- Message delivery guarantees

---

# 34. AMQP Message Delivery Guarantees

## At-most-once

Each message is delivered:

- Once
- Or never

## At-least-once

The message is certain to be delivered, but it may be delivered multiple times.

## Exactly-once

The message:

- Arrives
- And arrives only once

### Memory

```text
At-most-once  →  0 or 1
At-least-once  →  1 or more
Exactly-once   →  exactly 1
```

---

# 35. AMQP Frame Types

Important frame types:

| Frame                 | Function                           |
| --------------------- | ---------------------------------- |
| **Open**        | Open connection                    |
| **Begin**       | Open session                       |
| **Attach**      | Initiate link                      |
| **Transfer**    | Send actual messages               |
| **Flow**        | Control message-flow rate          |
| **Disposition** | Communicate transfer-state changes |
| **Detach**      | Terminate link                     |
| **End**         | Close session                      |
| **Close**       | Close connection                   |

### Most important exam fact

> **Flow frame controls message-flow rate.**

---

# 36. AMQP Components

## Exchange

- Receives messages
- Routes messages to queues

## Queue

- Stores messages
- Consumers/business processes receive messages from queues

## Binding

- Defines message-distribution rules
- Connects exchange routing logic to queues

### Memory

```text
Producer → Exchange → Queue → Consumer
                    ↑
                 Binding
```

---

# 37. AMQP Exchange Types

The lecture lists:

- Direct
- Fan-out
- Topic
- Header

---

# 38. AMQP Applications

- Monitoring
- Global update sharing
- Connecting different systems/processes
- Handling immediate requests
- Delegating time-consuming work
- Sending one message to multiple recipients
- Supporting offline clients
- Asynchronous systems
- Improving application reliability and uptime

---

# 39. IEEE 802.15.4

IEEE 802.15.4 is a well-known standard for **low-data-rate WPANs**.

It is designed for:

- Low-data-rate monitoring/control
- Extended-life
- Low-power consumption

### Layers

IEEE 802.15.4 primarily covers:

- Physical layer
- MAC layer

The lecture also discusses LLC and SSCS additions for communication with upper layers.

### Frequency

Operates in the **ISM band**.

---

# 40. IEEE 802.15.4 Modulation and Channel Access

## DSSS

Uses **Direct Sequence Spread Spectrum (DSSS)**.

Benefits include:

- Noise/interference tolerance
- Link reliability improvement

## Modulation

- Low-speed versions → **BPSK**
- High-data-rate versions → **O-QPSK**

## Channel access

Uses:

**CSMA/CA = Carrier Sense Multiple Access with Collision Avoidance**

---

# 41. IEEE 802.15.4 Power and Range

Important lecture points:

- Short packet transmissions
- Low duty cycle
- Power consumption is minimized
- Typical transmission range: **10 m to 75 m**
- Best outdoor cases can reach much farther
- Topologies include **Star** and **Mesh**

---

# 42. IEEE 802.15.4 Variants

Memorize this table:

| Variant               | Application / Region                 |
| --------------------- | ------------------------------------ |
| **802.15.4a/b** | Base version                         |
| **802.15.4c**   | China                                |
| **802.15.4d**   | Japan                                |
| **802.15.4e**   | Industrial applications              |
| **802.15.4f**   | Active RFID                          |
| **802.15.4g**   | Smart utility networks / Smart Grids |

### Assignment trap

The mapping of **c, e, f, g** is directly tested.

---

# 43. IEEE 802.15.4 Device Types

## FFD – Full Function Device

- Can communicate with all types of devices
- Supports full protocol functionality

## RFD – Reduced Function Device

- Can communicate only with an FFD
- Lower power consumption
- Minimal CPU/RAM requirement

### Memory

> **FFD = Full capability**

> **RFD = Reduced capability + lower power**

---

# 44. IEEE 802.15.4 Network Types

## Beacon-enabled

- Periodic beacon messages
- Beacon provides synchronization and association
- Data frames use **Slotted CSMA/CA**
- Superframe structure
- PAN coordinator manages the superframe

## Non-beacon-enabled

- Data frames use **Unslotted CSMA/CA**
- Beacons are used only for link-layer discovery
- Decentralized communication
- Requires source and destination IDs

### Very important

> **Non-beacon → Unslotted CSMA/CA**

> **Beacon-enabled → Slotted CSMA/CA**

---

# 45. ZigBee

ZigBee is a widely deployed enhancement that works on top of IEEE 802.15.4.

### Layer relationship

**IEEE 802.15.4 → Layers 1 and 2**

**ZigBee → Layer 3 and above**

ZigBee adds:

- Authentication
- Encryption
- Routing
- Forwarding
- Mesh networking

### Key exam statement

> IEEE 802.15.4 and ZigBee are **not identical**.

---

# 46. ZigBee Components

## ZDO – ZigBee Device Object

Responsible for:

- Device management
- Security
- Policies

## APS – Application Support Sublayer

Provides:

- Interfacing
- Control services
- Bridge between network and application-related layers

---

# 47. ZigBee Mesh

In a mesh network:

- Nodes can communicate with other nodes within range.
- If two nodes are not directly in range, intermediate nodes relay messages.
- Mesh supports larger-area deployment.
- Mesh improves reliability.
- ZigBee mesh networks can be self-configuring and self-healing.

### Example idea

If one path is blocked, another path can be used through intermediate nodes.

---

# 48. ZigBee Device Types

## ZigBee Coordinator (ZC)

- Forms the root of the ZigBee network tree
- One coordinator per network
- Initiates the network
- Stores network information
- Can act as a bridge between networks
- Acts as Trust Center
- Repository for security keys

## ZigBee Router (ZR)

- Can run applications
- Relays information between nodes

## ZigBee End Device (ZED)

- Talks to its parent
- **Cannot relay data for other devices**
- Reduced functionality
- Can sleep for significant periods
- Helps improve battery life
- Lower memory and cost than router/coordinator

### Memory

```text
ZC → Coordinator / root / Trust Center
ZR → Router / relay
ZED → End device / parent only / sleeps
```

---

# 49. ZigBee Routing

The ZigBee network layer uses **AODV** routing.

Basic idea:

1. Source broadcasts a route request.
2. Immediate neighbors receive it.
3. Neighbors relay the request.
4. Request spreads through the network.
5. Destination is discovered.
6. A low-cost path is calculated.
7. The route is returned using unicast messaging.

---

# 50. ZigBee Applications

Important applications:

- Building automation
- Consumer-electronics remote control
- Smart-energy monitoring
- Healthcare monitoring
- Home automation
- LED lighting control
- Telecom services

---

# 51. Assignment – Week 2 (15 Questions)

## Q1. MQTT routing information

**Question:** In MQTT, which field of a published message is used by the broker as routing information?

**Answer: `a. Topic`**

### Explanation

The publisher includes a topic in the message. The broker uses that topic to determine which subscribers should receive the message.

**Memory:** MQTT → **Topic = routing information**

---

## Q2. MQTT topic wildcards

Correct answers:

**a, b, d**

- `+` matches one hierarchy level.
- `#` matches underlying hierarchy levels.
- `house/+/temperature` can match `house/kitchen/temperature`.

### Incorrect

`house/#` does **not** match only the exact topic `house`.

---

## Q3. Secure MQTT (SMQTT)

Correct answers:

**a, b, c**

- Setup
- Publish
- Decryption

The complete SMQTT sequence is:

**Setup → Encryption → Publish → Decryption**

### Incorrect

Route discovery is not an SMQTT stage.

---

## Q4. CoAP transport

**Answer: `b. UDP`**

CoAP is designed for constrained environments and operates over UDP.

---

## Q5. CoAP piggyback/separate

**Answer: `a. True`**

- Piggyback → response is carried with ACK.
- Separate → ACK first, response later as a separate message.

---

## Q6. CoAP request mappings

**Correct answers: `a, b, c, d`**

| Method | Function |
| ------ | -------- |
| GET    | Retrieve |
| PUT    | Create   |
| PUSH   | Update   |
| DELETE | Delete   |

---

## Q7. AMQP frame controlling message flow

**Answer: `d. Flow`**

The **Flow** frame controls the rate of message flow between AMQP peers.

---

## Q8. AMQP components

Correct answers:

**a, b, c**

- Exchange receives and routes messages to queues.
- Queue stores messages for consumers/business processes.
- Binding defines message-distribution rules.
- A consumer does not route every producer message before it reaches an exchange.

---

## Q9. IEEE 802.15.4 variants

Correct answers:

**a, b, c, d**

- 802.15.4c → China
- 802.15.4e → Industrial applications
- 802.15.4f → Active RFID
- 802.15.4g → Smart utility networks

---

## Q10. Non-beacon IEEE 802.15.4

**Answer: `b. Unslotted CSMA/CA`**

### Compare

```text
Beacon-enabled      → Slotted CSMA/CA
Non-beacon-enabled  → Unslotted CSMA/CA
```

---

## Q11. IEEE 802.15.4 vs ZigBee

**Answer: `a`**

IEEE 802.15.4 provides the lower layers (primarily PHY and MAC), while ZigBee adds higher-layer functionality.

### ZigBee adds

- Authentication
- Encryption
- Routing
- Forwarding
- Mesh networking

---

## Q12. ZigBee end device

Correct answers:

**a, b, c**

A ZigBee End Device:

- Communicates with its parent.
- Cannot relay data for other devices.
- Is a reduced-functionality device.

### Incorrect

The coordinator forms the network root and can act as the Trust Center.

---

## Q13. 6LoWPAN addressing

**Answer: `b`**

- 16-bit short address → PAN-specific, assigned by PAN coordinator
- 64-bit extended address → globally unique

---

## Q14. LOADng RREQ response

**Answer: `b. False`**

Only the **destination** may respond to an RREQ.

An intermediate LOADng router is prohibited from responding even if it has an active route to the requested destination.

---

## Q15. Passive RFID power

**Answer: `b. It is powered inductively by an RFID reader.**

Passive RFID tags do not have their own power supply.

---

# 52. High-Priority Exam Memory List

Memorize these before the exam:

1. **6LoWPAN = IPv6 over Low-Power WPAN.**
2. **64-bit 6LoWPAN extended address = globally unique.**
3. **16-bit 6LoWPAN short address = PAN-specific.**
4. **LOADng is derived from AODV.**
5. **Only destination responds to LOADng RREQ.**
6. **RPL = IPv6 routing for low-power and lossy networks.**
7. **Passive RFID gets power inductively from the reader.**
8. **MQTT = publish/subscribe.**
9. **MQTT broker connects publishers and subscribers.**
10. **MQTT topic = broker routing information.**
11. **`+` = single-level MQTT wildcard.**
12. **`#` = multi-level MQTT wildcard.**
13. **SMQTT = setup, encryption, publish, decryption.**
14. **CoAP runs over UDP.**
15. **CoAP = lightweight RESTful protocol for constrained devices.**
16. **Piggyback = response with ACK.**
17. **Separate = response later, separate from ACK.**
18. **AMQP Flow frame controls message-flow rate.**
19. **AMQP: Exchange → Queue → Consumer; Binding defines routing/distribution rules.**
20. **At-most-once = 0 or 1 delivery.**
21. **At-least-once = one or more deliveries.**
22. **Exactly-once = exactly one delivery.**
23. **802.15.4 = mainly PHY + MAC.**
24. **802.15.4c = China.**
25. **802.15.4d = Japan.**
26. **802.15.4e = Industrial.**
27. **802.15.4f = Active RFID.**
28. **802.15.4g = Smart utility networks.**
29. **Non-beacon 802.15.4 = Unslotted CSMA/CA.**
30. **Beacon-enabled 802.15.4 = Slotted CSMA/CA.**
31. **FFD = Full Function Device.**
32. **RFD = Reduced Function Device.**
33. **ZigBee operates above IEEE 802.15.4 layers 1 and 2.**
34. **ZC = Coordinator/root/Trust Center.**
35. **ZR = Router/relay.**
36. **ZED = End Device/parent only/sleep.**
37. **ZigBee mesh = self-configuring and self-healing.**

---

# 53. Protocol Comparison Table

| Protocol / Technology | Main idea                      | Key exam fact                                |
| --------------------- | ------------------------------ | -------------------------------------------- |
| **6LoWPAN**     | IPv6 for low-power WPAN        | 16-bit short vs 64-bit extended              |
| **LOADng**      | On-demand routing              | Only destination responds to RREQ            |
| **RPL**         | IPv6 LLN routing               | Low-power/lossy networks                     |
| **RFID**        | Radio-frequency identification | Passive tag powered by reader                |
| **MQTT**        | Publish/subscribe messaging    | Topic is routing information                 |
| **SMQTT**       | Secure MQTT                    | Setup → Encryption → Publish → Decryption |
| **CoAP**        | Lightweight RESTful protocol   | Runs over UDP                                |
| **XMPP**        | XML-based messaging/presence   | Open, decentralized                          |
| **AMQP**        | Business messaging/queuing     | Flow controls message rate                   |
| **802.15.4**    | Low-rate WPAN                  | PHY + MAC                                    |
| **ZigBee**      | Higher-layer IoT/mesh stack    | Builds on 802.15.4                           |

---

# 54. Wildcard Examples

## Single level

```text
house/+/temperature
```

Matches:

```text
house/kitchen/temperature
house/bedroom/temperature
house/living-room/temperature
```

## Multiple levels

```text
house/#
```

Matches topics under the `house` hierarchy.

### Remember

```text
+ → one level
# → multiple/remaining levels
```

---

# 55. Important Comparisons

## MQTT vs CoAP

| MQTT                            | CoAP                                  |
| ------------------------------- | ------------------------------------- |
| Publish/subscribe               | Request/response                      |
| Broker-based                    | Client/server style                   |
| Topic-based                     | RESTful resources                     |
| Uses TCP/IP                     | Uses UDP                              |
| Good for event-driven messaging | Good for constrained RESTful services |

---

## IEEE 802.15.4 vs ZigBee

| IEEE 802.15.4            | ZigBee                                    |
| ------------------------ | ----------------------------------------- |
| Mainly PHY + MAC         | Higher layers                             |
| Low-rate WPAN foundation | Adds networking/application functionality |
| CSMA/CA                  | Routing, security, mesh support           |
| Base wireless standard   | Enhancement built on 802.15.4             |

---

## FFD vs RFD

| FFD                                   | RFD                   |
| ------------------------------------- | --------------------- |
| Full functionality                    | Reduced functionality |
| Can communicate with all device types | Communicates with FFD |
| More resources                        | Lower CPU/RAM         |
| Higher capability                     | Lower power           |

---

## ZC vs ZR vs ZED

| Device | Role                          |
| ------ | ----------------------------- |
| ZC     | Root/coordinator/Trust Center |
| ZR     | Routing/relaying              |
| ZED    | Parent communication only     |

---

# 56. MCQ Traps

| Question clue                | Correct thought                                     |
| ---------------------------- | --------------------------------------------------- |
| MQTT routing field           | **Topic**                                     |
| `+` wildcard               | **One level**                                 |
| `#` wildcard               | **Multiple levels**                           |
| SMQTT stage                  | **Setup / Encryption / Publish / Decryption** |
| CoAP transport               | **UDP**                                       |
| Piggyback                    | **Response + ACK**                            |
| Separate                     | **ACK first, response later**                 |
| AMQP flow rate               | **Flow frame**                                |
| AMQP routing                 | **Exchange + Binding**                        |
| 802.15.4e                    | **Industrial**                                |
| 802.15.4f                    | **Active RFID**                               |
| Non-beacon                   | **Unslotted CSMA/CA**                         |
| ZigBee lower layers          | **IEEE 802.15.4**                             |
| ZigBee end device            | **Cannot relay**                              |
| 6LoWPAN 16-bit               | **PAN-specific**                              |
| 6LoWPAN 64-bit               | **Globally unique**                           |
| LOADng intermediate response | **Not allowed**                               |
| Passive RFID                 | **Powered by reader**                         |

---

# 57. One-Page Final Revision

## 6LoWPAN

- IPv6 over low-power WPAN
- 64-bit = globally unique
- 16-bit = PAN-specific
- Header compression
- Fragmentation
- LOADng / RPL

## LOADng

- Derived from AODV
- RREQ → destination
- Destination → RREP
- Broken route → RERR
- Only destination responds

## RPL

- IPv6
- Low-power lossy networks
- Distance-vector
- Beaconing
- Energy/latency/objective optimization

## RFID

- Tag + reader + antenna
- No line-of-sight required
- Passive = reader-powered
- Active = own power

## MQTT

- Publish/subscribe
- Broker
- Topic = routing
- `+` = one level
- `#` = multiple levels

## SMQTT

- Setup
- Encryption
- Publish
- Decryption

## CoAP

- Constrained Application Protocol
- RESTful
- UDP
- Confirmable
- Non-confirmable
- Piggyback
- Separate

## XMPP

- XML
- Messaging + presence
- Open standard
- Decentralized
- No QoS
- Higher text overhead

## AMQP

- Business messaging
- Exchange
- Queue
- Binding
- Flow frame
- At-most-once / At-least-once / Exactly-once

## IEEE 802.15.4

- Low-rate WPAN
- PHY + MAC
- CSMA/CA
- Beacon → slotted
- Non-beacon → unslotted
- FFD / RFD

## ZigBee

- Above 802.15.4
- Authentication
- Encryption
- Routing
- Mesh
- ZC / ZR / ZED

---

# 58. Source Material

- **Week-2.pdf** – NPTEL lecture slides covering 6LoWPAN, routing, RFID, MQTT, SMQTT, CoAP, XMPP, AMQP, IEEE 802.15.4 and ZigBee.
- **Assignment-Week 2** – 15 MCQ/MSQ questions and solutions.

---

# 35. NEW — Mock-Exam Cross-Check (Uploaded Mock Exams 1–5)

> **Purpose:** This section is an exam-pattern layer added after the original Week-2 assignment + lecture notes. It does **not** replace the assignment or lecture material.

## 35.1 Highest-frequency Week-2 concept: MQTT

MQTT was repeatedly tested across the uploaded mocks.

### Core chain

**Publisher → MQTT Broker → Subscriber**

- **Publisher:** sends/publishes a message.
- **Broker:** central communication point; receives messages and dispatches them to matching subscribers.
- **Subscriber:** subscribes to a topic and receives matching messages.
- **Topic:** the broker uses the topic as **routing information**.

### Mock-exam recognition

If the question asks:

> “What is the central server that receives messages from publishers and forwards them to subscribers?”

Answer:

**Message Broker**

If it asks:

> “What is a topic used for?”

Answer:

**Categorizing messages / routing them to interested subscribers.**

### MQTT wildcard trap

| Wildcard | Meaning                         | Example                 |
| -------- | ------------------------------- | ----------------------- |
| `+`    | **Single-level** wildcard | `house/+/temperature` |
| `#`    | **Multi-level** wildcard  | `house/#`             |

#### Example

`house/+/temperature` can match:

- `house/kitchen/temperature`
- `house/living-room/temperature`

But `+` cannot replace multiple hierarchy levels.

`house/#` matches topics beginning with `house` across the underlying hierarchy.

### Repeated mock trap

**Do not confuse:**

- **Topic** → routing information
- **Broker** → dispatches messages
- **Publisher** → sends messages
- **Subscriber** → receives matching messages

---

## 35.2 6LoWPAN — repeated mock focus

The mocks repeatedly tested the **purpose of 6LoWPAN** and **header compression**.

### One-line definition

**6LoWPAN enables IPv6 packets to be transmitted over low-power, low-bandwidth wireless links, especially IEEE 802.15.4 networks.**

### Why header compression?

IPv6 has a large header, while IEEE 802.15.4 has a small packet structure.

Therefore:

**Header compression → reduces IPv6 header overhead so packets can fit efficiently into constrained 802.15.4 frames.**

### Mock-style question

> What is the primary function of header compression in 6LoWPAN?

**Answer:** Reduce the size of large IPv6 headers to fit within smaller IEEE 802.15.4 packets.

### 6LoWPAN memory chain

**IPv6 → constrained wireless → IEEE 802.15.4 → compression/adaptation → IoT**

---

## 35.3 6LoWPAN Mesh Addressing Header

A mock specifically tested the Mesh Addressing Header.

### Remember

**Mesh Addressing Header = mesh forwarding information**

Important field:

- **Hops Left** → decremented by each forwarding node before sending to the next hop.

### Do not confuse the headers

| Header                           | Main idea                                    |
| -------------------------------- | -------------------------------------------- |
| **Dispatch Header**        | Identifies/initiates the next header type    |
| **Mesh Addressing Header** | Supports mesh forwarding; includes Hops Left |
| **Fragmentation Header**   | Handles fragmentation of large datagrams     |

### Exam trap

If the option says:

> “Mesh Addressing Header breaks large IPv6 packets into fragments”

❌ Wrong.

That is the **Fragmentation Header**.

---

## 35.4 IEEE 802.15.4 — repeated mock focus

### Primary role

IEEE 802.15.4 mainly specifies:

- **Physical layer (PHY)**
- **MAC layer**

It is intended for **low-rate, low-power wireless personal area networks (LR-WPANs).**

### High-yield distinction

> **IEEE 802.15.4 ≠ ZigBee**

Think:

**802.15.4 → PHY + MAC**

**ZigBee → higher-layer networking/functions built on top of 802.15.4**

### FFD vs RFD

| Device        | Key capability                                                |
| ------------- | ------------------------------------------------------------- |
| **FFD** | Can act as **PAN coordinator, router, or end device**   |
| **RFD** | Reduced functionality; limited role; communicates with an FFD |

### Mock trap

If an option says:

> “FFD can only act as a simple sensing end device.”

❌ False.

Correct:

> **FFD can act as PAN coordinator, router, or end device.**

---

## 35.5 Passive RFID — repeated mock focus

### Passive RFID

A passive RFID tag:

- has **no internal battery**
- receives power **inductively from the RFID reader**
- then transmits its information

### Active vs Passive

| Feature               | Passive RFID                 | Active RFID                    |
| --------------------- | ---------------------------- | ------------------------------ |
| Own power supply      | ❌ No                        | ✅ Yes                         |
| Reader provides power | ✅ Yes                       | Not required for tag operation |
| Common exam clue      | **Inductive powering** | **Own power supply**     |

### Mock trap

> “Passive RFID does not require any power source.”

❌ False.

It has no **internal** power source, but it receives power from the reader.

---

## 35.6 CoAP — repeated mock focus

The uploaded mocks reinforced the basic identification of CoAP.

### One-line memory

**CoAP = lightweight web-transfer protocol for constrained IoT devices.**

### Transport

**CoAP runs over UDP.**

Why?

- constrained devices
- lower overhead
- lightweight communication

### CoAP vs MQTT

| Feature              | CoAP                                  | MQTT                  |
| -------------------- | ------------------------------------- | --------------------- |
| Main model           | Request/response                      | Publish/subscribe     |
| Transport in lecture | **UDP**                         | **TCP/IP**      |
| Typical idea         | Lightweight web/REST-like interaction | Lightweight messaging |
| Central broker       | ❌ Not the core model                 | ✅ Broker             |

### CoAP request mapping — memorize exactly as taught in the assignment

| Method           | Lecture mapping |
| ---------------- | --------------- |
| **GET**    | Retrieve data   |
| **PUT**    | Create data     |
| **PUSH**   | Update data     |
| **DELETE** | Delete data     |

> **Important:** Use the mapping given in the NPTEL Week-2 assignment/lecture for this exam.

### Piggyback vs Separate

**Piggyback:**

- ACK carries the response/data.

**Separate:**

- ACK is sent first.
- Server response arrives later in a separate message.

---

## 35.7 AMQP — mock + assignment reinforcement

### Three core components

**Exchange → Queue → Consumer**

The **binding** defines the relationship/routing rule between the exchange and queue.

### Remember

- **Exchange** → receives and routes messages
- **Queue** → stores messages
- **Binding** → defines message-distribution relationship/rule
- **Consumer** → receives/uses queued messages

### AMQP frame trap

**Flow frame → controls message-flow rate**

Do not confuse:

| Frame                 | Main role                               |
| --------------------- | --------------------------------------- |
| **Transfer**    | Carries messages                        |
| **Disposition** | Communicates a change in transfer state |
| **Detach**      | Terminates a link                       |
| **Flow**        | **Controls message-flow rate**    |

### Binding trap

If asked:

> “What is a Binding?”

Answer:

**A rule defining the relationship between an exchange and a queue and governing message flow.**

---

# 36. Mock-Exam Trap Bank — Week 2

## Trap 1: MQTT Topic vs Broker

- Topic = **routing information**
- Broker = **dispatches messages**

## Trap 2: MQTT `+` vs `#`

- `+` = **one level**
- `#` = **multiple/remaining hierarchy levels**

## Trap 3: 6LoWPAN vs IPv6

- 6LoWPAN does not mean “a new version of IPv6.”
- It is the adaptation needed to carry IPv6 over constrained low-power wireless networks.

## Trap 4: Header Compression vs Encryption

- Header compression = **reduce overhead**
- Encryption = **security**

## Trap 5: Mesh Addressing vs Fragmentation

- Mesh Addressing Header = **forwarding / Hops Left**
- Fragmentation Header = **large datagram fragmentation**

## Trap 6: IEEE 802.15.4 vs ZigBee

- 802.15.4 = **PHY + MAC**
- ZigBee = **higher-layer functionality on top**

## Trap 7: FFD vs RFD

- FFD = coordinator/router/end device
- RFD = reduced functionality / limited communication role

## Trap 8: Passive vs Active RFID

- Passive = **reader-powered**
- Active = **own power supply**

## Trap 9: CoAP vs MQTT

- CoAP = **request/response + UDP**
- MQTT = **publish/subscribe + broker + TCP/IP**

## Trap 10: AMQP Exchange vs Queue vs Binding

- Exchange = **routes**
- Queue = **stores**
- Binding = **defines routing relationship**

## Trap 11: AMQP Flow vs Transfer

- Flow = **flow control**
- Transfer = **message transfer**

---

# 37. Mock-Exam Priority Ranking for Week 2

### 🔴 Tier 1 — Must memorize

1. MQTT broker
2. MQTT topic as routing information
3. `+` vs `#`
4. 6LoWPAN purpose
5. 6LoWPAN header compression
6. IEEE 802.15.4 = PHY + MAC
7. FFD vs RFD
8. Passive RFID = inductive reader power
9. CoAP = UDP
10. CoAP piggyback vs separate
11. AMQP exchange / queue / binding
12. AMQP Flow frame

### 🟠 Tier 2 — Very important

13. 6LoWPAN 64-bit vs 16-bit addressing
14. Dispatch / Mesh / Fragmentation headers
15. LOADng RREQ/RREP behavior
16. RPL for low-power and lossy networks
17. IEEE 802.15.4 variants
18. Beacon vs non-beacon CSMA/CA
19. ZigBee relationship with 802.15.4
20. XMPP purpose and architecture

### 🟡 Tier 3 — Understand well

21. RFID applications
22. MQTT methods
23. SMQTT four stages
24. CoAP features
25. AMQP delivery/frames beyond the directly tested items
26. Functionality-based IoT protocol organization

---

# 38. 60-Second Week-2 Recall Chain

Say this aloud before the exam:

> **6LoWPAN = IPv6 over constrained low-power wireless.**
> **Header compression = fit IPv6 efficiently into 802.15.4.**
> **64-bit = globally unique; 16-bit = PAN-specific.**
> **LOADng = on-demand; only destination answers RREQ.**
> **RPL = IPv6 routing for low-power lossy networks.**
> **Passive RFID = reader-powered inductively.**
> **MQTT = publish/subscribe + broker + topic.**
> **`+` = one level; `#` = multiple levels.**
> **SMQTT = setup → encryption → publish → decryption.**
> **CoAP = lightweight REST/web style + UDP.**
> **Piggyback = ACK + response; separate = ACK first, response later.**
> **AMQP = exchange + queue + binding.**
> **Flow = flow control.**
> **802.15.4 = PHY + MAC.**
> **FFD = coordinator/router/end device; RFD = limited.**
> **ZigBee = higher-layer functionality over 802.15.4.**

---

# 39. Mock-Derived Mini Drill — Do Without Looking

1. MQTT routing field? → **Topic**
2. MQTT central server? → **Broker**
3. `+` wildcard? → **Single level**
4. `#` wildcard? → **Multi-level**
5. 6LoWPAN purpose? → **IPv6 over low-power wireless**
6. Header compression purpose? → **Reduce IPv6 header overhead**
7. Mesh Addressing Header key field? → **Hops Left**
8. Passive RFID power? → **Inductive power from reader**
9. CoAP transport? → **UDP**
10. Piggyback? → **ACK carries response**
11. AMQP routing component? → **Exchange**
12. AMQP storage component? → **Queue**
13. AMQP relationship/routing rule? → **Binding**
14. AMQP flow-control frame? → **Flow**
15. IEEE 802.15.4 layers? → **PHY + MAC**
16. FFD roles? → **Coordinator/router/end device**
17. RFD? → **Reduced functionality**
18. ZigBee vs 802.15.4? → **ZigBee adds higher-layer functions**
19. LOADng RREQ response? → **Destination only**
20. RPL target network type? → **Low-power and lossy networks**

---

# 40. Source Cross-Check Used for This Update

This update was based only on the uploaded course materials and uploaded mock exams:

- **Week-2 lecture PDF** — 96 pages covering 6LoWPAN, LOADng, RPL, RFID, MQTT, SMQTT, CoAP, XMPP, AMQP, IEEE 802.15.4 and ZigBee.
- **Week-2 assignment PDF** — all 15 assignment questions and official detailed solutions.
- **Mock Exam 1** — MQTT topic/wildcards and IEEE 802.15.4 purpose.
- **Mock Exam 2** — MQTT broker, IEEE 802.15.4 FFD, 6LoWPAN header compression.
- **Mock Exam 3** — MQTT acronym, 6LoWPAN purpose, Mesh Addressing Header, passive RFID, AMQP components.
- **Mock Exam 4** — MQTT broker, 6LoWPAN header compression, plus cross-week WirelessHART/Bluetooth items that were intentionally excluded from the Week-2 core.
- **Mock Exam 5** — MQTT broker, CoAP, IEEE 802.15.4 FFD/RFD, plus cross-week Bluetooth/coverage items that were intentionally excluded.

**Bottom line:** The original Week-2 notes are preserved, and this update adds the repeated mock-exam patterns and traps without removing any assignment or lecture topics.

---

## Update Status

**Version:** Week 2 — Improved with uploaded Mock Exams 1–5
**Priority order:** Assignment → All Week-2 lecture/PPT topics → Repeated mock-exam patterns → Final recall/drill
