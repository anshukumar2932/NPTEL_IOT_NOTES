# NPTEL Introduction to Internet of Things — Week 11
## Assignment-First + Complete Lecture Coverage + Exam-Trap Revision

> **Priority rule:** Assignment questions come first. After that, cover the complete Week-11 lecture material. The notes below are grounded in the uploaded `Assignment_11.pdf` and `Week-11.pdf`, with cumulative mock-exam cross-checks where directly relevant.
>
> **No images generated or added.**

---

# PART A — ASSIGNMENT 11: HIGHEST PRIORITY

## Answer Lock

| Q | Answer | Must remember |
|---|---|---|
| 1 | **C** | Smart grid → bidirectional energy + two-way communication/control |
| 2 | **B** | Smart meter → interface between consumer and energy service provider |
| 3 | **A** | Time-of-Use → consume during off-peak hours |
| 4 | **D** | Net metering → energy inflow + energy outflow |
| 5 | **A** | PMU → samples voltage/current |
| 6 | **B** | Distribution intelligence → outage detection + automatic power-flow restoration |
| 7 | **A** | Gateway → nearby smart meters ↔ DAU |
| 8 | **D** | Availability attack → DoS |
| 9 | **A** | IIoT → IoT application in industries linking automation, enterprise, planning, product lifecycle |
| 10 | **C** | IIoT existing-system strategy → Wrap and re-use |
| 11 | **D** | V2V/V2R enabling technology → DSRC |
| 12 | **A** | Mining WSN → air quality + poisonous gases + oxygen level |
| 13 | **C** | Bias/noise/abnormality → Veracity |
| 14 | **D** | Redundancy mitigation → detection + filtering + compression |
| 15 | **A** | HDFS actual data blocks → Datanode |

The assignment contains 15 MCQ/MSQ questions and gives these answer mappings explicitly. fileciteturn113file0L18-L59 fileciteturn113file0L66-L165 fileciteturn113file0L172-L234 fileciteturn113file0L238-L276 fileciteturn113file0L282-L342

---

# Q1. Smart Grid vs Traditional Grid

**Answer: C — It enables bidirectional flows of energy with two-way communication and control.**

### Traditional electrical grid
- Centralized power plants.
- Energy distribution is one-directional.
- Monitoring and restoration are manual.
- Limited communication/control.

### Smart grid
- Modernized electrical grid.
- Bidirectional energy flow.
- Two-way communication.
- Two-way control.
- Cyber-physical system.
- Designed for efficient, reliable and secure electricity delivery.

The lecture/NIST description explicitly emphasizes bidirectional energy flow and two-way communication/control. fileciteturn113file1L377-L417

### Exam trap
**Traditional = one-way energy + manual monitoring.**  
**Smart = two-way communication/control + bidirectional energy.**

---

# Q2. Smart Meter

**Answer: B — It provides the Smart Grid interface between the consumer and the energy service provider.**

A smart meter:
- Operates digitally.
- Provides the interface between consumer and energy service provider.
- Supports automated information exchange.
- Helps consumers understand electricity usage.
- Sends usage information toward the service provider.

Source: fileciteturn113file1L621-L640

### Trap
A smart meter is **not**:
- a renewable-energy generator,
- a replacement for the home energy management system,
- merely a one-way meter.

---

# Q3. Time-of-Use Pricing

**Answer: A — During off-peak hours.**

Time-of-Use pricing:
- Energy demand/load changes during the day.
- Consumers are encouraged to shift consumption to off-peak periods.
- Off-peak periods have lower grid load and lower energy price.
- Smart appliances can be scheduled automatically by a home energy management system.

Source: fileciteturn113file1L731-L778

### Memory
**TOU → shift load → off-peak → lower cost.**

---

# Q4. Net Metering

**Answer: D — Energy inflow from the grid and energy outflow from the consumer to the grid.**

Final bill depends on:
1. **In-flow**: grid → consumer
2. **Out-flow**: consumer → grid

A consumer with home generation can supply surplus electricity back to the grid.

Source: fileciteturn113file1L780-L803

### Trap
Do not reduce net metering to:
- battery energy only,
- centralized generation only,
- reactive power only.

---

# Q5. PMU

**Answer: A — Phasor Measurement Unit (PMU).**

PMU:
- Samples voltage and current.
- Operates at its installed location.
- Produces a snapshot of the active power system.
- Higher sampling rate gives a more dynamic view.
- Multiple PMUs form a phasor network.
- Centralized SCADA can analyze the collected information.

Source: fileciteturn113file1L877-L898

### Memory
**PMU → voltage + current + phasor network.**

---

# Q6. Distribution Intelligence

**Answer: B — Identifying the source of a power outage and supporting automatic power-flow restoration.**

Distribution intelligence:
- Uses smart IoT devices and smart meters.
- Identifies outage source.
- Supports automated switching.
- Optimizes real and reactive power.
- Protects/controls feeder lines.

Source: fileciteturn113file1L923-L945

### Trap
Distribution intelligence is about **automation and restoration**, not removing smart meters or forcing one-way communication.

---

# Q7. Smart Grid Gateway

**Answer: A — Closely located smart meters to Data Aggregator Units (DAUs).**

The gateway:
- Connects a group of nearby smart meters.
- Provides the communication link between smart meters and DAU.
- Supports two-way communication.
- Can communicate using Wi-Fi/IEEE 802.11 according to the lecture.

Source: fileciteturn113file1L1062-L1085

### Architecture memory

**Home appliances → Smart meter → Gateway → DAU → MDMS / operation center**

---

# Q8. Availability Attack

**Answer: D — Denial of Service (DoS) attack.**

Availability means:
- Grid components and transmitted/collected information remain accessible when needed.

A DoS attack:
- Makes components/information unavailable.
- Can block key signals.
- Can affect grid stability and observability.

Source: fileciteturn113file0L172-L189 and fileciteturn113file1L1195-L1212

### Security mapping

| Security property | Lecture attack/example |
|---|---|
| **Integrity** | Data Injection Attack, Time Synchronization Attack |
| **Availability** | **DoS** |
| **Dynamic system** | Replay / Dynamic Data Injection |
| **Physical** | Physical attacks |
| **Coordinated** | Cascading/system-wide attacks |

---

# Q9. Industrial Internet of Things (IIoT)

**Answer: A — An application of IoT in industries that links automation systems with enterprise, planning, and product lifecycle.**

IIoT:
- Applies IoT to industries.
- Modifies existing industrial systems.
- Links automation with:
  - Enterprise
  - Planning
  - Product lifecycle
- Includes machine learning, big data, M2M interaction and automation.

Source: fileciteturn113file0L192-L210 and fileciteturn115file0L218-L234

### Important
**IIoT ≠ all of IoT.**  
IIoT is the industrial application/context of IoT.

---

# Q10. Wrap and Re-use

**Answer: C — Wrap and re-use.**

The lecture explicitly contrasts:

- **Wrap & re-use** → integrate new IoT technologies with existing industrial assets.
- **Rip & replace** → discard/replace existing systems.

IIoT favors the first approach because existing industrial systems are valuable and should be integrated rather than completely discarded.

Source: fileciteturn115file0L282-L302

### Mock-exam cross-check
A cumulative mock asks the same concept and identifies integration of new technologies such as sensors with existing systems, minimizing disruption/cost, as the purpose of **wrap and reuse**. fileciteturn116file7L757-L763

---

# Q11. DSRC

**Answer: D — Dedicated Short-Range Communications (DSRC).**

DSRC is identified as the key enabling technology for:
- Vehicle-to-vehicle communication.
- Vehicle-to-road/infrastructure communication.
- Connected transportation / Intelligent Transportation Systems.

