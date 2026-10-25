# NPTEL – Introduction to Internet of Things
## Week 1 Exam Preparation Notes

> **Source basis:** Week-1 assignment and the uploaded Week-1 lecture PDFs (Part I, Part II, Sensing/Actuation/Networking).  
> The notes below preserve the terminology and framing used in the uploaded material.

---

# 1. Week 1 – Quick Revision

## Core topics
1. Introduction to IoT
2. Origin and definitions of IoT
3. IoT characteristics
4. IoT applications and connected-device evolution
5. IoT vs M2M
6. IoT vs Web of Things (WoT)
7. IoT addressing and address crunch
8. IoT LAN, WAN, Node, Gateway and Proxy
9. Local/LU addressing and gateway prefix allotment
10. Mobility and multi-homing
11. IPv4 vs IPv6
12. Sensors, transducers and sensor features
13. Sensor resolution and sensor classes
14. Sensor errors: sensitivity, offset/bias, nonlinearity, drift, noise, hysteresis, quantization and aliasing
15. Actuators and actuator types
16. Shape Memory Polymer actuators
17. Basics of IoT networking and the IoT implementation example

---

# 2. Introduction to IoT

## Definition / idea

The lecture describes IoT as Internet technology connecting devices, machines and tools to the Internet, together with the unification of technologies such as low-power embedded systems, cloud computing, big data, machine learning and networking.

An alternate definition in the lecture describes IoT as a network of physical objects containing embedded technology to communicate, sense, or interact with their internal states or the external environment.

### Important IoT characteristics
- Efficient and scalable architecture
- Unambiguous naming and addressing
- Abundance of sleeping nodes
- Mobile nodes
- Non-IP devices
- Intermittent connectivity

**Exam trap:** IoT does **not** require guaranteed continuous connectivity for every device.

---

# 3. Origin of the IoT Terminology

The lecture refers to the **ITU Internet Report 2005, “The Internet of Things.”**

The vision was that humans could become a minority as generators and receivers of Internet traffic, while much of the traffic would flow between devices and different kinds of “things.”

### IoT enablers mentioned
- RFID
- Nanotechnology
- Sensors
- Smart Networks

---

# 4. IoT Applications and Evolution

## Major application areas
### Business / Manufacturing
- Real-time analytics of supply chains and equipment
- Robotic machinery

### Healthcare
- Portable health monitoring
- Electronic recordkeeping
- Pharmaceutical safeguards

### Retail
- Inventory tracking
- Smartphone purchasing
- Anonymous analytics of consumer choices

### Security
- Biometric and facial-recognition locks
- Remote sensors

## Connected-device evolution examples
- ATMs
- Web
- Smart meters
- Digital locks
- Smart healthcare
- Smart vehicles
- Smart cities
- Smart dust

### Smart Dust
Very tiny computing devices, smaller than a grain of sand, that can be sprayed or injected for sensing purposes. The lecture gives examples such as measuring chemicals in soil and diagnosing problems in the human body.

---

# 5. IoT vs M2M

## M2M
M2M means **Machine-to-Machine** communication and interaction.

M2M:
- Focuses on communication between machines/devices
- Can use cloud infrastructure
- Can collect machine and/or sensor data
- Places emphasis on communication networks

## Relationship
**M2M is part of IoT.**

IoT has a broader scope and can include:
- Thing ↔ Thing
- Thing ↔ People
- Thing ↔ Applications
- People ↔ Applications

### Exam memory
> **M2M ⊂ IoT**

---

# 6. IoT vs Web of Things (WoT)

IoT creates a network involving objects, things, people, systems and applications.

WoT attempts to integrate IoT resources with the **Web**.

### WoT technologies / approach
- HTML
- JavaScript
- Ajax
- PHP
- Ruby on Rails
- RESTful principles
- REST APIs

WoT can be viewed as an application-layer approach over the IoT network layer.

### Important distinction
IoT has a broader scope than WoT because some IoT systems may not be accessible through the Web, such as conventional WSN and RFID systems.

---

# 7. IoT Address Crunch

The lecture discusses the large number of connected devices and the resulting addressing problem.

Reasons include:
- Integration of existing devices
- Smart devices
- Constrained nodes
- Cellular connectivity
- Wi-Fi
- Ethernet
- BLE
- DASH7
- Insteon
- IEEE 802.15.4

This large and heterogeneous device population creates a need for efficient addressing strategies.

---

# 8. IoT Connectivity Terminology

