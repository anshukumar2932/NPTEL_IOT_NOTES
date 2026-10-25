# NPTEL IoT – Week 5 Exam Notes
## Assignment Priority + Complete Lecture Coverage

**Source:** NPTEL *Introduction to Internet of Things*, Week 5 lecture material + Week 5 Assignment  
**Exam style:** MCQ/MSQ; the uploaded assignment contains **15 questions for 15 marks**.

> **Study rule for this file:** Learn the assignment section first. Then study the complete lecture coverage. The assignment questions are the highest-priority revision points, but all lecture topics are included because exam questions can come from outside the assignment.

---

# 1. WEEK 5 – ULTRA-QUICK REVISION

## Must memorize first

1. **Interoperability** = systems/products with understood interfaces can work with other systems/products without restrictions; they can communicate meaningfully and exchange data/services.
2. IoT interoperability is needed because of **heterogeneity** in protocols, hardware, operating systems, databases, data representations, control models, and syntactic/semantic interpretations.
3. Two major types emphasized:
   - **User interoperability** – interoperability problem between a user and a device.
   - **Device interoperability** – interoperability problem between two different devices.
4. **Syntactic interoperability** → message **format**.
5. **Semantic interoperability** → message **meaning**.
6. Device discovery can use **EPC, UPC, URI, IP addresses/IPv6**.
7. Device classification examples: **UNSPSC** and **eCl@ss**.
8. **UMB = Universal Middleware Bridge**.
9. UMB has:
   - **UMB-C (UMB Core)** → routing
   - **UMB-A (UMB Adaptor)** → maps local middleware/device information to global metadata
10. **UDT = Universal Device Template**.
11. UDT contains **Global Device ID, Global Function ID, Global Action ID, Global Event ID, Global Parameters**.
12. Arduino is an **open-source programmable board + software/IDE**.
13. Arduino UNO:
   - Operating voltage = **5 V**
   - Clock = **16 MHz**
   - Digital I/O = **14**
   - Analog inputs = **6**
   - PWM = **6**
   - UART = **1**
   - USB interface via **ATmega16U2**
14. Arduino IDE program = **Sketch**.
15. Arduino sketch has **setup()** and **loop()**.
16. `pinMode(pin, mode)` → configure a pin as input/output.
17. `digitalWrite()` → write HIGH/LOW to a digital pin.
18. `analogRead()` → read voltage from an analog input pin.
19. `delay()` takes **milliseconds**.
20. Array indexing starts at **0**.
21. `random()` → pseudo-random number.
22. `attachInterrupt(digitalPinToInterrupt(pin), ISR, mode)` → attach an interrupt service routine.
23. DHT sensor measures **temperature + humidity**.
24. DHT pins (left to right in the lecture):
   - Pin 1 → 3.3V–5V power
   - Pin 2 → Data
   - Pin 3 → Null
   - Pin 4 → Ground
25. DHT library functions:
   - `dht.readHumidity()`
   - `dht.readTemperature()`
26. `delay(2000)` = **2000 ms = 2 s**.
27. Actuator → mechanical/electro-mechanical device that converts energy into motion.
28. Motor actuator examples: **servo, stepper, hydraulic motor, solenoid, relay, AC motor**.
29. Servo motor → **high precision**, controlled rotary motion, shown as **0° to 180°** in the lecture.
30. Servo has 3 wires in the lecture:
   - Black/dark → Ground
   - Red → Power
   - Yellow → Signal
31. Servo code uses `#include <Servo.h>`, creates a Servo object, then **attach()** before using `write()`.
32. `Servo.write(angle)` sends the degree value for the servo position.
33. Assignment traffic-control sequence: **Green → Yellow → Red**.

---

# 2. ASSIGNMENT-FIRST: ALL 15 QUESTIONS

The uploaded Week 5 Assignment has 15 MCQ/True-False questions and gives the correct answers. These are the first things to revise before the lecture notes.

## Q1. What does interoperability allow IoT devices to do?

**Answer: A — Communicate and exchange data**

### Why?
Interoperability enables different IoT devices and systems to communicate and exchange data.

### Exam trap
- It does **not** mean devices must work offline.
- It does **not** force all devices to use only one protocol.
- It does **not** mean disabling other devices.

**Memory:** Interoperability → **communication + data/service exchange**.

---

## Q2. Syntactic interoperability deals with:

**Answer: A — Message format**

### Why?
Syntactic interoperability concerns whether the format of exchanged messages is understandable/executable between the communicating parties.

### Exam trap
Do not confuse:
- **Syntax → format**
- **Semantics → meaning**

**Memory:** `Syntax = structure/format`, `Semantics = meaning`.

---

## Q3. What does UMB stand for?

**Answer: A — Universal Middleware Bridge**

### Why?
UMB is the solution discussed for device interoperability across heterogeneous home-network middleware.

### High-priority detail
UMB creates compatibility among heterogeneous middleware environments and uses virtual mappings among physical devices.

**Memory:** `UMB → Universal Middleware Bridge`.

---

## Q4. What is the operating voltage of Arduino UNO?

**Answer: B — 5 V**

### Why?
The Week 5 lecture lists Arduino UNO operating voltage as **5 V**.

### UNO numbers to memorize
| Feature | Value |
|---|---:|
| Operating voltage | **5 V** |
| Clock speed | **16 MHz** |
| Digital I/O | **14** |
| Analog input | **6** |
| PWM | **6** |
| UART | **1** |
| Computer interface | **USB via ATmega16U2** |

---

## Q5. What is a program written in the Arduino IDE called?

**Answer: B — Sketch**

### Why?
A program coded in the Arduino IDE is called a **sketch**.

### Sketch structure
- `setup()` → initialization
- `loop()` → repeatedly executes the specified task

**Memory:** Arduino program = **Sketch**.

---

## Q6. Which interface is mainly used to connect an Arduino UNO to a computer?

**Answer: B — USB**

### Why?
The lecture shows USB as the computer/board interface. The USB connection is also used during development for programming and power.

### Exam trap
Do not confuse the USB interface with Arduino's digital/analog I/O pins.

---

## Q7. What is the conventional starting index of an array in Arduino programming?

**Answer: B — 0**

### Why?
Arduino arrays follow the C/C++ convention of **zero-based indexing**.

Example:
```text
int arre[5];
indices = 0, 1, 2, 3, 4
```

### Trap
First element is at index **0**, not 1.

---

## Q8. Which Arduino function generates a pseudo-random number within a specified range?

**Answer: A — `random()`**

### Related functions
- `random(maxi)` → lecture states range **[0, maxi]**
- `random(mini, maxi)` → lecture states range **[mini, maxi]**
- `randomSeed(v)` → resets the pseudo-random generator using seed `v`

### Trap
- `pinMode()` → pin configuration
- `digitalWrite()` → digital output
- `attachInterrupt()` → interrupt setup

---

## Q9. In the traffic-control example, which LED is switched ON first to represent GO?

**Answer: C — Green LED**

### Sequence
**Green → Yellow → Red**

From the lecture:
1. Green HIGH → `"Green LED: ON, GO"`
2. After delay → Green LOW, Yellow HIGH → WAIT
3. After delay → Yellow LOW, Red HIGH → STOP
4. Red LOW → All OFF

### Timing
Each color remains on for **5 seconds** in the `traffic()` function.