Source: fileciteturn113file0L238-L255

### Memory
**V2V + V2R → DSRC**

---

# Q12. IIoT Mining

**Answer: A — Air quality, poisonous gases, and oxygen level inside mines.**

Mining applications use:
- RFID
- Wi-Fi
- Other wireless technologies
- Wireless sensor networks

For:
- Early warning of disasters.
- Air-quality monitoring.
- Poisonous-gas detection.
- Oxygen-level monitoring.

Source: fileciteturn113file0L259-L276

---

# Q13. Veracity

**Answer: C — Veracity.**

Among the 7 Vs of Big Data, **Veracity** refers to:
- Bias
- Noise
- Abnormality
- Trustworthiness/understandability concerns in data

It is particularly important for:
- Automated decision making.
- Machine-learning systems.

Source: fileciteturn114file0L990-L1010

### Trap
- **Volume** = amount.
- **Velocity** = speed.
- **Variety** = types/formats.
- **Variability** = changing meaning/context.
- **Veracity** = bias/noise/abnormality.
- **Visualization** = graphical presentation.
- **Value** = useful business information.

---

# Q14. Redundancy Mitigation

**Answer: D — To eliminate repeated data through detection, filtering, and compression.**

Data preprocessing deals with:
- Noise
- Redundancy
- Inconsistency

Main relational-data preprocessing steps:
1. Integration
2. Cleaning
3. Redundancy mitigation

Redundancy mitigation:
- Detect repeated data.
- Filter it.
- Compress data.
- Avoid unnecessary transmission.

Source: fileciteturn114file1L1216-L1240

---

# Q15. HDFS

**Answer: A — Datanode.**

### Namenode
- Centralized/master role.
- Stores filesystem metadata.
- Maintains mappings between blocks and datanodes.

### Datanode
- Distributed/slave role.
- Stores actual data.
- Handles block creation/deletion/replication as instructed.
- Communicates block information to Namenode.

### HDFS
- Files divided into blocks.
- Blocks replicated across Datanodes.

Source: fileciteturn114file1L1327-L1367

### Exam lock
**Namenode = metadata.**  
**Datanode = actual data.**

---

# PART B — COMPLETE WEEK-11 LECTURE NOTES

# 1. Smart Grid

## 1.1 Traditional Electrical Grid

The lecture describes the traditional grid as:

- Energy generation at centralized power plants.
- One-directional energy distribution:
  **Power plant → homes/industries**
- Monitoring and restoration performed manually.
- Limited control and information about energy flow.

Source: fileciteturn113file1L377-L400

---

# 2. What is a Smart Grid?

A smart grid is conceptualized as a planned network using information technology to deliver electricity:

- Efficiently
- Reliably
- Securely

Other names in the lecture:
- **Electricity with a brain**
- **Energy internet**
- **Electronet**

NIST definition in the lecture:
- Modernized grid.
- Bidirectional energy flows.
- Two-way communication and control.
- Enables new functionalities and applications.

Source: fileciteturn113file1L402-L419

---

# 3. Benefits of Smart Grid

## General benefits

- More efficient electricity transmission.
- Faster restoration after disturbances.
- Lower utility operation/management cost.
- Lower power cost for consumers.
- Reduced peak demand.
- Better integration of renewable energy.
- Better integration of customer-owned generation.
- Improved security.

Source: fileciteturn113file1L425-L445

---

# 4. Consumer Benefits

Consumers get:

- Real-time information about energy usage.
- Support for electric cars.
- Smart-appliance charging.
- Scheduling during off-peak periods.
- Different pricing options.

Source: fileciteturn113file1L450-L466

---

# 5. Stakeholder Benefits

Stakeholders benefit through:

- Increased grid reliability.
- Fewer blackouts/brownouts.
- Infrastructure for monitoring, analysis and decision-making.
- Better resiliency.
- Reduced delivery inefficiencies.
- Integration of wind/solar.
- Better distributed-energy-resource management.
- Micro-grid and storage management.

Source: fileciteturn113file1L468-L488

---

# 6. Properties of Smart Grid

The lecture highlights:

## Consumer participation
- Real-time consumption monitoring.
- Smart-appliance control.
- Building automation.

## Real-time pricing

## Distributed generation
- Renewable resources.
- Micro-grid integration.

## Power-system efficiency
- Power monitoring.
- Asset management.
- Optimal utilization.
- Distribution automation/protection.

## Power quality
- Self-healing.
- Frequency monitoring/control.
- Load forecasting.
- Disturbance anticipation.

Source: fileciteturn113file1L490-L530

---

# 7. Smart Grid Components

The lecture lists:

- Smart Home
- Renewable Energy
- Consumer Engagement
- Operation Center
- Distribution Intelligence
- Plug-in Electric Vehicle

Source: fileciteturn113file1L559-L575

---

# 8. Smart Home in Smart Grid

Smart homes use smart-grid technologies to:

- Save energy.
- Seek lower energy rates.
- Help the grid operate smoothly.

Interactive relationships exist between:
- Grid operators
- Utilities
- Consumers

Computerized controls can:
- Reduce consumption during high-demand periods.
- Shift consumption to lower-cost periods.

Source: fileciteturn113file1L577-L600

---

# 9. Smart Home Components

The lecture identifies:

1. Smart meters
2. Home energy management systems
3. Smart appliances
4. Home power generation

Source: fileciteturn113file1L602-L619

---

# 10. Smart Meter

Smart meters:
- Interface consumer ↔ energy service provider.
- Operate digitally.
- Enable automated information transfer.
- Reduce consumer energy cost.
- Provide usage information to providers.

### Exam trigger
**Smart meter = Smart Grid interface.**

---

# 11. Home Energy Management System

HEMS allows consumers to:

- Track energy usage.
- Monitor real-time information.
- Monitor price signals.
- Automatically schedule power use when prices are low.
- Avoid peak-demand rates.
- Help prevent blackouts.
- Balance energy load.

The provider may offer financial incentives.

Source: fileciteturn113file1L642-L662

---

# 12. Smart Appliances

Smart appliances:
- Are automated/robust.
- Respond to provider signals.
- Avoid peak-demand periods.
- Include consumer override controls.

If the consumer overrides automated operation, the appliance can operate according to consumer need, but minimum cost is not guaranteed.

Source: fileciteturn113file1L664-L680

---

# 13. Home Power Generation

Examples:
- Rooftop solar.
- Small wind turbines.
- Small hydropower.
- Home fuel cells.

Surplus energy can be fed back to the grid.

During islanding, a home may obtain power from its distributed resources.

Source: fileciteturn113file1L682-L705

---

# 14. Renewable Energy

The lecture describes renewable energy as energy derived from natural processes that are constantly replenished.

Examples:
- Solar
- Wind
- Ocean
- Hydropower
- Biomass
- Geothermal
- Biofuels
- Hydrogen derived from renewable resources

Benefits:
- Reduced environmental pollution.
- Reduced dependence on main/micro-grid.
- Surplus energy can be supplied to grid.
- Consumers can potentially profit from surplus generation.

Source: fileciteturn113file1L707-L729

---

# 15. Consumer Engagement

Three important mechanisms:

1. **Time-of-Use pricing**
2. **Net metering**
3. **Financial incentives**

Source: fileciteturn113file1L731-L754

---

# 16. Time-of-Use Pricing

- Grid load is dynamic.
- On-peak periods can have high demand.
- High demand can cause less-efficient distribution.
- Non-renewable sources may be used to satisfy peak demand.
- Consumers are encouraged to move consumption to off-peak hours.

### Exam lock
**TOU → off-peak consumption.**

