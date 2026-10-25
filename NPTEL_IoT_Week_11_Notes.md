# NPTEL Introduction to Internet of Things — Week 11 Exam Notes

## Assignment Priority + Complete Lecture Coverage

**Week:** 11  
**Exam type:** MCQ/MSQ  
**Assignment:** 15 questions, 15 marks  
**Lecture PDF:** 132 pages

> **Study rule:** Assignment questions are the highest-priority revision source. They are placed first. After the assignment, all major lecture topics are covered so that questions outside the assignment are also prepared.

---

# 1. WEEK 11 ULTRA-QUICK REVISION

## Smart Grid
- Traditional grid: centralized generation, **one-directional energy flow**, manual monitoring/restoration.
- Smart Grid: modernized grid with **bidirectional energy flow + two-way communication/control**.
- Key benefits: efficiency, faster restoration, lower peak demand, renewable integration, improved security.
- Smart-home interface: **smart meter**.
- Time-of-Use pricing → shift consumption to **off-peak** hours.
- Net metering → bill depends on **energy inflow + energy outflow**.
- PMU → samples voltage/current; multiple PMUs form a phasor network analyzed by SCADA.
- Distribution intelligence → outage detection, automated switching/restoration, real/reactive power optimization.
- Gateway → connects nearby smart meters to **DAUs**.
- DoS → attacks **availability**.

## IIoT
- IIoT = IoT applied to industry.
- Links automation with **enterprise, planning and product lifecycle**.
- Uses ML, Big Data, M2M and automation.
- **Wrap & re-use**, not rip & replace.
- Industry 4.0 → IIoT.
- Key design objectives: Energy, Latency, Throughput, Scalability, Topology, Safety/Security.
- IIoT focuses on industrial efficiency, safety and security; M2M is extensive.
- Applications: manufacturing, healthcare, transportation/logistics, mining, firefighting.
- Mining → air quality, poisonous gases, oxygen level.
- Transportation → DSRC for V2V/V2R.
- Challenges: identification, huge data, integration of existing infrastructure, storage, safety, standardization, privacy/security.

## Big Data + Data Handling
- Data flow: **Generation → Acquisition → Storage → Analysis**
- Big Data = **7 Vs**:
  - Volume
  - Velocity
  - Variety
  - Variability
  - Veracity
  - Visualization
  - Value
- Veracity → **bias, noise, abnormality**.
- Structured data → organized, often relational/SQL.
- Unstructured data → no predefined model.
- Pre-processing:
  - Integration
  - Cleaning
  - Redundancy mitigation
- Redundancy mitigation → detection + filtering + compression to remove repeated data.
- HDFS:
  - **Namenode = metadata**
  - **Datanode = actual data blocks**
  - Files divided into blocks and replicated.
- Hadoop building blocks:
  - Hadoop Common
  - HDFS
  - MapReduce
  - YARN

---

# 2. ASSIGNMENT-FIRST: ALL 15 QUESTIONS

## Q1. Which feature distinguishes a smart grid from a traditional electrical grid?

**Answer: C — It enables bidirectional flows of energy with two-way communication and control.**

### Explanation
The NIST definition used in the lecture describes the Smart Grid as a modernized grid supporting:
- bidirectional energy flows,
- two-way communication,
- two-way control,
- new functionalities and applications.

Traditional grids are characterized by:
- centralized generation,
- one-directional distribution,
- manual monitoring/restoration.

### Exam trap
Do **not** select:
- one-directional energy,
- manual restoration,
- only centralized generation.

**Memory:** `Smart Grid = Bidirectional Energy + Two-Way Communication/Control`

**Lecture:** Smart Grid Part I, Slide 3.

---

## Q2. What is the role of a smart meter in a smart home?

**Answer: B — It provides the Smart Grid interface between the consumer and the energy service provider.**

### Explanation
Smart meters:
- operate digitally,
- enable automated information exchange,
- provide usage information,
- connect the consumer side to the energy service provider,
- can help reduce energy costs.

### Trap
A smart meter is **not** the same thing as:
- a renewable energy generator,
- a home energy management system,
- a simple one-way meter.

**Memory:** `Smart Meter = Consumer ↔ Energy Service Provider interface`

**Lecture:** Smart Grid Part I, Slide 14.

---

## Q3. Under Time-of-Use pricing, when are consumers encouraged to operate smart appliances?

**Answer: A — During off-peak hours.**

### Explanation
Energy demand changes throughout the day.

During on-peak periods:
- demand is high,
- distribution can become less efficient,
- more expensive/non-renewable generation may be needed.

Time-of-Use pricing encourages consumers to shift appliance operation to:
- lower-load periods,
- lower-price periods.

### Memory
`TOU → Off-Peak → Lower load + Lower cost`

**Lecture:** Smart Grid Part I, Slide 20.

---

## Q4. In net metering, what two energy flows determine the consumer's final bill?

**Answer: D — Energy inflow from the grid and energy outflow from the consumer to the grid.**

### Explanation
With home generation such as rooftop solar, a consumer may:
- consume electricity from the grid,
- send excess generated electricity back to the grid.

The final net-metering value considers both directions.

### Memory
`Net metering = Grid → Home + Home → Grid`

**Lecture:** Smart Grid Part I, Slide 21.

---

## Q5. Which device samples voltage and current for monitoring the transmission system?

**Answer: A — Phasor Measurement Unit (PMU).**

### Explanation
A PMU:
- samples voltage and current at its installed location,
- provides a snapshot of the active power system,
- can provide dynamic information at higher sampling rates,
- helps identify possible blackouts in advance.

Multiple PMUs form a:
- **phasor network**.

The collected information can be analyzed by:
- centralized **SCADA**.

### Memory
`PMU → Voltage + Current → Phasor Network → SCADA`

**Lecture:** Smart Grid Part II, Slide 3.

---

## Q6. Which is a function of distribution intelligence?

**Answer: B — Identifying the source of a power outage and supporting automatic power-flow restoration.**

### Explanation
Distribution intelligence equips the distribution system with smart IoT devices.

Together with smart meters it can:
- identify outage sources,
- perform automated switching,
- restore power flow,
- optimize real and reactive power,
- protect/control feeder lines.

### Trap
Distribution intelligence is about **automation and intelligent control**, not restricting communication.

**Memory:** `Distribution Intelligence → Detect + Switch + Restore + Optimize`

**Lecture:** Smart Grid Part II, Slide 5.

---

## Q7. What does a smart-grid gateway connect?

**Answer: A — Closely located smart meters to Data Aggregator Units (DAUs).**

### Explanation
A gateway:
- connects a group of nearby smart meters,
- supports two-way communication,
- acts as the communication link between meters and DAUs.

### Memory
`Smart Meters → Gateway → DAU`

**Lecture:** Smart Grid Part II, Slide 11.

---

## Q8. Which attack compromises availability by making smart-grid components/information inaccessible?

**Answer: D — Denial of Service (DoS) attack.**

### Explanation
Availability means that:
- grid components,
- transmitted information,
- collected information

remain accessible when required.

A DoS attack attempts to:
- block key signals,
- make services unavailable,
- affect grid stability and observability.

### Security mapping
- Integrity → data manipulation/injection
- Availability → **DoS**
- Time synchronization → false timing/phasor visualization
- Replay → repeated previously observed data

**Memory:** `Availability attack = DoS`

**Lecture:** Smart Grid Part II, Slide 17.

---

