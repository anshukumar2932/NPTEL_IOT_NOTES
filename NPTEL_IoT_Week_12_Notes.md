# NPTEL Introduction to Internet of Things — Week 12 Exam Notes

## Assignment Priority + Complete Lecture Coverage

**Week:** 12  
**Exam type:** MCQ/MSQ  
**Assignment:** 15 questions, 15 marks  
**Lecture PDF:** 71 pages

> **Study rule:** Assignment questions are the highest-priority revision source. They come first. After them, all major lecture topics are covered so that questions outside the assignment are also prepared.

---

# 1. WEEK 12 ULTRA-QUICK REVISION

## Data Analytics
- **Qualitative analysis** → categorical/descriptive data.
- **Quantitative analysis** → numerical data.
- Statistical model → mathematical relationship between variables.
- Model represented as **(X, P)**:
  - X = possible observations
  - P = probability distributions on X.
- **Complete model** → number of variables = number of equations.
- ANOVA → compares datasets, especially **more than two populations/samples**.
- ANOVA assumptions → independence, normality, homogeneity.
- Pearson correlation coefficient **r** → strength of association between two quantitative continuous variables.
- Regression → dependent variable vs one or more independent variables.
- Statistical significance → difference is unlikely to be due to random chance.
- Precision → closeness of estimates from different samples.
- Standard error ↓ → precision ↑.
- Limit of error = **Critical value × Standard deviation of statistic**.
- Dispersion → range, average absolute deviation, variance, standard deviation.

## AgriSens
- Objective → **more crop yield with less water**.
- Also supports:
  - automatic irrigation,
  - dynamic irrigation treatments,
  - remote monitoring/control.
- 3 layers:
  1. Sensing & actuating
  2. Processing, storage & service
  3. Application
- Sensor node includes:
  - sensors/actuators,
  - processing & memory,
  - wireless communication,
  - **power management unit**.
- Remote server:
  - repository data server,
  - web server,
  - multi-user server.
- Multi-user server → sends field information to farmer by SMS and executes farmer queries/control messages.
- Important sensors:
  - water-level sensor,
  - EC-05 soil-moisture sensor.
- Average packet delivery ratio shown → **98.75–89.75%**.
- Noise factors shown → air flow, temperature, solar radiation, rain.

## IoT Healthcare
- 4 layers:
  1. Sensing
  2. Aggregated
  3. Processing
  4. Cloud platform
- Smartphones/tablets → **aggregated layer**.
- Remote healthcare → bring healthcare to patients using wireless IoT.
- Real-time monitoring → physiological sensors + gateways/cloud analytics + caregivers.
- Preventive care:
  - fall detection,
  - emergency detection/alerts,
  - early anomaly detection.
- AmbuSens physiological parameters:
  - ECG,
  - temperature,
  - heart rate,
  - GSR.
- AmbuSens WBAN:
  - single-hop wireless body area network,
  - Bluetooth / IEEE 802.15.1,
  - power management and data-rate tuning,
  - calibration,
  - filtering/noise removal.
- Health cloud → privacy-aware, patient identity masking using hashing/reverse hashing, scalable architecture.

## Activity Monitoring
- Wearable sensors → medical, child-care, elderly-care, entertainment, security.
- Continuous monitoring → daily behavior + repetitive activity patterns + long-term observation.
- Sensors:
  - accelerometer,
  - gyroscope,
  - GPS,
  - cameras,
  - smartphone,
  - activity tracker band.
- Deep learning → sensor data + images + videos.
- **In-place approach** → processing on device; power intensive; no network required.
- Network-based approach → larger processing methods, group analytics, lower device power; needs average-to-good connectivity.
- Smartphone demonstration:
  - smartphone,
  - network,
  - remote server.
- Logged sensor values → **accelerometer values**.

---

# 2. ASSIGNMENT-FIRST: ALL 15 QUESTIONS

## Q1. Which type of data analysis is used for categorical data?

**Answer: A — Qualitative analysis**

### Explanation
Qualitative analysis deals with data that is:
- categorical,
- descriptive,
- non-numerical.

Examples:
- color,
- smell,
- taste,
- interview text,
- field notes,
- audio/video observations.

Quantitative analysis is for numerical data.

### Trap
- Categorical → **Qualitative**
- Numerical → **Quantitative**

**Lecture:** Data Handling and Analytics – Part II, Slide 3.

---

## Q2. When is a statistical model classified as a complete model?

**Answer: A — When the number of variables equals the number of equations**

### Explanation
The lecture divides statistical models into:
- complete models,
- incomplete models.

**Complete:**
`Number of variables = Number of equations`

**Incomplete:**
`Number of variables ≠ Number of equations`

### Memory
**Complete = equal**

**Lecture:** Data Handling and Analytics – Part II, Slide 9.

---

## Q3. ANOVA is best applied when what is being compared?

**Answer: B — More than two populations or samples**

### Explanation
ANOVA = **Analysis of Variance**.

It is a parametric statistical technique used to compare datasets, especially when:
- more than two populations/samples are compared.

ANOVA needs:
- a continuous response variable,
- at least one categorical factor,
- two or more factor levels.

### Trap
Do not confuse ANOVA with:
- correlation,
- regression,
- single-observation comparison.

### Memory
`ANOVA → Compare >2 groups`

**Lecture:** Data Handling and Analytics – Part II, Slide 11.

---

## Q4. What does Pearson's correlation coefficient (r) measure?

