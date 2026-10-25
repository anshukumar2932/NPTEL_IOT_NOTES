# NPTEL IoT – Week 6 Exam Notes
## Assignment Priority + Complete Lecture Coverage

**Course:** Introduction to Internet of Things  
**Week:** 6  
**Main topics:** Python Programming Part I & II, Raspberry Pi Part I & II, IoT implementation with Raspberry Pi  
**Exam style:** MCQ/MSQ

> **Priority rule:** Study the 15 assignment questions first. Then cover the complete lecture material. The assignment is the strongest exam signal, but every lecture topic is included because questions can come from outside the assignment.

---

# 1. WEEK 6 ULTRA-QUICK REVISION

## Python
- Five basic data types emphasized in the lecture: **Numbers, String, List, Tuple, Dictionary**.
- Python uses **indentation** to indicate code blocks.
- Function definition keyword = **`def`**.
- Function can have parameters and can return a value.
- A function can return **multiple values**, which are represented together as a tuple.
- Functions can be assigned/reassigned to variables.
- **Global variable** → declared outside a function and accessible inside/outside.
- **Local variable** → declared inside a function.
- Module = reusable code segment serving a particular task.
- Import whole module: `import module_name`
- Import a particular item: `from module import item`
- Exception handling uses **`try` + `except` + `else`**.
- `ValueError` is used in the lecture's invalid-integer example.

## Files
- Three basic file operations: **open → read/write → close**.
- `open(file, mode)` returns a file object.
- `r` = read
- `w` = write
- `a` = append
- `r+` = read + write
- `with open(...)` is good practice because it ensures the file is closed after the operation, including when an exception occurs.
- CSV operations use the **`csv` module**.
- `csv.reader()` reads CSV.
- `csv.writer()` writes CSV.

## Images
- PIL = Python Image Library.
- Install Pillow using `sudo pip install pillow` in the lecture.
- `from PIL import Image`
- `Image.open()` → open image.
- `image.show()` → display image.
- `image.resize()` → resize.
- `image.rotate()` → rotate counter-clockwise.
- `image.format` → image format.
- `image.size` → `(width, height)` in pixels.
- `image.mode` → image band/mode; `L` = grayscale, `RGB` = true colour.
- `image.convert('L')` → convert to grayscale.

## Networking
- Python supports client-server networking.
- Socket syntax: `socket.socket(socket_family, socket_type, protocol=0)`.
- `AF_INET` → Internet/IPv4 address family in the lecture.
- `SOCK_STREAM` → TCP / connection-oriented.
- `SOCK_DGRAM` → UDP / connectionless.
- Server flow: **socket → bind → listen → accept → recv**.
- Client flow: **socket → connect → send**.

## Raspberry Pi
- Raspberry Pi = **low-cost single-board computer**.
- Raspberry Pi 3 Model B:
  - RAM = **1 GB SDRAM**
  - CPU = **Quad Cortex-A53 @ 1.2 GHz**
  - GPU = **400 MHz VideoCore IV**
  - Ethernet = **10/100**
  - Wireless = **802.11 + Bluetooth 4.0**
  - GPIO = **40**
- Officially supported OS in lecture: **Raspbian, NOOBS**.
- Raspberry Pi GPIO can be digital **input or output**.
- Output → make GPIO HIGH/LOW.
- Input → detect GPIO HIGH/LOW.
- Basic setup: HDMI, monitor, keyboard, mouse, 5 V adapter, LAN cable, minimum 2 GB microSD card.
- Raspberry Pi can use Python, C, C++, Java, Scratch, Ruby; lecture notes any language that compiles for ARMv6 can be used.

## Raspberry Pi LED
- Install Python development tools:
  `sudo apt-get install python-dev`
- Install GPIO library:
  `sudo apt-get install python-rpi.gpio`
- LED negative → Pi ground.
- LED positive → Pi output pin.
- Lecture example uses **BOARD numbering**, GPIO pin **11**.
- `GPIO.setmode(GPIO.BOARD)`
- `GPIO.setup(11, GPIO.OUT)`
- `GPIO.output(11, True/False)`
- `time.sleep()` uses seconds.
- Example: ON 1 s, OFF 2 s, then ON; loop runs 5 times.
- `GPIO.cleanup()` cleans up GPIO.

## Pi Camera
- Dedicated camera module connects through the **CSI slot**.
- CSI slot is **between Ethernet and HDMI**.
- Enable camera using:
  `sudo raspi-config`
  → Interfacing Options
  → Camera
  → Enable
  → Reboot
- Still image command:
  `raspistill -o image.jpg`
- Python camera module:
  `sudo apt-get install python-picamera`
- Python:
  `import picamera`
  `camera = picamera.PiCamera()`
  `camera.capture('image.jpg')`

## DHT + Relay + Fan
- DHT = **Digital Humidity and Temperature**.
- DHT pins left-to-right:
  1. 3.3–5 V power
  2. Data
  3. Null
  4. Ground
- Relay = mechanical/electromechanical switch.
- Relay has **3 output terminals**:
  - NO = Normally Open
  - Common
  - NC = Normally Closed
- Auto-cooling system:
  **DHT sensor → Raspberry Pi → relay → fan**
- Lecture example reads DHT22 using Adafruit library.
- Fan operates when temperature is **above the threshold**.
- Example threshold = **30°C**.
- Relay is **active low** in the code:
  `GPIO.output(13,0)` → relay ON
  `GPIO.output(13,1)` → relay OFF after 5 s.
- Fan wiring uses relay NO/Common and a Li-po battery.

---