## Q9. How is IIoT described in the lecture?

**Answer: A — An application of IoT in industries that links automation systems with enterprise, planning, and product lifecycle.**

### Explanation
IIoT modifies/extends existing industrial systems using IoT ideas.

It connects:
- industrial automation,
- enterprise systems,
- planning,
- product lifecycle.

IIoT includes:
- machine learning,
- Big Data,
- machine-to-machine interaction,
- automation.

### Memory
`IIoT = IoT + Industry + Automation + Enterprise`

**Lecture:** IIoT Part I, Slide 3.

---

## Q10. Which approach is associated with IIoT for adapting existing industrial systems?

**Answer: C — Wrap and re-use.**

### Explanation
The lecture emphasizes:
- **wrap & re-use**

rather than:
- rip & replace.

This means existing industrial assets can be integrated into IIoT systems instead of being discarded and completely replaced.

### Memory
`IIoT → Wrap & Re-use`

**Lecture:** IIoT Part I, Slide 6.

---

## Q11. Which technology is the key enabler for V2V and V2R communication in Intelligent Transportation Systems?

**Answer: D — Dedicated Short-Range Communications (DSRC).**

### Explanation
The IIoT transportation section states that connected-vehicle systems support:
- vehicle-to-sensor,
- vehicle-to-vehicle,
- vehicle-to-internet,
- vehicle-to-road infrastructure.

For V2V and V2R:
- **DSRC** is the key enabling technology.

### Trap
Do not confuse DSRC with:
- SCADA,
- HDFS,
- power-line communication.

**Memory:** `V2V + V2R → DSRC`

**Lecture:** IIoT Part II, Slide 5.

---

## Q12. In IIoT-based mining, what environmental parameters can be monitored using wireless sensor networks?

**Answer: A — Air quality, poisonous gases, and oxygen level inside mines.**

### Explanation
Mining safety systems can use:
- RFID,
- Wi-Fi,
- wireless technologies,
- sensor networks

for:
- early disaster warning,
- air-quality monitoring,
- poisonous-gas detection,
- oxygen-level monitoring.

### Memory
`Mining safety → Air + Poisonous Gas + Oxygen`

**Lecture:** IIoT Part II, Slide 7.

---

## Q13. Which Big Data characteristic refers to biases, noise and abnormality?

**Answer: C — Veracity.**

### Explanation
**Veracity** concerns:
- bias,
- noise,
- abnormality,
- trustworthiness/understandability of data.

It matters especially for:
- automated decision making,
- machine-learning systems.

### Trap
Do not confuse:
- Volume → quantity,
- Velocity → speed,
- Variety → forms/types,
- Variability → changing meaning/context,
- Veracity → data quality/truth characteristics.

**Memory:** `Veracity = Bias + Noise + Abnormality`

**Lecture:** Data Handling and Analytics Part I, Slide 9.

---

## Q14. What is the purpose of redundancy mitigation during data pre-processing?

**Answer: D — To eliminate repeated data through detection, filtering, and compression.**

### Explanation
IoT datasets may contain:
- noise,
- redundancy,
- inconsistency.

Pre-processing includes:
1. Integration
2. Cleaning
3. Redundancy mitigation

Redundancy mitigation:
- detects repetition,
- filters repeated data,
- compresses data,
- reduces unnecessary transmission/storage.

### Memory
`Redundancy Mitigation = Detect + Filter + Compress`

**Lecture:** Data Handling and Analytics Part I, Slide 18.

---

## Q15. In HDFS, which node stores the actual data blocks?

**Answer: A — Datanode.**

### Explanation
**Namenode**
- stores filesystem metadata,
- maps blocks to Datanodes,
- manages filesystem namespace.

**Datanode**
- stores actual data blocks,
- participates in replication/rebalancing,
- reports block information to the Namenode.

Files are:
- divided into blocks,
- replicated across Datanodes.

### Memory
`Name = Metadata`  
`Data = Datanode`

**Lecture:** Data Handling and Analytics Part I, Slide 23.

---

# 3. SMART GRID — COMPLETE LECTURE COVERAGE

## 3.1 Traditional Electrical Grid

Traditional grid characteristics:
- energy generation at centralized power plants,
- one-directional energy distribution,
- power flows from plant → homes/industries,
- monitoring and restoration are largely manual,
- limited control capabilities,
- limited information about energy flow.

### Key weakness
The traditional model is mostly:

```text
Central Generation
       ↓
Transmission
       ↓
Distribution
       ↓
Consumers
```

---

# 4. WHAT IS A SMART GRID?

A Smart Grid is conceptualized as a nationwide network using information technology to deliver electricity:
- efficiently,
- reliably,
- securely.

Other names used in the lecture:
- Electricity with a brain
- Energy Internet
- Electronet

### NIST definition — exam concept
A smart grid is a modernized grid that enables:
- **bidirectional flows of energy**
- **two-way communication and control**

### Core contrast

| Traditional Grid | Smart Grid |
|---|---|
| Centralized generation | Distributed generation also integrated |
| One-directional energy | Bidirectional energy |
| Manual monitoring/restoration | Intelligent/automated monitoring/restoration |
| Limited information | Rich real-time information |
| Limited control | Two-way control |
| Weak integration of distributed resources | Better renewable/microgrid integration |

---

# 5. SMART GRID BENEFITS

The lecture lists:
- more efficient electricity transmission,
- quicker restoration after disturbances,
- lower utility operation/management costs,
- potentially lower consumer power costs,
- reduced peak demand,
- increased renewable integration,
- better integration of customer-owned generation,
- improved security.

### Customer benefits
- real-time usage information,
- charging of EVs and smart devices,
- scheduling appliances for off-peak periods,
- different pricing options.

### Stakeholder benefits
- improved grid reliability,
- fewer blackouts/brownouts,
- monitoring/analysis/decision infrastructure,
- better resiliency,
- lower delivery inefficiency,
- integration of wind and solar,
- better distributed-energy-resource management,
- microgrid and storage management.

---

# 6. SMART GRID PROPERTIES

## Consumer Participation
- real-time consumption monitoring,
- smart-appliance control,
- building automation.

## Real-Time Pricing
Energy prices can change according to grid conditions.

## Distributed Generation
- renewable integration,
- microgrid integration.

## Power-System Efficiency
- power monitoring,
- asset management,
- optimal utilization,
- distribution automation,
- protection.

## Power Quality / Self-Healing
- frequency monitoring/control,
- load forecasting,
- disturbance anticipation,
- self-healing.

### Memory
`Consumer + Pricing + Distributed Generation + Efficiency + Quality/Self-Healing`

---

# 7. SMART GRID ARCHITECTURE / DOMAINS

The lecture includes a basic Smart Grid architecture and NIST Smart Grid domains.

Important components shown in the course:
- Smart Home
- Renewable Energy
- Consumer Engagement
- Operation Center
- Distribution Intelligence
- Plug-in Electric Vehicle

### Exam focus
Questions are more likely to test the role of individual components than reproduce the entire architecture.

---

# 8. SMART HOME IN SMART GRID

A smart home uses smart-grid technologies to:
- save energy,
- find lower rates,
- support efficient grid operation.

The interaction between:
- grid operators,
- utilities,
- consumers

helps the smart grid function efficiently.

### Main smart-home elements
1. Smart meters
2. Home Energy Management Systems (HEMS)
3. Smart appliances
4. Home power generation

---

# 9. SMART METERS