---

# 17. Net Metering

Net metering is feasible with smart meters.

- Consumer can supply excess generated energy to grid.
- Price can be higher when supplying during on-peak periods.
- Price is lower during off-peak periods.
- Final bill depends on:
  - Grid → consumer energy inflow
  - Consumer → grid energy outflow

Source: fileciteturn113file1L780-L803

---

# 18. Financial Incentives

Energy service providers may incentivize:

- Shifting appliance operation to off-peak hours.
- Using stored battery energy.
- Using stored energy in PHEVs.
- Participation in smart-grid programs.

Benefits:
- Consumer savings.
- Efficient distribution.
- Better load balancing.

Source: fileciteturn113file1L805-L828

---

# 19. Operation Centers

## Traditional operation-center drawbacks

- Limited control.
- Limited energy-flow information.
- Difficulty detecting oscillations.
- Voltage problems can destabilize the grid.
- Potential for widespread blackout.

## Smart-grid operation center

- Provides information and control.
- Improves reliability.
- Reduces widespread-blackout possibility.

Source: fileciteturn113file1L852-L875

---

# 20. PMU and Phasor Network

PMU:
- Samples voltage/current at fixed sample rate.
- Provides system snapshot.
- Higher sampling rate gives dynamic scenario.
- Helps identify possible blackout in advance.

Multiple PMUs:
→ **Phasor network**

Phasor network information:
→ analyzed by centralized **SCADA**.

Source: fileciteturn113file1L877-L898

---

# 21. Self-Healing Grid

Self-healing functions include:
- Damping unwanted power oscillations.
- Avoiding unwanted current flows.
- Rerouting power flows.
- Avoiding overloaded transmission lines.

This is part of **distribution intelligence**.

Source: fileciteturn113file1L900-L921

---

# 22. Demand-Side Energy Distribution

Energy supply is based on consumer requirements.

Consumers pay according to:
- Energy consumed.
- Price decided by service provider at that time.

Energy distributors can form coalitions to serve requirements in geographic areas.

Source: fileciteturn113file1L911-L921

---

# 23. Distribution Intelligence

Definition:
> Energy distribution systems equipped with smart IoT devices.

Functions:
- Identify outage source.
- Automatic power-flow restoration.
- Automated switching.
- Optimize real/reactive power.
- Protect/control feeder lines.

### Reactive power
Lecture describes reactive-power devices as devices that:
- Store and release energy.
- Cause increased electrical currents without consuming real power.

Source: fileciteturn113file1L923-L945

---

# 24. Plug-in Electric Vehicles (PEVs)

Smart grids enable efficient PEV use.

Benefits:
- Reduce oil dependency.
- No pollution while running on electricity.
- Can be charged during off-peak hours.
- Can act as an energy source during on-peak hours.
- Can discharge energy to grid and receive incentives.

Source: fileciteturn113file1L947-L970

### Exam idea
PEV can be both:
- **Energy consumer**
- **Potential energy source**

---

# 25. Smart Grid Communication

Important components:

- Smart home appliances
- Smart meters
- Gateways
- Data Aggregator Units (DAUs)
- Meter Data Management Systems (MDMSs)

Associated networks:
- HAN
- NAN
- WAN
- IP networks
- SANETs

Source: fileciteturn113file1L972-L1008

---

# 26. Smart-Grid Communication Protocols

The lecture gives these examples:

| Technology | Key number / feature |
|---|---|
| **C-Bus** | 3500 bits/sec; cable up to 1000 m |
| **DECT** | 64000 bits/sec |
| **EnOcean** | 1880–1930 MHz; 9600 bits/sec; 902 MHz in North America |
| **Universal Powerline Bus** | 480 bits/sec; two-way communication |
| **Thread** | 20–250 Kbits/sec; IPv6 based 6LoWPAN |
| **ZigBee** | 20–250 Kbits/sec; 2.4 GHz; IEEE 802.15.4; ~100 m |
| **SCS** | 9.6 Kbits/sec; twisted pair; OpenWebNet basis |

Source: fileciteturn113file1L1010-L1060

### Number traps
These values are lecture-specific and are worth memorizing if the exam uses numerical MCQs.

---

# 27. Smart Meters and Gateways

### Gateway
- Connects a few nearby smart meters.
- Often communicates using Wi-Fi / IEEE 802.11.
- Supports two-way communication.
- Links smart meters to DAU.

### Smart meter
- Sends energy-consumption information.
- Receives billing/control information.

Source: fileciteturn113file1L1062-L1085

---

# 28. Data Aggregator Unit (DAU)

DAU:
- Aggregates energy consumption/requests in a geographic area.
- Forwards information to MDMS.
- Maintains a buffer for queued consumer energy information.

Source: fileciteturn113file1L1087-L1103

### Memory
**Gateway = local smart-meter connection.**  
**DAU = geographic aggregation.**

---

# 29. Meter Data Management System (MDMS)

MDMS:
- Centralized coordinator for smart-grid communication.
- Handled by energy service providers.
- Part of operation center.
- Decides price per unit energy paid by consumers.

Source: fileciteturn113file1L1105-L1121

### Mock cross-check
A cumulative mock directly asks MDMS's primary function and identifies it as the **centralized coordinator** that processes aggregated data and manages energy pricing. fileciteturn116file7L793-L800

---

# 30. Smart Grid Security

Smart grid is a **cyber-physical system**.

Major vulnerabilities:
- Integrity
- Availability
- Dynamic system attacks
- Physical threats
- Coordinated attacks

Source: fileciteturn116file6L727-L746

---

# 31. Integrity

Integrity = credibility/correctness of collected and transferred data.

## Data Injection Attacks (DIA)

Can manipulate:
- Sensor readings.
- Feedback control signals.
- Electricity price signals.

Attack can occur through:
- Compromised hardware.
- Intercepted communication links.

Consequences:
- False system measurements.
- Large fluctuations.
- Line tripping.
- Generator disconnection.
- Load shedding.
- Blackout.

Source: fileciteturn113file1L1145-L1167

---

# 32. Electricity-Price Manipulation

An attacker may manipulate electricity prices to:
- Buy energy cheaply.
- Gain financial benefit.

This is an **integrity** concern.

Source: fileciteturn113file1L1169-L1193

---

# 33. Time Synchronization Attack

An attacker manipulates the time reference of timestamped measured phasors.

Possible effects:
- False visualization of actual system conditions.
- Incorrect control/protection actions.

Attacks targeting PMU time synchronization are called:
**Time Synchronization Attacks (TSAs).**

Source: fileciteturn113file1L1180-L1193

---

# 34. Availability and DoS

Availability means:
- Grid components and information remain accessible when needed.

DoS attacks:
- Make components/information inaccessible.
- Can block key signals.
- Can compromise grid stability and observability.
- Can affect generation-load balance.

Source: fileciteturn113file1L1195-L1212

### Exam lock
**Availability → DoS.**

---

# 35. Dynamic System Attacks

## Replay Attack (RA)
- Attacker compromises sensors.
- Observes outputs.
- Repeats previously observed outputs while injecting attack signals.

## Dynamic Data Injection Attack (D-DIA)
- Uses knowledge of the grid dynamic model.
- Injects data that can cause unobservability of unstable poles.
- Can lead to system collapse.

## Covert attack
- Closed-loop version of replay attacks.

Source: fileciteturn113file1L1214-L1237

---

# 36. Physical Threats

Can target:
- Generators
- Substations
- Transmission lines
- Smart meters

Smart-meter physical manipulation can be used for energy theft.

Source: fileciteturn113file1L1239-L1262

---

# 37. Coordinated Attacks