# 2. ASSIGNMENT-FIRST: ALL 15 QUESTIONS

The Week 6 assignment contains **15 questions for 15 marks**. These should be revised before the lecture notes.

---

## Q1. What are the five basic Python data types introduced in the lecture?

**Answer: A — Numbers, Strings, List, Tuple, Dictionary**

### Explanation
The lecture explicitly introduces five basic data types:
1. Numbers
2. String
3. List
4. Tuple
5. Dictionary

### Trap
Do not replace these with generic programming categories such as Char, Byte, Struct, Object, etc.

**Memory:** `Numbers → String → List → Tuple → Dictionary`

---

## Q2. Which keyword is used to define a function in Python?

**Answer: B — `def`**

Example:

```python
def example(str):
    print(str + "!")
```

Then call it:

```python
example("Hi")
```

### Trap
`func`, `define`, and `function` are not the Python function-definition keyword.

**Memory:** Function definition → **`def`**

---

## Q3. Which keyword handles an exception raised inside a `try` block?

**Answer: B — `except`**

Python exception structure in the lecture:

```python
try:
    statements
except Exception:
    statements
else:
    statements
```

### Meaning
- `try` → code that may generate an exception
- `except` → handles the exception
- `else` → executes when no exception occurs

**Memory:** `try → except → else`

---

## Q4. Which `open()` mode adds data to the end of an existing file?

**Answer: C — `a` (append mode)**

| Mode | Meaning |
|---|---|
| `r` | Read |
| `w` | Write |
| `a` | Append |
| `r+` | Read + write |

### Trap
`w` is not append. It is write mode.

**Memory:** Append → **`a`**

---

## Q5. Which Python library is used for image read/write operations?

**Answer: B — PIL / Pillow**

### Key facts
- PIL = Python Image Library.
- Lecture installation command:
  `sudo pip install pillow`
- PIL is described as supporting Python 2.7.
- Pillow supports Python 3.x.

### Trap
Do not confuse Pillow with:
- NumPy
- OpenCV
- Matplotlib

**Memory:** Image file operations in this lecture → **PIL/Pillow**

---

## Q6. Which `socket_type` is used for a TCP/IP socket?

**Answer: B — `SOCK_STREAM`**

TCP/IP socket shown:

```python
socket.socket(socket.AF_INET, socket.SOCK_STREAM)
```

### Important mapping
- `AF_INET` → Internet/IPv4 family
- `SOCK_STREAM` → TCP / connection-oriented
- `SOCK_DGRAM` → UDP / connectionless

**Memory:** TCP → **STREAM**

---

## Q7. How many GPIO pins does Raspberry Pi 3 Model B have?

**Answer: C — 40**

The lecture specifications table gives **40 GPIO** for:
- Raspberry Pi 3 Model B
- Raspberry Pi 2 Model B
- Raspberry Pi Zero

### Trap
Do not confuse the total GPIO/header count with other board connector counts.

---

## Q8. Which is an officially supported Raspberry Pi OS mentioned in the lecture?

**Answer: A — Raspbian**

Officially supported:
- **Raspbian**
- **NOOBS**

Third-party examples:
- Ubuntu Mate
- Snappy Ubuntu Core
- Windows 10 Core
- Pinet
- RISC OS

### Trap
Windows XP, macOS, and Solaris are not the answer.

---

## Q9. Raspberry Pi is best described as a:

**Answer: D — Single-board computer**

The lecture describes Raspberry Pi as:
- A computer that fits in your palm
- Low cost
- Single-board
- Easy to access/use

---

## Q10. Which command installs the GPIO library before the blinking LED example?

**Answer: A**

```bash
sudo apt-get install python-rpi.gpio
```

The lecture first installs Python development tools:

```bash
sudo apt-get install python-dev
```

Then installs the GPIO library:

```bash
sudo apt-get install python-rpi.gpio
```

### Trap
Know the difference between the two commands.

---

## Q11. Where is the Raspberry Pi CSI camera connector?

**Answer: B — Between the Ethernet port and the HDMI port**

### Memory
**CSI camera slot = Ethernet ↔ HDMI**

This is also visible in the camera-board diagram in the lecture.

---

## Q12. Which command captures a still image?

**Answer: A**

```bash
raspistill -o image.jpg
```

The image is saved as:

```text
image.jpg
```

### Python alternative
```python
import picamera
camera = picamera.PiCamera()
camera.capture('image.jpg')
```

---

## Q13. What does DHT stand for?

**Answer: B — Digital Humidity and Temperature**

### DHT pins
1. 3.3–5 V power
2. Data
3. Null
4. Ground

---

## Q14. How many output terminals does the relay have in the auto-cooling system?

**Answer: B — 3**

From left to right:
1. **NO** — Normally Open
2. **Common**
3. **NC** — Normally Closed

### Trap
The relay is a switch; the three output terminals are not three independent power outputs.

---

## Q15. True or False: The fan operates when surrounding temperature rises above the threshold in the code.

**Answer: A — True**

### Why?
The auto-cooling program compares measured temperature with a threshold. When temperature exceeds the threshold, the relay activates and the fan operates.

### Lecture threshold example
**30°C**

### Memory
`temperature > threshold → fan ON`

---

# 3. PYTHON PROGRAMMING – PART I

## 3.1 Why Python?

The lecture highlights Python because it is:
- Versatile
- Easy to script
- Easy to read
- Less strict in syntax rules than many languages
- Installed with an integrated development environment
- Capable of interfacing with a wide range of hardware
- Open source
- Suitable as a backbone for large applications

---

# 4. PYTHON IDE