A smart meter:
- provides the Smart Grid interface between consumer and energy service provider,
- operates digitally,
- supports automated/complex information transfer,
- helps reduce consumer energy costs,
- provides electricity-use information to providers.

### Assignment connection
Q2 → **Smart meter = interface**

---

# 10. HOME ENERGY MANAGEMENT SYSTEM

HEMS allows consumers to:
- track energy use,
- monitor real-time information,
- monitor price signals,
- automatically schedule power use when prices are low,
- avoid peak rates,
- support load balancing,
- help prevent blackouts.

### Core idea
```text
Usage + Price Information
          ↓
HEMS
          ↓
Schedule Appliances
          ↓
Lower Cost + Better Load Balance
```

---

# 11. SMART APPLIANCES

Smart appliances are:
- automated,
- robust,
- responsive to energy-provider signals.

They can avoid operation during peak demand.

### Consumer override
Consumers can override automated controls.

**Important trap:** Override means the user can choose operation; it does **not** guarantee minimum cost.

---

# 12. HOME POWER GENERATION

Examples:
- rooftop solar,
- small wind turbines,
- small hydropower,
- home fuel-cell systems.

Surplus energy can be:
- supplied back to the grid.

### Islanding
During an islanding condition, a home may obtain power from:
- distributed/home generation resources.

---

# 13. RENEWABLE ENERGY

Renewable energy is derived from natural processes that are continually replenished.

Examples mentioned:
- solar,
- wind,
- ocean,
- hydropower,
- biomass,
- geothermal,
- biofuels,
- renewable hydrogen.

### Smart-grid relevance
Consumers with renewable generation can:
- reduce dependence on the main grid,
- supply surplus energy,
- potentially earn revenue.

---

# 14. CONSUMER ENGAGEMENT

Three major mechanisms:
1. Time-of-Use pricing
2. Net metering
3. Financial incentives

---

# 15. TIME-OF-USE PRICING

Consumers are encouraged to:
- operate appliances during off-peak hours.

### Why?
Off-peak:
- lower grid load,
- lower energy price,
- better efficiency.

### On-peak problem
High demand can cause:
- less-efficient energy distribution,
- more pollution when additional non-renewable resources are used.

### Memory
`TOU = shift load from peak → off-peak`

---

# 16. NET METERING

Net metering requires:
- smart meters.

Consumers may receive higher compensation for excess generation supplied during high-demand periods.

Final bill considers:
- **energy inflow** from grid,
- **energy outflow** from consumer to grid.

### Memory
`Net = Inflow − Outflow` conceptually, depending on billing scheme.

---

# 17. FINANCIAL INCENTIVES

Providers may reward:
- shifting appliance operation to off-peak hours,
- using stored battery energy,
- using PHEV/EV batteries to support the grid.

This benefits:
- consumers,
- service providers,
- overall load balancing.

---

# 18. OPERATION CENTERS

## Traditional operation-center problems
- tries to match generation and use,
- limited control,
- limited information,
- difficulty detecting oscillations,
- risk of widespread blackout.

## Smart-grid operation center
- information/control for transmission,
- improved reliability,
- reduced widespread-blackout risk.

---

# 19. PMU — PHASOR MEASUREMENT UNIT

PMU:
- samples voltage and current at fixed sampling rates,
- gives a snapshot of the active power system,
- higher sampling rates reveal dynamic behavior,
- can help identify blackout possibilities.

Multiple PMUs:
→ **phasor network**

Phasor network information:
→ centralized **SCADA**.

### Must memorize
`PMU → voltage/current`  
`Many PMUs → phasor network`  
`Phasor network → SCADA`

---

# 20. SELF-HEALING GRID

Self-healing includes:
- damping unwanted power oscillations,
- avoiding unwanted current flows,
- rerouting power,
- avoiding transmission-line overload.

This is part of:
- distribution intelligence.

---

# 21. DEMAND-SIDE ENERGY DISTRIBUTION

Energy supply can be adjusted according to:
- consumer requirements,
- current energy price,
- available supply.

The lecture also mentions:
- energy distributors can form coalitions,
- coalitions can serve energy requirements in a geographic area.

---

# 22. DISTRIBUTION INTELLIGENCE

Distribution intelligence means:
> energy distribution systems equipped with smart IoT devices.

Together with smart meters, it can:
- identify outage source,
- automate switching,
- restore power flow,
- optimize real/reactive power,
- protect/control feeder lines.

### Reactive power
The lecture describes devices that store/release energy and can cause increased electrical current without consuming real power.

### Memory
`Distribution Intelligence = Smart Devices + Smart Meters + Automated Distribution`

---

# 23. PLUG-IN ELECTRIC VEHICLES

Smart-grid infrastructure supports efficient PEV use.

Benefits:
- reduced oil dependence,
- no direct pollution while running on electricity.

PEVs:
- charge from the grid,
- are encouraged to charge during off-peak hours,
- can potentially discharge energy to the grid during peak hours,
- may receive incentives for supplying energy.

### Key concept
`PEV = Consumer load + Potential distributed energy source`

---

# 24. SMART GRID COMMUNICATION

Important components:
- Smart home appliances
- Smart meters
- Gateways
- Data Aggregator Units (DAUs)
- Meter Data Management Systems (MDMSs)

Networks:
- HAN
- NAN
- WAN
- IP networks
- SANETs

---

# 25. SMART-HOME COMMUNICATION PROTOCOLS / NUMBERS

## C-Bus
- Data rate: **3500 bits/sec**
- Cable length: up to **1000 m**

## DECT
- Data rate: **64,000 bits/sec**

## EnOcean
- Frequency: **1880–1930 MHz**
- Data rate: **9600 bits/sec**
- Also operates at **902 MHz in North America**

## Universal Powerline Bus
- Data rate: **480 bits/sec**
- Supports two-way communication.

## Thread
- Data rate: **20–250 Kbits/sec**
- IPv6 addressing,
- based on 6LoWPAN networking.

## Zigbee
- Data rate: **20–250 Kbits/sec**
- 2.4 GHz band,
- IEEE 802.15.4,
- approximately **100 m** range.

## Simplified Cable Solution (SCS)
- Data rate: **9.6 Kbits/sec**
- twisted pair,
- based on OpenWebNet.

### Exam numbers to memorize
`C-Bus = 3500 bps / 1000 m`  
`DECT = 64000 bps`  
`EnOcean = 1880–1930 MHz / 9600 bps / 902 MHz NA`  
`UPB = 480 bps`  
`Thread = 20–250 kbps`  
`Zigbee = 20–250 kbps / 2.4 GHz / ~100 m`  
`SCS = 9.6 kbps`

---

# 26. SMART METERS, GATEWAYS, DAUs, MDMS

## Gateway
- connects a few closely located smart meters,
- often communicates through Wi-Fi/IEEE 802.11,
- enables two-way communication,
- links meters to DAUs.

## Smart meter ↔ gateway
Smart meters can:
- forward energy-consumption information toward gateways,
- receive billing/control information through gateways.

## DAU
Data Aggregator Unit:
- aggregates energy consumption/requests for a geographic area,
- forwards information to MDMS,
- maintains a buffer/queue.

## MDMS
Meter Data Management System:
- centralized coordinator,
- handled by energy service providers,
- part of operation center,
- decides price per unit energy.

### Architecture
```text
Home Appliances
      ↓
Smart Meter
      ↓
Gateway
      ↓
DAU
      ↓
MDMS / Operation Center
```

---