**Answer: C — The strength of association between two variables**

### Explanation
Pearson's correlation:
- examines the relationship between two quantitative, continuous variables,
- produces coefficient **r**,
- indicates strength of association,
- can indicate a predictive relationship.

### Trap
Correlation does **not** by itself prove causation.

**Memory:** `Pearson r → strength of association`

**Lecture:** Data Handling and Analytics – Part II, Slide 18.

---

## Q5. What is a primary objective of AgriSens?

**Answer: D — Achieving more crop yield with less water**

### Explanation
AgriSens is a smart water-management system for agriculture.

Objectives:
- more yield with less water,
- save limited water resources,
- automatic irrigation,
- dynamic irrigation treatments during crop life,
- remote monitoring and control.

### Memory
`AgriSens → More yield + Less water`

**Lecture:** Agriculture Case Study, Slide 4.

---

## Q6. What are the three layers of the proposed AgriSens architecture?

**Answer: B**
1. Sensing and actuating layer
2. Processing, storage and service layer
3. Application layer

### Architecture
```text
Application Layer
        ↑
Processing, Storage & Service
        ↑
Sensing & Actuating
```

### Trap
Do not substitute generic OSI layers.

**Lecture:** Agriculture Case Study, Slide 5.

---

## Q7. Which component is included in the integrated AgriSens sensor-node design?

**Answer: B — Power management unit**

### Explanation
The sensor node contains:
- sensors,
- actuators,
- processing and memory unit,
- wireless communication unit,
- **power management unit**.

### Memory
`Sensor node = Sense + Actuate + Process + Communicate + Power`

**Lecture:** Agriculture Case Study, Slide 8.

---

## Q8. What is the function of the AgriSens multi-user server?

**Answer: C — It sends field information to the farmer's mobile phone using SMS and executes farmer queries/control messages.**

### Explanation
The remote-server design contains:
- repository data server,
- web server,
- multi-user server.

The **multi-user server**:
- sends field information to farmers using SMS,
- executes farmer queries,
- executes control messages.

### Trap
The multi-user server does not directly measure soil moisture.

**Lecture:** Agriculture Case Study, Slide 10.

---

## Q9. Which healthcare layer contains smartphones and tablets used as data aggregators?

**Answer: D — Aggregated layer**

### Healthcare architecture
```text
Sensing Layer
      ↓
Aggregated Layer
      ↓
Processing Layer
      ↓
Cloud Platform
```

### Layer mapping
- Sensing → sensors, RFIDs, WSN
- Aggregated → smartphones, tablets
- Processing → servers
- Cloud → processed data storage/access/analytics

### Memory
`Smartphone/Tablet = Aggregated Layer`

**Lecture:** Healthcare Case Study, Slide 3.

---

## Q10. Which is an example of preventive care enabled by IoT healthcare?

**Answer: A — Fall detection for senior citizens**

### Other preventive-care examples
- emergency-situation detection,
- alerts to family members,
- machine learning for health-trend tracking,
- early anomaly detection.

### Memory
`Preventive IoT healthcare → Detect before serious harm`

**Lecture:** Healthcare Case Study, Slide 8.

---

## Q11. What is an advantage of continuous activity monitoring?

**Answer: C — It enables daily observation of human behavior and repetitive activity patterns**

### Explanation
Continuous monitoring supports:
- daily behavior observation,
- repetitive-pattern detection,
- long-term monitoring,
- reliable activity recognition.

### Trap
Continuous monitoring does not mean:
- discard data,
- use only cameras,
- prohibit long-term observation.

**Lecture:** Activity Monitoring – Part I, Slide 5.

---

## Q12. What type of data can be analyzed using the deep-learning approach?

**Answer: A — Sensor data, images, and videos**

### Explanation
The lecture compares data-analysis approaches:
- statistical → sensor data,
- machine-learning based → sensor data,
- deep-learning based → sensor data + images + videos.

### Memory
`Deep Learning → Sensor + Image + Video`

**Lecture:** Activity Monitoring – Part I, Slide 8.

---

## Q13. What is processing activity-monitoring data directly on the device called?

**Answer: D — In-place approach**

### Explanation
In-place processing means:
- data is processed on the device itself.

Advantages:
- no network connection required for processing.

Disadvantage:
- power intensive.

### Compare
**In-place:**
- on device,
- power intensive,
- no network required.

**Network-based:**
- larger/processing-intensive methods,
- group analytics,
- lower device power,
- requires average-to-good connectivity.

**Lecture:** Activity Monitoring – Part I, Slide 9.

---

## Q14. What are the three basic elements in the smartphone-based activity-monitoring demonstration?

**Answer: C — A smartphone, a network, and a remote server**

### Flow
```text
Smartphone
    ↓
  Network
    ↓
Remote Server
    ↓
Processing / Visualization
```

**Lecture:** Activity Monitoring – Part II.

---

## Q15. Which sensor values are logged in the activity-monitoring demonstration?

**Answer: A — Accelerometer values**

### Explanation
The smartphone:
- generates accelerometer readings,
- transmits them through the network,
- sends them to a remote server,
- where the data are continuously logged.

### Memory
`Smartphone demo → Accelerometer`

**Lecture:** Activity Monitoring – Part II.

---

# 3. DATA ANALYTICS — COMPLETE LECTURE COVERAGE

## 3.1 What is Data Analytics?

Data analytics is the process of:
- examining datasets,
- drawing conclusions from the information they contain,
- using specialized systems/software when appropriate.