The loop then waits **10 seconds** before calling `traffic()` again.

---

## Q10. Which quantities are measured by a DHT sensor?

**Answer: A — Temperature and humidity**

### Why?
The DHT sensor is the **Digital Humidity and Temperature** sensor.

### Arduino library calls
```text
dht.readHumidity()
dht.readTemperature()
```

### Trap
DHT is not a distance, speed, light, sound, pressure, or altitude sensor in this lecture.

---

## Q11. What does a sensor convert a physical quantity into?

**Answer: D — An electrical signal**

### Why?
The lecture defines sensors as electronic elements that convert physical quantities/measurements into **electrical signals**.

Sensors can be:
- **Analog**
- **Digital**

---

## Q12. In the DHT sensor sketch, `delay(2000)` causes successive readings after approximately:

**Answer: C — 2 seconds**

### Conversion
```text
2000 milliseconds = 2 seconds
```

### Exam trap
`delay()` uses **milliseconds**, not seconds.

---

## Q13. Statement: A servo motor is a low-precision motor used only for linear motion.

**Answer: B — False**

### Correct concept
The lecture describes a servo motor as:
- **High precision**
- Produces **rotary motion**
- Shown operating from **0° to 180°**

---

## Q14. Which device provides controlled rotary motion?

**Answer: D — Servo motor**

### Why?
Servo is a motor actuator used for precise/controlled rotary motion.

### Do not confuse
- Ultrasonic sensor → sensing
- DHT → sensing temperature/humidity
- PIR → sensing
- Servo → **actuation**

---

## Q15. Statement: A stepper motor is a type of actuator.

**Answer: A — True**

### Why?
The lecture lists stepper motor among motor actuators.

Other listed examples:
- Servo motor
- Hydraulic motor
- Solenoid
- Relay
- AC motor

---

# 3. INTEROPERABILITY IN IoT

## 3.1 Current challenges in IoT

The lecture identifies:

### 1. Large-scale cooperation
Millions of distributed devices may need cooperation and coordination over the Internet.

### 2. Global heterogeneity
IoT contains heterogeneous devices and heterogeneous subnets.

### 3. Unknown IoT device configuration
IoT devices may come from unknown owners and have different configuration modes.

### 4. Semantic conflicts
Different processing logics can be applied to the same networked IoT devices/applications.

**Exam idea:** These challenges motivate interoperability.

---

# 4. WHAT IS INTEROPERABILITY?

The lecture defines interoperability as a characteristic of a product/system whose interfaces are completely understood so it can work with other products/systems, present or future, without restrictions.

Core outcomes:
- **Communicate meaningfully**
- **Exchange data or services**

### Why it matters in IoT
Interoperability helps IoT objectives such as:
- Physical objects interacting with other physical objects
- Information sharing
- Devices communicating from anywhere/anytime
- M2M communication
- D2D communication
- D2M communication
- Seamless device integration into an IoT network

---

# 5. WHY INTEROPERABILITY IS REQUIRED

The lecture emphasizes **heterogeneity**.

## Communication-protocol heterogeneity
Examples:
- ZigBee (IEEE 802.15.4)
- Bluetooth (IEEE 802.15.1)
- GPRS
- 6LoWPAN
- Wi-Fi (IEEE 802.11)

## Wired-protocol heterogeneity
Examples:
- Ethernet (IEEE 802.3)
- Higher-layer LAN protocols (IEEE 802.1)

## Programming-language heterogeneity
Examples:
- JavaScript
- Java
- C
- C++
- Visual Basic
- PHP
- Python

## Hardware heterogeneity
Examples mentioned:
- Crossbow
- NI

## Operating-system heterogeneity
Sensor-node examples:
- TinyOS
- SOS
- Mantis OS
- RETOS
- Vendor-specific OS

PC examples:
- Windows
- Mac
- Unix
- Ubuntu

## Database heterogeneity
Examples:
- DB2
- MySQL
- Oracle
- PostgreSQL
- SQLite
- SQL Server
- Sybase

## Other heterogeneity
- Different data representations
- Different control models
- Syntactic interpretations
- Semantic interpretations

---

# 6. TYPES OF INTEROPERABILITY

## 6.1 User Interoperability

**Problem between a user and a device.**

The lecture's CCTV example:
- Device A is in Delhi.
- Device B is in Tokyo.
- A, B, and user U use different languages.
- User U wants real-time CCTV service from both devices.

Problems:
- User does not know devices A and B.
- Devices differ in syntactic and semantic notions.
- CCTV device discovery becomes difficult.
- User cannot understand the services provided by A and B.
- A and B do not mutually understand each other.

### Problems to solve
1. Device identification and categorization for discovery
2. Syntactic interoperability for device interaction
3. Semantic interoperability for device interaction

---

# 7. DEVICE IDENTIFICATION AND CATEGORIZATION

## Unique-address solutions mentioned
- **EPC — Electronic Product Codes**
- **UPC — Universal Product Code**
- **URI — Uniform Resource Identifier**
- **IP addresses**
  - IPv6 is specifically mentioned

## Device classification solutions
### UNSPSC
**United Nations Standard Products and Services Code**

The lecture describes it as an open, global, multi-sector standard for efficient, accurate, flexible classification of products and services.

### eCl@ss
Standard for classification and clear description of cross-industry products.

### Exam distinction
- **EPC / UPC / URI / IP** → identification/addressing
- **UNSPSC / eCl@ss** → classification/categorization

---

# 8. SYNTACTIC INTEROPERABILITY

## Meaning
Interoperability in terms of **message formats**.

The lecture explains:
- A device-to-user message format should be understandable by the user's computer.
- A user-to-device message format should be executable by the device.

### Popular approaches
- Service-Oriented Computing (SOC)-based architecture
- Web services
- RESTful web services
- Open standards such as:
  - IEEE 802.15.4
  - IEEE 802.15.1
  - WirelessHART
- Closed protocols such as:
  - Z-Wave

The lecture explicitly notes that these standards/protocols are **incompatible with each other**, motivating interoperability mechanisms.

---

# 9. MIDDLEWARE FOR SYNTACTIC INTEROPERABILITY

## Middleware technology

Middleware acts as a **software bridge**.

Lecture points:
- Dynamically maps physical devices with different domains.
- Based on the map, devices can be discovered and controlled remotely.

## Cross-context syntactic interoperability
Uses:
- Collaborative concept exchange
- XML syntax

### Memory
**Syntactic = format**, and middleware can bridge different message/device environments.

---

# 10. SEMANTIC INTEROPERABILITY

## Meaning
Interoperability in terms of **message meaning**.

The device should understand the meaning of a user's instruction, and the user should understand the meaning of a device's response.

### Key distinction

| Type | Main concern |
|---|---|
| Syntactic interoperability | **Message format** |
| Semantic interoperability | **Message meaning** |

---

# 11. SEMANTIC INTEROPERABILITY APPROACHES

## 11.1 Ontology

Examples:
- Device ontology
- Physical-domain ontology
- Estimation ontology

### Important limitation
The lecture explicitly states:

> **Ontology-based solution is limited to the defined domain/context.**

This is a strong MCQ/statement trap.

---

## 11.2 Collaborative conceptualization theory

The lecture uses the term **cosign**.

A cosign of an object is represented as:

```text
cosign of an object = (A, B, C, D)
```