# 27. SMART GRID SECURITY

Smart Grid is a:
- **cyber-physical system**.

Major security properties/threat areas:
- Integrity
- Availability
- Dynamic system attacks
- Physical threats
- Coordinated attacks

---

# 28. INTEGRITY ATTACKS

## Data Injection Attacks (DIA)
Attackers manipulate:
- sensor readings,
- feedback-control signals,
- electricity-price signals.

Possible methods:
- compromising hardware,
- intercepting communication links.

### Consequences
Manipulated measurements can:
- hide a congested line,
- create false grid states,
- induce fluctuations,
- trip lines,
- disconnect generators,
- cause load shedding,
- contribute to blackout.

---

# 29. FINANCIAL / PRICE ATTACKS

Attackers may manipulate electricity prices to:
- buy energy cheaply,
- create financial profit.

### Trap
Price manipulation is an **integrity** issue because the information being used for decisions has been altered.

---

# 30. TIME SYNCHRONIZATION ATTACKS

A Time Synchronization Attack (TSA):
- manipulates the time reference used for timestamped phasor measurements.

This can:
- create false visualization of system conditions,
- cause inaccurate control/protection actions.

### Memory
`PMU timestamps + manipulated time → TSA`

---

# 31. AVAILABILITY / DoS

Availability means:
- components and information are accessible when required.

DoS attacks:
- make components/information inaccessible,
- block key signals,
- threaten grid stability and observability,
- can manipulate generation-load balance.

### Assignment
Q8 → **DoS**

---

# 32. DYNAMIC SYSTEM ATTACKS

## Replay Attack
Attacker:
1. compromises sensors,
2. observes outputs,
3. learns legitimate data,
4. replays old data while injecting attack signals.

## Dynamic Data Injection Attack (D-DIA)
Uses knowledge of:
- the grid's dynamic model

to inject data that can:
- create unobservability of unstable poles,
- lead to system collapse.

## Covert Attack
- closed-loop version of replay attacks.

---

# 33. PHYSICAL THREATS

Attack physical components such as:
- generators,
- substations,
- transmission lines.

Also:
- physical manipulation of smart meters for energy theft.

---

# 34. COORDINATED ATTACKS

Power systems have robustness measures, but interconnected components can be exploited.

A coordinated attacker can:
- target multiple components,
- use different attack types simultaneously,
- exploit interconnections,
- trigger cascading failures.

### Memory
`One failure → local`  
`Many coordinated failures → cascading system impact`

---

# 35. SMART GRID + CLOUD APPLICATIONS

Cloud applications can support:
1. Energy management
2. Information management
3. Security

---

# 36. CLOUD FOR ENERGY MANAGEMENT

Cloud can improve:
- demand response,
- large-scale scheduling,
- microgrid management,
- real-time supply-demand balancing.

Two cloud-based demand-response communication models:
- **Data-centric communication**
- **Topic-based group communication**

Cloud scheduling considers:
- available resources,
- job/request priority,
- applicable constraints.

---

# 37. CLOUD FOR MICROGRID MANAGEMENT

Cloud modules can support:
- infrastructure,
- power management,
- services.

Cloud can:
- support more customers,
- integrate/analyze many smart-meter streams,
- balance real-time demand and supply,
- share real-time energy usage and pricing,
- use mobile agents for monitoring heterogeneous smart-grid systems.

---

# 38. CLOUD FOR INFORMATION MANAGEMENT

Cloud supports:
- large-scale computing/storage,
- information sharing,
- real-time distributed data management,
- parallel information processing,
- dynamic data centers for real-time smart-meter information,
- dynamic pricing,
- multi-mobile-agent cooperation.

---

# 39. CLOUD FOR SECURITY

The lecture describes:
- private-cloud platforms for processing millions of user records,
- cloud-based protection against malicious software,
- distributed verification,
- real-time analysis/estimation,
- cloud-based privacy schemes.

### Exam connection
Cloud is not only for storage; it can also support:
- energy management,
- information processing,
- security/privacy.

---

# 40. IIoT — INDUSTRIAL INTERNET OF THINGS

## Definition
IIoT is an application of IoT in industry to modify existing industrial systems.

It links:
- automation,
- enterprise,
- planning,
- product lifecycle.

### Important
**IIoT is not simply “IoT in a factory.”**

The lecture presents IIoT as an intersection involving:
- industries,
- Industry 4.0,
- Internet of Things,
- enterprise/consumer contexts.

---

# 41. IIoT COMPONENTS / TECHNOLOGIES

IIoT includes:
- Machine Learning,
- Big Data,
- M2M interaction,
- Automation.

It is supported by:
- large amounts of sensor data.

### Core philosophy
**Wrap & Re-use**
rather than
**Rip & Replace**.

---

# 42. INDUSTRIAL REVOLUTIONS

The lecture associates:

1. **1st Industrial Revolution** → mechanized production
2. **2nd Industrial Revolution** → mass production
3. **3rd Industrial Revolution** → Internet evolution and automation
4. **4th Industrial Revolution** → IIoT / Industry 4.0

### Memory
`1 = Mechanization`  
`2 = Mass Production`  
`3 = Internet + Automation`  
`4 = IIoT`

---

# 43. IIoT NETWORK

IIoT is a network of:
- physical objects,
- systems,
- platforms,
- applications,
- people.

These can communicate:
- with one another,
- with the external environment.

Sensor, processor and connectivity advances make:
- real-time information capture,
- real-time access

more affordable and accessible.

---

# 44. IIoT REQUIREMENTS

Major requirements:
- Hardware and software connectivity
- Cloud platform
- Big Data analytics
- Application development

The lecture also highlights:
- access anywhere/anytime/anything,
- cloud efficiency/agility,
- end-to-end security,
- user experience,
- asset management,
- transition to smart machines.

---

# 45. PHYSICAL PLANT ↔ VIRTUAL PLANT

The lecture visualizes:
- **Physical Plant**
- **Virtual Plant**

Connected by:
- sensor readings,
- machine instructions.

### Concept
```text
Physical Plant
    ↕
Sensor Readings / Machine Instructions
    ↕
Virtual Plant
```

This is an important IIoT/cyber-physical concept.

---

# 46. IIoT DESIGN CONSIDERATIONS

For industrial IoT devices:

## Energy
Time for which device operates under limited power.

## Latency
Time required to transmit data.

## Throughput
Maximum data transmitted across the network.

## Scalability
Number of devices supported.

## Topology
Communication among devices / interoperability.

## Safety & Security
Degree of safety and security of the application.

### Memory
`E-L-T-S-T-S`
Energy, Latency, Throughput, Scalability, Topology, Safety/Security.

---

# 47. IoT VS IIoT

| IoT | IIoT |
|---|---|
| Consumer-oriented | Industrial-oriented |
| Convenience of individuals | Efficiency, safety, security |
| M2M more limited | M2M extensive |
| Consumer-level applications | Industrial applications |
| Comfort/consumer value | Operational/business value |

### Trap
Do not say IIoT is merely “consumer IoT with more sensors.”

---

# 48. SERVICE MANAGEMENT IN IIoT

Service management:
- implements/manages service quality according to end-user demand.

A service:
- is a collection of data and associated behaviors,
- performs a function/feature of a device or part of a device.

## Two service types

### Primary service
Basic services responsible for:
- primary node functions.

### Secondary service
Auxiliary services that support:
- primary services,
- or other secondary services.

