# NPTEL IoT – Week 7 Exam Notes
## Assignment Priority + Complete Lecture Coverage

**Course:** Introduction to Internet of Things  
**Week:** 7  
**Main topics:** Remote Data Logging with Raspberry Pi, Python UDP/socket programming, data processing and plotting, Software-Defined Networking (SDN), SDN architecture/APIs/rule placement/controller placement, SDN security and experimentation, SDN for IoT, Software-Defined WSN, SDN-WISE  
**Exam style:** MCQ/MSQ

> **Priority rule:** Study all 15 assignment questions first. Then study the complete lecture topics. The assignment is the strongest exam signal, but every lecture topic is included because questions can come from outside the assignment.

---

# 1. WEEK 7 ULTRA-QUICK REVISION

## Remote Data Logging
- IoT remote data logging: collect sensor data → send to remote server → save/process/respond.
- Sensor used: **DHT / DHT22**.
- DHT pins left-to-right:
  1. 3.3–5 V power
  2. Data
  3. Null
  4. Ground
- Raspberry Pi reads the sensor using **`Adafruit_DHT.read_retry()`**.
- Client creates a **UDP socket** using `AF_INET + SOCK_DGRAM`.
- Sensor message format: **humidity,temperature** separated by a comma.
- Client sends using **`sendto()`**.
- Server receives using **`recvfrom()`**.
- Server saves received data in **`DataLog.txt` / `Datalog.txt`** in append mode.
- Python `split(",")` separates the received string.

## Matplotlib
- Matplotlib → Python library for **2D plotting**.
- `plot(x,y)` → plot values.
- `xlabel()` → x-axis label.
- `ylabel()` → y-axis label.
- `title()` → title.
- `figure()` → new figure.
- `grid()` → grid.
- **`ion()` → interactive mode**.
- `subplot()` → subplot in a figure.
- `close()` → close current figure.
- `scatter()` → scatter plot.
- In the lecture's example, temperature and humidity are plotted separately.

## Traditional Network vs SDN
- Traditional network: routing/control logic such as **OSPF executes at individual switches**.
- Switches forward traffic in a distributed manner.
- They do not have a global network view.
- Vendor-specific switch architecture limits dynamic configuration.
- SDN separates **control logic from hardware/data-plane switches**.
- SDN architecture: **Application layer → Control layer → Infrastructure/Data layer**.
- **Northbound API**: control ↔ application.
- **Southbound API**: control ↔ infrastructure; OpenFlow is used.
- **East-Westbound API**: controller ↔ controller.

## SDN history
- **2006:** SANE proposal at Stanford.
- **2008:** OpenFlow project presented at ACM SIGCOMM; origin of SDN idea in the lecture.
- **2009:** Stanford publishes OpenFlow v1.0.0 specification.
- **2011:** Open Networking Foundation formed.

## Flow Rules
- SDN switches forward traffic according to controller-defined **flow rules**.
- Flow table exists at each switch.
- OpenFlow defines rule format/match fields.
- Match fields include source IP, destination IP, source port, priority, etc.
- Limited **TCAM** restricts the number of rules.
- TCAM is fast but expensive.
- No matching rule → switch sends **PACKET-IN** to controller.
- Controller decides a rule → rule inserted at switch.
- New rule placement typically takes **3–5 ms** in the lecture.

## Timeouts
- **Hard timeout:** all rules are deleted when hard timeout expires.
- **Soft timeout:** rule is deleted if no associated flow is received for the specified time.

## Controller Placement
- Controller must handle incoming requests and place rules with low delay.
- Lecture figure/fact: about **200 requests/second per single thread**.
- Small controller count in a large network can cause control-packet congestion.
- Architectures shown:
  - Flat
  - Hierarchical/tree
  - Ring
  - Mesh
- Control:
  - Distributed → different subnetworks controlled by different controllers.
  - Centralized → whole network controlled by a single controller.
- Backup controller provides continuity if main controller fails.

## SDN + IoT
Benefits:
- Intelligent routing
- Simplified information collection/analysis/decision-making
- Visibility of network resources
- Intelligent traffic-pattern analysis
- Coordinated decisions

Applications shown:
- Control sensors/actuators
- Rule placement at access devices considering mobility and heterogeneity
- Rule placement and traffic engineering at backbone networks
- Flow classification and enhanced security in data centers

## Software-Defined WSN
WSN challenges:
- Real-time programming
- Vendor-specific architecture
- Resource constraints / limited computation
- Limited memory for control programs

Opportunities:
- Program sensor nodes in real time
- Change forwarding path in real time
- Integrate different sensor nodes

Approaches:
- **Sensor OpenFlow**
  - Value-centric forwarding
  - ID-centric forwarding
- **Soft-WSN**
  - Sensor/device management
  - Dynamic sensing delay
  - Active/sleep management
  - Topology management
  - Node-specific/network-specific management
- **SDN-WISE**
  - Flow table for sensor-node rule placement
  - Real-time programming through API
  - IEEE 802.15.4 + MCU
  - Forwarding layer contains flow rules
  - **INPP = In Network Packet Processing**

---

# 2. ASSIGNMENT-FIRST: ALL 15 QUESTIONS

The Week 7 assignment has **15 questions for 15 marks**. The exact assignment pages should be your first revision target.

---