Power systems have robustness measures, but dense interconnections can be exploited.

An attacker can:
- Target multiple components.
- Use simultaneous attacks.
- Combine different attack types.
- Cause cascading failures.

Source: fileciteturn113file1L1250-L1262

---

# 38. Smart Grid + Cloud

Cloud applications can support:
- Energy management
- Information management
- Security

Source: fileciteturn113file1L1264-L1286

---

# 39. Cloud-Based Energy Management

Cloud can improve energy management.

The lecture describes cloud-based demand response models:
1. Data-centric communication
2. Topic-based group communication

Cloud scheduling considers:
- Available resources
- Priority
- Other constraints

Source: fileciteturn113file1L1288-L1311

---

# 40. Cloud for Micro-grid Management

Cloud integration can:
- Support infrastructure/power-management/service modules.
- Increase supported customers.
- Integrate/analyze data from multiple smart meters.
- Balance real-time demand and supply.
- Share real-time usage/pricing information.
- Use mobile agents to monitor heterogeneous smart-grid systems.

Source: fileciteturn113file1L1313-L1335

---

# 41. Information Management Using Cloud

Cloud supports:
- Information processing.
- Storage.
- Sharing information from different grid components.
- Real-time distributed data management.
- Parallel processing.

It also makes information retrieval more flexible and supports dynamic pricing.

Source: fileciteturn113file1L1337-L1357 and fileciteturn115file0L12-L34

---

# 42. Security in Smart Grid + Cloud

Cloud can support:
- Power-information security/protection.
- Large-scale processing using private cloud.
- Rapid response to malicious software.
- Distributed data-storage security.
- Real-time analysis/estimation.
- Cloud-based privacy schemes.

Source: fileciteturn115file0L36-L79

---

# PART C — INDUSTRIAL INTERNET OF THINGS (IIoT)

# 43. What is IIoT?

The lecture defines IIoT as:
- An application of IoT in industries.
- A mechanism to modify existing industrial systems.
- A link between:
  - Automation systems
  - Enterprise
  - Planning
  - Product lifecycle

Source: fileciteturn115file0L218-L234

---

# 44. IIoT and Industry 4.0

The lecture connects IIoT with **Industry 4.0**.

Industry 4.0 includes:
- Automation and data exchange in manufacturing.
- Cyber-physical systems.
- Internet of Things.
- Cloud computing.
- Smart factory.

Source: fileciteturn115file0L236-L257

---

# 45. IIoT Is Not Simply IoT

The lecture explicitly illustrates **IIoT ≠ IoT**.

### IoT
Broader concept.

### IIoT
Industrial intersection of:
- IoT
- Industrial systems / Industry 4.0

It focuses on industrial efficiency, safety and security rather than mainly consumer convenience.

Source: fileciteturn115file0L259-L280 and fileciteturn114file0L125-L159

---

# 46. IIoT Includes

- Machine learning.
- Big-data technology.
- Machine-to-machine interaction.
- Automation.
- Large volumes of sensor data.

### Key strategy
**Wrap & re-use**, not **rip & replace**.

Source: fileciteturn115file0L282-L302

---

# 47. Four Industrial Revolutions

| Revolution | Lecture description |
|---|---|
| **1st** | Mechanized production |
| **2nd** | Mass production |
| **3rd** | Internet evolution and automation |
| **4th** | IIoT / Industry 4.0 |

Source: fileciteturn115file0L304-L333

### Exam lock
**4th Industrial Revolution → IIoT / Industry 4.0.**

---

# 48. IIoT Requirements

Lecture lists:

1. Hardware and software connectivity
2. Cloud platform
3. Big-data analytics
4. Application development

Additional themes shown:
- Access: anything, anytime, anywhere
- End-to-end security
- User experience
- Cloud efficiency/agility
- Big data
- Asset management
- Transition to smart machines

Source: fileciteturn114file0L26-L79

---

# 49. Physical Plant ↔ Virtual Plant

The lecture shows:
- Physical plant
- Virtual plant
- Sensor readings
- Machine instructions

This illustrates the digital/virtual representation and communication of industrial processes.

### Conceptual flow
**Physical plant → sensor readings → virtual/analytics layer → machine instructions**

---

# 50. IIoT Design Considerations

Six major objectives:

| Objective | Lecture meaning |
|---|---|
| **Energy** | Time device can operate with limited power |
| **Latency** | Time required to transmit data |
| **Throughput** | Maximum data transmitted across network |
| **Scalability** | Number of devices supported |
| **Topology** | Communication/interoperability among devices |
| **Safety & Security** | Degree of application safety/security |

Source: fileciteturn114file0L104-L123

### MCQ mapping
- Transmission time → **Latency**
- Maximum data transmitted → **Throughput**
- Number of supported devices → **Scalability**
- Limited power lifetime → **Energy**

---

# 51. IoT vs IIoT

| IoT | IIoT |
|---|---|
| Focus on individual convenience | Focus on efficiency, safety, security |
| M2M relatively limited | M2M extensive |
| Consumer-level applications | Industrial applications |
| Consumer environments | Industrial environments |

Source: fileciteturn114file0L135-L159

### Memory
**IoT → convenience.**  
**IIoT → efficiency + safety + security.**

---

# 52. M2M Focus vs IoT Focus

The lecture diagram shows a relationship involving:

- Devices
- Network/connectivity
- M2M focus
- Service enablement
- Application/data
- System integration
- IoT focus

Interpretation from the lecture:
- M2M emphasizes machine/device communication.
- IoT expands beyond device communication into services, applications, data and system integration.

Source: fileciteturn114file0L161-L190

---

# 53. Service Management in IIoT

Service management:
- Implements and manages service quality to meet end-user demand.

A service:
- Is a collection of data and associated behaviors.
- Accomplishes a function/feature of a device or part of a device.

Source: fileciteturn114file0L192-L210

---

# 54. Primary vs Secondary Service

## Primary service
Basic service responsible for primary node functions.

## Secondary service
Auxiliary function supporting:
- Primary service
- Other secondary services

Source: fileciteturn114file0L212-L227

---

# 55. IIoT Application Areas

The lecture identifies:

1. Manufacturing industry
2. Healthcare service industry
3. Transportation & logistics
4. Mining
5. Firefighting

Source: fileciteturn114file0L250-L263

---

# 56. Manufacturing Industry

IIoT connects:
- Devices
- Equipment
- Workforce
- Supply chain
- Work platform

Goals:
- Smart production
- Lower operational costs
- Higher worker productivity
- Fewer workplace injuries
- Resource optimization
- Waste reduction
- End-to-end automation

Source: fileciteturn114file0L265-L281

---

# 57. Healthcare

Implanted/on-body sensors enable continuous patient monitoring.

Benefits:
- Improved treatment outcome.
- Reduced cost.
- Better disease detection.
- More accurate data collection.
- Improved drug management.

Source: fileciteturn114file0L283-L299

---

# 58. Transportation & Logistics

Connected vehicles support:
- Vehicle-to-sensor connectivity.
- Vehicle-to-vehicle connectivity.
- Vehicle-to-Internet connectivity.
- Vehicle-to-road infrastructure.

**DSRC** is the key enabling technology for V2V and V2R.

Source: fileciteturn114file0L301-L321

---

# 59. Supply-Chain Tracking

Physical objects can be equipped with:
- Barcodes
- RFID tags

This enables real-time monitoring of:
- Status
- Location

Across the supply chain from destination to origin.

Security and privacy must be maintained.

Source: fileciteturn114file0L323-L338

---

# 60. Mining

IIoT/wireless technologies support:
- Early disaster warning.
- Air-quality monitoring.
- Poisonous-gas detection.
- Oxygen-level monitoring.

