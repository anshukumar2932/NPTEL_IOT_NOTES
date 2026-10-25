# NPTEL Introduction to Internet of Things — Week 12
## Assignment-First Exam Notes + Complete Lecture Coverage

> **Exam priority:** Assignment questions are the highest priority, but these notes cover **all Week 12 lecture topics** from the uploaded Week-12 material.
>
> **Source basis:** `Assignment_12 (1).pdf` and `Week-12.pdf` uploaded in this conversation.
>
> **Image policy:** No images are generated or added.

---

# 0. WEEK 12 — WHAT TO STUDY FIRST

## Highest-priority blocks

1. **Assignment 12 — all 15 questions**
2. **Data Handling and Analytics — Part II**
   - Qualitative vs quantitative analysis
   - Statistical models
   - Complete vs incomplete models
   - ANOVA
   - TSS, F-ratio, degrees of freedom
   - Data dispersion
   - Contingency and correlation
   - Pearson correlation
   - Regression
   - Statistical significance
   - Precision and error limits
3. **AgriSens / Smart Water Management**
   - Objectives
   - 3-layer architecture
   - Sensor design
   - Sensor-node design
   - Remote-server design
   - Results
4. **IoT Healthcare / AmbuSens**
   - Emergence of IoT healthcare
   - 4-layer healthcare architecture
   - Remote healthcare
   - Real-time monitoring
   - Preventive care
   - AmbuSens physiological parameters
   - WBAN
   - Health-cloud framework
   - Privacy / identity masking
   - Web interface
   - System trials and ECG result
5. **Activity Monitoring**
   - Wearable sensors
   - Continuous monitoring
   - Important human activities
   - Sensor types
   - Statistical / ML / DL analysis
   - In-place vs network-based approaches
   - Smartphone demonstration

---

# PART I — ASSIGNMENT 12 (HIGHEST PRIORITY)

## Assignment Answer Lock

| Q | Answer | Core idea |
|---|---|---|
| 1 | **A — Qualitative analysis** | Categorical data |
| 2 | **A** | Complete model: variables = equations |
| 3 | **B** | ANOVA: more than two populations/samples |
| 4 | **C** | Pearson's `r`: strength of association |
| 5 | **D** | AgriSens: more crop yield with less water |
| 6 | **B** | AgriSens 3 layers |
| 7 | **B** | Sensor node includes power management unit |
| 8 | **C** | Multi-user server: SMS + farmer queries/control |
| 9 | **D** | Smartphones/tablets are in aggregated layer |
| 10 | **A** | Fall detection = preventive care |
| 11 | **C** | Continuous monitoring reveals daily/repetitive patterns |
| 12 | **A** | Deep learning: sensor data + images + videos |
| 13 | **D** | Processing on device = in-place |
| 14 | **C** | Smartphone + network + remote server |
| 15 | **A** | Demonstration logs accelerometer values |

---

## Q1. Which type of data analysis is used for categorical data?

**Answer: A — Qualitative analysis**

### Why
The lecture distinguishes:

- **Qualitative analysis** → categorical/descriptive data.
- **Quantitative analysis** → numerical data.

### Exam trap
Do not confuse:

- **Categorical** → qualitative
- **Numerical** → quantitative

### Memory
> **Qualitative = categories / descriptions.**  
> **Quantitative = quantities / numbers.**

---

## Q2. When is a statistical model a complete model?

**Answer: A — When the number of variables equals the number of equations**

### Lecture rule

- **Complete model:** number of variables = number of equations.
- **Incomplete model:** number of variables ≠ number of equations.

### Exam trap
The word **complete** is tied to the equality condition.

> **Complete → variables = equations**

---

## Q3. When is ANOVA best applied?

**Answer: B — More than two populations or samples**

### Why
The lecture describes ANOVA as a **parametric statistical technique** used to compare datasets and says it is best applied when **more than two populations or samples** are being compared.

### Important conditions from the lecture

ANOVA requires:

- A continuous response variable.
- At least one categorical factor.
- Factor with two or more levels.
- Approximately normally distributed populations.
- Independence.
- Normality.
- Homogeneity.

### Exam trap
Do not map ANOVA only to “two groups.”

> **ANOVA → compare multiple groups/populations.**

---

## Q4. What does Pearson's correlation coefficient `r` measure?

**Answer: C — The strength of association between two variables**

### Lecture framing

Correlation investigates the relationship between **two quantitative, continuous variables**.

Pearson's correlation coefficient `r` measures the **strength of association** between those variables.

### Trap
Correlation is not:

- sample size,
- maximum value,
- number of equations.

> **Pearson `r` → strength of association.**

---

## Q5. Primary objective of AgriSens

**Answer: D — Achieving more crop yield with less water**

### AgriSens objectives

The lecture lists:

- More yields with less water.
- Save limited water resources.
- Automatic irrigation cycle.
- Dynamic irrigation treatments in different phases of crop life.
- Remote monitoring and controlling.

### Exam trap
The objective is **not** simply “use more water.”

> **AgriSens = water-efficient agriculture + automation + remote control.**

---