### Memory
`Primary = core function`  
`Secondary = support function`

---

# 49. IIoT APPLICATION AREAS

The lecture identifies:
1. Manufacturing
2. Healthcare
3. Transportation & logistics
4. Mining
5. Firefighting

---

# 50. IIoT IN MANUFACTURING

Integrates:
- devices,
- equipment,
- workforce,
- supply chain,
- work platform.

Goals:
- smart production,
- lower operating costs,
- improved worker productivity,
- fewer workplace injuries,
- resource optimization,
- waste reduction,
- end-to-end automation.

---

# 51. IIoT IN HEALTHCARE

Implanted/on-body sensors enable:
- continuous patient monitoring,
- improved treatment outcomes,
- lower costs,
- improved disease detection,
- more accurate data collection,
- better drug management.

### Memory
`Healthcare IIoT → Continuous Monitoring`

---

# 52. IIoT IN TRANSPORTATION & LOGISTICS

Intelligent Transportation Systems (ITS) use connected vehicles.

Connectivity:
- Vehicle-to-Sensor
- Vehicle-to-Vehicle
- Vehicle-to-Internet
- Vehicle-to-Road infrastructure

### DSRC
Key enabling technology for:
- V2V,
- V2R.

---

# 53. IIoT IN SUPPLY CHAINS

Physical objects can carry:
- barcodes,
- RFID tags.

This enables real-time monitoring of:
- status,
- location,
- movement

across the supply chain.

### Security requirement
Supply-chain data must maintain:
- security,
- privacy.

---

# 54. IIoT IN MINING

Uses:
- RFID,
- Wi-Fi,
- wireless technologies,
- sensor networks.

Monitors:
- air quality,
- poisonous gases,
- oxygen levels.

Supports:
- early disaster warning,
- accident prevention.

### Assignment
Q12 directly tests this.

---

# 55. IIoT IN FIREFIGHTING

Uses:
- sensor networks,
- RFID tags.

Supports:
- automatic diagnosis,
- early warning,
- emergency rescue,
- real-time monitoring.

Result:
- improved public security.

---

# 56. IIoT EXAMPLES

Examples in lecture:
- UAVs inspecting oil pipelines,
- sensor-based food-safety monitoring,
- minimizing worker exposure to noise/chemicals/hazardous gases,
- unmanned marine vehicles collecting data for long periods without fuel/crew.

---

# 57. CONNECTED ECOSYSTEMS

Traditional industrial supply chains are:
- relatively linear.

IIoT encourages:
- shifting business focus from products → outcomes,
- digital ecosystems,
- faster adaptation to external changes.

### Memory
`Traditional = linear product chain`  
`IIoT = connected digital ecosystem + outcome focus`

---

# 58. DIGITAL + HUMAN WORKFORCE

IIoT makes machines:
- more intelligent,
- more capable of automated tasks.

Humans and machines can work together to:
- increase productivity,
- improve quality,
- reduce costs.

Workers' skills evolve toward:
- digital skills,
- analytical skills.

---

# 59. NEW JOBS

IIoT can create new composite industries such as:
- precision agriculture,
- digital healthcare,
- digital mines.

Automation can:
- reduce demand for some unskilled work,
- increase demand for skilled digital/analytical experts.

---

# 60. REFORMATION OF ROBOTS

IIoT robots are described with three major capabilities:

1. **Sensing**
2. **Thinking**
3. **Acting**

They can:
- perform repetitive tasks,
- work under human supervision,
- be reprogrammed,
- learn new tasks faster.

### Memory
`Robot = Sense + Think + Act`

---

# 61. IIoT CHALLENGES

Primary challenges:
- identification of objects/things,
- managing huge amounts of data,
- integrating existing infrastructure into IIoT,
- enabling data storage.

---

# 62. IIoT SAFETY CHALLENGES

Important areas:
- worker health and safety,
- regulatory compliance,
- environmental protection,
- optimized operations.

---

# 63. IIoT HAZARDS

The lecture lists:
- handling/storing/using hazardous substances,
- oxygen deficiency,
- particulates,
- radiation,
- physiological stress.

### Exam trap
These are **safety hazards**, not Big Data characteristics.

---

# 64. IIoT STANDARDIZATION

Standardization aims to:
- improve interoperability,
- allow different systems/applications to work together,
- improve product/service performance.

Problems:
- interoperability,
- semantic interoperability/data semantics,
- security and privacy,
- radio-access-level issues.

### Memory
`Standardization → Interoperability`

---

# 65. IIoT PRIVACY & SECURITY

Two major concerns:
1. Information security
2. Data privacy protection

Because devices/things can be:
- tracked,
- monitored,
- connected,

there is risk to:
- personal information,
- private data.

### Examples
Healthcare:
- patient medical data must not be tampered with.

Food industry:
- deterioration information may need confidentiality to protect company reputation.

---

# 66. MANUFACTURING RISKS

Factors that can hinder IIoT adoption:
- lack of vision/leadership,
- lack of management understanding of value,
- costly sensors,
- inadequate infrastructure.

---

# 67. MEETING IIoT CHALLENGES — SENSOR IMPROVEMENT

Sensor improvements include:
- miniaturization,
- performance,
- lower cost,
- lower energy consumption.

### Core idea
Better sensors make IIoT:
- more accessible,
- more scalable,
- more energy efficient.

---

# 68. IIoT + PREDICTIVE MAINTENANCE

Software capabilities can improve operational efficiency through:
- predictive maintenance,
- reduced scheduled-repair cost,
- lower maintenance cost,
- fewer breakdowns.

### Memory
`Sensor data → prediction → maintenance before failure`

---

# 69. IIoT PRODUCT EXAMPLES

## Intelligent Radio Modem (IRM)
Examples:
- IRM 1500
- ACE 1000

Capabilities:
- M2M connectivity,
- data transmission,
- easy installation/maintenance,
- connects IP and non-IP serial devices.

## Comtrol IO Link Master Gateway
Supports:
- Ethernet/IP,
- PROFINET (PNIO),
- Modbus TCP.

### Exam note
These are examples of industrial connectivity products, not core definitions.

---

# 70. IIoT BENEFITS

Benefits include:
- improved connectivity,
- improved efficiency,
- upgraded scalability,
- reduced operation time,
- remote diagnosis,
- cost effectiveness.

---

# 71. IIoT RESEARCH TRENDS

The lecture highlights:
- better communication among things/objects,
- energy-efficient sensor techniques,
- context-aware IoT middleware,
- smarter objects with more memory,
- more processing capability,
- more reasoning capability.

---

# 72. IIoT CONCLUSION

The lecture emphasizes the need for:
- smaller,
- less expensive,
- accessible sensors,
- distributed assembly-line control,
- automated monitoring,
- automated control,
- automated maintenance.

---

# 73. DATA HANDLING

Data handling ensures data is:
- stored safely,
- archived safely,
- disposed of safely.

It includes policies/procedures for:
- electronic data,
- non-electronic data.

### Why important in IoT?
IoT generates:
- heavy traffic,
- huge sensor datasets,
- continuous streams.

This leads naturally to:
- Big Data.

---

# 74. WHAT IS BIG DATA?

Big Data technologies are designed to:
- economically extract value,
- from very large volumes,
- of varied data,
- captured at high velocity,
- for discovery/analysis.

NIST framing emphasizes situations where:
- volume,
- acquisition speed,
- or data representation

limits traditional relational analysis.

### Key idea
`Big Data ≠ only “a lot of data”`