Applications include:
- business decision making,
- scientific model verification,
- scientific hypothesis testing.

### Core idea
```text
Raw Data
   ↓
Analysis
   ↓
Information / Patterns
   ↓
Conclusions
   ↓
Better Decisions
```

---

# 4. TYPES OF DATA ANALYSIS

## Qualitative Analysis

Deals with:
- categorical data,
- non-numerical descriptions,
- contextual information.

Sources:
- interviews,
- videos,
- audio recordings,
- field notes.

The data must often be:
- interpreted,
- grouped into themes.

### Three basic principles
The lecture summarizes qualitative analysis as:
1. Notice things
2. Collect things
3. Think about things

### Examples
- color,
- smell,
- taste,
- opinions,
- textual responses.

---

## Quantitative Analysis

Deals with:
- numerical data,
- measurements,
- mathematical/statistical relationships.

Includes:
- descriptive statistics,
- statistical models,
- data dispersion,
- analysis of variables,
- relationships between variables,
- regression,
- statistical significance,
- precision,
- error limits,
- contingency/correlation.

### Examples
- weight,
- volume,
- temperature,
- numerical sensor readings.

---

# 5. QUALITATIVE VS QUANTITATIVE

| Qualitative | Quantitative |
|---|---|
| Categorical | Numerical |
| Observed | Measured |
| Descriptions | Numbers |
| Quality emphasized | Quantity emphasized |
| Color, smell, taste | Volume, weight |

### Exam shortcut
**Categorical → Qualitative**  
**Numerical → Quantitative**

---

# 6. ADVANTAGES OF DATA ANALYTICS

Data analytics can:
- identify important/mission-critical trends,
- identify performance problems,
- support action,
- present data visually,
- improve decision speed,
- improve awareness of customer behavior,
- provide competitive advantage.

---

# 7. STATISTICAL MODELS

A statistical model:
- is a mathematical equation/relationship between variables,
- illustrates relationships among random variables.

The lecture represents a statistical model as:

**(X, P)**

where:
- **X** = set of all possible observations,
- **P** = set of probability distributions on X.

---

# 8. COMPLETE VS INCOMPLETE STATISTICAL MODEL

## Complete Model
Number of variables:
= number of equations.

## Incomplete Model
Number of variables:
≠ number of equations.

### One-line memory
**Complete = Equal**

---

# 9. STEPS TO BUILD A STATISTICAL MODEL

1. Data gathering
2. Descriptive methods
3. Thinking about predictors
4. Building the model
5. Interpreting results

### Memory
`Gather → Describe → Predictors → Build → Interpret`

---

# 10. ANOVA

ANOVA = **Analysis of Variance**

It is a:
- parametric statistical technique,
- used to compare datasets,
- especially useful for more than two populations/samples.

## Requirements
- continuous response variable,
- at least one categorical factor,
- factor has two or more levels,
- approximately normally distributed populations.

---

# 11. ANOVA ASSUMPTIONS

## Independence
- sample selected randomly,
- no systematic selection pattern.

## Normality
- distributions should be approximately normal.

## Homogeneity
- variance between groups should be approximately the same.

### Memory
**ANOVA → Independence + Normality + Homogeneity**

---

# 12. TYPES OF ANOVA

## One-way ANOVA
- one fixed factor,
- factor levels are set by investigator.

Examples:
- age,
- gender,
- location.

## Two-way ANOVA
- multiple factor variables,
- examines effects involving two factors.

## K-way ANOVA
- factor variables are **k**.

### Trap
Do not interpret "two-way" as "two samples"; it refers to factors.

---

# 13. TOTAL SUM OF SQUARES

TSS / SST:
- total sum of squares,
- sum of squared differences between each observation and the overall mean.

Conceptually:

**TSS = Σ(observation − overall mean)²**

### Memory
`TSS → Total deviation from overall mean, squared and summed`

---

# 14. F-RATIO

The F-ratio:
- compares variance between datasets/groups.

Lecture rule:
- approximately **1.0** when the null hypothesis is true,
- greater than **1.0** when the null hypothesis is false, as presented in the course.

### Exam caution
For the NPTEL course, remember the lecture's stated rule exactly.

---

# 15. DEGREES OF FREEDOM

Degrees of freedom represent:
- the number of values in the final calculation of a statistic that are free to vary.

### Memory
`df = independent/free information in a statistical calculation`

---

# 16. DATA DISPERSION

Dispersion measures how spread out data are.

A dispersion measure:
- is nonnegative,
- becomes zero when all observations are identical,
- increases as data become more diverse.

Measures:
1. Range
2. Average absolute deviation
3. Variance
4. Standard deviation

---

# 17. RANGE

**Range = Maximum − Minimum**

### Example
Data:
`2, 4, 7, 10`

Range:
`10 − 2 = 8`

### Memory
`Range = Max − Min`

---

# 18. AVERAGE ABSOLUTE DEVIATION

Average absolute deviation / mean absolute deviation:
- average of absolute deviations from the mean.

Conceptually:

**AAD = average(|x − mean|)**

---

# 19. VARIANCE

Variance:
- expectation of squared deviation of a random variable from its mean.

Conceptually:

**Variance = E[(X − μ)²]**

### Memory
`Variance → Squared deviations`

---

# 20. STANDARD DEVIATION

Standard deviation:
- measures the amount of variation/dispersion in data.

