# CS350 <br /> <br />
Fiinal Project: <br />
# Summarize the project and what problem it was solving<br />

This project involved creating a functional thermostat prototype using a Raspberry Pi. It monitors ambient temperature using a sensor and allows users to toggle between heating, cooling, and off states. The system uses LEDs to indicate mode, an LCD to show real-time information, and buttons to control the setpoint and mode. It also communicates temperature and state data over a serial connection, simulating integration with a server or larger home automation system.
Problem it solved: Demonstrated an embedded systems approach to automating environmental controls using Python and physical components. <br /><br />

# What did you do particularly well?<br />

State management: The use of a StateMachine class effectively modeled the system's three modes and encapsulated related logic. <br />

Hardware abstraction: The project neatly separated display logic (ManagedDisplay), hardware inputs (buttons), and outputs (LEDs), improving readability and reusability. <br />

Debug support: The DEBUG flag and periodic console logging helped with iterative testing and validation. <br /><br />

# Where could you improve?<br />

Error handling: More robust handling of sensor or serial connection errors (e.g. try/except around getFahrenheit or ser.write) would make the system more fault-tolerant.

Code organization: Some methods (like manageMyDisplay) are very long and could be broken into smaller helper methods for clarity.

Threading: While threading was used for display updates, more attention could be paid to safe exit handling or future expansion (e.g. if multiple sensors were introduced). <br /><br />

# What tools and/or resources are you adding to your support network?<br />

Python GPIO libraries: gpiozero, digitalio, and board for controlling LEDs and buttons.<br />

Adafruit libraries: For interfacing with the AHTx0 temperature sensor and character LCD over I2C. <br />

StateMachine library: Provided structure and clarity for mode transitions. <br />

Serial communication (pySerial): Gained experience in setting up and managing serial port data transfer. <br /><br />

# What skills from this project will be particularly transferable to other projects and/or course work?<br />

Embedded system design: Integrating hardware sensors/outputs with software logic. <br />

State machine implementation: Useful for game development, robotics, and other systems needing well-defined transitions. <br />

Threading and concurrency: Running a background task (LCD management) while the main loop continues—important in many real-time systems. <br />

Modular coding: Breaking up code into classes and methods for better maintainability. <br /><br />

# How did you make this project maintainable, readable, and adaptable?<br />

Commenting and documentation: Extensive docstrings and inline comments explain both what the code is doing and why. <br />

Class-based design: Use of TemperatureMachine and ManagedDisplay promotes reusability and modularity. <br />

Clear state representation: Thermostat states are cleanly modeled and easily extendable if more states or behaviors were needed. <br />

Constants and flags: The DEBUG flag and variable names like setPoint and endDisplay make the code easy to tune and extend. <br /><br />

Milestone 3: <br />
# Summarize the project and what problem it was solving<br />

This project involved building a Python program for a Raspberry Pi that simulates Morse code messages ("SOS" and "OK") using red and blue LEDs. The system toggles between messages using a button and uses a state machine to control the timing and signaling for dots, dashes, and pauses. An LCD screen displays the current message being transmitted. <br />
Problem it solved: It demonstrates how to use GPIO, threading, and state machines to implement time-sensitive LED-based signaling—helpful in learning how embedded systems communicate in constrained environments. <br /><br />

# What did you do particularly well?<br />

State machine design: Clear states for dot, dash, inter-symbol, inter-letter, and inter-word pauses made the logic both robust and extensible.<br />

Morse code dictionary: Allowed flexible message encoding and easy addition of new characters.<br />

Hardware control: Successfully coordinated LED behavior, LCD updates, and button input.<br />

Threaded operation: Kept the message transmission running in the background without blocking the main loop.<br /><br />

# Where could you improve?<br />

Redundant transitions: In the code (e.g., self.doDot(); self.doDot()), the double-calling of state transitions might be unintended or could be refactored for clarity.<br />

Error handling: No validation for characters not in the Morse dictionary, which could cause silent failures.<br />

Multi-word parsing: Right now, only one-word messages are supported directly ("OK" and "SOS"). Expansion to full sentences would require improved word and character spacing logic.<br /><br />

# What tools and/or resources are you adding to your support network?<br />

gpiozero: For abstracting button and LED input/output.<br />

Adafruit LCD libraries: To handle character LCD output over I2C.<br />

statemachine package: Introduced a scalable and structured way to manage behavior.<br />

Threading module: Enabled concurrent execution—key for future real-time applications.<br /><br />

# What skills from this project will be particularly transferable to other projects and/or course work?<br />

State machine modeling: Essential for game development, robotics, automation systems, and communication protocols.<br />

Time-based control and sequencing: Learned how to control hardware timing precisely, useful for signal processing and animations.<br />

Multithreading: Gained confidence in running non-blocking background tasks.<br />

Hardware-software integration: Strengthened skills in syncing code with physical output devices (LEDs, LCDs, buttons).<br /><br />

# How did you make this project maintainable, readable, and adaptable?<br />

Modular structure: The CWMachine class cleanly encapsulates all behavior.<br />

LCD display abstraction: Separated the display logic into ManagedDisplay, promoting reuse.<br />

Clear constants and naming: Variables like dotDashPause, letterPause, etc., clearly indicate their purpose.<br />

State comments and flow: Each transition and action is documented, helping future developers (or yourself) modify the system easily.<br /><br />