Where:
- **A** = cosign internal identifier
- **B** = natural language
- **C** = context of A
- **D** = definition of the object

### CCTV example
The lecture gives a CCTV cosign containing:
- internal identifier
- English language
- CCTV context
- definition including camera type, communication, and horizontal resolution

### Important point
This approach is presented as applicable to **different domains/contexts**.

---

# 12. DEVICE INTEROPERABILITY

## Universal Middleware Bridge (UMB)

The lecture presents **UMB** as a solution for device interoperability.

### What UMB does
- Solves seamless interoperability problems caused by heterogeneous home-network middleware.
- Creates virtual maps among physical devices of different middleware home networks.
- Creates compatibility among these middleware environments.

Middleware examples shown:
- HAVI
- Jini
- LonWorks
- UPnP

---

# 13. UMB ARCHITECTURE

UMB consists of:

1. **UMB Core (UMB-C)**
2. **UMB Adaptor (UMB-A)**

---

## 13.1 UMB Adaptor (UMB-A)

Main role:
- Converts physical devices into virtually abstracted devices described by a **Universal Device Template (UDT)**.
- Translates local middleware messages into global metadata messages.

### UDT contains
- Global Device ID
- Global Function ID
- Global Action ID
- Global Event ID
- Global Parameters

### Memory
**UMB-A = adaptor/translation/mapping side.**

---

## 13.2 UMB Core (UMB-C)

Main role:
- Routes the universal metadata message to its destination or another UMB adaptor.
- Uses the **Middleware Routing Table (MRT)**.

### Memory
**UMB-C = routing.**

### Very common trap
Do not swap:
- UMB-A → translation/abstraction
- UMB-C → routing

---

# 14. UMB DEVICE FLOW

## When a new device is plugged in

The lecture's diagram shows a sequence involving:
1. Detection & configuration
2. Creation of a virtual device
3. Device online status/device ID reporting
4. Notification of online status/device ID
5. Creation of VDP

The exact diagram should be understood as a flow rather than memorized as isolated words.

## When a device is controlled/monitored

The diagram shows:
1. Local control/monitoring message
2. Conversion to UMB message
3. Query/action request
4. UMB-to-local message conversion and local control/monitoring
5. Local message
6. Query/action response
7. Local message

---

# 15. ARDUINO PROGRAMMING – PART I

## 15.1 Features of Arduino

The lecture describes Arduino as:
- Open-source electronic programmable board (microcontroller)
- Open-source software/IDE
- Accepts analog and digital signals as input
- Produces desired output
- Does not require extra hardware to load a program into the controller board

---

# 16. TYPES OF ARDUINO BOARDS

The lecture groups boards by microcontroller family:

- **ATMEGA328**
- **ATMEGA32u4**
- **ATMEGA2560**
- **AT91SAM3X8E**

---

# 17. ARDUINO UNO – IMPORTANT NUMBERS

| Feature | Lecture value |
|---|---:|
| Operating voltage | **5 V** |
| Clock speed | **16 MHz** |
| Digital I/O | **14** |
| Analog input | **6** |
| PWM | **6** |
| UART | **1** |
| Interface | **USB via ATmega16U2** |

### Board details
The lecture identifies:
- USB or power barrel-jack power supply
- Voltage regulator
- LED power indicator
- TX/RX LED indicators
- Output power/GND
- Analog input pins
- Digital I/O pins

---

# 18. ARDUINO IDE

Arduino IDE:
- Is open-source software for programming the Arduino controller.
- Is based on variations of C/C++.
- Can be installed on a PC.

## Setup
1. Connect board to PC using USB.
2. Launch Arduino IDE.
3. Select board type.
4. Select port.

Menu path shown:
```text
TOOLS → BOARD → select board
TOOLS → PORT → select port
```

---

# 19. ARDUINO IDE OVERVIEW

### Sketch
A program coded in Arduino IDE is called a **Sketch**.

### File operations
- File → New → new sketch
- File → Open → existing sketch
- File → Examples → ready-to-use example programs

### Main IDE operations
- **Verify** → checks code for compilation errors
- **Upload** → uploads final code to controller board
- **New** → creates a blank sketch with basic structure
- **Open** → opens an existing sketch
- **Save** → saves current sketch
- **Serial Monitor** → opens serial console and displays printed data

---

# 20. SKETCH STRUCTURE

A sketch has two main parts:

```cpp
void setup() {
    // initialization
}

void loop() {
    // repeated task
}
```

## setup()
- Starting point for initialization.
- Comparable to `main()` in C/C++ in the lecture's explanation.
- Initialize I/O variables and pin modes here.

## loop()
- Repeatedly executes the specified task.

### Exam trap
Do not say `loop()` runs only once. It is the repeating part.

---

# 21. SUPPORTED DATA TYPES

The lecture lists:
- `void`
- `int`
- `boolean`
- `byte`
- `word`
- `float`
- `array`
- `String-object`
- `long`
- `char`
- `unsigned char`
- `unsigned int`
- `unsigned long`
- `double`
- String/character-array representation
- `short`

---

# 22. BASIC ARDUINO I/O FUNCTIONS

## `pinMode()`
Configures an Arduino pin as input or output.

```cpp
pinMode(pin, mode);
```

Where:
- `pin` = pin number
- `mode` = `INPUT` or `OUTPUT`

## `digitalWrite()`
Writes:
- `HIGH`
- `LOW`

to a digital pin.

## `analogRead()`
Reads the voltage applied to an analog input pin.

## Character functions
The lecture lists:
- `isdigit()`
- `isalpha()`
- `isalnum()`
- `isxdigit()`
- `islower()`
- `isupper()`
- `isspace()`

These return **1 (true)** or **0 (false)**.

## `delay()`
Provides a specified delay.

**Unit = milliseconds.**

Example:
```text
delay(1000) = 1000 ms = 1 second
delay(2000) = 2000 ms = 2 seconds
```

---

# 23. BLINKING LED EXAMPLE

## Hardware listed
- Arduino controller board
- USB connector
- Breadboard
- LED
- **1.4 kΩ resistor**
- Connecting wires
- Arduino IDE

## Connection
The lecture connects:
- LED positive terminal → **digital pin 12**
- LED negative terminal → **GND**

## Code

```cpp
void setup() {
    pinMode(12, OUTPUT);
}

void loop() {
    digitalWrite(12, HIGH);
    delay(1000);
    digitalWrite(12, LOW);
    delay(1000);
}
```

### What happens?
- Pin 12 HIGH → LED ON
- Wait 1 second
- Pin 12 LOW → LED OFF
- Wait 1 second
- Repeat

### Exam traps
- Pin used in the lecture example = **12**
- Delay = **1000 ms**
- `pinMode()` belongs in `setup()`
- Repeating behavior belongs in `loop()`

---

# 24. ARDUINO PROGRAMMING – PART II

## Topics covered
- Operators
- Control statements
- Loops
- Arrays
- Strings
- Math library
- Random number generation
- Interrupts
- Traffic-control example

---

# 25. OPERATORS

## Arithmetic
```text
=  +  -  *  /  %
```

## Comparison
```text
==  !=  <  >  <=  >=
```

## Boolean
```text
&&  ||  !
```

## Bitwise
```text
&  |  ^  ~  <<  >>
```

## Compound
```text
++  --  +=  -=  *=  /=  %=  |=  &=
```