| Term | Meaning |
|---|---|
| **IoT LAN** | Local, short-range communication; may or may not connect to Internet; building/organization-wide |
| **IoT WAN** | Connects network segments over organizational/geographical areas and connects to the Internet |
| **IoT Node** | Node connected to other nodes through IoT LAN; may sometimes connect to Internet through WAN |
| **IoT Gateway** | Router connecting IoT LAN to WAN/Internet and forwarding packets |
| **IoT Proxy** | Performs active application-layer functions between IoT nodes and other entities |

---

# 9. Local Addressing and Gateway Prefix Allotment

Nodes within a gateway's jurisdiction can have addresses valid only inside that gateway domain.

The **same local address can be reused under another gateway**.

### Advantage
This saves address space and avoids unnecessary global-address wastage.

The gateway has a unique network prefix that can be used to identify the nodes globally.

### Gateway functions
IoT gateways can provide:
- Internet connectivity
- IoT LAN intra-connectivity
- Upstream prefix acquisition, e.g. DHCPv6
- Address delegation to nodes using SLAAC

### Important terms
- **LU:** locally unique address
- **ULA:** used in the mobility/addressing discussion for keeping LAN addressing stable while WAN addressing changes
- **SLAAC:** Stateless Address Autoconfiguration
- **DHCPv6:** mechanism used for obtaining IPv6 addressing/prefix information

---

# 10. Mobility and Addressing

When a network moves, the network prefix can change.

The lecture explains that:
- The network prefix may change due to movement.
- The IoT LAN can remain protected from changes caused by movement.
- The gateway WAN address can change without changing the LAN address.
- ULA is used in the discussed approach.
- LU addressing helps keep node addresses unchanged within a gateway.

### Tunneling
For nodes that need direct Internet communication, tunneling can be used so that communication goes toward a remote anchor point.

---

# 11. Application-Layer Proxy

LU addresses provide internal address stability, but they cannot directly communicate with the Internet/upper layers.

An **application-layer proxy** can solve this.

The proxy may:
- Relay data
- Process data
- Gather data from nodes
- Route data globally

---

# 12. Multi-homing

**Multi-homing** means a node/network is connected to multiple networks for improved reliability.

Challenges include:
- Managing multiple IP addresses
- Mapping IP addresses to link-local addresses
- Source/destination address selection
- Routing information
- Gateway selection

For small IoT LANs, proxy-based or gateway-based approaches may be used.

---

# 13. IPv4 vs IPv6

| Feature | IPv4 | IPv6 |
|---|---|---|
| Address length | 32 bits | 128 bits |
| Number of addresses | 2^32 | 2^128 |
| Notation | Dotted decimal | Hexadecimal |
| Dynamic allocation in lecture table | DHCP | SLAAC / DHCPv6 |
| IPsec | Optional | Compulsory |
| Header size | Variable | Fixed |
| Header checksum | Yes | No |
| Header options | Yes | No |
| Broadcast | Yes | No |
| Multicast | No | Yes |

### Why IPv6 is important for IoT
The much larger address space is suitable for large-scale IoT addressing.

### IPv6 header
The lecture highlights fields such as:
- Version
- Traffic Class
- Flow Label
- Payload Length
- Next Header
- Hop Limit
- Source Address
- Destination Address

---

# 14. Sensors

## Definition
A sensor detects/senses changes in ambient conditions or the state of another device/system and forwards or processes the information.

### Sensor examples
- Temperature sensor
- Barometer
- Pressure sensor
- Ultrasonic distance sensor
- Tilt sensor
- Infrared motion sensor
- Camera sensor

---

# 15. Sensors vs Transducers

## Sensor
A sensor detects/measures a physical property.

Examples:
- Temperature sensor
- Pressure sensor

## Transducer
A transducer converts energy from one form to another.

Example:
- Microphone: sound → electrical signal
- Loudspeaker: electrical signal → sound

The lecture also uses “transducer” as a collective term involving sensors and actuators in the cited context.

---

# 16. Good Sensor Features

A good sensor should:

1. Be sensitive to the property being measured.
2. Be insensitive to unrelated properties.
3. Not influence/disturb the measured property.

### Example
A temperature sensor should respond to temperature and should not be significantly affected by unrelated properties such as light or pressure.

---

# 17. Sensor Resolution

**Resolution = the smallest change in the measured quantity that the sensor can detect.**

For a digital sensor, resolution is related to the smallest digital output step it can process.

### Very important
**Resolution and accuracy are not the same thing.**

A sensor can have high resolution but still have poor accuracy due to bias/calibration errors.

---

# 18. Sensor Classes

## Based on output
- Analog
- Digital