## Q1. In the remote data logging system, which socket type sends sensor data from client to server?

**Answer: B — `SOCK_DGRAM`**

### Explanation
The client creates:

```python
socket.socket(socket.AF_INET, socket.SOCK_DGRAM)
```

`SOCK_DGRAM` is the datagram socket type used for UDP.

### Trap
Do not select `SOCK_STREAM`; that is the stream/TCP socket type.

**Memory:** UDP → `SOCK_DGRAM`

---

## Q2. Which Adafruit function reads humidity and temperature from the DHT sensor?

**Answer: A — `Adafruit_DHT.read_retry()`**

Example:

```python
humidity, temperature = Adafruit_DHT.read_retry(sensor,17)
```

### Trap
The function is `read_retry()`, not `get_data()`, `sense()`, or `capture()`.

**Memory:** DHT reading → `read_retry()`

---

## Q3. Where does the server save received data?

**Answer: B — In a text file named `Datalog.txt`**

Lecture server code:

```python
with open("Datalog.txt","a") as f:
    ...
```

The data is appended to the text file.

### Trap
Not MySQL, cloud dashboard, or Excel.

**Memory:** Server storage → **Datalog/DataLog text file**

---

## Q4. Which Python string function splits comma-separated sensor data?

**Answer: A — `split()`**

Example:

```python
Data = "sunday,monday,tuesday"
Data.split(",")
```

Output:

```text
['sunday', 'monday', 'tuesday']
```

### Memory
Comma-separated data → `split(",")`

---

## Q5. Is Matplotlib used to plot the temperature and humidity data?

**Answer: TRUE**

Matplotlib is a Python library used to create 2D plots.

Lecture example uses:
- `plot()`
- `xlabel()`
- `ylabel()`
- `title()`

### Trap
Do not confuse Matplotlib with the DHT library. DHT library reads sensor data; Matplotlib visualizes it.

---

## Q6. Which Matplotlib function enables interactive mode for real-time plot updates?

**Answer: A — `ion()`**

```python
plt.ion()
```

### Meaning
`ion()` turns on interactive mode.

### Trap
- `figure()` → creates figure.
- `grid()` → grid.
- `subplot()` → subplot.
- `ion()` → **interactive mode**.

**Memory:** Interactive → **ION**

---

## Q7. In a traditional non-SDN network, where does routing protocol logic such as OSPF mainly execute?

**Answer: B — At the individual switches**

The lecture's network diagram explicitly shows **OSPF executing at switches**.

Traditional switches:
- Forward traffic in a distributed manner.
- Do not have a global network view.

### Trap
Traditional network ≠ centralized SDN controller.

---

## Q8. In which year was the OpenFlow project presented at ACM SIGCOMM?

**Answer: B — 2008**

Lecture history:
- 2006 → SANE
- **2008 → OpenFlow / SDN idea**
- 2009 → OpenFlow v1.0.0 specification
- 2011 → ONF formed

**Memory:** OpenFlow origin → **2008**

---

## Q9. What message does a switch send when no matching flow rule exists?

**Answer: A — `PACKET-IN`**

Flow:

```text
Packet arrives
     ↓
No matching flow rule
     ↓
PACKET-IN
     ↓
Controller
     ↓
Controller decides flow rule
     ↓
Rule inserted at switch
```

### Important number
The lecture states typical new rule placement takes **3–5 ms**.

---

## Q10. Which SDN API connects the control layer and infrastructure layer?

**Answer: B — Southbound API**

### API mapping

| API | Connects |
|---|---|
| **Northbound** | Control ↔ Application |
| **Southbound** | Control ↔ Infrastructure |
| **East-Westbound** | Controller ↔ Controller |

### Protocol
The lecture uses **OpenFlow** for the Southbound communication.

---

## Q11. Approximately how many requests per second can a typical SDN controller handle through one thread?

**Answer: C — 200**

Lecture statement:

> A controller can typically handle **200 requests in a second through a single thread**.

### Trap
Do not confuse 200 requests/sec with the 3–5 ms rule-placement delay.

---

## Q12. What control mechanism uses a single controller for the whole network?

**Answer: B — Centralized control**

### Centralized
One controller controls the network.

### Distributed
Different subnetworks can be controlled by different controllers.

**Memory:** One controller → **Centralized**

---

## Q13. Which is a benefit of integrating SDN with IoT?

**Answer: B — Visibility of network resources**

Benefits include:
- Intelligent routing decisions
- Simplified information collection/analysis/decision-making
- **Visibility of network resources**
- Intelligent traffic pattern analysis
- Coordinated decisions

### Trap
SDN does not increase hardware cost as a benefit, reduce sensor accuracy, or eliminate all controllers.

---

## Q14. What resource-constraint challenge motivates software-defined WSN?

**Answer: B — Limited memory for control programs**

WSN challenges include:
- Real-time programming
- Vendor-specific architecture
- Resource-constrained devices
- Limited memory
- Heavy computation cannot be performed easily
- Too many control programs cannot be inserted

### Memory
WSN → **resource constrained + limited memory**

---

## Q15. In SDN-WISE, what does INPP stand for?

**Answer: C — In Network Packet Processing**

The SDN-WISE stack includes:
- IEEE 802.15.4
- MCU
- Forwarding layer with flow rules
- **INPP = In Network Packet Processing**