### Trap
`=` is assignment; `==` is comparison.

---

# 26. CONTROL STATEMENTS

## If
```cpp
if (condition) {
    // statements
}
```

## If–else
```cpp
if (condition) {
    // true
}
else {
    // false
}
```

## If–elseif–else
Used for multiple conditions.

## Switch-case
```cpp
switch(choice) {
    case opt1:
        statement_1;
        break;
    case opt2:
        statement_2;
        break;
    default:
        statement_default;
        break;
}
```

### Trap
The lecture's switch example uses `break` after cases.

---

# 27. CONDITIONAL OPERATOR

Form:

```cpp
Val = (condition) ? (Statement1) : (Statement2);
```

Meaning:
- If condition is true → choose Statement1
- Otherwise → choose Statement2

---

# 28. LOOPS

## For loop
```cpp
for (initialization; condition; increment) {
    // statement
}
```

## While loop
```cpp
while (condition) {
    // statement
}
```

## Do-while
```cpp
do {
    // statement
} while (condition);
```

### Key difference
`do-while` executes the body before checking the condition.

## Nested loop
A loop inside another loop.

## Infinite loop
Condition remains true, so the loop never terminates.

---

# 29. ARRAYS

Definition from the lecture:
A collection of elements having a **homogeneous datatype** stored in adjacent memory locations.

## Index
Conventional starting index = **0**.

## Declaration
```cpp
<Datatype> array_name[size];
```

Example:
```cpp
int arre[5];
```

## Initialization
```cpp
int arre[] = {0,1,2,3,4};
```

or

```cpp
int arre[5] = {0,1,2};
```

## Multidimensional array
```cpp
<Datatype> array_name[n1][n2][n3]...;
```

Example:
```cpp
int arre[row][col][height];
```

### Exam trap
Array index starts at **0**.

---

# 30. STRINGS

The lecture describes a string as an **array of characters with NULL termination**.

## Character-array form
```cpp
char str[] = "ABCD";
```

## String object
```cpp
String str = "ABC";
```

## String functions shown
### `ToUpperCase()`
Converts characters to uppercase.

### `replace(str1, str2)`
If `str1` occurs as a substring, it is replaced by `str2`.

### `length()`
Returns string length **without considering NULL**.

---

# 31. MATH LIBRARY

The lecture states that `MATH.h` is needed for mathematical functions/constants.

Functions listed:

```text
cos(double radian)
sin(double radian)
tan(double radian)
fabs(double val)
fmod(double val1, double val2)
exp(double val)
log(double val)
log10(double val)
square(double val)
pow(double base, double power)
```

### Exam trap
The lecture explicitly lists `square(double val)`; memorize it as presented in the source.

---

# 32. RANDOM NUMBER

## `randomSeed(v)`
Resets the pseudo-random number generator using seed `v`.

## `random(maxi)`
Lecture states it gives a random number in:
```text
[0, maxi]
```

## `random(mini, maxi)`
Lecture states it gives a random number in:
```text
[mini, maxi]
```

### Assignment priority
If the question asks which function generates pseudo-random values → **`random()`**.

---

# 33. INTERRUPTS

An interrupt is described as an external signal for which the system blocks the current running process to process that signal.

## Types
- Hardware interrupt
- Software interrupt

## `digitalPinToInterrupt(pin)`
Converts/maps an actual digital pin to the specific interrupt number.

## `attachInterrupt()`
Lecture form:

```cpp
attachInterrupt(digitalPinToInterrupt(pin), ISR, mode);
```

Where **ISR = Interrupt Service Routine**.

### Exam trap
`attachInterrupt()` is for interrupts, not random numbers or ordinary digital output.

---

# 34. TRAFFIC CONTROL SYSTEM

## Requirements
- Arduino board
- 3 different-color LEDs
- **330 Ω resistors**
- Jumper wires

## Connections
- Positive terminals → assigned digital output pins
- Negative terminals → ground

## Pin variables shown
```cpp
int r = 2;
int g = 3;
int y = 4;
```

So:
- Red → pin 2
- Green → pin 3
- Yellow → pin 4

## Setup
The lecture starts serial communication with:

```cpp
Serial.begin(9600);
```

and configures all three pins as outputs, initially LOW.

## Traffic sequence
```text
GREEN → YELLOW → RED → ALL OFF
```

### Timing
- Green → 5 seconds
- Yellow → 5 seconds
- Red → 5 seconds
- Then all OFF
- `loop()` calls `traffic()` and waits 10 seconds before the next cycle

### Assignment trap
The **first GO LED is Green**.

---

# 35. SENSORS WITH ARDUINO

## Sensor definition
A sensor is an electronic element that converts a **physical quantity/measurement into an electrical signal**.

Sensors can be:
- Analog
- Digital

## Examples listed
- Temperature
- Humidity
- Compass
- Light
- Sound
- Accelerometer

---

# 36. DHT SENSOR

DHT = **Digital Humidity and Temperature** sensor.

The lecture discusses DHT11 and DHT22.

## Four pins
From left to right:

| Pin | Function |
|---|---|
| 1 | 3.3V–5V power supply |
| 2 | Data |
| 3 | Null |
| 4 | Ground |

## Example connection in lecture
- Pin 1 → 3.3 V supply
- Pin 2 → digital pin **12**
- Pin 4 → GND

---

# 37. DHT SENSOR LIBRARY

Arduino provides a DHT library for **DHT11 and DHT22**.

Important functions:

```cpp
dht.readHumidity();
dht.readTemperature();
```

## Installing library
Lecture steps:
```text
Sketch → Include Library → Manage Library
```

Search:
```text
DHT SENSOR
```

Select the DHT sensor library and install it.

---

# 38. DHT SENSOR SKETCH – CORE IDEA

The lecture shows:

```cpp
#include <DHT.h>;

DHT dht(8, DHT22);

float humidity;
float temperature;

void setup() {
    Serial.begin(9600);
    dht.begin();
}

void loop() {
    humidity = dht.readHumidity();
    temperature = dht.readTemperature();

    Serial.print("Humidity: ");
    Serial.print(humidity);
    Serial.print("%, Temperature: ");
    Serial.print(temperature);
    Serial.println(" Celsius");

    delay(2000);
}
```

### Important source-specific observation
The lecture's displayed sketch initializes the DHT object with pin **8**, while the connection slide gives an example using data pin **12**. For the exam, follow the exact value/options used in the question rather than assuming one universal pin.

### Output
Readings are printed with a delay of **2 seconds**, because:
```cpp
delay(2000);
```

---

# 39. ACTUATORS

## Definition
An actuator is a:
- Mechanical/electro-mechanical device
- Converts energy into motion
- Mainly used to provide controlled motion to other components

## Basic working principle
Uses combinations of mechanical structures such as:
- Screws
- Ball bearings
- Gears

to produce motion.

---

# 40. TYPES OF MOTOR ACTUATORS

The lecture lists:
1. Servo motor
2. Stepper motor
3. Hydraulic motor
4. Solenoid
5. Relay
6. AC motor

### Assignment connection
**Stepper motor is an actuator → TRUE.**

---

# 41. SERVO MOTOR

## Key facts
- **High precision motor**
- Provides rotary motion from **0° to 180°** in the lecture
- Has **3 wires**

### Wire identification in the lecture
- Black/darkest → Ground
- Red → Power supply
- Yellow → Signal