### Analog sensor
Produces a continuous output signal/voltage generally proportional to the measured quantity.

Examples of continuous physical quantities:
- Temperature
- Speed
- Pressure
- Displacement
- Strain

### Digital sensor
Produces discrete digital output.

A binary output can be:
- Logic 1 / ON
- Logic 0 / OFF

---

# 19. Scalar vs Vector Sensors

## Scalar sensor
Measures a quantity where magnitude is sufficient.

Example:
- Room temperature

## Vector sensor
Produces information related to magnitude, direction and/or orientation.

Examples:
- Acceleration
- Velocity
- Orientation
- Sound/image in the lecture's classification

### Accelerometer
An accelerometer can measure acceleration components along:
- X-axis
- Y-axis
- Z-axis

Therefore, the assignment classifies it as a **vector sensor**.

---

# 20. Sensor Types to Remember

| Physical quantity | Example sensor |
|---|---|
| Light | LDR, photodiode |
| Temperature | Thermocouple, thermistor |
| Force | Strain gauge, pressure switch |
| Position | Potentiometer, encoder |
| Speed | Opto-coupler, Doppler-effect sensor |
| Sound | Carbon microphone, piezoelectric crystal |
| Chemical | Liquid/gaseous chemical sensor |

---

# 21. Sensor Errors / Deviations

## Full-scale range
The full-scale range defines the maximum and minimum values of the measured property that the sensor can represent.

## Sensitivity error
The actual sensitivity differs from the specified sensitivity.

## Offset / Bias error
The output differs from the correct value by a constant amount.

## Nonlinearity
Deviation of the sensor transfer function from an ideal straight-line transfer function.

## Drift
The output slowly changes independently of the measured property.

Long-term drift can occur because of physical changes in the sensor.

## Noise
Random deviation of the signal that varies with time.

## Hysteresis error
The output depends on previous input history.

The same input can produce different outputs depending on whether the input was reached by increasing or decreasing the measured quantity.

## Quantization error
For a digital output, the measured quantity is represented approximately using discrete values.

## Dynamic / aliasing errors
Digital monitoring can introduce dynamic errors due to sampling frequency; periodic signals/noise can produce aliasing when related to the sampling rate.

---

# 22. Actuators

An **actuator** is a component that moves or controls a mechanism/system.

An actuator:
- Requires a control signal
- Requires a source of energy
- Converts energy into mechanical motion after receiving the control signal

The control system can be:
- Fixed mechanical/electronic system
- Software-based
- Human input
- Other input

---

# 23. Actuator Types

1. Hydraulic
2. Pneumatic
3. Electrical
4. Thermal / Magnetic
5. Mechanical

---

# 24. Hydraulic Actuators

A hydraulic actuator uses hydraulic power for mechanical operation.

It can produce:
- Linear motion
- Rotary motion
- Oscillatory motion

### Key point
Liquids are nearly incompressible, so hydraulic actuators can exert considerable force.

**Exam answer:** The statement “A hydraulic actuator can produce considerable force because liquids are nearly incompressible” is **True**.

---

# 25. Pneumatic Actuators

Pneumatic actuators convert energy from vacuum or compressed air into:
- Linear motion
- Rotary motion

Important points:
- Quick response to starting/stopping signals
- Convert pressure into force
- Can produce large forces from relatively small pressure changes
- Example: pneumatic brakes
- Rack-and-pinion pneumatic actuators can control valves

---

# 26. Electrical Actuators

Electrical actuators are generally powered by a motor that converts electrical energy into mechanical torque.

Examples:
- Motor-driven rotary actuator
- Solenoid valve

The lecture describes them as relatively cheap, clean and speedy actuator types.

---

# 27. Thermal / Magnetic Actuators

These are actuated using:
- Thermal energy
- Magnetic energy

Characteristics:
- Compact
- Lightweight
- Economical
- High power density

They can use shape-memory materials such as:
- Shape Memory Alloys (SMAs)
- Magnetic Shape Memory Alloys (MSMAs)

---

# 28. Mechanical Actuators

Mechanical actuators convert rotary motion into linear motion to execute movement.

They can involve:
- Gears
- Rails
- Pulleys
- Chains

### Example
**Rack and pinion**

---

# 29. Soft Actuators and Shape Memory Polymers

Soft actuators, including polymer-based actuators, can be used for:
- Handling fragile objects
- Fruit harvesting
- Biomedical manipulation
- Robotics

They produce flexible motion through molecular-level changes resulting in macroscopic deformation.

## Shape Memory Polymer (SMP) actuators