It also involves:
- speed,
- variety,
- processing/analysis challenges.

---

# 75. TYPES OF DATA

## Structured Data
- easily organized,
- often stored in relational databases,
- managed with SQL,
- lecture states roughly **20%** of available data.

## Unstructured Data
- no predefined model,
- traditional RDBMSs struggle with it,
- lecture states roughly **80%** of available data.

### Exam memory
`Structured ≈ 20%`  
`Unstructured ≈ 80%`

---

# 76. BIG DATA — 7 Vs

## 1. Volume
Quantity of data generated.

Example:
- LSST: **30 TB of images every night**.

## 2. Velocity
Speed of data generation/processing.

Examples from lecture:
- **140 million tweets/day** (2011 survey),
- NYSE: **1 TB** trade information per trading session.

## 3. Variety
Different data forms:
- text,
- images,
- audio,
- video,
- web,
- GPS,
- sensor data,
- SMS,
- documents,
- PDFs.

## 4. Variability
Meaning/context can change continuously.

Examples:
- language processing,
- hashtags,
- geospatial data,
- multimedia,
- sensor events.

## 5. Veracity
- bias,
- noise,
- abnormality,
- understandability/trustworthiness.

**Assignment Q13 → Veracity**

## 6. Visualization
Presenting data:
- pictorially,
- graphically.

Supports:
- pattern recognition,
- decision making.

## 7. Value
Extracting useful business information from scattered data.

### Mnemonic
**V-V-V-V-V-V-V**
- Volume
- Velocity
- Variety
- Variability
- Veracity
- Visualization
- Value

---

# 77. BIG DATA 7-V COMPARISON

| V | Meaning | Trigger word |
|---|---|---|
| Volume | Quantity | How much? |
| Velocity | Speed | How fast? |
| Variety | Types/forms | How many formats? |
| Variability | Changing meaning/context | Does meaning change? |
| Veracity | Bias/noise/abnormality | Can we trust/understand it? |
| Visualization | Graphical representation | How do we see it? |
| Value | Useful information | What benefit do we get? |

### MCQ traps
- Bias/noise → **Veracity**
- Speed → **Velocity**
- Quantity → **Volume**
- Forms → **Variety**
- Changing meaning → **Variability**
- Graphical presentation → **Visualization**
- Useful business information → **Value**

---

# 78. DATA HANDLING TECHNOLOGIES

## Cloud Computing
NIST essential characteristics:
1. On-demand self-service
2. Broad network access
3. Resource pooling
4. Rapid elasticity
5. Measured service

Service models:
- IaaS
- PaaS
- SaaS

## IoT
Sensors:
- embedded in devices/machines,
- deployed in fields,
- transmit sensed data to remote servers.

Continuous acquisition can come from:
- mobile equipment,
- transportation,
- public facilities,
- home appliances.

## Data Centers
Support:
- storage,
- management,
- organization,
- processing capacity,
- network infrastructure,
- energy management,
- backup/replication,
- business analytics.

---

# 79. FLOW OF DATA

The lecture gives a four-stage flow:

```text
Generation
    ↓
Acquisition
    ↓
Storage
    ↓
Analysis
```

## Generation sources
- Enterprise data
- IoT data
- Bio-medical data
- Other fields

## Acquisition
- data collection,
- data transportation,
- data pre-processing.

## Storage
- Hadoop,
- MapReduce-related ecosystem,
- NoSQL databases.

## Analysis
- Bloom filters,
- parallel computing,
- hashing,
- indexing.

---

# 80. DATA SOURCES

## Enterprise data
- online trading/analysis,
- production/inventory,
- sales,
- financial data.

## IoT data
- industry,
- agriculture,
- traffic,
- transportation,
- healthcare,
- public departments,
- families.

## Biomedical data
- gene sequencing,
- clinics,
- medical R&D.

## Other fields
- computational biology,
- astronomy,
- nuclear research.

---

# 81. DATA ACQUISITION

## Data Collection
Sources:
- log/record files,
- sensory data,
- mobile-device data.

Sensor examples:
- sound,
- voice,
- vibration,
- automobile data,
- chemical,
- current,
- weather,
- pressure,
- temperature.

Mobile data examples:
- geographic location,
- 2D barcodes,
- pictures,
- videos.

## Data Transmission
After collection:
- data is transferred to storage for processing/analysis.

Transmission categories:
- **Inter-DCN**
- **Intra-DCN**

---

# 82. DATA PRE-PROCESSING

Collected data can suffer from:
- noise,
- redundancy,
- inconsistency.

Main relational-data preprocessing stages:
1. Integration
2. Cleaning
3. Redundancy mitigation

---

# 83. INTEGRATION

Integration:
- combines data from multiple sources,
- provides a uniform view.

### Memory
`Integration = Combine sources → Uniform view`

---

# 84. CLEANING

Cleaning:
- identifies inaccurate data,
- identifies incomplete data,
- identifies unreasonable data,
- modifies or deletes such data.

### Memory
`Cleaning = Find bad data → Fix/Delete`

---

# 85. REDUNDANCY MITIGATION

Redundancy mitigation:
- detects repeated data,
- filters repeated data,
- compresses data,
- avoids unnecessary transmission.

### Assignment
Q14 → **Eliminate repeated data through detection, filtering and compression.**

### Memory
`Redundancy = Repetition`  
`Mitigation = Detect + Filter + Compress`

---

# 86. DATA STORAGE

## Distributed File Systems
Designed for:
- massive data,
- consistency,
- availability,
- fault tolerance.

Examples:
- GFS,
- HDFS,
- Kosmosfs.

### GFS
A notable large-scale distributed file system.

Lecture notes:
- performance is limited for small files.

---

# 87. NoSQL DATABASES

NoSQL emerged to handle Big Data characteristics.

Three main categories mentioned:
1. Key-value databases
2. Column-oriented databases
3. Document-oriented databases

### Memory
`NoSQL = Key-Value + Column + Document`

---

# 88. HADOOP

Hadoop:
- software framework for distributed processing,
- processes large datasets,
- across large computer clusters,
- open-source implementation inspired by Google's GFS and MapReduce.

Apache Hadoop:
- MapReduce derived from Google MapReduce,
- HDFS derived from Google File System.

---

# 89. HADOOP BUILDING BLOCKS

## Hadoop Common
Utilities supporting Hadoop components.

## HDFS
Reliable distributed data storage/access.

## MapReduce
Parallel processing framework for large datasets.

## YARN
Allocates:
- CPU,
- memory,
- storage

to applications running on the Hadoop cluster.

### Memory
`Common = utilities`  
`HDFS = storage`  
`MapReduce = processing`  
`YARN = resource allocation`

---

# 90. HDFS

HDFS = **Hadoop Distributed File System**

### Centralized node
**Namenode**
- maintains filesystem metadata.

### Distributed nodes
**Datanodes**
- store actual data.

### File handling
- files divided into blocks,
- blocks replicated.

### Core architecture
```text
             Namenode
          (Metadata / Map)
             /    |    \
            /     |     \
       Datanode Datanode Datanode
        Blocks    Blocks   Blocks
```

---

# 91. NAMENODE

Namenode:
- stores filesystem metadata,
- maintains mappings between:
  - Datanodes and blocks,
  - blocks and Datanodes.

### Trap
Namenode does **not** store the actual file blocks in the basic architecture described here.

**Memory:** `NAME = Metadata`

---

# 92. DATANODE