### Exam traps
- Servo is **not low precision**.
- Servo provides **rotary**, not only linear, motion.
- Servo is an **actuator**, not a sensor.

---

# 42. SERVO LIBRARY

Arduino provides the **Servo** library.

Create an object:

```cpp
Servo myservo;
```

or as in the lecture:

```cpp
Servo ServoDemo;
```

Include:

```cpp
#include <Servo.h>
```

### Core rule
The servo instance must be **attached to a pin before use**.

```cpp
ServoDemo.attach(servoPin);
```

Then:

```cpp
ServoDemo.write(angle);
```

The `write()` function takes a degree value and rotates the motor accordingly.

---

# 43. SERVO EXAMPLE

The lecture uses:

```cpp
int servoPin = 12;
Servo ServoDemo;

void setup() {
    ServoDemo.attach(servoPin);
}

void loop() {
    ServoDemo.write(0);
    delay(1000);

    ServoDemo.write(90);
    delay(1000);

    ServoDemo.write(180);
    delay(1000);
}
```

### Behavior
The motor turns:
```text
0° → 90° → 180°
```

with **1-second delay at each position**.

---

# 44. SERVO CONNECTION

The lecture's connection example:
- Servo ground → Arduino ground
- Servo power → Arduino **5 V**
- Servo signal → digital output pin; the example uses **pin 8**

### Board setup
1. Connect board to PC.
2. Set port and board type.
3. Verify code.
4. Upload.

---

# 45. OTHER SERVO LIBRARY FUNCTIONS

The lecture lists:
- `Knob()`
- `Sweep()`
- `write()`
- `writeMicroseconds()`
- `read()`
- `attached()`
- `detach()`

### Highest priority
Know:
- `attach()` → attach servo to a pin
- `write()` → set degree position
- `detach()` → detach servo
- `attached()` → check attachment status

---

# 46. HIGH-PRIORITY COMPARISONS

## Syntax vs Semantics

| Syntactic | Semantic |
|---|---|
| Message **format** | Message **meaning** |
| Concerned with structure/representation | Concerned with interpretation |
| Example approach: middleware/message-format methods | Example approaches: ontology, collaborative conceptualization |

---

## User vs Device Interoperability

| User Interoperability | Device Interoperability |
|---|---|
| User ↔ device problem | Device ↔ device problem |
| Discovery and user/device understanding are important | Heterogeneous middleware/device compatibility is important |
| Includes syntactic + semantic issues | UMB is a solution discussed in lecture |

---

## UMB-A vs UMB-C

| UMB-A | UMB-C |
|---|---|
| UMB Adaptor | UMB Core |
| Converts physical device into virtual abstraction/UDT | Routes universal metadata messages |
| Translates local middleware messages to global metadata | Uses Middleware Routing Table (MRT) |
| Mapping/adaptation | Routing |

---

## Sensor vs Actuator

| Sensor | Actuator |
|---|---|
| Measures/senses physical quantity | Produces controlled motion/action |
| Converts physical quantity to electrical signal | Converts energy into motion |
| Example: DHT | Example: servo |
| Input side | Output/action side |

---

## `setup()` vs `loop()`

| `setup()` | `loop()` |
|---|---|
| Initialization | Repeated execution |
| Runs as initialization section | Repeats specified task |
| Configure pin modes/I/O variables | Main repeating behavior |

---

## `pinMode()` vs `digitalWrite()` vs `analogRead()`

| Function | Purpose |
|---|---|
| `pinMode()` | Set pin mode |
| `digitalWrite()` | Write HIGH/LOW |
| `analogRead()` | Read analog input voltage |

---

# 47. EXAM TRAPS / MCQ-MS​​Q ALERTS

1. **Interoperability ≠ using one protocol.**
2. **Syntax = message format.**
3. **Semantics = message meaning.**
4. UMB = **Universal Middleware Bridge**.
5. UMB-A and UMB-C are not interchangeable.
6. **UMB-A → UDT/global metadata mapping.**
7. **UMB-C → routing using MRT.**
8. Ontology solution is **limited to the defined domain/context**.
9. Arduino UNO voltage = **5 V**.
10. UNO clock = **16 MHz**.
11. UNO digital I/O = **14**.
12. UNO analog input = **6**.
13. Arduino IDE program = **Sketch**.
14. USB is the main computer interface shown for UNO.
15. Array starts at index **0**.
16. `random()` → pseudo-random number.
17. `delay()` uses **milliseconds**.
18. Green LED is first in the traffic example.
19. DHT → temperature + humidity.
20. Sensor → physical quantity → electrical signal.
21. `delay(2000)` = **2 seconds**.
22. Servo = **high precision**, controlled rotary motion.
23. Stepper motor = actuator.
24. Servo must be **attached before use**.
25. `write()` takes a degree value.
26. Servo example positions = **0°, 90°, 180°**.
27. Servo example delay = **1 second**.
28. Traffic LED pins shown = red 2, green 3, yellow 4.
29. Traffic serial speed shown = **9600**.
30. Traffic color order = **Green → Yellow → Red**.

---

# 48. NUMBERS TO MEMORIZE

| Topic | Number/value |
|---|---|
| Arduino UNO operating voltage | **5 V** |
| UNO clock | **16 MHz** |
| UNO digital I/O | **14** |
| UNO analog input | **6** |
| UNO PWM | **6** |
| UNO UART | **1** |
| Blink LED pin | **12** |
| Blink delay | **1000 ms = 1 s** |
| Traffic red pin | **2** |
| Traffic green pin | **3** |
| Traffic yellow pin | **4** |
| Traffic serial speed | **9600** |
| Traffic color delay | **5 s** |
| Traffic loop delay | **10 s** |
| DHT example data pin on connection slide | **12** |
| DHT sketch object shown | **pin 8, DHT22** |
| DHT reading delay | **2000 ms = 2 s** |
| Servo example pin | **12** in the sketch |
| Servo connection signal pin | **8** in the connection example |
| Servo positions | **0°, 90°, 180°** |
| Servo delay | **1 s** |

> **Important:** Some lecture examples use different example pins in different slides. Treat the pin number as part of that specific example, not as a universal rule.

---

# 49. ONE-PAGE FINAL REVISION

## INTEROPERABILITY
- Interoperability → meaningful communication + data/service exchange.
- IoT challenge → large-scale cooperation, heterogeneity, unknown configuration, semantic conflicts.
- User interoperability → user ↔ device.
- Device interoperability → device ↔ device.
- Identification → EPC, UPC, URI, IP/IPv6.
- Classification → UNSPSC, eCl@ss.
- Syntax → message format.
- Semantics → message meaning.
- Syntactic approaches → SOC, web services, RESTful web services, open standards, middleware, XML/cross-context exchange.
- Semantic approaches → ontology + collaborative conceptualization.
- Ontology limitation → defined domain/context.
- UMB → Universal Middleware Bridge.
- UMB-A → abstraction/mapping/translation.
- UMB-C → routing.
- UDT → Global Device ID, Function ID, Action ID, Event ID, Parameters.
- MRT → Middleware Routing Table.