SMP actuators can respond to:
- Light
- Electrical stimuli
- Magnetic stimuli
- Heat
- pH
- Moisture

Important properties:
- Low density
- High strain recovery
- Biocompatibility
- Biodegradability

### Light Activated Polymers (LAP)
- Special type of SMP
- Activated by light
- Instant response
- Can be controlled remotely without physical contact by changing light frequency/intensity

---

# 30. Basics of IoT Networking

## Main IoT components
- Device / Thing
- Local Network
- Internet
- Backend Services
- Applications

## Functional components
- Interaction/communication with other IoT devices
- Processing and analysis
- Internet interaction
- Web-service handling
- Application-service integration
- User interface

---

# 31. Example IoT Implementation

The lecture's example contains:

**Sensor → Sensor Mote / Processor / Radio → Gateway → Proxy Server → Internet / WebSocket → Cloud Server → Analytics → Actuation**

The assignment specifically asks about the path:

**Sensor → Gateway → Proxy Server → Cloud Server**

and marks this statement **True**.

---

# 32. IoT Categories

## Industrial IoT
- Device connects to an IP network/global Internet
- Communication can use regular and industry-specific technologies

## Consumer IoT
- Devices communicate within local networks
- Common technologies include Bluetooth, Zigbee and Wi-Fi
- Communication is generally limited locally by a gateway

---

# 33. IoT Challenges

Important challenges listed in the lecture:

- Interfacing
- Interoperability
- Data storage
- Data analytics
- Complexity management
- Security
- Scalability
- Energy efficiency
- Bandwidth management
- Modeling and analysis

### Network complexity
- Network growth
- Device interference
- Network management
- Network heterogeneity
- Protocol standardization

### Scalability
- Flexibility within the Internet
- IoT integration
- Large-scale deployment
- Real-time connectivity of billions of devices

---

# 34. Assignment – Week 1 (15 Questions)

## Q1. Future Internet / ITU 2005
**Question:** Why was the future Internet expected to become wider and more complex?

**Answer:** **b. Most Internet traffic may flow between devices and different kinds of things.**

**Reason:** Humans may become a minority of traffic generators/receivers, while communication increasingly occurs between devices and things.

---

## Q2. Characteristics of IoT
**Correct answers:** **a, b, c**

- Efficient and scalable architecture
- Unambiguous naming and addressing
- Sleeping nodes, mobile nodes and non-IP devices

**Incorrect:** Guaranteed continuous connectivity.

---

## Q3. Smart Dust
**Correct answer:** **c. Very tiny computing devices that can be sprayed or injected for sensing purposes.**

**Remember:** Smaller than a grain of sand; examples include soil chemical measurement and medical diagnosis.

---

## Q4. IoT vs M2M
**Correct answer:** **c. M2M is a part of IoT, while IoT has a broader scope of interactions.**

**Memory:** M2M ⊂ IoT.

---

## Q5. Web of Things
**Statement:** In WoT, IoT sensors are completely replaced by cloud databases.

**Answer:** **False.**

Sensors still collect physical-world data; Web technologies expose/access IoT resources.

---

## Q6. Local addresses
**Correct answer:** **b. It helps conserve address space.**

Local addresses can be reused in different gateway domains, avoiding unnecessary global-address consumption.

---

## Q7. IoT gateway functions
**Correct answers:** **a, b, c, d**

- Internet connectivity
- IoT LAN intra-connectivity
- Obtain upstream prefixes using mechanisms such as DHCPv6
- Delegate addresses using SLAAC

---

## Q8. IPv6 vs IPv4
**Correct answer:** **c. IPv6 uses hexadecimal notation and supports a much larger address space.**

Key numbers:
- IPv4 = 32 bits = 2^32 addresses
- IPv6 = 128 bits = 2^128 addresses

---

## Q9. Good sensor
**Correct answer:** **c. It should be sensitive to the measured property and should not disturb it.**

It should also remain insensitive to unrelated properties.

---

## Q10. Sensor resolution
**Correct answers:** **a, b, d**

- Resolution = smallest detectable change
- Digital sensor resolution relates to smallest digital output step
- Accuracy does not depend only on resolution

**Do not equate resolution with accuracy.**

---

## Q11. Accelerometer
**Statement:** An accelerometer measuring x, y and z acceleration is a vector sensor.

**Answer:** **True.**

It measures acceleration components along coordinate axes.

---

## Q12. Hysteresis
**Correct answer:** **b. Hysteresis error.**

The output depends on previous input history; the same current input can produce different readings depending on whether the input was increasing or decreasing.