Python IDE:
- Free and open-source software
- Used to write code
- Can integrate modules and libraries
- Available for Windows, Linux and Mac

Examples mentioned:
- **Spyder**
- **PyCharm**

---

# 5. BASIC PYTHON SYNTAX

The lecture demonstrates the Python interpreter using:

```text
>>> print "Hi, Welcome to python!"
```

### Important concept
Python uses **rigid indentation** to indicate different blocks of code.

Example concept:

```python
if True:
    print("Correct")
else:
    print("Error")
```

### Exam trap
Indentation is not merely visual formatting in Python; it defines code blocks.

---

# 6. FIVE PYTHON DATA TYPES

The assignment directly tests this.

## 1. Numbers
The lecture example assigns:
```python
x, y, z = 10, 10.2, "Python"
```

## 2. String
Example:
```python
x = 'This is Python'
```

String indexing/slicing:
```python
x[0]
x[2:4]
```

## 3. List
Example:
```python
x = [10, 10.2, 'python']
```

## 4. Tuple
A sequence type emphasized as one of the five basic data types.

## 5. Dictionary
Example:
```python
d = {1:'item', 'k':2}
```

### Assignment priority
Memorize exactly:
**Numbers, String, List, Tuple, Dictionary**

---

# 7. CONTROL STATEMENTS

The lecture covers:

## `if`
Used for conditional execution.

## `elif`
Used to test additional conditions.

## `else`
Executes the alternative block.

## `while`
Repeats while a condition remains true.

## `for`
Used for iteration.

Example:
```python
x = [1,2,3,4]

for i in x:
    print(i)
```

---

# 8. BREAK VS CONTINUE

## `break`
Terminates the loop.

Lecture concept:
```python
for s in "string":
    if s == 'n':
        break
    print(s)
```

## `continue`
Skips the current iteration and continues with the next iteration.

Lecture concept:
```python
for s in "string":
    if s == 'y':
        continue
    print(s)
```

### Memory
- `break` → **stop loop**
- `continue` → **skip current iteration**

---

# 9. FUNCTIONS IN PYTHON

## Defining a function

### Without return value
```python
def funct_name(arg1, arg2, arg3):
    statement1
    statement2
```

### With return value
```python
def funct_name(arg1, arg2, arg3):
    statement1
    statement2
    return x
```

### Assignment trap
Function keyword = **`def`**

---

# 10. CALLING FUNCTIONS

Example:

```python
def example(str):
    print(str + "!")

example("Hi")
```

Output:
```text
Hi!
```

### Memory
**Define with `def`; execute by calling the function name.**

---

# 11. FUNCTIONS RETURNING MULTIPLE VALUES

The lecture gives:

```python
def greater(x, y):
    if x > y:
        return x, y
    else:
        return y, x

val = greater(10, 100)
print(val)
```

Output:
```text
(100, 10)
```

### Important
Multiple returned values are grouped together as a tuple-like result.

---

# 12. FUNCTIONS AS OBJECTS

Python allows functions to be:
- Assigned to variables
- Reassigned
- Called through the variable

Example concept:

```python
def add(a,b):
    return a+b

print(add(4,6))
c = add(4,6)
print(c)
```

Output:
```text
10
10
```

### Exam idea
A function is not limited to being called only directly by its original name.

---

# 13. VARIABLE SCOPE

## Global variable
Declared outside any function.

It can be accessed:
- Inside the function
- Outside the function

Example:

```python
g_var = 10

def example():
    l_var = 100
    print(g_var)

example()
```

Output:
```text
10
```

## Local variable
Declared inside a function.

Example:

```python
var = 10

def example():
    var = 100
    print(var)

example()
print(var)
```

Output:
```text
100
10
```

### Important
The local `var = 100` does not overwrite the global `var = 10` in this example.

---

# 14. MODULES IN PYTHON

## Definition
A module is a segment of code that performs a particular task and can be commonly reused.

## Import entire module

```python
import module_name
```

Access items using:

```python
module_name.var
```

## Example: random module

```python
import random

for i in range(1,10):
    val = random.randint(1,10)
    print(val)
```

Output varies between executions.

## Import only a particular item

```python
from math import pi
```

Then:

```python
print(pi)
```

### Trap
- `import random` → imports module.
- `from math import pi` → imports a specific item.

---

# 15. EXCEPTION HANDLING

## Definition
An exception is an error generated during execution of a program.

## Structure

```python
try:
    statements
except Exception:
    statements
else:
    statements
```

### Roles
| Block | Purpose |
|---|---|
| `try` | Potentially problematic code |
| `except` | Handles exception |
| `else` | Runs when no exception occurs |

---

# 16. VALUEERROR EXAMPLE

The lecture asks for an integer:

```python
while True:
    try:
        n = input("Please enter an integer: ")
        n = int(n)
        break
    except ValueError:
        print("No valid integer!")
```

If conversion fails:
- `ValueError` occurs.
- `except ValueError` handles it.
- User is prompted again.

After valid input:
```text
It is an integer!
```

### Assignment trap
The correct exception-handling keyword is **`except`**, not `catch`.

---

# 17. PRIME-NUMBER EXAMPLE

The lecture includes a program to determine whether a number is prime.

Core logic:
- Input an integer.
- If number > 1, test divisibility by values in a range.
- If a divisor is found → not prime.
- Otherwise → prime.

Important code idea:

```python
for i in range(2,num):
    if (num % i) == 0:
        # not prime
        break
else:
    # prime
```

### Exam concept
The example also demonstrates `break` and the loop's `else` behavior.

---