### Trap
Do not invent a new expansion from the letters.

---

# 3. REMOTE DATA LOGGING – COMPLETE LECTURE

## 3.1 IoT Remote Data Logging

The lecture defines the remote logging workflow as:
1. Collect data from devices in the network.
2. Send data to a server/remote machine.
3. Save/process the data.
4. Respond/control as required.

The Week 7 visual system diagrams show a Raspberry Pi connected to temperature/humidity sensing, with the data sent to a remote server.

### Core architecture

```text
DHT Sensor
     ↓
Raspberry Pi
     ↓
Read sensor
     ↓
UDP client
     ↓
Network
     ↓
UDP server
     ↓
Save DataLog.txt
     ↓
Split / Process
     ↓
Plot temperature + humidity
```

---

# 4. DHT SENSOR

DHT = **Digital Humidity and Temperature Sensor**

## Requirements
Lecture lists:
- DHT sensor
- **4.7 kΩ resistor**
- Jumper wires
- Raspberry Pi

## Pin order

| Pin | Function |
|---|---|
| 1 | 3.3–5 V power |
| 2 | Data |
| 3 | Null |
| 4 | Ground |

## Raspberry Pi interface
Lecture uses:
- DHT pin 1 → Pi 3.3 V
- DHT pin 2 → Pi input; example uses **pin 11**
- DHT pin 4 → Pi ground

---

# 5. READING DHT DATA

Adafruit provides a library for DHT22.

Core function:

```python
Adafruit_DHT.read_retry(sensor,17)
```

Example:

```python
def sensordata():
    GPIO.setmode(GPIO.BOARD)
    GPIO.setwarnings(False)

    sensor = Adafruit_DHT.AM2302
    humidity, temperature = Adafruit_DHT.read_retry(sensor,17)

    return(humidity, temperature)
```

### Important
The function returns:

```text
humidity, temperature
```

---

# 6. SOCKET PROGRAMMING

Socket programming:
- Creates two-way communication between two network nodes.
- Nodes are called **server and client**.
- Server performs the service requested by the client.

## Socket syntax

```python
s = socket.socket(SocketFamily, SocketType, Protocol=0)
```

### Socket family
- `AF_UNIX`
- `AF_INET`

### Socket type
- `SOCK_STREAM`
- `SOCK_DGRAM`

### Protocol
- Default = `0`

---

# 7. WHY UDP IN THE REMOTE LOGGING EXAMPLE?

The assignment explicitly tests that the remote data logging client uses:

```python
socket.AF_INET
socket.SOCK_DGRAM
```

Therefore:

```text
AF_INET + SOCK_DGRAM
        ↓
IPv4 + UDP datagram socket
```

The client sends using:

```python
sock.sendto(message, server_address)
```

The server receives using:

```python
sock.recvfrom(4096)
```

### Exam trap
This Week 7 remote logging example is **UDP**, even though earlier Week 6 material showed TCP with `SOCK_STREAM`.

---

# 8. UDP CLIENT – SENSOR DATA

Lecture client code concept:

```python
sock = socket.socket(socket.AF_INET, socket.SOCK_DGRAM)
server_address = ('10.14.3.194', 10001)

while (1):
    h,t = sensordata()
    message = str(h)+','+str(t)

    sent = sock.sendto(message, server_address)
```

## Message format

```text
humidity,temperature
```

Example concept:

```text
68.9,23.5
```

### Key functions
- `sensordata()` → read DHT
- `str()` → convert values to strings
- `+ ',' +` → join with comma
- `sendto()` → send UDP datagram

---

# 9. UDP SERVER – RECEIVE AND SAVE

Lecture:

```python
sock = socket.socket(socket.AF_INET, socket.SOCK_DGRAM)
server_address = ('10.14.3.194', 10001)
sock.bind(server_address)

while True:
    data, address = sock.recvfrom(4096)

    with open("DataLog.txt","a") as f:
        mess = str(data)
        f.write(mess)
```

## Flow

```text
UDP socket
   ↓
bind()
   ↓
recvfrom()
   ↓
convert received data
   ↓
open DataLog.txt in append mode
   ↓
write()
```

### Important
File mode = **`a`** because data is appended.

---

# 10. DATA PROCESSING

After receiving the data, the lecture performs:
1. **Data splitting/filtering**
2. **Data plotting**

The received values are separated by a comma.

Example:

```python
Data = "sunday,monday,tuesday"
Data.split(",")
```

Output:

```text
['sunday', 'monday', 'tuesday']
```

### Sensor data
If:

```text
68.9,23.5
```

then conceptually:
- first value → humidity
- second value → temperature

---

# 11. MATPLOTLIB

Matplotlib is a Python library used for **2D plotting**.

## Core functions

### `plot(x,y)`
Plots x and y values.

### `xlabel()`
Labels x-axis.

### `ylabel()`
Labels y-axis.

### `title()`
Adds a title.

Example:

```python
import matplotlib.pyplot as myplot

myplot.plot([1,2,3,4])
myplot.ylabel('Y-Axis')
myplot.show()
```

### Important
If only y-values are supplied:
- x-values are generated automatically.
- They start from **0** in the lecture example.

---

# 12. MATPLOTLIB COMMON FUNCTIONS