Technologies mentioned:
- RFID
- Wi-Fi
- Other wireless technologies

Source: fileciteturn114file0L340-L355

---

# 61. Firefighting

Uses:
- Sensor networks
- RFID tags

For:
- Automatic diagnosis
- Early disaster warning
- Emergency rescue
- Real-time monitoring
- Improved public security

Source: fileciteturn114file0L357-L373

---

# 62. IIoT Examples

Lecture examples:
- UAVs inspecting oil pipelines.
- Sensors monitoring food safety.
- Reducing worker exposure to noise, chemicals and hazardous gases.
- Unmanned marine vehicles collecting data for long periods without fuel/crew.

Source: fileciteturn114file0L375-L390

---

# 63. Connected Ecosystems

Traditional industrial supply chains are:
- Linear.

IIoT encourages:
- Digital ecosystems.
- A shift from product focus to outcome focus.
- Faster adaptation to external changes.

Source: fileciteturn114file0L392-L406

---

# 64. Digital + Human Workforce

IIoT makes machines more intelligent.

Results:
- More automated tasks.
- Lower cost.
- Higher quality.
- Humans work with machines.
- Higher overall productivity.
- Worker skills are reformed/redefined.

Source: fileciteturn114file0L408-L422

---

# 65. New Jobs

IIoT can create new composite industries such as:
- Precision agriculture.
- Digital healthcare.
- Digital mines.

Automation may reduce unskilled work but increase demand for:
- Skilled experts.
- Digital skills.
- Analytical skills.

Source: fileciteturn114file0L424-L438

---

# 66. Reformation of Robots

IIoT robots gain:
1. **Sensing**
2. **Thinking**
3. **Acting**

They can:
- Perform repetitive tasks.
- Work under human supervision.
- Be reprogrammed.
- Perform new tasks.
- Learn faster.

Source: fileciteturn114file0L440-L456

### Memory
**Robot = Sense + Think + Act.**

---

# 67. IIoT Challenges

Primary challenges:
- Identification of objects/things.
- Managing huge data volumes.
- Integrating existing infrastructure into new IIoT infrastructure.
- Enabling data storage.

Source: fileciteturn114file0L458-L477

---

# 68. IIoT Safety Challenges

The lecture lists:
- Worker health and safety.
- Regulatory compliance.
- Environmental protection.
- Optimized operations.

Source: fileciteturn114file0L479-L495

---

# 69. IIoT Hazards

Hazards include:
- Handling/storing/using hazardous substances.
- Oxygen deficiency.
- Particulates.
- Radiation.
- Physiological stress.

Source: fileciteturn114file0L497-L519

---

# 70. Standardization in IIoT

Standardization aims to:
- Improve interoperability.
- Help different systems/applications work together.
- Improve product/service performance.

Problems:
- Interoperability.
- Semantic interoperability.
- Security/privacy.
- Radio-access-level issues.

Source: fileciteturn114file0L521-L552

### Trap
**Semantic interoperability** is specifically about **data semantics/meaning**, not merely physical connectivity.

---

# 71. IIoT Privacy and Security

Two major concerns:
1. Information security
2. Data privacy protection

Because industrial devices/things can be:
- Tracked
- Monitored
- Connected

there are risks to personal/private data.

Examples:
- Healthcare → patient medical data must not be tampered with.
- Food industry → deterioration information can affect company reputation and must remain confidential.

Source: fileciteturn114file0L554-L588

---

# 72. Manufacturing Risks

Factors hindering IIoT adoption:
- Lack of vision and leadership.
- Lack of management understanding of value.
- Costly sensors.
- Inadequate infrastructure.

Source: fileciteturn114file0L590-L604

---

# 73. Improving Sensors

Sensor technology improvements include:
- Miniaturization.
- Performance improvement.
- Lower cost.
- Lower energy consumption.

Source: fileciteturn114file0L606-L619

---

# 74. Manufacturing Improvement Through Software

Software can improve operational efficiency through:
- Predictive maintenance.
- Savings on scheduled repairs.
- Reduced maintenance costs.
- Reduced breakdowns.

Source: fileciteturn114file0L621-L636

---

# 75. Rt Tech Software Case Study

Lecture case study:
- Improves industrial-facility efficiency.
- Improves productivity.
- Provides energy-management solution.
- Automates mapping and management of energy consumption.
- Targets reduction of a plant's highest variable cost.

Source: fileciteturn114file0L638-L659

---

# 76. Industrial Products

## Intelligent Radio Modem (IRM)

Lecture mentions:
- IRM 1500
- ACE 1000-IRM

Features:
- Simple M2M connectivity.
- Data transmission.
- Easy maintenance/installation.
- Can connect IP and non-IP serial devices.
- Extends monitoring/communication capability.

Source: fileciteturn114file0L661-L682

## Comtrol IO Link Master Gateway

Supports:
- Ethernet/IP
- PROFINET (PNIO)
- Modbus TCP

Can integrate with existing and new industrial networks.

Source: fileciteturn114file0L684-L704

---

# 77. IIoT Benefits

The lecture lists:

- Improved connectivity among devices.
- Improved efficiency.
- Upgraded scalability.
- Reduced operation time.
- Remote diagnosis.
- Cost effectiveness.

Source: fileciteturn114file0L706-L727

---

# 78. IIoT Research Trends

Research directions:
- Improve communication among objects/things.
- Develop energy-efficient sensor techniques.
- Develop context-aware IoT middleware.
- Create smart objects with larger:
  - Memory
  - Processing capability
  - Reasoning capability

Source: fileciteturn114file0L729-L746

---

# 79. IIoT Conclusion

The lecture concludes that IIoT requires:
- Smaller, cheaper sensors.
- Distributed assembly-line control.
- Automated monitoring.
- Automated control.
- Automated maintenance.

Source: fileciteturn114file0L748-L761

---

# PART D — BIG DATA AND DATA HANDLING

# 80. What is Data Handling?

Data handling:
- Stores, archives or disposes of data safely and securely.
- Includes policies/procedures for electronic and non-electronic data.

IoT creates huge data volumes because:
- IoT devices generate heavy traffic.
- Large sensor deployments generate massive amounts of data.

Source: fileciteturn114file1L841-L862

---

# 81. What is Big Data?

The lecture presents Big Data as technology/architecture for extracting value from:
- Very large data volumes.
- Wide variety of data.
- High-velocity capture/discovery/analysis.

NIST framing in the lecture:
- Data volume, acquisition speed or representation limits traditional relational analysis methods.

Source: fileciteturn114file1L864-L886

---

# 82. Structured vs Unstructured Data

## Structured data
- Easily organized.
- Usually stored in relational databases.
- SQL manages it.
- Lecture states approximately **20%** of available data.

## Unstructured data
- No predefined model.
- Traditional RDBMS cannot directly process it.
- Lecture states approximately **80%** of available data.
- Includes many forms of non-tabular information.

Source: fileciteturn114file1L888-L909

### Number trap
**Structured ≈ 20%**  
**Unstructured ≈ 80%**

---

# 83. Seven Vs of Big Data

Memorize in order:

1. **Volume**
2. **Velocity**
3. **Variety**
4. **Variability**
5. **Veracity**
6. **Visualization**
7. **Value**

Source: fileciteturn114file1L911-L928

---

# 84. Volume

Volume:
- Quantity of generated data.
- Data sources continually increase.

Lecture examples:
- 30 TB of images every night from LSST.
- 72 hours of video uploaded to YouTube every minute.

Source: fileciteturn114file1L930-L947

### Trigger
**How much data? → Volume**