# 18. PYTHON FILE READ/WRITE

No separate library/module is required for basic file read/write.

## Three basic steps
1. **Open**
2. **Read/Write**
3. **Close**

---

# 19. OPENING FILES

Syntax:

```python
open(file_name, mode)
```

Returns a file object.

## Four basic modes

```text
r  → read
w  → write
a  → append
r+ → read + write
```

### Assignment priority
Append = **`a`**

---

# 20. READING AND WRITING

## Read

```python
file = open('data.txt', 'r')
file.read()
```

## Write

```python
file = open('data.txt', 'w')
file.write('writing to the file')
```

## Close

```python
file.close()
```

### Why close?
The lecture states closing ensures the file is free to be used by other resources.

---

# 21. `with open()` – GOOD PRACTICE

Example:

```python
with open("data.txt", "w") as file:
    file.write("writing to the text file")
```

### Why use `with`?
It ensures the file is closed after the operation is completed, even if an exception occurs.

### Important
The lecture examples still show `file.close()` after a `with` block, but conceptually the `with` statement handles resource cleanup.

---

# 22. CSV FILES

Python supports CSV files using the **CSV module**.

## Reading CSV

```python
with open(file, "r") as csv_file:
    reader = csv.reader(csv_file)
    for row in reader:
        print(" ".join(row))
```

## Writing CSV

```python
data = ["1,2,3,4,5,6,7,8,9".split(",")]
file = "output.csv"

with open(file, "w") as csv_file:
    writer = csv.writer(csv_file, delimiter=',')
    for line in data:
        writer.writerow(line)
```

### Memory
- CSV read → `csv.reader`
- CSV write → `csv.writer`

---

# 23. IMAGE READ/WRITE – PIL / PILLOW

## Installation

```bash
sudo pip install pillow
```

### Version distinction in lecture
- PIL → supported up to Python 2.7
- Pillow → supports Python 3.x

---

# 24. OPEN AND DISPLAY AN IMAGE

```python
from PIL import Image

image = Image.open(image_name)
image.show()
```

### Meaning
- `Image.open()` → opens image file.
- `image.show()` → displays image.

---

# 25. IMAGE OPERATIONS

## Resize

```python
image.resize((255,255))
```

Concept: resizes image to specified dimensions.

## Rotate

```python
image.rotate(90)
```

Lecture states rotation is **counter-clockwise**.

## Image properties

```python
image.format
image.size
image.mode
```

### `format`
Gives image format.

### `size`
Tuple containing:
```text
(width, height)
```
in pixels.

### `mode`
Gives image band/mode:
- `L` → grayscale
- `RGB` → true colour

---

# 26. IMAGE MODE CONVERSION

Convert to grayscale:

```python
conv_image = image.convert('L')
```

The lecture states an image can be converted to `L` or `RGB`.

For conversion between other modes, the lecture says to use `L` or `RGB` as an intermediate mode.

---

# 27. NETWORKING IN PYTHON

Python provides network services for a **client-server model**.

Sockets allow clients and servers for:
- Connection-oriented protocols
- Connectionless protocols

Python also provides libraries for higher-level application network protocols.

---

# 28. SOCKET CREATION

Syntax:

```python
s = socket.socket(socket_family, socket_type, protocol=0)
```

## `socket_family`
Examples:
- `AF_UNIX`
- `AF_INET`

## `socket_type`
Examples:
- `SOCK_STREAM`
- `SOCK_DGRAM`

## `protocol`
Default:
```text
0
```

---

# 29. TCP/IP SOCKET

Assignment asks this directly.

TCP/IP example:

```python
sock = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
```

Therefore:
- Address family = **AF_INET**
- Socket type = **SOCK_STREAM**

### Memory
**TCP = STREAM**

---

# 30. SIMPLE TCP SERVER FLOW

Lecture server example:

```python
import socket
import sys

sock = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

server_address = ('10.14.88.82', 2017)
sock.bind(server_address)

sock.listen(1)

connection, client_address = sock.accept()

data = connection.recv(1024)
print(data)

sock.close()
```

## Sequence

```text
Create socket
    ↓
Bind to address/port
    ↓
Listen
    ↓
Accept client
    ↓
Receive data
    ↓
Close
```

### Key functions
- `bind()` → associate socket with address/port.
- `listen()` → wait for incoming connections.
- `accept()` → accept a connection.
- `recv()` → receive data.

---

# 31. SIMPLE TCP CLIENT FLOW

Lecture example:

```python
client_socket = socket.socket(
    socket.AF_INET,
    socket.SOCK_STREAM
)

client_socket.connect(("10.14.88.82", 2017))
client_socket.send('Message to the server')
```

## Sequence

```text
Create socket
    ↓
Connect
    ↓
Send data
```

### Key function
`connect()` establishes connection to the server.

---

# 32. TCP VS UDP – EXAM MEMORY

| TCP-related lecture value | UDP-related lecture value |
|---|---|
| `SOCK_STREAM` | `SOCK_DGRAM` |
| Connection-oriented | Connectionless |
| Server uses bind/listen/accept | Datagram communication |
| Reliable stream-style communication concept | Datagram-style communication |

---

# 33. RASPBERRY PI – PART I

## What is Raspberry Pi?

The lecture describes Raspberry Pi as:
- A computer that fits in your palm
- A **single-board computer**
- Low cost
- Easy to access/use

### Assignment priority
Raspberry Pi → **Single-board computer**

---

# 34. RASPBERRY PI SPECIFICATIONS

## Raspberry Pi 3 Model B