| Function | Purpose |
|---|---|
| `figure()` | Create new figure |
| `grid()` | Enable/disable axis grid |
| `ion()` | Turn on interactive mode |
| `subplot()` | Add subplot to figure |
| `close()` | Close current figure |
| `scatter()` | Create scatter plot |
| `plot()` | Plot values |
| `xlabel()` | Label x-axis |
| `ylabel()` | Label y-axis |
| `title()` | Add plot title |

### Assignment priority
Interactive mode → **`ion()`**

---

# 13. REAL-TIME TEMPERATURE + HUMIDITY MONITOR

The lecture's server-side plotting example:
- Enables interactive mode using `plt.ion()`.
- Creates a figure.
- Creates two subplots.
- Plots temperature and humidity separately.
- Receives data repeatedly.
- Saves the received message.
- Updates the plot.

The output visual in the Week 7 PDF shows **two separate plots**, one for temperature and one for humidity, along with the received sensor values. This is the visual result of the server-side monitoring code.

### Conceptual flow

```text
UDP data
   ↓
split comma-separated string
   ↓
temperature + humidity
   ↓
subplot 1 → temperature
subplot 2 → humidity
   ↓
interactive update
```

---

# 14. SOFTWARE-DEFINED NETWORKING (SDN)

## 14.1 Motivation

The lecture's traditional-network diagrams show:
- Multiple switches.
- OSPF executing at switches.
- Distributed traffic forwarding.
- A switch can fail/come under attack.
- Traffic may need an alternate path.
- There is **no centralized control**.

The diagrams on lecture pages 42–46 visually emphasize the lack of a global network view and the distributed nature of traditional forwarding.

---

# 15. LIMITATIONS OF CURRENT NETWORKS

## 1. Distributed forwarding
Switches forward traffic independently.

## 2. No global network view
Each switch does not have a complete global view of the network.

## 3. Vendor-specific architecture
Vendor-specific switch architecture limits dynamic configuration.

## 4. OS dependency
Switches are configured according to their installed operating system.

## 5. Centralized control is difficult
Traditional networks are not naturally designed around a centralized controller.

## 6. Expensive specialized hardware
Lecture diagram highlights:
- Millions of gates
- Specialized packet-forwarding hardware
- Large code/software complexity
- Cost-expensive infrastructure

---

# 16. SDN BASIC IDEA

SDN restructures the current network infrastructure.

### Central concept
**Separate control logic from hardware switches.**

Instead of every switch independently implementing all control logic:

```text
Applications
     ↓
Controller / Control Layer
     ↓
Hardware switches / Data plane
```

This allows centralized network-wide control and a global view.

---

# 17. SDN ARCHITECTURE

Three conceptual layers:

```text
Application Layer
       ↓
Control Layer
       ↓
Infrastructure / Data Layer
```

## Application layer
Network applications define requirements/policies.

## Control layer
SDN controller contains control logic and determines forwarding rules.

## Infrastructure layer
Hardware switches execute forwarding rules.

### APIs
Communication between layers occurs through APIs.

---

# 18. SDN COMPONENTS

The lecture lists:
- Hardware switches
- Controller
- Applications
- Flow rules
- APIs

### Memory
**Switch + Controller + Application + Flow-rule + API**

---

# 19. SDN VS OPENFLOW

This is a major exam trap.

### SDN
A **technology/concept/architecture** for separating control from data-plane hardware.

### OpenFlow
A **protocol** used for communication between control plane and data plane.

The lecture explicitly says:

> **SDN is NOT OpenFlow.**

OpenFlow is one protocol used for the control/data-plane interaction.

---

# 20. SDN HISTORY

Memorize the timeline:

| Year | Event |
|---|---|
| **2006** | Stanford team proposes SANE for centralized security policy control |
| **2008** | OpenFlow project; SDN idea originated |
| **2009** | Stanford publishes OpenFlow v1.0.0 specs |
| **2011** | Open Networking Foundation formed |
| **2011 Oct** | First Open Networking Summit |

### Assignment priority
OpenFlow project at ACM SIGCOMM → **2008**

---

# 21. SDN APIs

## Southbound API

Connects:

```text
Control Layer ↔ Infrastructure Layer
```

Lecture uses **OpenFlow**.

### Assignment
Q10 → Southbound API.

---

## Northbound API

Connects:

```text
Control Layer ↔ Application Layer
```

Standard APIs are used.

---

## East-Westbound API

Connects:

```text
Controller ↔ Controller
```

Used for communication among multiple controllers.

### Memory
```text
North = Application
South = Switch/Infrastructure
East-West = Controller-to-controller
```

---

# 22. FLOW RULES

Traditional network:
- Routing table at L3 switch/router.

SDN:
- **Flow table** at each switch.

Each flow-table entry is a **flow rule**.

The controller defines the flow rules.

### Match fields shown
- Source IP
- Destination IP
- Source Port
- Priority
- etc.

---

# 23. RULE PLACEMENT

Switches forward traffic based on controller-defined flow rules.

### Rule placement challenge
Need to decide:
- Which rules should be installed?
- Where should they be installed?
- How to use limited TCAM efficiently?
- How to reduce PACKET-IN messages?

---

# 24. TCAM

TCAM = **Ternary Content-Addressable Memory**