## Q6. Three layers of proposed AgriSens architecture

**Answer: B**

### The three layers

1. **Sensing and actuating layer**
2. **Processing, storage, and service layer**
3. **Application layer**

### Memory chain

> **Sense/Actuate → Process/Store/Serve → Application**

### Trap
Do not substitute generic OSI/network layers.

---

## Q7. Component in integrated AgriSens sensor-node design

**Answer: B — Power management unit**

### Sensor-node components highlighted by the lecture

- Sensors and actuators
- Processing and memory unit
- Wireless communication unit
- **Power management unit**

### Exam trap
PMU is especially important in a field-deployed sensor node because the node needs managed power for sensing, processing, and wireless communication.

---

## Q8. Function of the AgriSens multi-user server

**Answer: C**

It:

- Sends field information to the farmer's mobile phone using **SMS**.
- Executes farmer queries.
- Executes controlling/control messages.

### Remote-server components

| Component | Lecture role |
|---|---|
| Repository data server | Communicates with deployed IoT gateway in the field using **GPRS** |
| Web server | Provides remote access to field data |
| Multi-user server | Sends field information to farmer by **SMS** and executes farmer queries/control messages |

### Trap
Do not swap **GPRS** and **SMS**:

> **Repository ↔ GPRS**  
> **Multi-user ↔ SMS**

---

## Q9. Layer containing smartphones and tablets as data aggregators

**Answer: D — Aggregated layer**

### IoT healthcare architecture

1. **Sensing layer**
2. **Aggregated layer**
3. **Processing layer**
4. **Cloud platform**

The aggregated layer contains aggregators such as:

- Smartphones
- Tablets

### Memory
> Sensors collect → smartphones/tablets aggregate → servers process → cloud stores/accesses.

---

## Q10. Example of preventive care enabled by IoT healthcare

**Answer: A — Fall detection for senior citizens**

Other lecture examples:

- Emergency situation detection.
- Alerts to family members.
- Machine learning for health trend tracking.
- Early anomaly detection.

### Trap
Preventive care means **detecting problems early / reducing risk**, not merely storing records.

---

## Q11. Advantage of continuous activity monitoring

**Answer: C — It enables daily observation of human behavior and repetitive activity patterns**

### Why
Continuous monitoring helps:

- Observe human behavior daily.
- Observe repetitive activity patterns.
- Support more reliable activity recognition.
- Enable long-term monitoring.

### Trap
It is not restricted to cameras.

---

## Q12. Data types analyzable by the deep-learning approach

**Answer: A — Sensor data, images, and videos**

### Week 12 data-analysis mapping

| Approach | Lecture-supported data |
|---|---|
| Statistical | Sensor data |
| Machine learning based | Sensor data |
| Deep learning based | Sensor data + images + videos |

### Trap
Do not interpret deep learning as “images only.”

---

## Q13. Processing activity-monitoring data directly on the device

**Answer: D — In-place approach**

### In-place

- Processing happens **on the device**.
- Generally **power intensive**.
- Does **not require a network connection** for the processing task.

### Network-based

- Larger and processing-intensive methods can be applied.
- Group-based analytics possible.
- Lower power consumption.
- Requires an average-to-good network connection.

### Core comparison

> **In-place → local processing, high power, no network needed.**  
> **Network-based → remote/group processing, lower device power, network needed.**

---

## Q14. Three basic elements in smartphone activity-monitoring demonstration

**Answer: C**

1. **Smartphone**
2. **Network**
3. **Remote server**

### Data flow

**Smartphone sensors → Network → Remote server**

The smartphone generates sensor data; the network transports it; the remote server receives/processes/visualizes it.

---

## Q15. Sensor values logged in the activity-monitoring demonstration

**Answer: A — Accelerometer values**

### Trap
Do not confuse this with:

- Soil moisture
- Water level
- Smart-grid phasors

> **Smartphone activity demo → accelerometer readings.**

---

# PART II — DATA HANDLING AND ANALYTICS

## 1. What is Data Analytics?

The lecture defines data analytics as the process of **examining datasets to draw conclusions about the information they contain**, increasingly using specialized systems and software.

### Why it matters in IoT

IoT continuously produces data. Analytics converts that data into useful information for:

- Understanding patterns.
- Finding relationships.
- Identifying trends.
- Supporting decisions.
- Prediction and forecasting.
- Measuring performance.

---

# 2. Types of Data Analysis

The lecture gives two main types.

## 2.1 Qualitative Analysis

Deals with data that is **categorical in nature**.

Characteristics:

- Data is not primarily described through numerical values.
- Descriptive context is important.
- Can be gathered through interviews, videos, audio recordings, field notes.
- Requires interpretation.
- Data can be grouped into identifiable themes.

### Three basic principles mentioned

1. **Notice things**
2. **Collect things**
3. **Think about things**

### Examples

- Color
- Smell
- Taste
- Descriptive observations

---

## 2.2 Quantitative Analysis

Deals with **numerical data**.

The lecture mentions:

- Mean
- Median
- Standard deviation
- Statistical models
- Data dispersion
- Analysis of variables
- Relationships between variables
- Regression
- Statistical significance
- Precision
- Error limits
- Contingence/correlation