---

# 85. Velocity

Velocity:
- Speed at which data is generated.
- Processing time must decrease for real-time services.
- Older batch processing may not handle high-velocity data.

Lecture examples:
- 140 million tweets/day average (2011 survey).
- NYSE captures 1 TB trade information during each session.

Source: fileciteturn114file1L949-L968

### Trigger
**How fast? → Velocity**

---

# 86. Variety

Variety:
- Different categories/formats of data.
- No restriction on input formats.
- Data is often unstructured/semi-structured.

Examples:
- Text
- Images
- Audio
- Video
- Web
- GPS
- Sensor data
- SMS
- Documents
- PDFs

Source: fileciteturn114file1L970-L988

### Trigger
**What type/format? → Variety**

---

# 87. Variability

Variability:
- Meaning of data changes.
- Meaning depends on context.
- Data may appear as an unstructured/indecipherable mass.

Examples in lecture:
- Language processing
- Hashtags
- Geo-spatial data
- Multimedia
- Sensor events

Source: fileciteturn114file1L990-L1010

### Trigger
**Does the meaning/context change? → Variability**

---

# 88. Veracity

Veracity:
- Bias.
- Noise.
- Abnormality.
- Important for automated decision making.
- Important for unsupervised machine learning.

Source: fileciteturn114file1L1002-L1010

### Assignment lock
**Bias + noise + abnormality → Veracity.**

---

# 89. Visualization

Visualization:
- Presents data graphically/pictorially.
- Helps decision makers see analytics visually.
- Helps identify patterns.

Source: fileciteturn114file1L1024-L1046

### Trigger
**Graphical presentation → Visualization**

---

# 90. Value

Value:
- Extracting useful business information from scattered data.
- Uses large volume/variety.
- Provides useful analytics for informed decisions.

Source: fileciteturn114file1L1036-L1046

### Trigger
**Useful business insight → Value**

---

# PART E — DATA-HANDLING TECHNOLOGIES

# 91. Cloud Computing

NIST characteristics shown in the lecture:

1. On-demand self-service
2. Broad network access
3. Resource pooling
4. Rapid elasticity
5. Measured service

Service models:
- IaaS
- PaaS
- SaaS

Source: fileciteturn114file1L1048-L1070

---

# 92. IoT as a Data Source

The lecture describes IoT as:
- Physical objects connected to the Internet.
- Objects can identify themselves to other devices.
- Sensors are embedded in devices/machines.
- Sensors transmit sensed data to remote servers.
- Continuous acquisition occurs from:
  - Mobile equipment
  - Transportation
  - Public facilities
  - Home appliances

Source: fileciteturn114file1L1072-L1112

---

# 93. Data Centers

Data-center handling includes:
- Storing data.
- Managing/organizing data.
- Providing processing capacity.
- Providing network infrastructure.
- Managing energy.
- Replicating data for backup.
- Developing business-oriented solutions.
- Helping personnel analyze data.
- Discovering operational problems.

Source: fileciteturn114file1L1114-L1134

---

# 94. Flow of Data

The lecture gives:

**Generation → Acquisition → Storage → Analysis**

### Generation
- Enterprise data
- IoT data
- Biomedical data
- Other data

### Acquisition
- Data collection
- Data transportation
- Data preprocessing

### Storage
- Hadoop
- MapReduce
- NoSQL databases

### Analysis
- Bloom filter
- Parallel computing
- Hashing/indexing

Source: fileciteturn114file1L1136-L1161

---

# 95. Data Sources

## Enterprise data
- Online trading/analysis.
- Production/inventory.
- Sales/financial data.

## IoT data
- Industry.
- Agriculture.
- Traffic.
- Transportation.
- Medical care.
- Public departments.
- Families.

## Biomedical
- Gene sequencing.
- Clinics.
- Medical R&D.

## Other fields
- Computational biology.
- Astronomy.
- Nuclear research.

Source: fileciteturn114file1L1163-L1189

---

# 96. Data Acquisition

## Data collection
Sources include:
- Automatically generated log/record files.
- Sensor data:
  - Sound
  - Voice
  - Vibration
  - Automobile
  - Chemical
  - Current
  - Weather
  - Pressure
  - Temperature
- Mobile-device data:
  - Geographic location
  - 2D barcodes
  - Pictures
  - Videos

## Data transmission
After collection, data moves to storage for processing/analysis.

Lecture categorizes transmission into:
- Inter-DCN transmission
- Intra-DCN transmission

Source: fileciteturn114file1L1191-L1214

---

# 97. Data Pre-processing

Collected datasets can contain:
- Noise
- Redundancy
- Inconsistency

Three main preprocessing activities:
1. **Integration**
2. **Cleaning**
3. **Redundancy mitigation**

### Integration
Combine data from various sources into a uniform view.

### Cleaning
Identify:
- Inaccurate data.
- Incomplete data.
- Unreasonable data.

Then modify/delete it.

### Redundancy mitigation
- Detect repeated data.
- Filter.
- Compress.
- Avoid unnecessary transmission.

Source: fileciteturn114file1L1216-L1240

---

# 98. Data Storage

## Distributed file systems

Goals:
- Consistency.
- Availability.
- Fault tolerance.

Examples:
- GFS
- HDFS
- Kosmosfs

GFS has performance limitations for small files.

## NoSQL databases

Used because Big Data has characteristics that traditional relational databases may not handle well.

Three main NoSQL types:
1. Key-value
2. Column-oriented
3. Document-oriented

Source: fileciteturn114file1L1242-L1265

---

# PART F — HADOOP

# 99. What is Hadoop?

Hadoop is:
- Open-source software framework.
- Distributed processing of large datasets.
- Works across large computer clusters.

Lecture links Hadoop to Google's:
- GFS
- MapReduce

Apache Hadoop components include:
- MapReduce
- HDFS

Source: fileciteturn114file1L1277-L1303

---

# 100. Hadoop Building Blocks

## Hadoop Common
Utilities supporting Hadoop components.

## HDFS
Reliable distributed data storage/access.

## MapReduce
Framework for parallel processing of large datasets.

## YARN
Yet Another Resource Negotiator:
- Allocates CPU.
- Allocates memory.
- Allocates storage to applications running in Hadoop cluster.

Source: fileciteturn114file1L1305-L1325

---

# 101. HDFS Architecture

### Namenode
- Centralized node.
- Maintains filesystem metadata.

### Datanode
- Distributed node.
- Stores actual data.

### File storage
- Files divided into blocks.
- Blocks replicated.

Source: fileciteturn114file1L1327-L1349

### Assignment lock
**Actual data blocks → Datanode.**

---

# 102. Namenode Details

Namenode:
- Stores filesystem metadata.
- Maintains in-memory mappings:
  - Datanodes → blocks
  - Blocks → datanodes

It is the master/centralized role in the HDFS architecture shown.

Source: fileciteturn114file1L1351-L1371

---

# 103. Datanode Details

Datanode:
- Stores actual data.
- Can communicate with other Datanodes.
- Helps rebalance/replicate data.
- Periodically updates Namenode with block information.
- Verifies checksums before updates.

Source: fileciteturn114file1L1351-L1371

---

# 104. Job Tracker and Task Tracker

The lecture presents the older Hadoop architecture:

## Job Tracker
- Runs with Namenode.
- Receives user's job.
- Decides number of tasks/mappers.
- Decides where each mapper runs.
- Uses locality.

## Task Tracker
- Runs on each Datanode.
- Receives tasks from Job Tracker.
- Reports progress.

Source: fileciteturn114file1L1373-L1399