Lecture points:
- TCAM size is limited.
- Therefore only a limited number of rules can be inserted.
- TCAM provides fast processing.
- TCAM is expensive.

### Exam trap
TCAM is not unlimited memory.

---

# 25. PACKET-IN

When a packet arrives and no matching flow rule exists:

```text
Switch
  ↓
PACKET-IN
  ↓
Controller
  ↓
Controller determines flow rule
  ↓
Rule inserted at switch
```

### Number
Typical new-rule placement delay in the lecture:
**3–5 ms**

### Assignment
Q9 → **PACKET-IN**

---

# 26. OPENFLOW VERSIONS

The lecture lists:
- 1.0
- 1.1
- 1.2
- 1.3
- etc.

Different versions provide different numbers of match fields.

---

# 27. HARD TIMEOUT VS SOFT TIMEOUT

## Hard timeout
All rules are deleted when the hard timeout expires.

Possible use:
- Reset the switch/rule state.

## Soft timeout
A rule is deleted if no associated flow is received for the specified time.

Possible use:
- Empty rule space by deleting unused rules.

### Memory
- **Hard** → delete after fixed timeout.
- **Soft** → delete when inactive/no flow for timeout.

---

# 28. OPENFLOW SWITCH SOFTWARE

Lecture examples:
- **Indigo**
- **LINC**
- **Pantou**
- **Of13softswitch**
- **Open vSwitch**

### High-priority fact
The lecture calls **Open vSwitch** the most popular one present today.

---

# 29. CONTROLLER PLACEMENT

Controllers:
- Define flow rules according to application-specific requirements.
- Must handle incoming requests from switches.
- Should place rules without large delay.

### Capacity
A controller can handle approximately:

**200 requests/second through one thread**

This is directly tested in Assignment Q11.

---

# 30. CONTROLLER DISTANCE

Lecture states:
- Controllers are logically connected to switches in one-hop distance.
- Physically, they may be connected through multiple hops.

### Problem
Too few controllers for a large network can cause congestion due to control packets such as PACKET-IN messages.

---

# 31. CONTROLLER ARCHITECTURES

The lecture shows four architectures:

## 1. Flat
Controllers have a flat relationship.

## 2. Hierarchical / Tree
Controllers arranged in hierarchy.

## 3. Ring
Controllers connected in a ring.

## 4. Mesh
Controllers interconnected with multiple paths.

### Visual note
The Week 7 lecture pages 74–77 contain diagrams of these four architectures. The important exam distinction is the topology/organization, not the artistic layout of the diagrams.

---

# 32. CONTROL MECHANISMS

## Distributed control

```text
Subnetwork A → Controller A
Subnetwork B → Controller B
...
```

Control decisions are distributed.

## Centralized control

```text
             Controller
             /   |   \
          Network switches
```

A single controller makes control decisions for the network.

### Assignment
Q12 → **Centralized control**

---

# 33. BACKUP CONTROLLER

If the main controller fails:
- A backup controller is introduced.
- Backup is a replica of the main controller.
- Backup takes over network control.
- Goal → uninterrupted network management.

### Memory
**Main controller down → backup controller takes over**

---

# 34. SDN SECURITY

Lecture lists enhanced security mechanisms using SDN:
- Firewall
- Proxy
- HTTP
- Intrusion Detection System (IDS)

The lecture visual illustrates a possible policy chain involving:

```text
Firewall → IDS → Proxy
```

### Key idea
SDN can centrally coordinate policy enforcement across the network.

---

# 35. EXPERIMENTING WITH SDN

The lecture discusses simulator/emulator requirements.

Infrastructure deployment:
- Must support **OpenFlow**.

Controller placement:
- Must support OpenFlow.

Controller can be:
- **Remote**
- **Local**

Remote controller:
- Can be located elsewhere.
- Communicates using IP address and port number.

---

# 36. MININET

**Mininet**:
- Creates a virtual network with OpenFlow-enabled switches.
- Based on Python.
- Supports remote and local controllers.

### Memory
Mininet → **virtual OpenFlow network**

---

# 37. CONTROLLER SOFTWARE

Lecture examples:
- Pox
- Nox
- FloodLight
- **OpenDayLight**
- **ONOS**

The lecture marks:
- OpenDayLight → Popular
- ONOS → Popular

---

# 38. SDN PERFORMANCE

The lecture summary emphasizes:
- Performance depends on **rule placement**.
- Performance depends on **controller placement**.
- Control-message overhead can increase due to additional PACKET-IN messages.
- SDN enables unified network management using a global network view.

---

# 39. SDN FOR IoT

The lecture's SDN-for-IoT section presents SDN as a way to manage and control IoT networks.

## Benefits

### 1. Intelligent routing
Routing decisions can be dynamically adapted.

### 2. Simplified information collection
Collection, analysis, and decision-making can be coordinated.

### 3. Visibility
Network resources become easier to monitor/manage based on:
- User
- Device
- Application requirements

### 4. Intelligent traffic analysis
Traffic patterns can be analyzed and decisions coordinated.

### Assignment
Benefit tested directly:
**Visibility of network resources**

---

# 40. SDN FOR IoT – APPLICATION AREAS

Lecture diagrams/pages show:

## End-device control
Control:
- Sensors
- Actuators

## Access networks
Rule placement while considering:
- Mobility
- Heterogeneity of end users