### Qualitative vs Quantitative

| Qualitative | Quantitative |
|---|---|
| Categorical/descriptive | Numerical |
| Data is observed | Data is measured |
| Descriptions | Numbers |
| Quality emphasis | Quantity emphasis |
| Color, smell, taste | Volume, weight |

### MCQ trap
If the question says **categorical**, immediately think:

> **Qualitative**

If it says **numerical**, think:

> **Quantitative**

---

# 3. Advantages of Data Analytics

The lecture highlights that analytics can:

- Identify important and mission-critical trends.
- Identify performance problems requiring action.
- Present information visually for faster/better decisions.
- Improve awareness of customer habits.
- Provide competitive advantage.

### Exam idea

> Analytics is not merely data storage; it is about extracting useful conclusions from data.

---

# 4. Statistical Models

## Definition

A statistical model is a mathematical representation of relationships between variables.

The lecture describes it as a mathematical equation formulated as relationships between variables.

A statistical model illustrates how one set of random variables is related to another set.

### Mathematical representation

The lecture represents a statistical model as:

**(X, P)**

where:

- `X` = set of all possible observations.
- `P` = set of probability distributions on `X`.

---

# 5. Complete vs Incomplete Statistical Model

## Complete model

**Number of variables = number of equations**

## Incomplete model

**Number of variables ≠ number of equations**

### Must memorize

> **Complete → equal**  
> **Incomplete → unequal**

---

# 6. Building a Statistical Model

The lecture gives the following broad sequence:

1. **Data gathering**
2. **Descriptive methods**
3. **Thinking about predictors**
4. **Building of model**
5. **Interpreting the results**

### Exam trap
The sequence is not “model first, data later.”

---

# 7. Analysis of Variance — ANOVA

## Definition

ANOVA is a **parametric statistical technique** used to compare datasets.

The lecture states that it is best applied when **more than two populations or samples** are being compared.

### Required conditions highlighted

- Continuous response variable.
- At least one categorical factor.
- Factor has two or more levels.
- Approximately normally distributed populations.

### Important properties

#### Independence of cases

- Sample should be selected randomly.
- There should not be a pattern in sample selection.

#### Normality

- Distribution of each group should be normal.

#### Homogeneity

- Variance between groups should be the same.

---

# 8. Types of ANOVA

The lecture lists:

### One-way analysis

- One fixed factor.
- Factor levels are set by investigator.
- Examples of factors: age, gender.

### Two-way analysis

The lecture describes factor variables as more than two.

### K-way analysis

- Factor variables are `k`.

### Exam priority

Remember the naming:

> **One-way → one fixed factor**  
> **Two-way → two-factor case**  
> **K-way → k factors**

---

# 9. Total Sum of Squares — TSS / SST

The lecture defines total sum of squares as the sum, over observations, of the squared differences of each observation from the overall mean.

Conceptually:

**TSS/SST = total squared deviation from the overall mean**

### Exam trap
Do not confuse TSS with a simple sum of raw observations.

---

# 10. F-ratio

The F-ratio helps understand the ratio of variance between two data sets.

Lecture rule:

- F-ratio is approximately **1.0** when the null hypothesis is true.
- F-ratio is **greater than 1.0** when the null hypothesis is false, according to the lecture framing.

### Memory