Datanode:
- stores actual data,
- talks to other Datanodes,
- supports rebalancing,
- supports replication,
- periodically updates Namenode with block information,
- verifies checksums before updates.

### Memory
`DATA = Actual blocks`

---

# 93. JOB TRACKER / TASK TRACKER

The lecture presents the classic Hadoop MapReduce architecture.

## Job Tracker
- runs with Namenode,
- receives user jobs,
- decides number of mapper tasks,
- decides where each mapper runs,
- uses locality.

## Task Tracker
- runs on each Datanode,
- receives tasks from Job Tracker,
- reports progress.

### Exam warning
This is a **classic Hadoop architecture** concept. Do not confuse Job Tracker/Task Tracker with the newer YARN architecture.

---

# 94. HADOOP MASTER-SLAVE ARCHITECTURE

Hadoop is shown as a:
- master-slave,
- shared-nothing architecture.

## Master
- handles file operations such as open/close/rename,
- determines block-to-Datanode mapping.

## Slaves
- serve read/write requests,
- create/delete/replicate blocks as instructed by Namenode.

---

# 95. HIGH-PRIORITY COMPARISON TABLES

## Traditional Grid vs Smart Grid

| Traditional | Smart Grid |
|---|---|
| One-way energy | Two-way/bidirectional energy |
| Manual restoration | Automated/intelligent restoration |
| Centralized generation | Distributed generation integration |
| Limited information | Rich real-time information |
| Limited control | Two-way communication/control |
| Weak renewable integration | Better renewable integration |

---

## Smart Meter vs HEMS

| Smart Meter | HEMS |
|---|---|
| Grid interface | Home energy management |
| Measures/provides usage information | Tracks and schedules usage |
| Communicates with provider | Uses price/signals to optimize appliance operation |

---

## PMU vs DAU vs MDMS

| Component | Main role |
|---|---|
| PMU | Voltage/current sampling and phasor measurements |
| DAU | Aggregates energy data for an area |
| MDMS | Central coordinator / pricing / meter data management |

---

## Smart Grid security

| Threat | Key clue |
|---|---|
| Data Injection | Manipulate sensor/control/price data |
| Time Synchronization | Manipulate PMU time references |
| DoS | Availability becomes inaccessible |
| Replay | Re-send observed sensor outputs |
| D-DIA | Uses dynamic model knowledge |
| Physical | Attack physical components/meters |
| Coordinated | Multiple simultaneous/cascading attacks |

---

## IoT vs IIoT

| IoT | IIoT |
|---|---|
| Consumer convenience | Industrial efficiency |
| Consumer applications | Industrial applications |
| Limited M2M | Extensive M2M |
| Comfort-oriented | Safety/security/operations-oriented |

---

## Big Data Vs

| Characteristic | Key word |
|---|---|
| Volume | Quantity |
| Velocity | Speed |
| Variety | Forms |
| Variability | Changing meaning |
| Veracity | Bias/noise/abnormality |
| Visualization | Graphical view |
| Value | Useful information |

---

## HDFS

| Node | Role |
|---|---|
| Namenode | Metadata |
| Datanode | Actual blocks |

---

# 96. MCQ/MSQ TRAPS

1. Smart Grid is **not** one-directional.
2. Smart Grid supports **bidirectional energy flow**.
3. Smart meter = interface between consumer and provider.
4. TOU → off-peak consumption.
5. Net metering → inflow + outflow.
6. PMU → voltage/current sampling.
7. Multiple PMUs → phasor network.
8. Phasor network → centralized SCADA analysis.
9. Distribution intelligence → automated outage detection/restoration.
10. Gateway → nearby meters ↔ DAU.
11. DoS → availability.
12. Data injection → integrity.
13. Replay attack → repeats observed outputs.
14. Time synchronization attack → manipulates PMU time reference.
15. IIoT → industrial IoT, not consumer-only IoT.
16. IIoT → wrap & re-use.
17. IIoT includes ML, Big Data, M2M and automation.
18. Industry 4.0 → IIoT.
19. DSRC → V2V/V2R.
20. Mining → air quality + poisonous gases + oxygen.
21. Veracity → bias/noise/abnormality.
22. Redundancy mitigation → detection/filtering/compression.
23. HDFS Datanode → actual data.
24. HDFS Namenode → metadata.
25. HDFS files → blocks + replication.
26. Hadoop Common → utilities.
27. MapReduce → parallel processing.
28. YARN → resource allocation.
29. Structured data → relational/SQL.
30. Unstructured data → no predefined model.
31. Variability ≠ Variety.
32. Visualization ≠ Value.
33. Cloud supports smart-grid energy, information and security applications.
34. PEVs can be both loads and potential energy sources.
35. Consumer override of smart appliances does not guarantee minimum cost.
36. IIoT safety hazards include oxygen deficiency, particulates and radiation.
37. Standardization aims to improve interoperability.
38. Semantic interoperability is a data-meaning issue.
39. Primary service = basic node function.
40. Secondary service = auxiliary/support function.

---

# 97. IMPORTANT NUMBERS / IDENTIFIERS

| Item | Memorize |
|---|---|
| Week 11 lecture length | **132 pages** |
| Smart-grid C-Bus | **3500 bits/sec** |
| C-Bus cable length | **up to 1000 m** |
| DECT | **64000 bits/sec** |
| EnOcean | **1880–1930 MHz** |
| EnOcean data rate | **9600 bits/sec** |
| EnOcean North America | **902 MHz** |
| Universal Powerline Bus | **480 bits/sec** |
| Thread | **20–250 Kbits/sec** |
| Zigbee | **20–250 Kbits/sec** |
| Zigbee band | **2.4 GHz** |
| Zigbee range | **~100 m** |
| SCS | **9.6 Kbits/sec** |
| Structured data in lecture | **~20%** |
| Unstructured data in lecture | **~80%** |
| LSST images | **30 TB/night** |
| YouTube example | **72 hours/minute** |
| Tweets example | **140 million/day** |
| NYSE example | **1 TB/session** |
| Big Data characteristics | **7 Vs** |
| HDFS actual data | **Datanode** |
| HDFS metadata | **Namenode** |

---

# 98. VISUAL / DIAGRAM-BASED EXAM NOTES

## Smart-grid architecture
The lecture's architecture diagram emphasizes the connection between:
- consumers/smart homes,
- distribution/transmission,
- generation,
- communication/control.

### Recall
Smart Grid is a **cyber-physical energy system**, not merely a communication network.

---

## Smart-grid communication architecture

```text
Home Appliances
       ↓
   Smart Meter
       ↓
     Gateway
       ↓
      DAU
       ↓
     MDMS
       ↓
Operation Center
```

Remember:
- Gateway = local communication bridge.
- DAU = aggregation.
- MDMS = centralized coordination.

---

## PMU architecture

```text
PMU 1 ─┐
PMU 2 ─┼──→ Phasor Network ─→ SCADA
PMU 3 ─┘
```

---

## Data flow architecture

```text
Generation
     ↓
Acquisition
     ↓
Storage
     ↓
Analysis
```

---

## HDFS architecture

```text
              Namenode
             Metadata
                 |
       ---------------------
       |         |         |
   Datanode   Datanode   Datanode
    Block A    Block B    Block C
       ↘         ↓         ↙
        Replicated blocks
```

---

# 99. CODE/CONCEPT RECOGNITION DRILL

### If question says:
**“Bidirectional energy + two-way communication”**
→ Smart Grid