## Backbone networks
- Rule placement
- Traffic engineering

## Data centers
- Flow classification
- Enhanced security

### Memory
```text
IoT SDN:
Sensors/Actuators
→ Access devices
→ Backbone
→ Data centers
```

---

# 41. WIRELESS SENSOR NETWORK (WSN) CHALLENGES

Lecture lists:

1. **Real-time programming of sensor nodes**
2. **Vendor-specific architecture**
3. **Resource constrained**
   - Heavy computation cannot be performed.
4. **Limited memory**
   - Too many control programs cannot be inserted.

### Assignment
Q14 → **Limited memory for control programs**

---

# 42. WSN OPPORTUNITIES WITH SDN

Questions raised in the lecture:

- Can sensor nodes be programmed in real time?
- Can forwarding paths be changed in real time?
- Can different sensor nodes be integrated in one WSN?

### Core idea
Use software-defined control to make WSN behavior more dynamic and programmable.

---

# 43. SENSOR OPENFLOW

Lecture example: **Sensor OpenFlow**

Two forwarding styles:

## Value-centric data forwarding
Forward sensed data if it exceeds a certain value.

Example concept:

```text
if sensed_value > threshold:
    forward
```

## ID-centric data forwarding
Forward sensed data based on the source node's ID.

### Important
The lecture notes that a real-life implementation of this method had not been done at that point.

---

# 44. SOFT-WSN

Soft-WSN provides software-based management of sensor networks.

## Sensor Device Management
- Sensor management.
- Multiple sensors can be implemented in a single sensor board.
- Sensors can be selected based on application-specific requirements.

## Delay Management
- Sensing delay can be changed dynamically in real time.

## Active-Sleep Management
- Active and sleep states can be changed dynamically.

---

# 45. SOFT-WSN TOPOLOGY MANAGEMENT

## Node-specific management
Forwarding logic of a particular sensor can be modified.

## Network-specific management
Examples:
- Forward all traffic of a node in the network.
- Drop all traffic of a node in the network.

### Result
Experimental results in the lecture show that Soft-WSN can improve network performance compared with traditional WSN.

---

# 46. SOFT-WSN RESULTS

## Packet delivery ratio
**Increases** with Soft-WSN compared with traditional WSN.

## Replicated data packets
**Decrease** with Soft-WSN.

## Control messages
**Increase** with Soft-WSN.

### Why do control messages increase?
Because of **PACKET-IN** messages.

When a node receives a new packet:
- It asks the controller for suitable forwarding logic.
- This creates additional control traffic.

### Very important comparison

| Metric | Soft-WSN vs Traditional WSN |
|---|---|
| Packet delivery ratio | **Higher** |
| Replicated data packets | **Lower** |
| Control messages | **Higher** |

---

# 47. SDN-WISE

**SDN-WISE** is a software-defined WSN platform.

Lecture says:
- Flow table for rule placement at sensor nodes.
- Any programming language can be used through an API to program nodes in real time.

### Assignment
INPP = **In Network Packet Processing**

---

# 48. SDN-WISE PROTOCOL STACK

A sensor node includes:

```text
Forwarding layer
    ↓
Flow-rules
    ↓
IEEE 802.15.4
    ↓
MCU / sensor-node hardware
```

The lecture specifically identifies:
- IEEE 802.15.4 protocol
- Micro Control Unit (MCU)
- Forwarding layer with flow rules
- **INPP – In Network Packet Processing**

### Assignment priority
Q15 → INPP expansion.

---

# 49. IMPORTANT VISUALS FROM THE WEEK 7 PDF

## Traditional network diagrams — lecture pages 42–46
The diagrams show:
- User I and User II
- Multiple switches
- OSPF executing at switches
- A switch being attacked/failing
- Need for alternate routing
- No centralized control

**Exam meaning:** traditional network control is distributed across switches.

## SDN architecture — lecture page 52
The architecture diagram highlights:
- Application/control/infrastructure separation.
- Northbound API.
- Southbound API via OpenFlow.

**Exam meaning:** control logic is separated from hardware.

## Controller architectures — pages 74–77
The visual diagrams show:
- Flat
- Hierarchical/tree
- Ring
- Mesh

**Exam meaning:** different ways of organizing multiple controllers.

## SDN-WISE stack — page 104
The visual/text stack shows:
- IEEE 802.15.4
- MCU
- Forwarding layer with flow rules
- INPP

**Exam meaning:** SDN-style programmable forwarding is brought into sensor nodes.

---

# 50. HIGH-PRIORITY COMPARISONS

## TCP vs UDP socket type

| TCP | UDP |
|---|---|
| `SOCK_STREAM` | **`SOCK_DGRAM`** |
| Stream | Datagram |
| Connection-oriented | Connectionless |
| Week 6 TCP example | **Week 7 remote logging example** |

### Exam trap
Week 7 remote data logging uses **UDP**, not TCP.

---

## Traditional Network vs SDN

| Traditional | SDN |
|---|---|
| Control logic at switches | Control separated from switches |
| Distributed control | Centralized/logically centralized control possible |
| No global view | Global network view |
| Vendor-specific architecture | Programmable control |
| Routing logic such as OSPF at switches | Controller defines flow rules |
| Switches forward independently | Switches follow controller rules |

---