It is related to variance:

**SD = √Variance**

### Exam trap
Variance and standard deviation are related, but they are not identical.

---

# 21. CONTINGENCY TABLE

A contingency table:
- is a matrix/crosstab,
- displays multivariate frequency distributions,
- helps show the interrelation between variables.

### Memory
`Contingency table = Frequency relationship across categories`

---

# 22. CORRELATION

Correlation investigates relationships between:
- two quantitative,
- continuous variables.

## Pearson correlation coefficient
**r** measures:
- strength of association.

### Exam trap
Correlation:
- indicates association,
- may help indicate predictive relationship,
- does not automatically establish causation.

---

# 23. REGRESSION ANALYSIS

Regression:
- estimates relationships among variables.

It focuses on:
- dependent variable,
- one or more independent variables.

### Uses
- prediction,
- forecasting,
- understanding which independent variables relate to the dependent variable.

### Regression vs Correlation

| Correlation | Regression |
|---|---|
| Strength of association | Estimates relationship |
| Usually symmetric relationship | Has dependent + independent variables |
| Coefficient r | Regression function/model |
| Association | Prediction/forecasting |

### Memory
`Correlation → strength`  
`Regression → prediction/relationship model`

---

# 24. STATISTICAL SIGNIFICANCE

Statistical significance refers to the likelihood that:
- an observed difference is not merely due to random chance.

Two important variables:
1. Sample size
2. Effect size

### Sample size
Larger randomized samples generally:
- increase confidence in experimental results.

### Effect size
Represents:
- standardized mean difference between groups.

---

# 25. PRECISION

Precision:
- how close estimates from different samples are to one another.

## Standard error
Standard error measures precision.

Relationship:

**Smaller standard error → higher precision**

### Memory
`SE ↓ → Precision ↑`

---

# 26. LIMIT OF ERROR

Limits of error represent:
- maximum overestimate,
- maximum underestimate

from:
- sampling errors,
- non-sampling errors.

The lecture gives:

**Limit of Error = Critical Value × Standard Deviation of the Statistic**

### Critical value
Determines:
- tolerance level of error.

---

# 27. AGRISENS — SMART WATER MANAGEMENT

AgriSens is an IoT case study for:
- irrigated crops,
- smart water management.

## Main objective
**More yield with less water**

Other objectives:
- save limited water,
- automatic irrigation cycle,
- dynamic irrigation treatment according to crop phase,
- remote monitoring and control.

---

# 28. FUTURE OF IoT IN AGRICULTURE

The lecture identifies:
- soil moisture monitoring,
- water-level monitoring,
- automated irrigation,
- automated organic-waste recycling/vermicomposting,
- automated sowing,
- automated weeding.

### Memory
`Agriculture IoT → Sense → Decide → Irrigate/Automate`

---

# 29. AGRISENS ARCHITECTURE

Three layers:

## Layer 1 — Sensing and Actuating
- sensors,
- actuators,
- field measurements,
- irrigation control.

## Layer 2 — Processing, Storage and Service
- process collected information,
- store information,
- provide services.

## Layer 3 — Application
- user-facing agricultural applications,
- monitoring,
- control,
- decision support.

### Diagram
```text
        Application Layer
               ↑
 Processing / Storage / Service
               ↑
     Sensing & Actuating
```

The proposed three-layer architecture appears in the lecture's AgriSens diagram on **page 31**. fileciteturn55file0L609-L624

---

# 30. AGRISENS SENSOR DESIGN

The lecture presents integrated designs for:
- sensors,
- sensor node,
- remote server.

### Sensor examples
- designed water-level sensor,
- EC-05 soil-moisture sensor.

The sensor design diagrams are shown on **pages 33–35** of the lecture PDF. fileciteturn55file0L651-L696

---

# 31. AGRISENS SENSOR NODE

Integrated sensor-node components:
- sensors,
- actuators,
- processing unit,
- memory,
- wireless communication,
- power management unit.

### Conceptual block diagram

```text
Sensors ─┐
         ├→ Processing + Memory
Actuators┘          ↓
             Wireless Communication
                      ↓
              Remote Infrastructure

Power Management → supports node operation
```

### Assignment trap
If the options include:
- PMU,
- Hadoop Namenode,
- smart-grid MDMS,
- another unrelated IoT component,

choose **Power Management Unit**.

---

# 32. AGRISENS REMOTE SERVER

Three important server components:

## Repository Data Server
- communicates with deployed IoT gateway,
- uses **GPRS**.

## Web Server
- provides remote access to field data.

## Multi-User Server
- sends field information to farmers' mobile phones,
- uses **SMS**,
- executes farmer queries,
- executes control messages.

### Memory
`Repository → GPRS`  
`Web → Remote field-data access`  
`Multi-user → SMS + Queries + Control`

The remote-server design is shown on **page 36**. fileciteturn55file0L703-L719

---

# 33. AGRISENS IMPLEMENTATION

The lecture includes:
- field demonstration,
- website demonstration,
- project details from website.

Results include:
- soil-moisture behavior across crop phases,
- water-level behavior,
- packet-delivery performance.

---

# 34. AGRISENS RESULTS

The lecture presents crop phases:
1. Vegetative
2. Reproductive
3. Maturity

Measurements include:
- average soil moisture,
- average water level.

### Packet Delivery Ratio
Reported average PDR:
**98.75 – 89.75%**

### Noise factors
- air flow,
- temperature,
- solar radiation,
- rain.