| Feature | Value |
|---|---|
| RAM | **1 GB SDRAM** |
| CPU | **Quad Cortex-A53 @ 1.2 GHz** |
| GPU | **400 MHz VideoCore IV** |
| Ethernet | **10/100** |
| Wireless | **802.11 / Bluetooth 4.0** |
| Video output | HDMI / Composite |
| GPIO | **40** |

## Raspberry Pi 2 Model B

| Feature | Value |
|---|---|
| RAM | **1 GB SDRAM** |
| CPU | **Quad Cortex-A53 @ 900 MHz** |
| GPU | **250 MHz VideoCore IV** |
| Ethernet | **10/100** |
| Wireless | **None in the table** |
| GPIO | **40** |

## Raspberry Pi Zero

| Feature | Value |
|---|---|
| RAM | **512 MB SDRAM** |
| CPU | **ARM11 @ 1 GHz** |
| GPU | **250 MHz VideoCore IV** |
| Ethernet | **None** |
| Wireless | **None in the table** |
| GPIO | **40** |

### High-priority number
**Pi 3 Model B GPIO = 40**

---

# 35. RASPBERRY PI GPIO

GPIO pins can act as:
- **Digital output**
- **Digital input**

## Output
Turn GPIO pin:
- HIGH
- LOW

## Input
Detect whether GPIO pin is:
- HIGH
- LOW

### Exam trap
GPIO is not output-only.

---

# 36. BASIC RASPBERRY PI SETUP

Lecture lists:
- HDMI cable
- Monitor
- Keyboard
- Mouse
- 5 V power adapter
- LAN cable
- Minimum **2 GB microSD card**

---

# 37. RASPBERRY PI OPERATING SYSTEM

## Officially supported in lecture
- **Raspbian**
- **NOOBS**

## Third-party examples
- Ubuntu Mate
- Snappy Ubuntu Core
- Windows 10 Core
- Pinet
- RISC OS

### Assignment trap
**Raspbian = official answer**

---

# 38. RASPBERRY PI OS SETUP

## Download Raspbian
Lecture says:
1. Download latest Raspbian image from Raspberry Pi's official site.
2. Unzip it.
3. Obtain an `.img` file.

## Write image to SD card
Lecture uses **Win32 Disk Imager** on Windows:
1. Install Win32 Disk Imager.
2. Run it.
3. Insert SD card.
4. Select device.
5. Browse to image file.
6. Click/write the image.

---

# 39. BASIC INITIAL CONFIGURATION

## Enable SSH
Lecture steps:
1. Open terminal/command prompt.
2. Run:
   ```bash
   sudo raspi-config
   ```
3. Navigate to SSH in Advanced options.
4. Enable SSH.

## Expand filesystem
Again use:
```bash
sudo raspi-config
```

Then:
- Navigate to **Expand Filesystem**
- Press Enter

### Memory
`raspi-config` → configuration utility.

---

# 40. PROGRAMMING ON RASPBERRY PI

The lecture lists as default installed:
- Python
- C
- C++
- Java
- Scratch
- Ruby

### Additional lecture statement
Any language that can compile for **ARMv6** can be used with Raspberry Pi.

---

# 41. RASPBERRY PI APPLICATIONS

Lecture examples:
- Media streamer
- Home automation
- Controlling BOT
- VPN
- Lightweight web server for IoT
- Tablet computer

---

# 42. RASPBERRY PI PART II

Topics:
1. Using GPIO pins
2. Taking pictures using PiCam

---

# 43. BLINKING LED – HARDWARE

Requirements:
- Raspberry Pi
- LED
- **100 Ω resistor**
- Breadboard
- Jumper cables

### Connection
- LED negative terminal → Raspberry Pi ground.
- LED positive terminal → Raspberry Pi output pin.

---

# 44. INSTALL GPIO LIBRARY

Open terminal:

```bash
sudo apt-get install python-dev
```

Then:

```bash
sudo apt-get install python-rpi.gpio
```

### Assignment priority
The second command is the answer to Q10.

---

# 45. EDITING THE LED PROGRAM

Lecture uses:

```bash
sudo nano filename.py
```

This opens the **nano** editor.

Important keyboard commands:
- `Ctrl + O` → write/save code to file
- `Ctrl + X` → exit editor

---

# 46. RASPBERRY PI LED CODE

Lecture example:

```python
import RPi.GPIO as GPIO
import time

GPIO.setmode(GPIO.BOARD)
GPIO.setup(11, GPIO.OUT)

for i in range(0,5):
    GPIO.output(11, True)
    time.sleep(1)

    GPIO.output(11, False)
    time.sleep(2)

GPIO.output(11, True)
GPIO.cleanup()
```

## Important concepts
- `GPIO.setmode(GPIO.BOARD)` → board pin numbering.
- `GPIO.setup(11, GPIO.OUT)` → pin 11 as output.
- `GPIO.output(11, True)` → output HIGH/ON.
- `GPIO.output(11, False)` → output LOW/OFF.
- `time.sleep(1)` → 1 second.
- `time.sleep(2)` → 2 seconds.
- `GPIO.cleanup()` → cleanup GPIO configuration.

### Lecture behavior
The LED blinks with:
- ON for **1 second**
- OFF for **2 seconds**
- Loop from `0` to `4` → **5 iterations**
- Then final output is set HIGH before cleanup.

---

# 47. BOARD NUMBERING VS GPIO NUMBERING

The lecture's LED code uses:

```python
GPIO.setmode(GPIO.BOARD)
```

and then:

```python
GPIO.setup(11, GPIO.OUT)
```

Therefore the code is using **physical board pin numbering**.