## ARDUINO
- Arduino → open-source programmable board + IDE.
- UNO → 5 V, 16 MHz, 14 digital I/O, 6 analog, 6 PWM, 1 UART.
- Program → sketch.
- `setup()` → initialize.
- `loop()` → repeat.
- `pinMode()` → configure.
- `digitalWrite()` → HIGH/LOW.
- `analogRead()` → analog input.
- `delay()` → milliseconds.
- Verify → compile check.
- Upload → send program to board.
- Serial Monitor → console output.

## PROGRAMMING
- Arithmetic → `+ - * / %`
- Comparison → `== != < > <= >=`
- Boolean → `&& || !`
- Array index → 0.
- `random()` → pseudo-random.
- `randomSeed()` → seed/reset generator.
- Interrupt → external signal processing; `attachInterrupt()`.
- For/while/do-while → loops.
- Switch-case → cases + `break`.

## SENSOR
- Sensor → physical quantity → electrical signal.
- Analog or digital.
- DHT → temperature + humidity.
- DHT library → `readHumidity()`, `readTemperature()`.
- `delay(2000)` → 2 s.

## ACTUATOR
- Actuator → energy → motion.
- Examples → servo, stepper, hydraulic motor, solenoid, relay, AC motor.
- Servo → high precision, rotary, 0–180° in lecture.
- Servo wires → ground, power, signal.
- Servo object → attach → write(angle).
- Example → 0° → 90° → 180°, 1 s each.

---

# 50. LAST-MINUTE 15-ANSWER DRILL

Before the exam, answer these without looking:

1. Interoperability allows devices to ________.  
   **Communicate and exchange data.**

2. Syntactic interoperability deals with ________.  
   **Message format.**

3. UMB full form?  
   **Universal Middleware Bridge.**

4. UNO operating voltage?  
   **5 V.**

5. Arduino IDE program?  
   **Sketch.**

6. Main computer interface?  
   **USB.**

7. Array starts at?  
   **0.**

8. Pseudo-random function?  
   **`random()`**

9. First traffic GO LED?  
   **Green.**

10. DHT measures?  
   **Temperature and humidity.**

11. Sensor converts physical quantity into?  
   **Electrical signal.**

12. `delay(2000)`?  
   **2 seconds.**

13. Servo is low precision and linear only?  
   **False.**

14. Controlled rotary motion device?  
   **Servo motor.**

15. Stepper motor is an actuator?  
   **True.**

---

# 51. SOURCE / PAGE MAP

The uploaded Week 5 lecture PDF contains 97 pages and includes three major lecture blocks:

- **Interoperability in Internet of Things:** pages 1–25
- **Introduction to Arduino Programming – Part I:** pages 26–47
- **Introduction to Arduino Programming – Part II:** pages 48–70
- **Integration of Sensors and Actuators with Arduino – Part I:** pages 71–83
- **Integration of Sensors and Actuators with Arduino – Part II:** pages 84–97

The Week 5 Assignment contains 15 questions covering interoperability, Arduino basics, Arduino programming, DHT sensors, and actuators.

---

# 52. EXAM STRATEGY FOR WEEK 5

### Priority 1 — Assignment
Memorize all 15 answers and the reason for each.

### Priority 2 — High-frequency facts
Focus on:
- Syntax vs semantics
- UMB / UMB-A / UMB-C / UDT / MRT
- UNO specifications
- Sketch / setup / loop
- `pinMode`, `digitalWrite`, `analogRead`, `delay`
- Array index = 0
- `random()`
- Interrupts
- DHT
- Servo
- Stepper as actuator

### Priority 3 — Code recognition
Be able to identify what these snippets do:

```cpp
pinMode(12, OUTPUT);
digitalWrite(12, HIGH);
delay(1000);
```

```cpp
random();
```

```cpp
attachInterrupt(digitalPinToInterrupt(pin), ISR, mode);
```

```cpp
dht.readHumidity();
dht.readTemperature();
```

```cpp
ServoDemo.attach(servoPin);
ServoDemo.write(90);
```

### Priority 4 — MCQ traps
If the options contain pairs like:
- format vs meaning → **format = syntax**
- user vs device → identify the endpoints
- adaptor vs core → **Adaptor maps; Core routes**
- sensor vs actuator → **sensor measures; actuator acts**
- 1 vs 0 for first array element → **0**
- seconds vs milliseconds → `delay()` uses **milliseconds**
- green/yellow/red → **Green first**

---

## FINAL MEMORY LINE

**Interoperability = communicate/exchange → Syntax = format → Semantics = meaning → UMB-A = adapt/map → UMB-C = route → Arduino = Sketch → setup initializes → loop repeats → array starts 0 → DHT = temperature + humidity → sensor = electrical signal → actuator = motion → servo = precise rotary control.**


---

# 🚨 WEEK 5 UPDATE — MOCK-EXAM CROSS-CHECK

**Priority remains: Assignment first → ALL Week-5 lecture topics → repeated mock patterns → traps/numbers/code recognition.**

This update uses the uploaded cumulative mock exams and keeps only the patterns relevant to **Week 5: Interoperability + Arduino + Sensors + Actuators**.

## 1. HIGH-PRIORITY MOCK PATTERNS

### A. UMB Adaptor — VERY HIGH PRIORITY

Repeated mock pattern:

> What is the primary function of the UMB Adaptor?

**Answer:** It converts physical IoT devices into **virtual abstractions using a Universal Device Template (UDT)**.

The Week-5 lecture further specifies that:
- UMB-A converts physical devices into virtual abstractions.
- UDT contains:
  - Global Device ID
  - Global Function ID
  - Global Action ID
  - Global Event ID
  - Global Parameters
- UMB adaptors translate local middleware messages into global metadata messages.

fileciteturn72file2

**Memory:**  
**UMB-A = Adapt + Abstract + Translate**

Mock exams repeatedly test this distinction. fileciteturn74file1 fileciteturn74file2

---

### B. UMB-A vs UMB-C — DO NOT MIX

| Component | Main role |
|---|---|
| **UMB-A / UMB Adaptor** | Converts/maps local device/middleware information into a universal/global representation |
| **UMB-C / UMB Core** | Core/routing function between heterogeneous middleware environments |

### Trap

- “UMB-A routes between UMB cores” → **❌**
- “UMB-A converts devices into virtual abstractions using UDT” → **✅**

---

# 2. ARDUINO UNO — NUMBERS TO MEMORIZE

The Week-5 lecture gives the following Arduino UNO values:

| Feature | Value |
|---|---:|
| Operating voltage | **5 V** |
| Clock speed | **16 MHz** |
| Digital I/O | **14** |
| Analog input | **6** |
| PWM | **6** |
| UART | **1** |
| Computer interface | **USB via ATmega16U2** |

fileciteturn72file1

### Assignment-confirmed traps

- UNO operating voltage → **5 V**
- Arduino IDE program → **Sketch**
- PC connection → **USB**
- Array starting index → **0**

fileciteturn74file0 fileciteturn74file4

### Fast memory

> **UNO = 5V / 16MHz / 14 digital / 6 analog / 6 PWM / 1 UART**

---

# 3. ARDUINO IDE SETUP — EXAM RECOGNITION

The lecture's setup sequence is:

1. Connect/power the board through USB.
2. Launch Arduino IDE.
3. Select the board type.
4. Select the port.

Menu path:

**TOOLS → BOARD → select board**

**TOOLS → PORT → select port**

fileciteturn72file3

### Trap

Selecting the correct **board** and selecting the correct **port** are separate steps.