### “Interface between consumer and energy provider”
→ Smart Meter

### “Off-peak appliance scheduling”
→ Time-of-Use pricing

### “Grid-to-home + home-to-grid”
→ Net metering

### “Voltage/current sampling”
→ PMU

### “PMU network analyzed centrally”
→ SCADA

### “Automatic outage detection/restoration”
→ Distribution Intelligence

### “Nearby meters to DAU”
→ Gateway

### “Availability attack”
→ DoS

### “Existing industrial systems”
→ Wrap & Re-use

### “V2V/V2R”
→ DSRC

### “Mine air/gas/oxygen”
→ IIoT mining

### “Bias/noise/abnormality”
→ Veracity

### “Repeated data”
→ Redundancy mitigation

### “Actual HDFS blocks”
→ Datanode

### “HDFS metadata”
→ Namenode

### “Parallel large-dataset processing”
→ MapReduce

### “CPU/memory/storage allocation”
→ YARN

---

# 100. ONE-PAGE FINAL REVISION

## SMART GRID

```text
Traditional:
Centralized → One-way → Manual

Smart Grid:
Bidirectional → Two-way communication/control
              → Automated/intelligent
              → Renewable + distributed generation
```

### Smart-home chain
```text
Appliances
   ↓
Smart Meter
   ↓
Gateway
   ↓
DAU
   ↓
MDMS
   ↓
Operation Center
```

### Consumer mechanisms
```text
TOU → Off-peak
Net Metering → Inflow + Outflow
Incentives → Shift usage / use stored energy
```

### PMU
```text
Voltage + Current
       ↓
      PMU
       ↓
Phasor Network
       ↓
     SCADA
```

### Security
```text
Integrity → Data Injection / Price manipulation
Time → Time Synchronization Attack
Availability → DoS
Dynamic → Replay / D-DIA / Covert
Physical → Generator/Substation/Meter
Coordinated → Cascading failures
```

---

## IIoT

```text
IoT + Industry
      ↓
IIoT
      ↓
ML + Big Data + M2M + Automation
```

### Philosophy
**Wrap & Re-use**

### Design
```text
Energy
Latency
Throughput
Scalability
Topology
Safety/Security
```

### Applications
```text
Manufacturing
Healthcare
Transportation
Mining
Firefighting
```

### Mining
```text
Air quality
Poisonous gases
Oxygen
```

### Robots
```text
Sense → Think → Act
```

---

## BIG DATA

### 7 Vs
```text
Volume       → Quantity
Velocity     → Speed
Variety      → Formats
Variability  → Changing meaning
Veracity     → Bias/noise/abnormality
Visualization→ Graphical
Value        → Useful information
```

### Pre-processing
```text
Integration
Cleaning
Redundancy Mitigation
```

### Redundancy
```text
Detect → Filter → Compress
```

### Hadoop
```text
Hadoop Common → Utilities
HDFS          → Storage
MapReduce     → Processing
YARN          → Resource allocation
```

### HDFS
```text
Namenode  → Metadata
Datanode  → Actual data blocks
```

---

# 101. LAST-MINUTE 15-ANSWER DRILL

1. Smart Grid's key distinction?  
   **Bidirectional energy + two-way communication/control**

2. Smart meter role?  
   **Consumer ↔ energy provider interface**

3. TOU encourages?  
   **Off-peak usage**

4. Net metering uses?  
   **Energy inflow + energy outflow**

5. Voltage/current sampling?  
   **PMU**

6. Distribution intelligence?  
   **Outage identification + automatic restoration**

7. Gateway connects?  
   **Nearby smart meters ↔ DAU**

8. Availability attack?  
   **DoS**

9. IIoT definition?  
   **IoT applied to industry, linking automation/enterprise/planning/product lifecycle**

10. Existing industrial systems?  
    **Wrap & re-use**

11. V2V/V2R technology?  
    **DSRC**

12. Mining parameters?  
    **Air quality + poisonous gases + oxygen**

13. Bias/noise/abnormality?  
    **Veracity**

14. Repeated-data removal?  
    **Redundancy mitigation**

15. Actual HDFS blocks?  
    **Datanode**

---

# 102. FINAL EXAM MEMORY LIST

If you have only a few minutes, memorize these exact pairs:

- **Smart Grid → Bidirectional energy + two-way communication/control**
- **Smart Meter → Consumer/provider interface**
- **TOU → Off-peak**
- **Net Metering → Inflow + Outflow**
- **PMU → Voltage + Current**
- **PMU network → SCADA**
- **Distribution Intelligence → Automatic outage detection/restoration**
- **Gateway → Smart meters ↔ DAU**
- **DoS → Availability**
- **DIA → Integrity**
- **Replay → Repeated observed data**
- **TSA → PMU time reference**
- **IIoT → Industrial IoT**
- **IIoT → Wrap & Re-use**
- **Industry 4.0 → IIoT**
- **DSRC → V2V/V2R**
- **Mining → Air + Gas + Oxygen**
- **Veracity → Bias + Noise + Abnormality**
- **Redundancy mitigation → Detect + Filter + Compress**
- **Namenode → Metadata**
- **Datanode → Actual data**
- **MapReduce → Parallel processing**
- **YARN → Resource allocation**
- **HDFS → Blocks + Replication**
- **7 Vs → Volume, Velocity, Variety, Variability, Veracity, Visualization, Value**

---

# 103. SOURCE / LECTURE MAP

The Week 11 lecture PDF has **132 pages** and contains:

- **Pages 1–23:** Smart Grid – Part I
- **Pages 24–53:** Smart Grid – Part II
- **Pages 54–72:** IIoT – Part I
- **Pages 73–104:** IIoT – Part II
- **Pages 105–132:** Data Handling and Analytics – Part I

### Assignment-linked high-priority lecture slides
- Smart Grid Part I:
  - Slide 3 → Smart Grid definition
  - Slide 14 → Smart meter
  - Slide 20 → TOU
  - Slide 21 → Net metering
- Smart Grid Part II:
  - Slide 3 → PMU
  - Slide 5 → Distribution intelligence
  - Slide 11 → Gateway
  - Slide 17 → DoS
- IIoT Part I:
  - Slide 3 → IIoT definition
  - Slide 6 → Wrap & re-use
- IIoT Part II:
  - Slide 5 → DSRC
  - Slide 7 → Mining
- Data Handling and Analytics Part I:
  - Slide 9 → Veracity
  - Slide 18 → Redundancy mitigation
  - Slide 23 → HDFS Datanode

These assignment-linked slides should be revised first immediately before the exam.

---

# 104. FINAL MEMORY SENTENCE

**Week 11 = Smart Grid + IIoT + Big Data:** Smart Grid is **bidirectional energy + two-way communication/control**; smart meter is the **consumer/provider interface**; TOU shifts usage to **off-peak**; net metering considers **inflow and outflow**; **PMU** samples voltage/current and feeds a phasor network analyzed by **SCADA**; distribution intelligence enables automatic outage restoration; gateway connects meters to **DAUs**; **DoS = availability attack**; IIoT connects industrial automation with enterprise/planning/product lifecycle and uses **wrap & re-use**; **DSRC = V2V/V2R**; mining monitors **air quality, poisonous gases and oxygen**; **Veracity = bias/noise/abnormality**; redundancy mitigation removes repeated data through **detection, filtering and compression**; in HDFS **Namenode = metadata** and **Datanode = actual data**.