### Exam trap
Do not automatically interpret every number in the code as a BCM GPIO number when `GPIO.BOARD` is selected.

---

# 48. RASPBERRY PI CAMERA

## Requirements
- Raspberry Pi
- Raspberry Pi Camera

## Camera hardware
- Raspberry Pi-specific camera module
- Dedicated **CSI slot**
- Cable slot located **between Ethernet and HDMI**

### Assignment priority
CSI slot location → **between Ethernet and HDMI**

---

# 49. CONFIGURE THE CAMERA

After connecting the camera, boot the Pi.

Then run:

```bash
sudo raspi-config
```

Navigate:

```text
Interfacing Options
    ↓
Camera
    ↓
Enable
    ↓
Reboot
```

---

# 50. CAPTURE STILL IMAGE

Command:

```bash
raspistill -o image.jpg
```

Result:
- Captures still image.
- Stores it as `image.jpg`.

### Assignment priority
This is the exact answer for Q12.

---

# 51. PYTHON PICAMERA

Install:

```bash
sudo apt-get install python-picamera
```

Python:

```python
import picamera

camera = picamera.PiCamera()
camera.capture('image.jpg')
```

### Memory
`PiCamera()` → camera object  
`capture()` → capture image

---

# 52. IMPLEMENTATION OF IoT WITH RASPBERRY PI

## IoT concept in the lecture
IoT is presented as:
- Creating an interactive environment
- A network of devices connected together

---

# 53. SENSOR

The lecture defines a sensor as:
- Electronic element
- Converts physical quantity into electrical signals
- Can be analog or digital

### Memory
**Sensor = physical quantity → electrical signal**

---

# 54. ACTUATOR

The lecture defines an actuator as:
- Mechanical/electro-mechanical device
- Converts energy into motion
- Mainly used to provide controlled motion to other components

### Memory
**Actuator = energy → motion**

---

# 55. SENSOR-ACTUATOR SYSTEM WITH RASPBERRY PI

System overview:

```text
DHT Sensor
    ↓
Read sensor data
    ↓
Raspberry Pi
    ↓
Decision/control logic
    ↓
Relay
    ↓
Fan / actuator
```

The lecture states the system:
1. Interfaces sensor and actuator with Raspberry Pi.
2. Reads data from the sensor.
3. Controls the actuator according to sensor reading.
4. Connects the actuator to a device.

---

# 56. AUTO-COOLING SYSTEM – REQUIREMENTS

Lecture requirements:
- DHT sensor
- **4.7 kΩ resistor**
- Relay
- Jumper wires
- Raspberry Pi
- Mini fan

---

# 57. DHT SENSOR WITH RASPBERRY PI

DHT = **Digital Humidity and Temperature Sensor**

Four pins:

| Pin | Function |
|---|---|
| 1 | 3.3–5 V power supply |
| 2 | Data |
| 3 | Null |
| 4 | Ground |

### Connection shown
- Pin 1 → Raspberry Pi 3.3 V
- Pin 2 → input pin; lecture uses **pin 11**
- Pin 4 → Raspberry Pi ground

---

# 58. RELAY

A relay is a:
- Mechanical/electromechanical switch.

## Three output terminals
1. **NO** — Normally Open
2. **Common**
3. **NC** — Normally Closed

### Assignment priority
Relay output terminals = **3**

---

# 59. RELAY CONNECTION

Lecture connection:
- Relay VCC → Raspberry Pi **5 V**
- Relay GND → Raspberry Pi GND
- Relay input/signal → assigned Raspberry Pi output pin
- Lecture uses **pin 7** for the relay signal connection.

---

# 60. ADAFRUIT DHT LIBRARY

The lecture uses an Adafruit library for DHT22.

Installation sequence:

```bash
git clone <Adafruit DHT repository>
cd Adafruit_Python_DHT
sudo python setup.py install
```

### Exam concept
Know the purpose:
**Install Adafruit DHT library so Raspberry Pi Python code can read the DHT22.**

---

# 61. DHT22 PROGRAM – CORE CODE

Lecture code:

```python
import RPi.GPIO as GPIO
from time import sleep
import Adafruit_DHT

GPIO.setmode(GPIO.BOARD)
GPIO.setwarnings(False)

sensor = Adafruit_DHT.AM2302

humidity, temperature = Adafruit_DHT.read_retry(sensor,17)

print(
    'Temp={0:0.1f}*C humidity={1:0.1f}%'
    .format(temperature, humidity)
)
```

### Important
- `Adafruit_DHT.AM2302` corresponds to the DHT22 sensor type in the lecture.
- `read_retry()` reads the sensor and retries if necessary.
- The returned values are:
  - humidity
  - temperature

### Source-specific pin trap
The lecture connection diagram and the displayed code use different example pin values in different places. Do not assume the pin number itself is universal; answer according to the exact code/options shown in the question.

---

# 62. RELAY CONTROL LOGIC

Lecture sets the relay input pin as output:

```python
GPIO.setup(13, GPIO.OUT)
```

Then checks:

```python
if temperature > 30:
    GPIO.output(13,0)
    print('Relay is on')
    sleep(5)
    GPIO.output(13,1)
```

### Important
- Threshold = **30°C**
- Relay is **active low**
- `0` → relay ON
- `1` → relay OFF after the 5-second delay

### Assignment connection
Fan operates when:
```text
temperature > threshold
```

---

# 63. FAN CONNECTION

The lecture uses a Li-po battery in series with the fan.

Connections:
- Relay **NO** terminal → fan positive
- Relay **Common** → battery positive
- Battery negative → fan negative