---

# 4. SERIAL MONITOR

The Arduino IDE's **Serial Monitor**:

- opens the serial console
- displays data printed to the console

fileciteturn72file4

### Memory

**Serial Monitor = see `Serial.print()` / `Serial.println()` output**

---

# 5. ARDUINO DATA TYPES — LECTURE DETAIL

The Week-5 lecture lists Arduino-supported types including:

- `void`
- `long`
- `int`
- `char`
- `boolean`
- `unsigned char`
- `byte`
- `unsigned int`
- `word`
- `unsigned long`
- `float`
- `double`
- arrays
- String object
- string/char array
- `short`

fileciteturn72file7

### MCQ trap

Do not assume the question is asking only for C/C++ primitive types. The lecture explicitly includes arrays and string forms in its supported-type list.

---

# 6. ARDUINO FUNCTIONS — MUST RECOGNIZE FROM CODE

## `pinMode()`

Configures a pin as input/output.

Typical pattern:

```cpp
pinMode(pin, OUTPUT);
```

## `digitalWrite()`

Writes a digital state:

```cpp
digitalWrite(pin, HIGH);
digitalWrite(pin, LOW);
```

## `delay()`

Delay is specified in **milliseconds**.

Therefore:

```cpp
delay(2000);
```

means:

**2000 ms = 2 seconds**

The Week-5 assignment explicitly tests this. fileciteturn73file1

## `random()`

Generates a pseudo-random number within a specified range.

The assignment explicitly identifies `random()` as the answer. fileciteturn74file4

## Arrays

Arduino arrays use **zero-based indexing**.

First element:

```text
array[0]
```

The assignment explicitly tests this. fileciteturn74file0

## Interrupts

The Week-5 lecture covers interrupts as part of Arduino programming.

A typical recognition pattern is:

```cpp
attachInterrupt(digitalPinToInterrupt(pin), ISR, mode);
```

### Why interrupts matter

For an external event, an interrupt lets the controller respond to the event rather than repeatedly checking the pin in the main loop.

A cumulative mock specifically tests the advantage of interrupts: prompt response to critical events without wasting CPU cycles on constant polling. fileciteturn74file7

### Trap

**Interrupt ≠ polling**

- Polling → repeatedly check
- Interrupt → event triggers the handler

---

# 7. TRAFFIC-CONTROL EXAMPLE — VERY HIGH PRIORITY

The Week-5 assignment asks which LED is turned on first for the **GO** signal.

### Correct sequence

**Green → Yellow → Red**

Therefore:

> **Green LED is switched ON first.**

The assignment explanation states that the `traffic()` function first sets the green LED HIGH and displays the GO message, then changes to yellow and red. fileciteturn74file4

### Trap

Do not choose red simply because red is commonly associated with “stop.” The question asks for the **first/GO** state.

---

# 8. DHT SENSOR — HIGH PRIORITY

## What DHT measures

**Temperature + Humidity**

The Week-5 lecture identifies the device as a:

**Digital Humidity and Temperature Sensor (DHT)**

fileciteturn72file0

The assignment also directly tests this. fileciteturn73file1

## DHT pin mapping from the lecture

From left to right:

| Pin | Function |
|---|---|
| **1** | 3.3–5 V power supply |
| **2** | Data |
| **3** | Null |
| **4** | Ground |

fileciteturn72file0

### Memory

**DHT = Power – Data – Null – Ground**

---

# 9. SENSOR — CORE DEFINITION

The Week-5 assignment asks:

> What does a sensor convert a physical quantity into?

**Answer: an electrical signal.**

The assignment explanation states that a sensor is an electronic element converting a physical quantity/measurement into an electrical signal. fileciteturn73file1

### Core chain

**Physical quantity → Sensor → Electrical signal**

### Do not confuse

- Sensor → detects/measures
- Actuator → performs physical action

---

# 10. DHT TIMING TRAP

The assignment asks about:

```cpp
delay(2000);
```

Correct interpretation:

**2 seconds**

because:

\[
2000\text{ ms} = 2\text{ s}
\]

fileciteturn74file9

### Common traps

- 0.2 s → ❌
- 1 s → ❌
- 2 s → ✅
- 20 s → ❌

---

# 11. SERVO MOTOR — VERY HIGH PRIORITY

A servo motor is:

> **A high-precision actuator providing controlled rotary motion.**

The assignment explicitly marks the statement “servo is a low-precision motor used only for linear motion” as **False**. fileciteturn73file1

### Therefore

**Servo → controlled rotary motion**

### Trap

Servo is **not**:
- a sensor
- a DHT device
- an ultrasonic sensor
- a low-precision linear-only motor

---

# 12. SERVO CONNECTION — LECTURE NUMBERS

The Week-5 lecture's servo example uses:

- Servo ground → Arduino ground
- Servo power → Arduino **5V**
- Servo signal → digital output pin
- Example signal pin → **pin 8**

fileciteturn73file5

### Memory

**Servo: GND → GND, Power → 5V, Signal → digital pin 8 (example)**

> The pin number is an example from the lecture connection diagram; do not treat pin 8 as a universal requirement for every servo setup.

---

# 13. SERVO LIBRARY CODE RECOGNITION

The Week-5 lecture covers the Servo library.

Typical pattern:

```cpp
#include <Servo.h>

Servo myservo;

myservo.attach(8);
myservo.write(90);
```

### Meaning

- `attach(pin)` → associates the Servo object with a physical digital pin.
- `write(angle)` → commands the servo to move to a specified angle.

A cumulative mock explicitly tests the meaning of `Servo.attach()`: it associates a Servo object with a specific physical GPIO pin. fileciteturn73file8

### Trap

`attach()` does **not**:
- read the current angle
- directly provide power
- itself command the angle

**attach = connect Servo object to pin**

**write = command angle**

---

# 14. STEPPER MOTOR

The Week-5 assignment explicitly asks:

> Is a stepper motor a type of actuator?

**YES / TRUE**

fileciteturn73file1

### Core classification

**Stepper motor → actuator**

Do not confuse:
- DHT → sensor
- servo → actuator
- stepper → actuator

---

# 15. SENSOR vs ACTUATOR — MASTER COMPARISON

| Sensor | Actuator |
|---|---|
| Measures/detects | Performs action |
| Physical quantity → electrical signal | Control signal → physical action |
| Input side of sensing loop | Output/action side |
| DHT example | Servo example |
| Temperature/humidity | Controlled rotary motion |

### Fast recall

> **Sensor senses. Actuator acts.**

---

# 16. INTEROPERABILITY — MOCK + LECTURE CROSS-CHECK

The assignment establishes:

- interoperability → devices/systems can communicate and exchange data
- syntactic interoperability → message format
- UMB → Universal Middleware Bridge

fileciteturn74file0

The lecture explains why interoperability is needed because of heterogeneity in:

- operating systems
- databases
- data representations
- control models
- syntactic/semantic interpretations

Examples of operating systems/databases are explicitly shown in the lecture. fileciteturn73file7

### Memory

**Heterogeneity → interoperability problem**

---

# 17. SYNTACTIC vs SEMANTIC — CLASSIC MCQ TRAP

| Type | Meaning |
|---|---|
| **Syntactic interoperability** | **Format / structure** |
| **Semantic interoperability** | **Meaning / interpretation** |

### One-line memory