These results appear on **pages 38–40**. fileciteturn55file0L742-L808

---

# 35. IoT HEALTHCARE

IoT healthcare is enabled by:
- advances in sensors,
- wireless connectivity,
- automated data collection,
- cloud analytics.

Benefits:
- collecting patient data over time,
- preventive care,
- understanding therapy effects,
- automatic data acquisition,
- reduced error,
- improved efficiency,
- reduced cost.

---

# 36. FOUR-LAYER IoT HEALTHCARE ARCHITECTURE

## 1. Sensing Layer
Contains:
- sensors,
- RFIDs,
- WSNs.

Examples:
- Google Glass,
- Fitbit tracker.

## 2. Aggregated Layer
Contains:
- data aggregators.

Examples:
- smartphones,
- tablets.

## 3. Processing Layer
Contains:
- servers that process information from aggregators.

## 4. Cloud Platform
- stores processed data,
- provides access to many users,
- supports analytics.

### Diagram
```text
Sensors / RFID / WSN
        ↓
Smartphone / Tablet
        ↓
Processing Servers
        ↓
Cloud Platform
```

The four-layer architecture is described on **page 44**. fileciteturn55file0L859-L877

---

# 37. REMOTE HEALTHCARE

Problem:
- many people lack easy access to effective healthcare,
- physical presence may be necessary.

IoT solution:
- wireless sensors,
- remote data capture,
- intelligent analysis,
- wireless sharing with healthcare professionals.

### Key idea
**Bring healthcare to patients rather than patients to healthcare.**

---

# 38. REAL-TIME HEALTHCARE MONITORING

IoT enables:
- non-invasive monitoring,
- comprehensive physiological data,
- gateway-based communication,
- cloud-based analytics/storage,
- wireless data delivery to caregivers.

Benefits:
- lower healthcare cost,
- faster awareness of patient status.

---

# 39. PREVENTIVE CARE

Examples:
- fall detection for seniors,
- emergency detection,
- family alerts,
- health-trend tracking,
- early anomaly detection.

### Memory
`Preventive care = detect early + alert early`

---

# 40. AMBUSENS

AmbuSens is the healthcare IoT case study.

It demonstrates:
- wearable/medical sensing,
- WBAN,
- cloud framework,
- healthcare web interface,
- hospital and ambulatory trials.

---

# 41. AMBUSENS PHYSIOLOGICAL PARAMETERS

The lecture specifically shows:
- **Electrocardiogram (ECG)**
- **Temperature**
- **Heart Rate**
- **Galvanic Skin Response (GSR)**

### Memory
`AmbuSens → ECG + Temperature + Heart Rate + GSR`

---

# 42. AMBUSENS WBAN

WBAN = **Wireless Body Area Network**

The lecture's AmbuSens development uses:
- single-hop wireless body area network,
- Bluetooth,
- IEEE **802.15.1**,
- power management,
- data-rate tuning,
- data calibration,
- filtering,
- noise removal.

### Trap
Do not confuse:
- Bluetooth / IEEE 802.15.1
with
- IEEE 802.15.4, which appears in other IoT/WSN contexts.

---

# 43. AMBUSENS HEALTH-CLOUD FRAMEWORK

The health-cloud framework is:
- privacy-aware,
- scalable.

### Patient identity masking
Uses:
- hashing,
- reverse hashing of patient ID.

### Memory
`AmbuSens Cloud → Privacy + Identity Masking + Scalability`

---

# 44. AMBUSENS WEB INTERFACE

Web interface features:
- paramedic portal,
- doctor portal,
- medical-history recording,
- feedback,
- sensor initialization,
- data streaming,
- data visualization.

The lecture identifies the web interface on **page 56**. fileciteturn56file0L71-L89

---

# 45. AMBUSENS IMPLEMENTATION / TRIALS

The lecture covers:
- hospital implementation,
- ambulatory healthcare,
- sensor descriptions,
- hospital trials,
- ambulatory trials.

The results include a comparison between:
- ECG tracing from manual system,
- real-time ECG tracing from AmbuSens.

---

# 46. ACTIVITY MONITORING

Wearable sensors are popular for:
- medical applications,
- child-care,
- elderly-care,
- entertainment,
- security.

They monitor:
- physical human activity.

IoT activity monitoring supports:
- better quality of life,
- safety,
- reliable information,
- continuous monitoring.

---

# 47. CONTINUOUS ACTIVITY MONITORING

Advantages:
- daily observation of human behavior,
- detection of repetitive activity patterns,
- easy integration,
- fast deployment/equipping,
- long-term monitoring.

### Sensors in handheld devices
- accelerometer,
- gyroscope,
- GPS,
- other sensors.

### Assignment connection
Q11 → daily behavior + repetitive patterns.

---

# 48. HUMAN ACTIVITIES

The lecture gives examples such as:
- running,
- jumping,
- folding legs,
- moving hand.

These can be recognized using:
- wearable sensors,
- smartphone sensors,
- cameras.

---

# 49. ACTIVITY-MONITORING SENSOR TYPES

The lecture shows:
- camera,
- smartphone,
- activity tracker band.

### Concept
Different sensing platforms provide different:
- data modalities,
- power requirements,
- processing requirements,
- privacy characteristics.

---

# 50. DATA-ANALYSIS TOOLS FOR ACTIVITY MONITORING

## Statistical
Used for:
- sensor data.

## Machine-Learning Based
Used for:
- sensor data.