## Northbound vs Southbound vs East-Westbound

| API | Connection |
|---|---|
| Northbound | Control ↔ Application |
| **Southbound** | Control ↔ Infrastructure |
| East-Westbound | Controller ↔ Controller |

---

## Centralized vs Distributed control

| Centralized | Distributed |
|---|---|
| One controller | Multiple controllers/subnetworks |
| Network-wide control | Control distributed among subnetworks |
| Assignment Q12 | Different subnetworks controlled by different controllers |

---

## Hard vs Soft timeout

| Hard timeout | Soft timeout |
|---|---|
| All rules deleted after timeout | Rule deleted if no associated flow for timeout |
| Can reset switch/rule state | Helps remove unused rules |

---

## Sensor OpenFlow vs Soft-WSN vs SDN-WISE

| Approach | Key idea |
|---|---|
| Sensor OpenFlow | Value-centric / ID-centric forwarding |
| Soft-WSN | Sensor, delay, active-sleep, topology management |
| SDN-WISE | Flow tables + API-based real-time programming |

---

# 51. MCQ/MSQ TRAPS

1. Week 7 remote logging socket → **`SOCK_DGRAM`**.
2. DHT reading → **`Adafruit_DHT.read_retry()`**.
3. Server file → **Datalog/DataLog text file**.
4. File mode → **append `a`**.
5. Split comma-separated data → **`split(",")`**.
6. Matplotlib → **2D plotting**.
7. Interactive plotting → **`ion()`**.
8. Traditional OSPF → **switches**.
9. OpenFlow origin in lecture → **2008**.
10. No flow-rule → **PACKET-IN**.
11. Control ↔ infrastructure → **Southbound API**.
12. Control ↔ application → **Northbound API**.
13. Controller ↔ controller → **East-Westbound API**.
14. One controller → **Centralized control**.
15. Typical controller capacity → **200 requests/sec/thread**.
16. New flow-rule placement delay → **3–5 ms**.
17. TCAM → limited and expensive but fast.
18. SDN ≠ OpenFlow.
19. OpenFlow → protocol.
20. SDN → architecture/concept.
21. SDN + IoT benefit → **visibility of network resources**.
22. WSN memory challenge → **limited memory for control programs**.
23. Sensor OpenFlow → value-centric + ID-centric.
24. Soft-WSN packet delivery ratio → **increases**.
25. Soft-WSN replicated packets → **decreases**.
26. Soft-WSN control messages → **increase**.
27. Reason for extra control messages → **PACKET-IN**.
28. SDN-WISE → flow table at sensor nodes.
29. INPP → **In Network Packet Processing**.
30. SDN-WISE lower protocol → **IEEE 802.15.4**.
31. SDN-WISE includes an **MCU**.
32. DHT pin order → power, data, null, ground.
33. DHT example input pin → **11**.
34. DHT resistor → **4.7 kΩ**.

---

# 52. NUMBERS / DATES TO MEMORIZE

| Fact | Value |
|---|---|
| DHT resistor | **4.7 kΩ** |
| DHT example input pin | **11** |
| UDP server port in lecture | **10001** |
| UDP receive buffer | **4096** |
| Controller capacity | **200 requests/s/thread** |
| New rule placement delay | **3–5 ms** |
| SDN/SANE history | **2006** |
| OpenFlow / SDN origin | **2008** |
| OpenFlow v1.0.0 | **2009** |
| ONF formed | **2011** |

---

# 53. CODE RECOGNITION DRILL

## UDP socket
```python
sock = socket.socket(socket.AF_INET, socket.SOCK_DGRAM)
```

→ UDP / datagram socket.

## DHT reading
```python
humidity, temperature = Adafruit_DHT.read_retry(sensor,17)
```

→ Reads humidity and temperature.

## Sensor message
```python
message = str(h)+','+str(t)
```

→ Comma-separated sensor data.

## UDP send
```python
sock.sendto(message, server_address)
```

→ Sends UDP data.

## UDP receive
```python
data, address = sock.recvfrom(4096)
```

→ Receives UDP datagram.

## Append to log
```python
with open("DataLog.txt","a") as f:
```

→ Appends to data log.

## Split
```python
Data.split(",")
```

→ Splits comma-separated string.

## Interactive Matplotlib
```python
plt.ion()
```

→ Enables interactive mode.

## Plot
```python
plt.plot(x,y)
```

→ 2D plot.

---

# 54. SDN FLOW RECOGNITION

## No matching flow rule
```text
Packet
  ↓
Switch
  ↓
No match
  ↓
PACKET-IN
  ↓
Controller
  ↓
New flow-rule
  ↓
Switch
```

## Southbound
```text
Application
     ↓
Control Layer
     ↓
Southbound API
     ↓
Infrastructure
```

## Northbound
```text
Application
     ↕
Northbound API
     ↕
Control Layer
```

## East-Westbound
```text
Controller A ↔ Controller B
```

---

# 55. ONE-PAGE FINAL REVISION

## REMOTE LOGGING
```text
DHT
 ↓
Raspberry Pi
 ↓
Adafruit_DHT.read_retry()
 ↓
humidity, temperature
 ↓
message = h + "," + t
 ↓
UDP SOCK_DGRAM
 ↓
sendto()
 ↓
Server recvfrom()
 ↓
DataLog.txt append
 ↓
split(",")
 ↓
Matplotlib
```