### Exam caution
The Week-11 lecture explicitly presents **Job Tracker/Task Tracker**. Do not silently replace these lecture terms when answering source-based questions.

---

# 105. Hadoop Master-Slave Architecture

The lecture describes a:
**Master-slave shared-nothing architecture**

### Master
- Opens/closes/renames files/directories.
- Determines block-to-Datanode mapping.

### Slave
- Serves read/write requests.
- Performs block creation/deletion/replication as instructed by Namenode.

Source: fileciteturn114file1L1401-L1425

---

# PART G — HIGH-PRIORITY COMPARISON TABLES

# 106. Traditional Grid vs Smart Grid

| Traditional | Smart |
|---|---|
| Centralized generation | Supports distributed/customer generation |
| One-directional energy | **Bidirectional energy** |
| Manual monitoring | Digital/automated monitoring |
| Limited control | Two-way communication/control |
| Less adaptive | More reliable/resilient |
| Limited renewable integration | Better renewable integration |

---

# 107. Smart Meter vs Gateway vs DAU vs MDMS

| Component | Main role |
|---|---|
| **Smart Meter** | Consumer ↔ energy-service-provider interface; measures/communicates usage |
| **Gateway** | Nearby smart meters ↔ DAU |
| **DAU** | Aggregates geographically grouped energy data |
| **MDMS** | Centralized coordination + pricing |

### One-line chain
**Meter → Gateway → DAU → MDMS**

---

# 108. Smart Grid Security Mapping

| Concept | Key association |
|---|---|
| Integrity | Correctness/credibility of data |
| Data Injection | Manipulates sensor/control/price data |
| Time Synchronization Attack | Manipulates PMU time |
| Availability | Accessibility |
| **DoS** | **Availability attack** |
| Replay Attack | Repeats learned sensor outputs |
| D-DIA | Uses grid dynamic model |
| Physical threat | Attacks physical components |
| Coordinated attack | Multiple simultaneous/cascading attacks |

---

# 109. IoT vs IIoT

| IoT | IIoT |
|---|---|
| Convenience | Efficiency/safety/security |
| Consumer-level | Industrial-level |
| M2M limited | M2M extensive |
| Smart consumer applications | Smart industrial systems |
| Broad ecosystem | Industrial ecosystem |

---

# 110. Big Data 7 Vs

| V | Meaning |
|---|---|
| Volume | Amount |
| Velocity | Speed |
| Variety | Data types/formats |
| Variability | Changing meaning/context |
| **Veracity** | **Bias/noise/abnormality** |
| Visualization | Graphical presentation |
| Value | Useful information/business insight |

### Mnemonic
**V V V V V V V** → remember the meanings, not just the letters.

---

# 111. Data Preprocessing

| Step | Purpose |
|---|---|
| **Integration** | Combine sources into uniform view |
| **Cleaning** | Fix/remove inaccurate/incomplete/unreasonable data |
| **Redundancy mitigation** | Remove repeated data using detection/filtering/compression |

---

# 112. HDFS

| Component | Function |
|---|---|
| **Namenode** | Metadata |
| **Datanode** | Actual data |
| Files | Divided into blocks |
| Blocks | Replicated |
| Job Tracker | Receives/assigns jobs in lecture's older architecture |
| Task Tracker | Executes/report tasks on Datanodes |

---

# PART H — MOCK-STYLE CROSS-CHECK

The cumulative mock material reinforces several Week-11 concepts.

## Directly relevant patterns

### 1. Industry 4.0
A cumulative mock asks for the fourth industrial revolution and identifies:
**Industry 4.0**. fileciteturn116file3L396-L402

### 2. Wrap and reuse
A mock asks how wrap-and-reuse helps IIoT adoption:
**Integrates new technologies with existing systems, minimizing disruption and cost.** fileciteturn116file7L757-L763

### 3. MDMS
A mock asks for the primary smart-grid MDMS function:
**Centralized coordination, aggregated-data processing and energy pricing.** fileciteturn116file7L793-L800

### 4. DSRC
The Week-11 assignment itself identifies DSRC as the key V2V/V2R technology. fileciteturn113file0L238-L255

### 5. Big Data
The assignment directly tests:
- Veracity.
- Redundancy mitigation.
- HDFS Datanode.

These are especially high priority because they are both assignment and lecture concepts. fileciteturn113file0L282-L342

---

# PART I — EXAM TRAP BANK

## Smart Grid

### Trap 1
**Bidirectional energy + two-way communication/control**
→ Smart Grid

### Trap 2
**One-directional energy + manual restoration**
→ Traditional Grid

### Trap 3
**Smart meter**
→ Consumer ↔ Energy Service Provider interface

### Trap 4
**Time-of-Use**
→ Off-peak consumption

### Trap 5
**Net metering**
→ Inflow + outflow

### Trap 6
**Voltage/current sampling**
→ PMU

### Trap 7
**Nearby smart meters ↔ DAU**
→ Gateway

### Trap 8
**Availability attack**
→ DoS

---

## IIoT

### Trap 9
**Existing industrial systems**
→ Wrap & re-use

### Trap 10
**Fourth Industrial Revolution**
→ Industry 4.0 / IIoT

### Trap 11
**IIoT**
→ Industrial application of IoT

### Trap 12
**Efficiency + safety + security**
→ IIoT

### Trap 13
**V2V/V2R**
→ DSRC

### Trap 14
**Mine gases/oxygen/air quality**
→ IIoT wireless sensing

---

## Big Data

### Trap 15
**Bias/noise/abnormality**
→ Veracity

### Trap 16
**Repeated data**
→ Redundancy mitigation

### Trap 17
**Actual HDFS blocks**
→ Datanode

### Trap 18
**Filesystem metadata**
→ Namenode

### Trap 19
**Graphical data presentation**
→ Visualization

### Trap 20
**Useful business information**
→ Value

### Trap 21
**Data speed**
→ Velocity

### Trap 22
**Data amount**
→ Volume

### Trap 23
**Data types/formats**
→ Variety

### Trap 24
**Changing context/meaning**
→ Variability

---

# PART J — IMPORTANT NUMBERS / FACTS

| Topic | Number / fact |
|---|---|
| Structured data in lecture | **20%** |
| Unstructured data in lecture | **80%** |
| C-Bus | **3500 bits/sec** |
| C-Bus cable length | **up to 1000 m** |
| DECT | **64000 bits/sec** |
| EnOcean | **1880–1930 MHz**, 9600 bits/sec |
| EnOcean North America | **902 MHz** |
| Universal Powerline Bus | **480 bits/sec** |
| Thread | **20–250 Kbits/sec** |
| ZigBee smart-grid communication | **20–250 Kbits/sec** |
| ZigBee band | **2.4 GHz** |
| ZigBee range in lecture | **~100 m** |
| SCS | **9.6 Kbits/sec** |
| LSST example | **30 TB/night** |
| YouTube example | **72 hours/minute** |
| Tweets example | **140 million/day** |
| NYSE example | **1 TB/session** |

> **Exam advice:** The conceptual mappings are more important than lecture-era example statistics unless the question explicitly asks for a number.

---

# PART K — 60-SECOND RECALL

> **Smart Grid:** bidirectional energy + two-way communication/control.  
> **Traditional grid:** centralized + one-way + manual.  
> **Smart meter:** consumer ↔ service provider interface.  
> **TOU:** off-peak.  
> **Net metering:** inflow + outflow.  
> **PMU:** voltage/current sampling → phasor network → SCADA.  
> **Distribution intelligence:** outage detection + automatic restoration.  
> **Gateway:** smart meters ↔ DAU.  
> **Availability attack:** DoS.  
> **IIoT:** industrial IoT + automation + enterprise/planning/product lifecycle.  
> **Industry 4.0:** fourth industrial revolution.  
> **Existing industrial assets:** wrap & reuse.  
> **V2V/V2R:** DSRC.  
> **Mining:** air quality + poisonous gases + oxygen.  
> **Big Data 7 Vs:** Volume, Velocity, Variety, Variability, Veracity, Visualization, Value.  
> **Veracity:** bias/noise/abnormality.  
> **Preprocessing:** integration + cleaning + redundancy mitigation.  
> **HDFS:** Namenode = metadata, Datanode = actual data.