### Result
When the temperature exceeds the threshold:
- Relay switches.
- Fan receives the appropriate power path.
- Fan operates.

---

# 64. AUTO-COOLING SYSTEM – COMPLETE FLOW

```text
DHT22
  │
  │ Temperature
  ▼
Raspberry Pi
  │
  │ if temperature > 30°C
  ▼
Relay GPIO
  │
  ▼
Relay switches
  │
  ▼
Fan ON
```

When temperature is not above the threshold, the relay is not activated and the fan remains off.

---

# 65. HIGH-PRIORITY COMPARISONS

## `r` vs `w` vs `a` vs `r+`

| Mode | Meaning |
|---|---|
| `r` | Read |
| `w` | Write |
| `a` | Append |
| `r+` | Read + write |

**Most important:** Append → `a`.

---

## TCP vs UDP socket types

| TCP | UDP |
|---|---|
| `SOCK_STREAM` | `SOCK_DGRAM` |
| Connection-oriented | Connectionless |
| Stream-oriented | Datagram-oriented |

---

## `break` vs `continue`

| `break` | `continue` |
|---|---|
| Terminates loop | Skips current iteration |
| Execution leaves loop | Execution continues with next iteration |

---

## Global vs Local variable

| Global | Local |
|---|---|
| Declared outside function | Declared inside function |
| Accessible inside/outside in lecture example | Scope is the function |
| Example `var = 10` outside | Example `var = 100` inside |

---

## Sensor vs Actuator

| Sensor | Actuator |
|---|---|
| Converts physical quantity to electrical signal | Converts energy to motion |
| Measures | Acts/controls |
| DHT | Fan through relay / motor-type actuator |

---

## `GPIO.BOARD` vs conceptual GPIO input/output

| Concept | Meaning |
|---|---|
| `GPIO.BOARD` | Physical board pin numbering |
| GPIO output | Set pin HIGH/LOW |
| GPIO input | Detect pin HIGH/LOW |

---

# 66. MCQ/MSQ TRAPS

1. Five lecture data types → **Numbers, String, List, Tuple, Dictionary**.
2. Python function keyword → **`def`**.
3. Exception handler → **`except`**.
4. Append mode → **`a`**.
5. Image library → **PIL/Pillow**.
6. Pillow is the Python 3-compatible continuation mentioned in the lecture.
7. TCP socket → **`SOCK_STREAM`**.
8. UDP socket → **`SOCK_DGRAM`**.
9. Raspberry Pi 3 Model B GPIO → **40**.
10. Raspberry Pi → **single-board computer**.
11. Official OS mentioned → **Raspbian / NOOBS**.
12. GPIO library installation → **`sudo apt-get install python-rpi.gpio`**.
13. CSI slot → **between Ethernet and HDMI**.
14. Still-image command → **`raspistill -o image.jpg`**.
15. DHT → **Digital Humidity and Temperature**.
16. Relay → **3 output terminals**.
17. Relay terminals → **NO, Common, NC**.
18. Fan turns on when temperature is **above threshold**.
19. Lecture auto-cooling threshold → **30°C**.
20. Relay in the code is **active low**.
21. `GPIO.output(13,0)` → relay ON in the example.
22. `GPIO.output(13,1)` → relay OFF after delay.
23. `GPIO.setmode(GPIO.BOARD)` → board/physical pin numbering.
24. `time.sleep(1)` → 1 second.
25. `time.sleep(2)` → 2 seconds.
26. LED example pin → **11** under BOARD numbering.
27. LED resistor in Pi blinking example → **100 Ω**.
28. DHT auto-cooling resistor → **4.7 kΩ**.
29. DHT pin order → power, data, null, ground.
30. `raspi-config` is used for Raspberry Pi configuration such as SSH, filesystem expansion, and camera enablement.

---

# 67. NUMBERS / COMMANDS TO MEMORIZE

| Topic | Value / command |
|---|---|
| Pi 3 Model B RAM | **1 GB** |
| Pi 3 Model B CPU | **Quad Cortex-A53 @ 1.2 GHz** |
| Pi 3 GPU | **400 MHz VideoCore IV** |
| Pi 3 Ethernet | **10/100** |
| Pi 3 wireless | **802.11 + Bluetooth 4.0** |
| Pi 3 GPIO | **40** |
| Pi 2 GPIO | **40** |
| Pi Zero GPIO | **40** |
| Minimum microSD in setup | **2 GB** |
| LED resistor | **100 Ω** |
| LED example board pin | **11** |
| LED ON time | **1 s** |
| LED OFF time | **2 s** |
| LED loop count | **5** |
| DHT resistor in auto-cooling | **4.7 kΩ** |
| DHT data connection in diagram | **pin 11** |
| Relay supply | **5 V** |
| Relay signal example | **pin 7** |
| Relay control GPIO in code | **pin 13** |
| Cooling threshold | **30°C** |
| Relay ON delay | **5 s** |
| Camera slot | **Ethernet ↔ HDMI** |

### Commands
```bash
sudo apt-get install python-dev
sudo apt-get install python-rpi.gpio
sudo raspi-config
raspistill -o image.jpg
sudo apt-get install python-picamera
sudo pip install pillow
```

---

# 68. CODE RECOGNITION DRILL

Be able to identify these instantly.

## Function
```python
def add(a,b):
    return a+b
```
→ Defines a function.

## Exception
```python
try:
    ...
except ValueError:
    ...
```
→ Handles a ValueError.

## Append
```python
open("data.txt", "a")
```
→ Appends to file.