---

## Q13. Hydraulic actuator
**Statement:** A hydraulic actuator can produce considerable force because liquids are nearly incompressible.

**Answer:** **True.**

---

## Q14. Shape Memory Polymer actuators
**Correct answers:** **a, b, c**

They:
- Respond to light, heat, electrical, magnetic, pH or moisture stimuli
- Can show high strain recovery
- May have low density and biocompatibility

**Incorrect:** They are only passive temperature sensors.

---

## Q15. IoT implementation data path
**Statement:** Sensor data travels through a gateway and proxy server before arriving at the cloud server.

**Answer:** **True.**

Path to remember:

**Sensor → Gateway → Proxy Server → Cloud Server**

---

# 35. High-Priority Exam Memory List

Memorize these first:

1. **M2M is part of IoT.**
2. **WoT integrates IoT resources with the Web.**
3. **Smart Dust = extremely tiny sensing/computing devices.**
4. **IoT characteristics include intermittent connectivity.**
5. **Local addresses can be reused under different gateways → address conservation.**
6. **Gateway: Internet connectivity + IoT LAN connectivity.**
7. **DHCPv6 → upstream prefixes; SLAAC → address delegation/stateless addressing.**
8. **IPv4 = 32-bit; IPv6 = 128-bit.**
9. **IPv4 dotted decimal; IPv6 hexadecimal.**
10. **IPv6 has a much larger address space.**
11. **Good sensor = sensitive to target property, insensitive to unrelated properties, does not disturb target.**
12. **Resolution = smallest detectable change.**
13. **Resolution ≠ accuracy.**
14. **Accelerometer (x,y,z) = vector sensor.**
15. **Hysteresis = output depends on previous input history.**
16. **Hydraulic actuator → high force because liquid is nearly incompressible.**
17. **SMP stimuli = light, electrical, magnetic, heat, pH, moisture.**
18. **SMP properties = low density, high strain recovery, biocompatibility, biodegradability.**
19. **IoT path example = Sensor → Gateway → Proxy → Cloud.**
20. **IoT challenges = security, scalability, interoperability, energy, storage, analytics, bandwidth.**

---

# 36. Rapid MCQ Traps

| If question says... | Think... |
|---|---|
| “Humans become minority in traffic” | IoT / ITU 2005 |
| “Tiny devices smaller than sand” | Smart Dust |
| “Machine-to-machine” | M2M |
| “M2M broader than IoT” | **False** |
| “Sensors replaced by cloud in WoT” | **False** |
| “Same local address in multiple gateway domains” | Address conservation |
| “128-bit hexadecimal” | IPv6 |
| “Smallest detectable change” | Resolution |
| “Same input, different output based on history” | Hysteresis |
| “x, y, z acceleration” | Vector sensor |
| “Nearly incompressible liquid” | Hydraulic actuator |
| “High strain recovery + biocompatibility” | Shape Memory Polymer |
| “Sensor → Gateway → Proxy → Cloud” | IoT implementation example |

---

# 37. One-Page Final Revision

### IoT
- Connects things/devices/machines
- Scalable
- Unambiguous addressing
- Sleeping/mobile/non-IP nodes
- Intermittent connectivity

### M2M
- Machine-to-machine communication
- **Part of IoT**

### WoT
- Brings IoT resources to the Web
- REST / REST APIs
- Web technologies

### Addressing
- Local/LU addresses
- Gateway prefixes
- DHCPv6
- SLAAC
- ULA
- Address conservation
- Mobility
- Multi-homing

### IPv6
- 128-bit
- Hexadecimal
- 2^128 addresses
- No broadcast
- Multicast supported

### Sensor
- Detects/measures physical property
- Resolution = smallest detectable change
- Analog/digital
- Scalar/vector
- Errors: bias, sensitivity, nonlinearity, drift, noise, hysteresis, quantization, aliasing

### Actuator
- Converts energy into mechanical action
- Hydraulic
- Pneumatic
- Electrical
- Thermal/magnetic
- Mechanical
- Soft/SMP

### Networking
- Device → Local Network → Internet → Backend → Application
- Example: Sensor → Gateway → Proxy → Cloud → Analytics → Actuation

---

## Source files used

- `NPTEL-Assignment_W1.pdf` – 15-question Week 1 assignment and solutions.
- `Week-1_A.pdf` – Introduction to IoT – Part I.
- `Week-1_B.pdf` – Introduction to IoT – Part II.
- `Week-1_C.pdf` – Sensing, Actuation and Basics of IoT Networking.