## Deep-Learning Based
Used for:
- sensor data,
- images,
- videos.

### Assignment trap
If the question asks which approach can analyze **sensor + image + video**, choose:
**Deep learning based**.

---

# 51. IN-PLACE APPROACH

In-place means:
- activity data are processed **on the device**.

### Advantages
- no network connection required for the processing task,
- data can remain local.

### Disadvantage
- power intensive.

### Memory
`In-place = Device processing = Power intensive = No network required`

---

# 52. NETWORK-BASED APPROACH

Network-based processing:
- sends data for remote processing,
- allows larger and more processing-intensive methods,
- supports group-based analytics,
- reduces device-side power consumption.

Requirement:
- average-to-good network connection.

### Comparison

| In-place | Network-based |
|---|---|
| On device | Remote/network processing |
| Power intensive | Lower device power |
| No network required | Needs connectivity |
| Limited local resources | Larger processing methods |
| Local processing | Group analytics possible |

---

# 53. SMARTPHONE ACTIVITY-MONITORING DEMONSTRATION

The demonstration has three basic elements:

1. **Smartphone**
2. **Network**
3. **Remote server**

### Data path
```text
Smartphone Sensors
       ↓
   Network
       ↓
 Remote Server
       ↓
Processing / Logging / Visualization
```

### Specifically logged
**Accelerometer values**

---

# 54. HIGH-PRIORITY COMPARISONS

## Qualitative vs Quantitative

| Qualitative | Quantitative |
|---|---|
| Categorical | Numerical |
| Descriptive | Measured |
| Text/audio/video context | Numerical values |
| Themes | Statistical calculations |

---

## Correlation vs Regression

| Correlation | Regression |
|---|---|
| Strength of association | Estimates relationship |
| Two quantitative continuous variables | Dependent + independent variables |
| Pearson r | Regression function |
| Association | Prediction/forecasting |

---

## ANOVA vs Correlation

| ANOVA | Correlation |
|---|---|
| Compare datasets/groups | Examine relationship |
| >2 populations/samples emphasized | Two quantitative continuous variables |
| Parametric technique | Association measure |
| F-ratio | Pearson r |

---

## AgriSens vs AmbuSens

| AgriSens | AmbuSens |
|---|---|
| Agriculture | Healthcare |
| Water management | Patient monitoring |
| Soil moisture/water level | ECG/temp/HR/GSR |
| Irrigation control | WBAN + cloud |
| Farmer | Patient/paramedic/doctor |

---

## Healthcare architecture

| Layer | Main role | Example |
|---|---|---|
| Sensing | Capture data | Sensors, RFID, WSN |
| Aggregated | Aggregate | Smartphone, tablet |
| Processing | Process | Servers |
| Cloud | Store/access/analyze | Cloud platform |

---

# 55. MCQ/MSQ TRAPS

1. Categorical data → **Qualitative**.
2. Numerical data → **Quantitative**.
3. Complete statistical model → variables = equations.
4. ANOVA → compare **more than two** groups/populations.
5. ANOVA requires a continuous response variable.
6. ANOVA assumptions → independence, normality, homogeneity.
7. Pearson r → strength of association.
8. Correlation does not automatically imply causation.
9. Regression → dependent + independent variables.
10. Smaller standard error → higher precision.
11. AgriSens → more yield with less water.
12. AgriSens has **three layers**.
13. AgriSens sensor node → power management unit.
14. Multi-user server → SMS + farmer queries + control.
15. Healthcare smartphone/tablet → aggregated layer.
16. Preventive healthcare → fall detection.
17. Continuous monitoring → daily behavior + repetitive patterns.
18. Deep learning → sensor + image + video.
19. In-place → device-side processing.
20. In-place is power intensive.
21. Network-based → larger processing + group analytics.
22. Smartphone demonstration → smartphone + network + remote server.
23. Activity demo logs **accelerometer values**.
24. AmbuSens → ECG, temperature, heart rate, GSR.
25. AmbuSens WBAN → Bluetooth / IEEE 802.15.1.
26. AmbuSens cloud → privacy-aware.
27. Patient identity masking → hashing/reverse hashing.
28. Do not confuse Bluetooth IEEE 802.15.1 with IEEE 802.15.4.
29. Repository server → GPRS.
30. Web server → remote field-data access.
31. Multi-user server → SMS and control/query execution.

---

# 56. IMPORTANT FORMULAS / RELATIONSHIPS

## Range
**Range = Maximum − Minimum**

## Variance
**Variance = E[(X − μ)²]**

## Standard deviation
**SD = √Variance**

## Total Sum of Squares
**TSS = Σ(xᵢ − x̄)²**

## Limit of error
**Limit of Error = Critical Value × Standard Deviation of the Statistic**

## Precision
**Standard Error ↓ → Precision ↑**

---

# 57. IMPORTANT NUMBERS / IDENTIFIERS

| Item | Memorize |
|---|---|
| Week 12 lecture | **71 pages** |
| Assignment | **15 questions / 15 marks** |
| Complete model | **variables = equations** |
| ANOVA | **>2 populations/samples** |
| AgriSens layers | **3** |
| Healthcare layers | **4** |
| AgriSens PDR shown | **98.75–89.75%** |
| AmbuSens WBAN | **Single-hop** |
| AmbuSens protocol | **Bluetooth** |
| Bluetooth standard | **IEEE 802.15.1** |
| AmbuSens parameters | **ECG, temperature, heart rate, GSR** |
| Activity demo | **Accelerometer** |

