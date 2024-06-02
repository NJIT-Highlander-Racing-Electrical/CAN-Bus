# CAN-Bus
A repository dedicated to the education and implementation of CAN-Bus on Baja vehicles

## What is CAN-Bus?

The CAN (Controller Area Network) protocol is a asynchronous two-wire communication protocol developed by Bosch in the 1980's. Its main purpose was to reduce the amount of wiring needed in vehicles.

Imagine a vehicle where every electronic device needed a wire for each piece of data being sent to every other subsystem. Power windows, wheel speed sensors, engine sensors, door locks, radios, navigation, etc would all have several wires going back to a main ECU. Not only would it be expensive and time-consuming to implement, but it would also add lots of weight and size to the vehicle. This means less space for other accessories and safety features, as well as far worse fuel efficiency.

CAN fixes this by allowing a significantly higher number of sensors and inputs to send their data over just two wires.

However, reducing all of these devices to two wires introduces some issues; for instance, two packets of data cannot be sent at the same time. To account for this, each packet of data and subsystem has an identifier attached to the message it is trying to send. These identifiers assign priority, and if two messages collide, the message with the higher priority will win and finish sending its message. After the first message is finished, the other messages can continue to send. This allows for time critical messages (for example, anti-lock brakes) to have communication priority over something less urgent (for example, power windows).

It also means that devices can choose to ignore messages that do not apply to them. The climate control system does not care if you press the gas, but that data is highly valuable to the traction control system. If a device sees an ID not relevant to it, it will simply not read the message.

In a more technical aspect, CAN implements a differential-pair signal. The two wires in a CAN-Bus system are called CAN High and CAN LOW). These signals are mirror images of each other. For example, if CAN High is 2V, CAN Low may be -2V). The purpose of this is to be more immune to electrical noise. If a noisy signal penetrates the system and adds +1V into the wires, the CAN signal itself will not change. CAN High will now be 3V, and CAN Low will now be -1V; however, the 'difference' of the two signals (4V) will still be identical, and thus the bit being sent (1 or 0) will remain the same.

CAN is also different from communication protocols like SPI (Serial Peripheral Interface) in the sense that there is no "master" device. All devices along the CAN network are known as Nodes. Nodes can be added and removed with no issues, and each node in the network is capable of sending and receiving messages to and from every other node.

Read more about CAN-Bus here: https://www.autopi.io/blog/can-bus-explained/

## Why do we use it for Baja?

We use it for many of the same reasons it is still used in vehicles today:
* Reduced wiring means less weight, less installation complexity, easier troubleshooting, and much more
* It is an extremely researched and widely implemented protocol, so learning about it and implementing it is simple
* Many controllers and transceivers exist off-the-shelf for Arduino
* There are many well-tested libraries that simplify sending messages over CAN-Bus using Arduino's
* It adds lots of flexibility to our design process. Subsystems can be added and removed to the network without significantly changing the wiring between subsystems

## CAN-Bus on ESP32

There are two main benefits to using ESP32 Microcontrollers for implementing CAN-Bus:

### Built-in CAN Controllers

A CAN Node is made up of a controller and transceiver. The controller is responsible for processing the data that is being sent and received by a microcontroller on the CAN bus. The transceiver is the interface between the controller and CAN Bus. The transceiver translates the logic level messages from the controller into the CAN differntial signals on the CAN-H and CAN-L pins.

Unlike standard Arduinos, the ESP32 has a built in CAN Controller. This means that to create a CAN Node, we only need the transceiver. The transceivers we use are from Adafruit (https://www.adafruit.com/product/5708) and are far more compact than a CAN controller/transceiver combo like the MCP2515 you may have seen online that are controlled via SPI (https://www.amazon.com/HiLetgo-MCP2515-TJA1050-Receiver-Arduino/dp/B01D0WSEWU)

Read more about the ESP32's built in CAN Controller here: https://docs.espressif.com/projects/esp-idf/en/release-v3.3/api-reference/peripherals/can.html

### Dual-Core Functionality

ESP32's also generally have dual cores. In a standard, simple microcontroller, the program loops sequentially and indefinitely. If it is doing something like reading a sensor or updating an LCD, that is all it can do at that moment. However, dual cores allow two operations to be done at once. This is invaluable for CAN-Bus as it simplifies the programs greatly. One core of each microcontroller can be dedicated to scanning the CAN-Bus, sending and receiving data and updating variables as needed. The other core can be doing the meat of the program, whether it is reading a wheel speed sensor, temperature, pedal position, or something else.

* Read more about dual core functionality on ESP32's here: https://randomnerdtutorials.com/esp32-dual-core-arduino-ide/

### Important Note regarding CAN-Bus frequency on some ESP32 Microcontrollers

* Some of the newer ESP32's have a known issue where CAN/TWAI frequencies are not actually what the programmer defines. These newer microcontrollers send messages at half the input frequency, meaning that the programmer will have to double the frequency in software (e.g. if we use 500 KB/s transmission speed, you would need to define it as 1000) 

* This was discovered from this forum post: https://www.eevblog.com/forum/microcontrollers/psa-esp32-can-frequency-assignment-broken-in-chip-revision/

### An additional note

* ESP32 sometimes refers to the CAN protocol as TWAI (Two-wire automotive interface), but they are essentially the same thing.

## Aviation Plug Wiring for CAN-Bus

* +12V on PIN 1
* GND on PIN 2
* CAN-H on PIN 3
* CAN-L on PIN 4

## CAN-Bus Message ID List

* In this repository is a CAN-Bus Message ID List that describes each CAN-Bus message that may need to be sent, the subsystem microcontroller it is coming from, and the priority number 