> **F ≈ 1 → null hypothesis true**  
> **F > 1 → null hypothesis false**  
> *(Use the lecture's stated rule for the exam.)*

---

# 11. Degrees of Freedom

Degrees of freedom describe the number of values in the final calculation of a statistic that are free to vary.

The lecture also describes factors with no effect on variance in this context.

### Exam wording

If the question asks:

> “Number of values free to vary?”

Answer:

> **Degrees of freedom**

---

# 12. Data Dispersion

A measure of statistical dispersion:

- Is a nonnegative real number.
- Is zero if all data values are the same.
- Increases as data become more diverse.

## Examples

- Range
- Average absolute deviation
- Variance
- Standard deviation

---

# 13. Range

The lecture gives:

**Range = maximum value − minimum value**

### Memory

> **Range = max − min**

---

# 14. Average Absolute Deviation

Also called mean absolute deviation.

It is the average of the **absolute deviations from the mean**.

Key word:

> **Absolute**

So positive and negative deviations do not cancel each other.

---

# 15. Variance

Variance is the expectation of the **squared deviation** of a random variable from its mean.

### Memory

> **Variance → squared deviation**

---

# 16. Standard Deviation

Standard deviation is a measure used to quantify the amount of variation or dispersion of a dataset.

### Trap

- Variance → squared-deviation based.
- Standard deviation → dispersion measure derived from variance conceptually.

---

# 17. Contingency Tables

A contingency table, also called a cross-tabulation/crosstab, is a matrix-style table displaying the frequency distribution of variables.

It provides a basic picture of the interrelation between two variables.

### Memory

> **Contingency table → frequency distribution / cross-tabulation**

---

# 18. Correlation

Correlation investigates the relationship between **two quantitative, continuous variables**.

## Pearson's correlation coefficient

Pearson's `r` measures the **strength of association** between two variables.

Correlations are useful because they can indicate a predictive relationship that can be exploited in practice.

### Assignment lock

> **Pearson `r` → strength of association**

### Trap
Do not confuse correlation with regression.

---

# 19. Regression Analysis

Regression analysis is a statistical process for estimating relationships among variables.

It focuses on:

- A **dependent variable**.
- One or more **independent variables**.

It estimates the conditional expectation of the dependent variable given the independent variables.

### Regression function

The estimation target is a function of the independent variables called the **regression function**.

### Uses

- Prediction.
- Forecasting.
- Understanding which independent variables are related to the dependent variable.

### Correlation vs Regression

| Correlation | Regression |
|---|---|
| Relationship/association | Estimates relationship |
| Pearson `r` measures strength | Models dependent variable using independent variables |
| Two quantitative continuous variables in lecture framing | Dependent + one or more independent variables |
| Can indicate predictive relationship | Used directly for prediction/forecasting |

---

# 20. Statistical Significance

The lecture describes statistical significance as the likelihood that a difference in conversion rates between a variation and baseline is **not due to random chance**.

The significance level reflects:

- Risk tolerance.
- Confidence level.

### Two key variables highlighted

1. **Sample size**
2. **Effect size**

---

# 21. Sample Size and Effect Size

## Sample size

Larger sample size can increase confidence in the result of an experiment, assuming a randomized sample.

## Effect size

The lecture describes effect size as the standardized mean difference between two groups.

### Exam trap

Do not treat:

- Sample size = effect size.
- Effect size = number of samples.

They are different concepts.

---

# 22. Precision and Error Limits

## Precision

Precision refers to how close estimates from different samples are to each other.

The lecture states:

> **Standard error is a measure of precision.**

It also states:

> **Precision is inversely related to standard error.**

Therefore:

- Small standard error → greater precision.
- Large standard error → lower precision.

---

## Limits of Error

The limits of error are the maximum overestimate and maximum underestimate arising from sampling and non-sampling errors.

### Lecture formula

**Limit of error = Critical value × Standard deviation of the statistic**

The critical value determines the tolerance level of error.

### Exam trap
Memorize the exact lecture form.

---

# PART III — AGRISENS: SMART WATER MANAGEMENT USING IoT

# 23. Future IoT Applications in Agriculture

The lecture identifies applications including:

- Soil moisture and water-level monitoring.
- Automated irrigation systems.
- Automation in recycling organic waste and vermicomposting.
- Automated sowing and weeding systems.

### Core theme

> IoT can connect sensing, irrigation, automation, monitoring, and control in agriculture.

---

# 24. AgriSens — Main Objective

AgriSens is the Week 12 smart-water-management case study.

### Objectives from the lecture

- **More yields with less water**
- Save limited water resources in a country.
- Automatic irrigation cycle.
- Dynamic irrigation treatments in different phases of a crop's life.
- Remote monitoring and controlling.

### Exam priority

The strongest one-line memory:

> **AgriSens → more crop yield with less water.**

---

# 25. AgriSens Proposed Architecture

The architecture has **three layers**:

### Layer 1 — Sensing and Actuating Layer

Responsible for:

- Sensing field/environment conditions.
- Actuation/control.

### Layer 2 — Processing, Storage and Service Layer

Responsible for:

- Processing.
- Storage.
- Services.

### Layer 3 — Application Layer

Provides application-level functionality to users.

### Memory chain

**Sensing/Actuating → Processing/Storage/Service → Application**

---

# 26. AgriSens Integrated Design

The lecture divides the integrated design into:

1. **Sensors**
2. **Sensor node**
3. **Remote server**

---

# 27. AgriSens Sensor Design

The lecture shows designed sensors including:

- A designed **water-level sensor**.
- **EC-05 soil moisture sensor**.

### Exam association

> **Water management → water level + soil moisture**

---

# 28. AgriSens Sensor Node

The lecture presents an integrated sensor-node design.

The assignment specifically identifies the **power management unit** as a component.

The lecture solution also describes the sensor node as containing:

- Sensors and actuators.
- Processing and memory unit.
- Wireless communication unit.
- Power management unit.

### Functional chain

**Sensors/Actuators → Processing/Memory → Wireless communication → Power management**

---

# 29. AgriSens Remote Server

The remote-server design contains:

## Repository Data Server

- Communicates with the deployed IoT gateway in the field.
- Uses **GPRS** technology.

## Web Server

- Provides access to field data remotely.

## Multi-User Server

- Sends field information to farmer's cell/mobile phone using **SMS**.
- Executes farmer queries.
- Executes controlling messages.

### High-priority association

| Component | Remember |
|---|---|
| Repository data server | **GPRS** |
| Web server | Remote field-data access |
| Multi-user server | **SMS + queries + control** |

---

# 30. AgriSens Implementation

The lecture mentions:

- Field demo.
- Website demo.
- Project details from website.

The case study is presented as a practical IoT agriculture system rather than only a theoretical architecture.

---

# 31. AgriSens Results

The lecture presents results for:

- Average soil moisture.
- Average water level.
- Average packet delivery ratio.

### Crop phases shown

- Vegetative phase.
- Reproductive phase.
- Maturity phase.

This is important because the project uses **dynamic irrigation treatments in different phases of crop life**.

---

# 32. Packet Delivery Ratio Result

The lecture shows:

**Average PDR: 98.75 – 89.75%**

The slide also identifies noise sources such as:

- Air flow.
- Temperature.
- Solar radiation.
- Rain.

### Exam number

> **PDR: 98.75–89.75%**

Do not confuse PDR with water level or soil moisture.

---

# PART IV — IoT HEALTHCARE

# 33. Emergence of IoT Healthcare

The lecture attributes the emergence of IoT healthcare to advances in:

- Sensors.
- Connectivity.

### Benefits

IoT healthcare can:

- Collect patient data over time.
- Enable preventive care.
- Help understand effects of therapy on a patient.
- Allow devices to collect data automatically.
- Obtain data when and where needed by doctors.
- Reduce risk of human error through automation.
- Increase efficiency.
- Reduce cost.

### Memory chain

**Sensors + connectivity → continuous data → preventive care + better therapy understanding**

---

# 34. Four-Layer IoT Healthcare Architecture

The lecture organizes IoT healthcare into **four layers**:

1. **Sensing layer**
2. **Aggregated layer**
3. **Processing layer**
4. **Cloud platform**

---

## 34.1 Sensing Layer

Contains:

- Sensors.
- RFIDs.
- Wireless sensor networks (WSNs).

Examples given:

- Google Glass.
- Fitbit tracker.

---

## 34.2 Aggregated Layer

Contains different types of aggregators based on sensing-layer sensors.

Examples:

- **Smartphones**
- **Tablets**

### Assignment lock

> Smartphones and tablets → **Aggregated layer**

---

## 34.3 Processing Layer

Contains servers for processing information coming from the aggregated layer.

---

## 34.4 Cloud Platform

Processed data are uploaded to the cloud platform.

The cloud platform can be accessed by a large number of users.

### Four-layer memory

> **Sense → Aggregate → Process → Cloud**

---

# 35. Remote Healthcare

Problem:

- Many people do not have ready access to effective healthcare.

IoT solution:

- Wireless IoT-driven solutions bring healthcare to patients rather than requiring patients to travel to healthcare facilities.
- Medical data can be securely captured using IoT sensors and smart algorithms.
- Data can be wirelessly shared with healthcare professionals.
- Professionals can provide appropriate recommendations.

### Exam idea

> **Remote healthcare = healthcare comes to the patient.**

---

# 36. Real-Time Monitoring

IoT-driven non-invasive monitoring can use:

- Sensors for comprehensive physiological information.
- Gateways.
- Cloud-based analytics and data storage.
- Wireless communication to caregivers.

### Benefit

- Lower cost of healthcare.

---

# 37. Preventive Care

The lecture lists:

- **Fall detection for seniors**
- Emergency situation detection.
- Alerts to family members.
- Machine learning for health trend tracking.
- Early anomaly detection.

### Assignment lock

> **Fall detection → preventive care**

---

# 38. AmbuSens — IoT Healthcare Use Case

AmbuSens is the healthcare use case presented in Week 12.

It addresses problems around:

- Telemedicine.
- Remote healthcare.
- Emergency response.
- Real-time patient status monitoring.
- Digitized medical history.

---

# 39. AmbuSens Problem Definition and Scope

## Telemedicine and Remote Healthcare

### Problem

Physical presence is necessary.

### Solution

Wireless sensors.

---

## Emergency Response Time

### Problem

Systems may not be equipped to deal with complications.

### Solution

- Instant remote monitoring.
- Feedback from skilled medical professionals.

---

## Real-Time Patient Status Monitoring

### Problem

Lack of collaboration.

### Solution

Real-time monitoring.

---

## Digitized Medical History

### Problems

- Inconsistent records.
- Physical records vulnerable to wear and tear.
- Physical records vulnerable to loss.

### Solution

Consistent cloud-based medical history.

---

# 40. AmbuSens Physiological Parameters

The lecture identifies:

- **Electrocardiogram (ECG)**
- **Temperature**
- **Heart rate**
- **Galvanic Skin Response (GSR)**

### Memory

> **ECG + Temperature + Heart Rate + GSR**

---

# 41. AmbuSens WBAN

The AmbuSens development uses a:

**Single-hop Wireless Body Area Network (WBAN)**

### Communication protocol

**Bluetooth — IEEE 802.15.1**

### Other development elements

- Power management.
- Data-rate tuning.
- Calibration of data.
- Filtering.
- Noise removal.

### Exam trap

Do not confuse this Bluetooth standard with the IEEE 802.15.4 used in low-rate wireless sensor-network contexts earlier in the course.

For Week 12 AmbuSens:

> **WBAN → Bluetooth → IEEE 802.15.1**

---

# 42. AmbuSens Health-Cloud Framework

The lecture describes the health-cloud framework as:

- Privacy-aware.
- Scalable.

### Patient identity masking

Patient identity masking involves:

- Hashing.
- Reverse hashing of patient ID.

### Key idea

> **Privacy-aware framework → patient identity masking**

---

# 43. AmbuSens Web Interface

The lecture provides a web interface with:

- Paramedic portal.
- Doctor portal.
- Medical-history recording.
- Feedback mechanism.
- Sensor initialization.
- Data streaming.
- Data visualization tools.

### URL shown in lecture

`ambusens.iitkgp.ac.in`

### Exam note

The important concept is the functionality of the interface, not memorizing the URL unless the exam explicitly asks it.

---

# 44. AmbuSens Implementation

The lecture mentions an implementation demonstration with:

- AmbuSens in the hospital.
- Brief description of sensors.
- Ambulatory healthcare.

---

# 45. AmbuSens System Trials

The lecture presents:

- Hospital system trials.
- Ambulatory system trials.

---

# 46. AmbuSens Results

The lecture compares:

- ECG tracing from a manual system.
- Real-time ECG tracing from AmbuSens.

### Main idea

> AmbuSens supports real-time ECG monitoring as part of an IoT healthcare system.

---

# PART V — ACTIVITY MONITORING

# 47. Why Activity Monitoring?

Wearable sensors are increasingly popular for:

- Medical applications.
- Child-care.
- Elderly-care.
- Entertainment.
- Security.

These sensors help monitor physical activities of humans.

---

# 48. Importance in IoT

The lecture states that activity monitoring:

- Helps provide better quality of life.
- Helps safeguard humans.
- Provides information accurately and reliably.
- Provides continuous monitoring support.

### Core idea

> **Activity monitoring = continuous sensing of human physical behavior.**

---

# 49. Traditional Activity-Monitoring Architecture

The lecture presents a traditional architecture involving:

- Continuous monitoring.
- An analyzer.

The important exam concept is that sensor/activity data are collected continuously and then analyzed.

---

# 50. Advantages of Continuous Activity Monitoring

The lecture emphasizes:

- Daily observation of human behavior.
- Identification of repetitive activity patterns.
- Easy integration and fast equipping.
- Long-term monitoring.
- Use of handheld-device sensors.

### Sensors mentioned

- **Accelerometer**
- **Gyroscope**
- **GPS**
- Other sensors

### Assignment lock

> Continuous monitoring → daily behavior + repetitive patterns.

---

# 51. Important Human Activities

The lecture gives examples including:

## Actions

- Running.
- Jumping.

## Gestures

- Folding legs.
- Moving hand.

### Exam framing

If asked for examples of human activities/gestures, use the exact lecture examples.

---

# 52. Types of Activity-Monitoring Sensors

The lecture shows:

- **Camera**
- **Smartphone**
- **Activity tracker band**

### Important point

Activity monitoring is not restricted to a single sensor type.

---

# 53. Data Analysis Tools for Activity Monitoring

The lecture identifies three analysis approaches.

## Statistical

Used for:

- Sensor data.

## Machine Learning Based

Used for:

- Sensor data.

## Deep Learning Based

Used for:

- Sensor data.
- Images.
- Videos.

### Assignment lock

> **Deep learning → sensor data + images + videos**

---

# 54. In-Place Approach

## Definition

Activity-monitoring sensor data are processed **directly on the device**.

### Characteristics

- Processing happens on the device.
- Power intensive.
- No network connection is required for the processing task.

### Assignment lock

> **In-place = on-device processing**

---

# 55. Network-Based Approach

### Characteristics

- Larger and processing-intensive methods can be applied.
- Group-based analytics are possible.
- Lower power consumption.
- Average-to-good network connection is needed.

---

# 56. In-Place vs Network-Based

| In-place | Network-based |
|---|---|
| Processing on device | Processing through network-connected resources |
| Power intensive | Lower power consumption at device |
| No network required for processing | Average-to-good network connection |
| Suitable for local processing | Supports larger/processing-intensive methods |
| Local analytics | Group-based analytics possible |

### Fast exam mapping

If question says:

- **“directly on the device”** → In-place.
- **“larger processing-intensive methods”** → Network-based.
- **“group-based analytics”** → Network-based.
- **“no network connection required”** → In-place.

---

# 57. Smartphone Activity-Monitoring Demonstration

The demonstration uses three basic elements:

1. **Smartphone**
2. **Network**
3. **Remote server**

### Data flow

**Smartphone → Network → Remote server**

The smartphone generates sensor readings.

The network carries the readings.

The remote server receives and processes/visualizes the data.

---

# 58. Sensor Logged in the Demonstration

The specific sensor values logged are:

**Accelerometer values**

### Trap

Do not select:

- Soil moisture.
- Water level.
- Smart-grid phasor values.

---

# PART VI — HIGH-PRIORITY COMPARISONS

## 59. Qualitative vs Quantitative

| Feature | Qualitative | Quantitative |
|---|---|---|
| Data | Categorical | Numerical |
| Nature | Descriptive | Measured |
| Examples | Color, smell, taste | Volume, weight |
| Main emphasis | Quality | Quantity |

---

## 60. Complete vs Incomplete Statistical Model

| Complete | Incomplete |
|---|---|
| Variables = equations | Variables ≠ equations |

---

## 61. Correlation vs Regression

| Correlation | Regression |
|---|---|
| Investigates relationship | Estimates relationship |
| Pearson `r` measures strength | Uses dependent + independent variables |
| Two quantitative continuous variables | One dependent + one or more independent variables |
| Can indicate predictive relationship | Used for prediction/forecasting |

---

## 62. Range vs Variance vs Standard Deviation

| Measure | Key idea |
|---|---|
| Range | Maximum − minimum |
| Variance | Expected squared deviation from mean |
| Standard deviation | Amount of variation/dispersion |

---

## 63. AgriSens vs AmbuSens

| AgriSens | AmbuSens |
|---|---|
| Agriculture | Healthcare |
| Smart water management | Remote/real-time healthcare |
| Soil moisture + water level | ECG + temperature + heart rate + GSR |
| Automatic irrigation | Patient monitoring |
| Farmer-oriented control | Doctor/paramedic-oriented monitoring |
| Remote monitoring/control | Real-time health monitoring |

---

## 64. IoT Healthcare Layers

**Sensing → Aggregated → Processing → Cloud**

Remember:

- Sensors/RFID/WSN → Sensing.
- Smartphones/Tablets → Aggregated.
- Servers → Processing.
- Cloud → processed-data platform.

---

## 65. Activity Analysis Mapping

| Question wording | Answer |
|---|---|
| Categorical data | Qualitative |
| Numerical data | Quantitative |
| More than two populations | ANOVA |
| Strength of association | Pearson `r` |
| Prediction/forecasting | Regression |
| On-device processing | In-place |
| Large processing-intensive methods | Network-based |
| Sensor + images + videos | Deep learning |
| Smartphone demo sensor | Accelerometer |

---

# PART VII — EXAM TRAP BANK

## Trap 1: Qualitative vs Quantitative

**Wrong instinct:** categorical = quantitative.

**Correct:** categorical → **qualitative**.

---

## Trap 2: Complete model

**Correct:** variables = equations.

---

## Trap 3: ANOVA

The lecture's exam framing:

> **More than two populations/samples.**

---

## Trap 4: Pearson `r`

> **Strength of association**, not sample size or maximum value.

---

## Trap 5: AgriSens layers

Correct order:

> **Sensing & actuating → Processing/storage/service → Application**

---

## Trap 6: AgriSens remote servers

Remember:

- Repository → **GPRS**
- Web → remote data access
- Multi-user → **SMS + queries + control**

---

## Trap 7: Healthcare aggregated layer

> Smartphones/tablets → **Aggregated layer**

Not sensing layer and not cloud platform.

---

## Trap 8: Preventive care

> Fall detection → **preventive care**

---

## Trap 9: Deep learning

> Sensor data + images + videos

Not images only.

---

## Trap 10: In-place

> Processing directly on device.

Properties:

- Power intensive.
- No network needed for the processing task.

---

## Trap 11: Smartphone activity demo

Three elements:

> **Smartphone + Network + Remote server**

---

## Trap 12: Activity demo data

> **Accelerometer values**

---

## Trap 13: AmbuSens WBAN

> Single-hop WBAN using **Bluetooth / IEEE 802.15.1**

---

## Trap 14: AmbuSens privacy

> Patient identity masking uses hashing and reverse hashing of patient ID.

---

## Trap 15: AgriSens sensor node

> **Power management unit** is an explicitly tested component.

---

# PART VIII — MUST-MEMORIZE LIST

1. Qualitative → categorical data.
2. Quantitative → numerical data.
3. Complete statistical model → variables = equations.
4. Incomplete model → variables ≠ equations.
5. ANOVA → compare more than two populations/samples.
6. ANOVA → continuous response + categorical factor.
7. ANOVA properties → independence, normality, homogeneity.
8. TSS/SST → squared deviations from overall mean.
9. F-ratio ≈ 1 when null hypothesis is true in the lecture's stated framing.
10. Degrees of freedom → values free to vary.
11. Range = max − min.
12. Average absolute deviation → average absolute deviations from mean.
13. Variance → squared deviation.
14. Standard deviation → dispersion/variation.
15. Pearson `r` → strength of association.
16. Regression → dependent + independent variables; prediction/forecasting.
17. Statistical significance → difference not due to random chance, in lecture framing.
18. Larger randomized sample size → greater confidence.
19. Precision inversely related to standard error.
20. Limit of error = critical value × standard deviation of statistic.
21. AgriSens → more crop yield with less water.
22. AgriSens → automatic irrigation.
23. AgriSens → remote monitoring and controlling.
24. AgriSens layers → sensing/actuating → processing/storage/service → application.
25. AgriSens sensor node → power management unit.
26. Repository server → GPRS.
27. Multi-user server → SMS + farmer queries/control.
28. AgriSens sensors → water-level + EC-05 soil-moisture sensor.
29. AgriSens average PDR → 98.75–89.75%.
30. Healthcare layers → sensing → aggregated → processing → cloud.
31. Smartphones/tablets → aggregated layer.
32. Preventive care → fall detection, emergency detection, early anomaly detection.
33. AmbuSens parameters → ECG, temperature, heart rate, GSR.
34. AmbuSens WBAN → single-hop.
35. AmbuSens communication → Bluetooth / IEEE 802.15.1.
36. AmbuSens privacy → patient identity masking.
37. Identity masking → hashing + reverse hashing of patient ID.
38. Activity monitoring → continuous human-activity observation.
39. Important activity sensors → accelerometer, gyroscope, GPS.
40. Deep learning → sensor data + images + videos.
41. In-place → on-device, power intensive, no network needed for processing.
42. Network-based → larger processing, group analytics, lower device power, network required.
43. Smartphone demo → smartphone + network + remote server.
44. Demo logs → accelerometer values.

---

# PART IX — NUMBERS / TERMS / NAMES TO REMEMBER

| Item | Week 12 value / association |
|---|---|
| ANOVA | More than 2 populations/samples |
| Complete model | Variables = equations |
| Pearson `r` | Strength of association |
| AgriSens layers | 3 |
| IoT healthcare architecture | 4 layers |
| AmbuSens WBAN | Single hop |
| AmbuSens wireless protocol | Bluetooth / IEEE 802.15.1 |
| AgriSens remote repository link | GPRS |
| AgriSens farmer notification/control | SMS |
| AgriSens average PDR | 98.75–89.75% |
| Activity demo | Smartphone + network + remote server |
| Activity demo sensor | Accelerometer |

---

# PART X — 60-SECOND WEEK 12 RECALL

**Data analytics:** qualitative = categorical, quantitative = numerical. Statistical model = relationships among variables. Complete = variables equal equations. ANOVA = more than two populations/samples. TSS = squared deviations from overall mean. F-ratio ≈ 1 under the lecture's null-hypothesis framing. Dispersion = range, average absolute deviation, variance, SD. Pearson `r` = strength of association. Regression = dependent + independent variables and prediction. Precision increases as standard error decreases. Error limit = critical value × standard deviation of statistic.

**AgriSens:** more yield with less water; save water; automatic irrigation; dynamic crop-phase irrigation; remote monitoring/control. Three layers = sensing & actuating → processing/storage/service → application. Sensor node includes power management. Repository server uses GPRS; web server gives remote data access; multi-user server uses SMS and executes farmer queries/control. Water-level + EC-05 soil-moisture sensing. Average PDR = 98.75–89.75%.

**Healthcare:** four layers = sensing → aggregated → processing → cloud. Smartphones/tablets = aggregated layer. Remote healthcare, real-time monitoring, preventive care. Fall detection = preventive care. AmbuSens measures ECG, temperature, heart rate, GSR; uses single-hop WBAN with Bluetooth IEEE 802.15.1; privacy-aware health cloud uses identity masking.

**Activity monitoring:** wearable sensors support medical, child-care, elderly-care, entertainment and security. Continuous monitoring finds daily/repetitive patterns. Sensors include accelerometer, gyroscope, GPS. Statistical → sensor data; ML → sensor data; DL → sensor data + images + videos. In-place = on-device, power intensive, no network required. Network-based = larger processing/group analytics, lower device power, network required. Demo = smartphone + network + remote server; logs accelerometer values.

---

# PART XI — FINAL EXAM STRATEGY

## If you see a one-line definition

Match the keyword:

- **Categorical** → Qualitative.
- **Numerical** → Quantitative.
- **Variables = equations** → Complete model.
- **More than two groups** → ANOVA.
- **Strength of association** → Pearson `r`.
- **Dependent + independent variables** → Regression.
- **On device** → In-place.
- **Sensor + images + videos** → Deep learning.

## If you see AgriSens

Think:

**Water → soil moisture/water level → automatic irrigation → remote control → farmer**

Then recall:

- 3 layers.
- Power management unit.
- GPRS repository server.
- SMS multi-user server.
- PDR 98.75–89.75%.

## If you see healthcare

Think:

**Sensing → Aggregated → Processing → Cloud**

Then:

**Smartphone/tablet = Aggregated**

**Preventive care = fall detection / emergency / anomaly detection**

## If you see AmbuSens

Think:

**ECG + Temperature + Heart Rate + GSR**

**Single-hop WBAN**

**Bluetooth / IEEE 802.15.1**

**Privacy-aware cloud + identity masking**

## If you see activity monitoring

Think:

**Wearable sensors → continuous monitoring → patterns → analytics**

Then:

**In-place = device**

**Network-based = network**

**Demo = smartphone + network + remote server**

**Logged = accelerometer**

---

# PART XII — SOURCE COVERAGE NOTE

This Week 12 file is grounded in the uploaded:

1. **Assignment_12 (1).pdf**
   - All 15 assignment questions and their supplied correct answers/solutions.
2. **Week-12.pdf**
   - Data Handling and Analytics — Part II.
   - Case Study: Agriculture / AgriSens.
   - Case Study: Healthcare / AmbuSens.
   - Activity Monitoring — Part I and Part II.

No images are included in this Markdown study file.