---

# PART L — 30-QUESTION RAPID SELF-TEST

1. What distinguishes a smart grid from a traditional grid?
2. What is the main role of a smart meter?
3. Under TOU pricing, when should smart appliances operate to reduce cost?
4. Which two energy flows matter in net metering?
5. What does a PMU sample?
6. What is distribution intelligence?
7. What does a smart-grid gateway connect?
8. Which attack targets availability?
9. What is IIoT?
10. What approach does IIoT use for existing industrial systems?
11. What is Industry 4.0?
12. What is the key V2V/V2R technology?
13. What environmental parameters are monitored in mines?
14. What is the Big Data V referring to data amount?
15. Which V refers to speed?
16. Which V refers to types/formats?
17. Which V refers to changing meaning/context?
18. Which V refers to bias/noise/abnormality?
19. Which V refers to graphical presentation?
20. Which V refers to useful business information?
21. What are the three preprocessing activities?
22. What does redundancy mitigation do?
23. What does HDFS store?
24. What does the Namenode store?
25. What does the Datanode store?
26. What does MapReduce do?
27. What does YARN allocate?
28. What are the six IIoT design considerations?
29. What are the main IIoT application areas?
30. What are the main smart-grid security categories?

## Answers

1. Bidirectional energy + two-way communication/control.
2. Smart-grid interface between consumer and energy service provider.
3. Off-peak hours.
4. Grid-to-consumer inflow and consumer-to-grid outflow.
5. Voltage and current.
6. Smart-IoT-based distribution intelligence that detects outages, restores power automatically, optimizes real/reactive power and protects feeders.
7. Nearby smart meters to DAU.
8. DoS.
9. Industrial application of IoT linking automation with enterprise/planning/product lifecycle.
10. Wrap and re-use.
11. Fourth Industrial Revolution.
12. DSRC.
13. Air quality, poisonous gases and oxygen level.
14. Volume.
15. Velocity.
16. Variety.
17. Variability.
18. Veracity.
19. Visualization.
20. Value.
21. Integration, cleaning, redundancy mitigation.
22. Removes repeated data through detection, filtering and compression.
23. Distributed large-scale data.
24. Filesystem metadata.
25. Actual data.
26. Parallel processing of large datasets.
27. CPU, memory and storage to applications.
28. Energy, latency, throughput, scalability, topology, safety/security.
29. Manufacturing, healthcare, transportation/logistics, mining, firefighting.
30. Integrity, availability, dynamic system attacks, physical threats, coordinated attacks.

---

# PART M — FINAL EXAM PRIORITY ORDER

## Priority 1 — Memorize all 15 assignment mappings

**C, B, A, D, A, B, A, D, A, C, D, A, C, D, A**

But do **not** memorize only the letters. Memorize the concept:

1. Smart grid → bidirectional/two-way
2. Smart meter → interface
3. TOU → off-peak
4. Net metering → inflow/outflow
5. PMU → voltage/current
6. Distribution intelligence → outage/restoration
7. Gateway → meters/DAU
8. Availability → DoS
9. IIoT → industrial application
10. Wrap/re-use
11. DSRC
12. Mining sensors
13. Veracity
14. Redundancy mitigation
15. Datanode

## Priority 2 — Smart Grid architecture

Know:
**Meter → Gateway → DAU → MDMS**

## Priority 3 — Security

Know:
**Integrity vs Availability vs Dynamic vs Physical vs Coordinated**

## Priority 4 — IIoT

Know:
**IoT → Industry → Industry 4.0 → wrap/re-use → applications → challenges**

## Priority 5 — Big Data

Know all **7 Vs** and their exact meanings.

## Priority 6 — Hadoop

Know:
**Namenode = metadata**  
**Datanode = actual data**  
**MapReduce = parallel processing**  
**YARN = resource allocation**

---

# PART N — FINAL ONE-PAGE REVISION

## SMART GRID

**Traditional:** centralized + one-way + manual  
**Smart:** bidirectional + two-way communication/control + digital

**Smart meter:** consumer ↔ energy service provider

**TOU:** off-peak

**Net metering:** inflow − outflow concept

**PMU:** voltage/current → phasor network → SCADA

**Distribution intelligence:** outage detection + automatic restoration

**Gateway:** smart meters → DAU

**DAU:** geographic aggregation

**MDMS:** centralized coordinator + pricing

---

## SMART GRID SECURITY

**Integrity:** correct/credible data  
**DIA:** data manipulation  
**TSA:** PMU time manipulation  
**Availability:** accessibility  
**DoS:** availability attack  
**Replay:** repeat learned outputs  
**D-DIA:** dynamic-model-based injection  
**Physical:** physical components  
**Coordinated:** multiple/cascading attacks

---

## IIoT

**IIoT = industrial application of IoT**

**Industry 4.0 = fourth industrial revolution**

**IIoT strategy = Wrap & Re-use**

**IIoT focus = efficiency + safety + security**

**Design:** Energy + Latency + Throughput + Scalability + Topology + Safety/Security

**Applications:**
- Manufacturing
- Healthcare
- Transportation/logistics
- Mining
- Firefighting

**V2V/V2R → DSRC**

**Mining → air quality + poisonous gases + oxygen**

**Robot → sensing + thinking + acting**

---

## BIG DATA

**7 Vs:**

- Volume = amount
- Velocity = speed
- Variety = types
- Variability = changing meaning
- Veracity = bias/noise/abnormality
- Visualization = graphical
- Value = useful information

**Structured ≈ 20%**  
**Unstructured ≈ 80%**

---

## DATA PREPROCESSING

**Integration → Cleaning → Redundancy Mitigation**

- Integration → uniform view
- Cleaning → inaccurate/incomplete/unreasonable data
- Redundancy mitigation → repeated data → detection/filtering/compression

---

## HADOOP

**Hadoop = distributed processing of large datasets**

**HDFS = distributed storage**

**Namenode = metadata**

**Datanode = actual data**

**MapReduce = parallel processing**

**YARN = CPU + memory + storage allocation**

**Files → blocks → replicated blocks**

---

# SOURCE BASIS

This file is based on:

1. **Assignment_11.pdf** — all 15 Week-11 assignment questions, answer keys and explanations. fileciteturn113file0L18-L59 fileciteturn113file0L66-L165 fileciteturn113file0L172-L234 fileciteturn113file0L238-L342
2. **Week-11.pdf** — Smart Grid Part I, Smart Grid Part II, IIoT Part I, IIoT Part II, and Data Handling & Analytics Part I. fileciteturn113file1L377-L530 fileciteturn113file1L559-L705 fileciteturn113file1L877-L1121 fileciteturn114file0L218-L456 fileciteturn114file0L458-L746 fileciteturn114file1L841-L1425
3. **Uploaded cumulative mock exams** — used only for directly relevant Week-11 cross-checks such as Industry 4.0, wrap-and-reuse, and MDMS. fileciteturn116file3L396-L402 fileciteturn116file7L757-L800

> **No outside web research and no invented assignment questions were used.**
>
> **No images were generated or added.**

---

# END OF WEEK 11 NOTES