> **Syntax = how data is written. Semantics = what data means.**

---

# 18. MOCK-EXAM PRIORITY RANKING FOR WEEK 5

## 🔴 Tier 1 — MEMORIZE

1. UMB-A → physical device → virtual abstraction using UDT
2. UDT identifiers/parameters
3. UMB-A vs UMB-C
4. UNO = **5V, 16MHz, 14 digital, 6 analog, 6 PWM, 1 UART**
5. Sketch
6. USB
7. Array starts at **0**
8. `random()`
9. Traffic sequence = **Green → Yellow → Red**
10. DHT = **temperature + humidity**
11. Sensor → electrical signal
12. `delay(2000)` = **2 seconds**
13. Servo = controlled rotary motion
14. `attach(pin)` = associate Servo object with pin
15. Stepper = actuator

## 🟠 Tier 2 — VERY IMPORTANT

16. Arduino setup sequence
17. Serial Monitor
18. `pinMode()`
19. `digitalWrite()`
20. `delay()`
21. interrupts vs polling
22. DHT pin mapping
23. Servo wiring
24. `Servo.write(angle)`
25. syntactic vs semantic interoperability

## 🟡 Tier 3 — UNDERSTAND

26. Why interoperability is needed
27. heterogeneous OS/database/data representations
28. device discovery
29. device classification
30. complete Arduino data-type list from the lecture
31. sensor/actuator integration examples

---

# 19. WEEK-5 MCQ/MSQ TRAP BANK

### Trap 1
**Syntactic = meaning**

❌ Wrong.

**Syntactic = format.**

### Trap 2
**Semantic = message structure**

❌ Wrong.

**Semantic = meaning.**

### Trap 3
**UMB-A = routing**

❌ Wrong.

**UMB-A = adaptation/virtual abstraction/mapping.**

### Trap 4
**UMB-C = converts physical devices to UDT**

❌ Wrong.

**UMB-A does that.**

### Trap 5
**Arduino program = packet/frame**

❌ Wrong.

**Arduino program = sketch.**

### Trap 6
**Array starts at 1**

❌ Wrong.

**Array starts at 0.**

### Trap 7
**`random()` configures a pin**

❌ Wrong.

**`random()` generates a pseudo-random value.**

### Trap 8
**Green is the stop signal in the traffic example**

❌ Wrong.

In the lecture's traffic example:

**Green = GO → Yellow → Red**

### Trap 9
**DHT measures distance**

❌ Wrong.

**DHT = temperature + humidity.**

### Trap 10
**Sensor converts physical quantity into mechanical motion**

❌ Wrong.

**Sensor → electrical signal.**

### Trap 11
**Servo = low-precision linear-only motor**

❌ Wrong.

**Servo = high-precision controlled rotary motion.**

### Trap 12
**Stepper is not an actuator**

❌ Wrong.

**Stepper = actuator.**

### Trap 13
**`delay(2000)` = 2000 seconds**

❌ Wrong.

**2000 milliseconds = 2 seconds.**

### Trap 14
**`attach()` moves servo to an angle**

❌ Wrong.

`attach()` associates the Servo object with a pin.

`write(angle)` commands the angle.

### Trap 15
**Interrupt = polling**

❌ Wrong.

Interrupt is event-driven; polling repeatedly checks.

---

# 20. WEEK-5 NUMBERS / CODE SHEET

| Item | Value / Meaning |
|---|---|
| Arduino UNO voltage | **5 V** |
| Clock | **16 MHz** |
| Digital I/O | **14** |
| Analog inputs | **6** |
| PWM | **6** |
| UART | **1** |
| USB interface | **ATmega16U2** |
| First array index | **0** |
| `delay(2000)` | **2 s** |
| DHT power range | **3.3–5 V** |
| DHT data | **Pin 2** |
| DHT null | **Pin 3** |
| DHT ground | **Pin 4** |
| Servo example signal pin | **8** |
| Traffic first LED | **Green** |

---

# 21. 60-SECOND WEEK-5 RECALL

> **Interoperability = communicate/exchange.**  
> **Syntax = format.**  
> **Semantics = meaning.**  
> **UMB = Universal Middleware Bridge.**  
> **UMB-A = adapt/map/virtualize.**  
> **UDT = global device/function/action/event/parameters.**  
> **Arduino = open-source programmable board + IDE.**  
> **UNO = 5V, 16MHz, 14 digital, 6 analog, 6 PWM, 1 UART.**  
> **Program = sketch.**  
> **PC = USB.**  
> **Array starts = 0.**  
> **random() = pseudo-random number.**  
> **Traffic = Green → Yellow → Red.**  
> **DHT = temperature + humidity.**  
> **Sensor = physical quantity → electrical signal.**  
> **delay(2000) = 2 seconds.**  
> **Servo = controlled rotary motion.**  
> **attach(pin) = Servo object → pin.**  
> **write(angle) = command angle.**  
> **Stepper = actuator.**

---

# 22. FINAL WEEK-5 RAPID DRILL

1. What does interoperability enable?  
   → **Communication and data exchange**

2. Syntactic interoperability?  
   → **Message format**

3. Semantic interoperability?  
   → **Meaning**

4. UMB full form?  
   → **Universal Middleware Bridge**

5. Main role of UMB-A?  
   → **Convert physical devices into virtual abstractions using UDT**

6. Five major UDT fields?  
   → **Global Device ID, Function ID, Action ID, Event ID, Parameters**

7. UNO voltage?  
   → **5 V**

8. UNO clock?  
   → **16 MHz**

9. UNO digital I/O?  
   → **14**

10. UNO analog inputs?  
    → **6**

11. Arduino IDE program called?  
    → **Sketch**

12. Computer connection?  
    → **USB**

13. First array index?  
    → **0**

14. Pseudo-random function?  
    → **random()**

15. First traffic LED?  
    → **Green**

16. DHT measures?  
    → **Temperature + humidity**

17. Sensor output?  
    → **Electrical signal**

18. `delay(2000)`?  
    → **2 seconds**

19. Servo motion?  
    → **Controlled rotary motion**

20. `attach()`?  
    → **Associates Servo object with a physical pin**

21. `write(90)`?  
    → **Commands servo angle**

22. Stepper classification?  
    → **Actuator**

23. DHT pin 2?  
    → **Data**

24. DHT pin 4?  
    → **Ground**

25. Interrupt vs polling?  
    → **Interrupt responds to an event; polling repeatedly checks**

---

# 23. UPDATE SOURCE CHECK

The Week-5 assignment directly supports the 15 assignment answers and their explanations, including interoperability, syntactic interoperability, UMB, Arduino UNO, sketch, USB, array indexing, `random()`, traffic control, DHT, sensor output, `delay(2000)`, servo, and stepper. fileciteturn74file0 fileciteturn73file1

The Week-5 lecture supports the UNO specifications, DHT pin arrangement, UMB-A/UDT structure, Arduino setup, Serial Monitor, Arduino data types, and servo connection details. fileciteturn72file1 fileciteturn72file0 fileciteturn72file2 fileciteturn72file3 fileciteturn72file4

The cumulative mock exams reinforce the UMB-A/UDT pattern and the Arduino interrupt and Servo `attach()` recognition patterns. fileciteturn74file1 fileciteturn74file2 fileciteturn74file7 fileciteturn73file8

**No images were generated or added.**