---

# 58. VISUAL / DIAGRAM-BASED EXAM NOTES

## AgriSens architecture
Remember the three stacked layers:

```text
APPLICATION
     ↑
PROCESSING + STORAGE + SERVICE
     ↑
SENSING + ACTUATING
```

The actual proposed-architecture figure is on **lecture page 31**. fileciteturn55file0L609-L624

---

## AgriSens remote-server architecture

```text
Field IoT Gateway
       ↓ GPRS
Repository Data Server

Field Data
    ↓
Web Server → Remote Access

Field Data
    ↓
Multi-User Server
    ↓
SMS → Farmer
    ↑
Queries / Control
```

The lecture's remote-server slide is on **page 36**. fileciteturn55file0L703-L719

---

## Healthcare architecture

```text
Sensing
(Sensors/RFID/WSN)
        ↓
Aggregated
(Smartphone/Tablet)
        ↓
Processing
(Servers)
        ↓
Cloud Platform
```

---

## AmbuSens

```text
Physiological Sensors
        ↓
WBAN
(Bluetooth / 802.15.1)
        ↓
Gateway / Network
        ↓
Health Cloud
        ↓
Doctor / Paramedic Web Portal
```

---

## Activity monitoring

```text
Wearable / Smartphone
        ↓
Sensor Data
        ↓
 ┌───────────────┐
 │ In-place      │ → Device
 │ Network-based │ → Remote
 └───────────────┘
```

---

# 59. CODE/CONCEPT RECOGNITION DRILL

### If question says:
**“Categorical data”**
→ Qualitative analysis

### “Numerical data”
→ Quantitative analysis

### “Variables equal equations”
→ Complete statistical model

### “More than two groups”
→ ANOVA

### “Strength of association”
→ Pearson correlation coefficient

### “Dependent + independent variables”
→ Regression

### “More crop yield with less water”
→ AgriSens

### “Three AgriSens layers”
→ Sensing/Actuating + Processing/Storage/Service + Application

### “Power management unit”
→ AgriSens sensor node

### “SMS to farmer”
→ AgriSens multi-user server

### “Smartphone/tablet”
→ Healthcare aggregated layer

### “Fall detection”
→ Preventive healthcare

### “Sensor + image + video”
→ Deep learning

### “Process on device”
→ In-place

### “No network required”
→ In-place

### “Lower device power + group analytics”
→ Network-based approach

### “Smartphone + network + remote server”
→ Activity-monitoring demonstration

### “Accelerometer readings”
→ Activity-monitoring demonstration

### “ECG + temperature + heart rate + GSR”
→ AmbuSens

### “Bluetooth / 802.15.1”
→ AmbuSens WBAN

---

# 60. ONE-PAGE FINAL REVISION

## DATA ANALYTICS

```text
Categorical → Qualitative
Numerical   → Quantitative
```

### Statistical model
```text
Complete → variables = equations
Incomplete → variables ≠ equations
```

### ANOVA
```text
>2 groups
Continuous response
Categorical factor
Independence
Normality
Homogeneity
```

### Correlation
```text
Pearson r → strength of association
```

### Regression
```text
Dependent variable
        ↑
Independent variable(s)
→ Prediction / Forecasting
```

### Precision
```text
SE ↓ → Precision ↑
```

### Dispersion
```text
Range
AAD
Variance
Standard Deviation
```

---

## AGRISENS

```text
Goal:
More crop yield
       +
Less water
```

### Three layers
```text
Application
    ↑
Processing / Storage / Service
    ↑
Sensing / Actuating
```

### Sensor node
```text
Sensors + Actuators
Processing + Memory
Wireless Communication
Power Management
```

### Remote server
```text
Repository → GPRS
Web → Remote access
Multi-user → SMS + Queries + Control
```

---

## IoT HEALTHCARE

```text
Sensing
   ↓
Aggregated
   ↓
Processing
   ↓
Cloud
```

### Examples
```text
Sensing → Sensors/RFID/WSN
Aggregated → Smartphone/Tablet
Processing → Servers
Cloud → Storage/Analytics/Access
```

### Preventive
```text
Fall detection
Emergency detection
Early anomaly detection
```

### AmbuSens
```text
ECG
Temperature
Heart Rate
GSR

WBAN:
Bluetooth
IEEE 802.15.1
```

---

## ACTIVITY MONITORING

```text
Wearable Sensors
      ↓
Continuous Monitoring
      ↓
Daily Behavior + Repetitive Patterns
```

### Data analysis
```text
Statistical → Sensor data
ML → Sensor data
Deep Learning → Sensor + Image + Video
```

### Processing
```text
In-place:
On device
Power intensive
No network required

Network-based:
Remote
Larger processing
Group analytics
Lower device power
Connectivity required
```

### Demo
```text
Smartphone
   ↓
Network
   ↓
Remote Server
```

Logged:
**Accelerometer values**

---

# 61. LAST-MINUTE 15-ANSWER DRILL

1. Categorical data analysis?  
   **Qualitative**

2. Complete statistical model?  
   **Variables = equations**

3. ANOVA?  
   **Compare more than two populations/samples**

4. Pearson r?  
   **Strength of association**

5. AgriSens objective?  
   **More yield with less water**

6. AgriSens layers?  
   **Sensing/Actuating + Processing/Storage/Service + Application**