## TCP
```python
socket.socket(socket.AF_INET, socket.SOCK_STREAM)
```
→ TCP/IP stream socket.

## Pi GPIO
```python
GPIO.setmode(GPIO.BOARD)
GPIO.setup(11, GPIO.OUT)
```
→ Physical board numbering; pin 11 configured as output.

## Pi camera
```bash
raspistill -o image.jpg
```
→ Capture still image.

## DHT
```python
humidity, temperature = Adafruit_DHT.read_retry(sensor,17)
```
→ Read DHT sensor values.

## Auto cooling
```python
if temperature > 30:
    GPIO.output(13,0)
```
→ Threshold exceeded; relay activated in this active-low example.

---

# 69. ONE-PAGE FINAL REVISION

## PYTHON
**5 data types:**
Numbers, String, List, Tuple, Dictionary.

**Function:**
`def`

**Exception:**
`try → except → else`

**Files:**
`r = read`, `w = write`, `a = append`, `r+ = read/write`

**Images:**
PIL/Pillow → `Image.open()`, `show()`, `resize()`, `rotate()`, `convert()`

**Networking:**
`AF_INET + SOCK_STREAM = TCP/IP`

**Loop controls:**
`break = stop`, `continue = skip current`

---

## RASPBERRY PI
- Single-board computer.
- Pi 3 Model B → **1 GB, 1.2 GHz A53, 400 MHz GPU, 40 GPIO**.
- Official OS in lecture → **Raspbian + NOOBS**.
- GPIO → digital input/output.
- `GPIO.BOARD` → physical board numbering.

---

## PI LED
```text
python-dev
    ↓
python-rpi.gpio
    ↓
GPIO.BOARD
    ↓
GPIO.setup(11, OUT)
    ↓
HIGH 1 s
LOW 2 s
```

---

## CAMERA
```text
CSI slot
between Ethernet and HDMI
        ↓
sudo raspi-config
        ↓
Enable Camera
        ↓
Reboot
        ↓
raspistill -o image.jpg
```

---

## AUTO COOLING
```text
DHT22
 ↓
Raspberry Pi
 ↓
temperature > 30°C
 ↓
Relay active low
 ↓
Fan ON
```

**DHT = Digital Humidity and Temperature**

**Relay = 3 terminals: NO, Common, NC**

---

# 70. LAST-MINUTE 15-ANSWER DRILL

Answer without looking:

1. Five Python data types?  
   **Numbers, String, List, Tuple, Dictionary**

2. Function keyword?  
   **`def`**

3. Exception handler?  
   **`except`**

4. Append mode?  
   **`a`**

5. Image library?  
   **PIL/Pillow**

6. TCP socket type?  
   **`SOCK_STREAM`**

7. Raspberry Pi 3 GPIO?  
   **40**

8. Official Pi OS?  
   **Raspbian**

9. Raspberry Pi type?  
   **Single-board computer**

10. GPIO library installation command?  
   **`sudo apt-get install python-rpi.gpio`**

11. CSI slot location?  
   **Between Ethernet and HDMI**

12. Capture image command?  
   **`raspistill -o image.jpg`**

13. DHT full form?  
   **Digital Humidity and Temperature**

14. Relay output terminals?  
   **3 — NO, Common, NC**

15. Fan above temperature threshold?  
   **True**

---

# 71. EXAM STRATEGY

### Priority 1 — Memorize the 15 assignment answers
The assignment directly covers:
- Python basics
- Exception handling
- File modes
- Image processing
- TCP sockets
- Raspberry Pi specs/OS
- GPIO
- Camera
- DHT
- Relay
- Auto cooling

### Priority 2 — Memorize numbers
Especially:
- **40 GPIO**
- **1 GB RAM**
- **1.2 GHz A53**
- **400 MHz GPU**
- **100 Ω LED resistor**
- **4.7 kΩ DHT resistor**
- **30°C threshold**
- **5 s relay delay**
- **11 / 7 / 13** for the specific Raspberry Pi examples

### Priority 3 — Recognize commands
Know what each command does:
- `sudo raspi-config`
- `sudo apt-get install python-dev`
- `sudo apt-get install python-rpi.gpio`
- `raspistill -o image.jpg`
- `sudo apt-get install python-picamera`
- `sudo pip install pillow`

### Priority 4 — Understand flows
**Python exception:**  
`try → except → else`

**TCP server:**  
`socket → bind → listen → accept → recv`

**TCP client:**  
`socket → connect → send`

**Pi camera:**  
`connect CSI → enable camera → reboot → raspistill`

**Auto cooling:**  
`DHT → Pi → threshold → relay → fan`

---

# 72. SOURCE / PAGE MAP

The uploaded Week 6 lecture PDF has **103 pages** and is organized into:

- **Pages 1–22:** Introduction to Python Programming – Part I
- **Pages 23–44:** Introduction to Python Programming – Part II
- **Pages 45–65:** Introduction to Raspberry Pi – Part I
- **Pages 66–84:** Introduction to Raspberry Pi – Part II
- **Pages 85–103:** Implementation of IoT with Raspberry Pi – Part I

The assignment is **7 pages** and contains **15 questions / 15 marks**.

---

# FINAL MEMORY LINE

**Python: 5 types → `def` → `try/except/else` → `a` append → PIL/Pillow → TCP=`SOCK_STREAM`; Raspberry Pi: single-board computer → 40 GPIO → Raspbian → GPIO library → CSI between Ethernet/HDMI → `raspistill`; IoT implementation: DHT = humidity+temperature → relay = NO/Common/NC → temperature above threshold → fan ON.**