### Must know
- UDP → `SOCK_DGRAM`
- DHT function → `read_retry()`
- File → DataLog/Datalog.txt
- Append → `a`
- Split → `split(",")`
- Interactive plot → `ion()`

---

## SDN
```text
Application Layer
       ↓
Control Layer / Controller
       ↓
Infrastructure / Switches
```

### APIs
- Northbound → control/application
- Southbound → control/infrastructure
- East-Westbound → controller/controller

### Flow
```text
No matching rule
      ↓
PACKET-IN
      ↓
Controller
      ↓
Flow-rule
      ↓
Switch
```

### Key values
- OpenFlow origin → **2008**
- Controller → **200 requests/s/thread**
- Rule placement → **3–5 ms**
- TCAM → limited, fast, expensive

---

## SDN + IoT
Benefits:
- Intelligent routing
- Simplified information processing
- Visibility
- Traffic analysis
- Coordinated decisions

Applications:
- Sensors/actuators
- Access devices
- Backbone
- Data centers

---

## SOFTWARE-DEFINED WSN
Challenges:
- Real-time programming
- Vendor-specific architecture
- Resource constraints
- Limited memory

Approaches:
- Sensor OpenFlow
- Soft-WSN
- SDN-WISE

### Soft-WSN
- Delivery ratio ↑
- Replicated packets ↓
- Control messages ↑

### SDN-WISE
- IEEE 802.15.4
- MCU
- Flow rules
- INPP = In Network Packet Processing

---

# 56. LAST-MINUTE 15-ANSWER DRILL

1. Week 7 remote logging socket?  
   **`SOCK_DGRAM`**

2. DHT read function?  
   **`Adafruit_DHT.read_retry()`**

3. Server log file?  
   **Datalog/DataLog.txt**

4. Split comma-separated data?  
   **`split()`**

5. Plotting library?  
   **Matplotlib**

6. Interactive plotting function?  
   **`ion()`**

7. Traditional OSPF executes where?  
   **At switches**

8. OpenFlow project year?  
   **2008**

9. No flow-rule message?  
   **PACKET-IN**

10. Control ↔ infrastructure API?  
   **Southbound**

11. Controller capacity?  
   **200 requests/sec/thread**

12. One-controller mechanism?  
   **Centralized control**

13. SDN + IoT benefit?  
   **Visibility of network resources**

14. Key WSN resource challenge?  
   **Limited memory for control programs**

15. INPP?  
   **In Network Packet Processing**

---

# 57. EXAM STRATEGY

### Priority 1 — Memorize the 15 assignment answers
The assignment directly tests:
- UDP
- DHT reading
- File logging
- String splitting
- Matplotlib
- Traditional routing
- SDN history
- PACKET-IN
- SDN APIs
- Controller capacity
- Centralized control
- SDN-IoT benefits
- WSN constraints
- SDN-WISE

### Priority 2 — Memorize these 10 facts
1. `SOCK_DGRAM`
2. `read_retry()`
3. `DataLog.txt`
4. `split(",")`
5. `ion()`
6. OSPF → switches
7. OpenFlow → 2008
8. PACKET-IN
9. Southbound API
10. INPP

### Priority 3 — Memorize numbers
- 4.7 kΩ
- Pin 11
- Port 10001
- Buffer 4096
- 200 requests/s/thread
- 3–5 ms
- 2008

### Priority 4 — Understand the two big flows

**Remote logging:**
```text
Sensor → Pi → UDP → Server → File → Split → Plot
```

**SDN:**
```text
Application → Controller → Flow Rules → Switch
```

---

# 58. SOURCE / PAGE MAP

The uploaded Week 7 lecture PDF contains **106 pages** and is divided into:

- **Pages 1–19:** Implementation of IoT with Raspberry Pi – Part 2
- **Pages 20–40:** Implementation of IoT with Raspberry Pi – Part 3
- **Pages 41–67:** Software-Defined Networking – Part I
- **Pages 69–85:** Software-Defined Networking – Part II
- **Pages 87–105:** Software-Defined IoT Networking – Part I
- **Page 106:** closing slide

The Week 7 assignment contains **8 pages and 15 questions / 15 marks**.

### Particularly important lecture pages
- Pages **4–18** → remote logging and UDP implementation.
- Pages **23–38** → data processing and Matplotlib.
- Pages **43–65** → traditional network, SDN architecture, flow rules, PACKET-IN, OpenFlow.
- Pages **71–85** → APIs, controller placement, architectures, control, security, Mininet and controller software.
- Pages **89–105** → SDN for IoT, WSN challenges, Soft-WSN, SDN-WISE.

---

# FINAL MEMORY LINE

**Week 7 = Remote Logging + SDN:**  
**DHT → `read_retry()` → UDP `SOCK_DGRAM` → `sendto()` → `recvfrom()` → DataLog.txt → `split(",")` → Matplotlib `ion()`; Traditional OSPF runs at switches; SDN separates control from hardware; OpenFlow = 2008; no rule → PACKET-IN; Southbound = control↔infrastructure; 200 requests/s/thread; centralized = one controller; SDN+IoT gives visibility; WSN has limited memory; SDN-WISE INPP = In Network Packet Processing.**