7. AgriSens sensor node component?  
   **Power management unit**

8. Multi-user server?  
   **SMS + farmer queries/control**

9. Healthcare smartphones/tablets?  
   **Aggregated layer**

10. Preventive healthcare example?  
    **Fall detection**

11. Continuous monitoring advantage?  
    **Daily behavior + repetitive patterns**

12. Deep-learning data?  
    **Sensor + image + video**

13. Device-side processing?  
    **In-place**

14. Smartphone activity demo?  
    **Smartphone + network + remote server**

15. Logged sensor values?  
    **Accelerometer**

---

# 62. FINAL MEMORY LIST

If you have only a few minutes, memorize these exact pairs:

- **Categorical → Qualitative**
- **Numerical → Quantitative**
- **Complete model → Variables = Equations**
- **ANOVA → >2 populations/samples**
- **ANOVA → Independence + Normality + Homogeneity**
- **Pearson r → Strength of association**
- **Regression → Dependent + Independent variables**
- **Small SE → High precision**
- **AgriSens → More yield + Less water**
- **AgriSens → 3 layers**
- **AgriSens sensor node → Power management**
- **Multi-user server → SMS + Queries + Control**
- **Healthcare → 4 layers**
- **Smartphone/Tablet → Aggregated layer**
- **Fall detection → Preventive care**
- **Continuous monitoring → Daily behavior + repetitive patterns**
- **Deep learning → Sensor + Image + Video**
- **In-place → Device-side + Power intensive + No network**
- **Network-based → Remote + Group analytics + Lower device power**
- **AmbuSens → ECG + Temperature + Heart Rate + GSR**
- **AmbuSens WBAN → Bluetooth / IEEE 802.15.1**
- **Health cloud → Privacy-aware + Identity masking**
- **Activity demo → Smartphone + Network + Remote Server**
- **Activity demo → Accelerometer**

---

# 63. SOURCE / LECTURE MAP

The Week 12 lecture PDF contains **71 pages** and is divided into:

- **Pages 1–25:** Data Handling and Analytics – Part II
- **Pages 27–41:** Case Study: Agriculture / AgriSens
- **Pages 42–61:** Case Study: Healthcare / AmbuSens
- **Pages 62–71:** Activity Monitoring – Part I & II

### Assignment-linked high-priority slides
- Data Handling and Analytics – Part II:
  - Slide 3 → Qualitative vs quantitative
  - Slide 9 → Complete statistical model
  - Slide 11 → ANOVA
  - Slide 18 → Pearson correlation
- Agriculture:
  - Slide 4 → AgriSens objective
  - Slide 5 → AgriSens architecture
  - Slide 8 → Sensor-node design
  - Slide 10 → Multi-user server
- Healthcare:
  - Slide 3 → Four-layer architecture
  - Slide 8 → Preventive care
- Activity Monitoring:
  - Slide 5 → Continuous monitoring
  - Slide 8 → Deep learning
  - Slide 9 → In-place approach
  - Part II → Smartphone/network/server demo and accelerometer logging

### Visuals worth revising
- AgriSens architecture diagram — lecture page 31.
- AgriSens sensor designs — pages 33–35.
- AgriSens remote-server design — page 36.
- AgriSens result graphs — pages 38–40.
- Healthcare four-layer architecture — page 44.
- AmbuSens physiological parameters — page 53.
- AmbuSens WBAN — page 54.
- AmbuSens cloud framework — page 55.
- AmbuSens web interface — page 56.
- AmbuSens system architecture/trials — pages 57–60.
- Activity-monitoring architecture/approaches — pages 65–70.

---

# 64. FINAL EXAM STRATEGY FOR WEEK 12

### First priority
Revise all 15 assignment answers until you can answer them without seeing the options.

### Second priority
Memorize the exact mappings:
- Qualitative ↔ categorical
- Quantitative ↔ numerical
- Complete ↔ variables = equations
- ANOVA ↔ >2 groups
- Pearson r ↔ association strength
- AgriSens ↔ yield/water
- Aggregated ↔ smartphone/tablet
- Deep learning ↔ sensor/image/video
- In-place ↔ device
- Accelerometer ↔ activity demo

### Third priority
Revise the diagrams:
- AgriSens 3-layer architecture
- AgriSens remote server
- Healthcare 4-layer architecture
- AmbuSens WBAN/cloud
- Activity-monitoring data path

### Final warning
The Week 12 assignment is strongly aligned with the lecture slides. Treat every assignment explanation as a high-probability exam concept, then use the remaining lecture notes to cover non-assignment questions.

---

# 65. FINAL MEMORY SENTENCE

**Week 12 = Data Analytics + Agriculture + Healthcare + Activity Monitoring:** categorical data is **qualitative**, numerical data is **quantitative**, a complete statistical model has **equal variables and equations**, **ANOVA compares more than two groups**, Pearson **r** measures association strength, and regression supports prediction; **AgriSens** aims for **more crop yield with less water** using three layers and a sensor node with **power management**; the healthcare architecture is **Sensing → Aggregated → Processing → Cloud**, with smartphones/tablets in the aggregated layer and **fall detection** as preventive care; **deep learning** handles sensor data, images and videos; **in-place** means device-side, power-intensive processing without requiring a network; **AmbuSens** uses ECG, temperature, heart rate and GSR with Bluetooth/IEEE 802.15.1 WBAN; and the smartphone activity demo sends **accelerometer values** through a network to a remote server.
