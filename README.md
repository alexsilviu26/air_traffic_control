# Air Traffic Control – OOP Project

---

This project implements an **Air Traffic Control system** using **Object-Oriented Programming (OOP)** principles.

The goal of the application is to simulate the processes involved in air traffic management, including:

- managing airplanes and runways
- scheduling aircraft for takeoff and landing
- handling emergency situations
- generating reports regarding flight and runway status

The application is designed to be modular, efficient, and easy to extend.

---

## Project Structure

The project is organized into multiple classes, each representing a component of the air traffic control system.

Each class is implemented in separate files to ensure:

- modularity
- readability
- maintainability

---

## Main Classes

### Airplane

The **Airplane** class models aircraft in a generic way and is extended by the subclasses:

- `NarrowBodyAirplane`
- `WideBodyAirplane`

It contains information such as:

- airplane model
- airplane ID
- takeoff and landing times
- departure and destination airports
- other relevant flight information

The class provides constructors and methods for managing aircraft data.

---

### Main

The **Main** class is the entry point of the application and contains the `main` method.

Responsibilities include:

- reading commands from the input file
- invoking the appropriate methods from the `Command` class
- handling certain exceptions specified in the assignment
- initializing input and output files

To efficiently store airplanes and runways, the following data structures are used:

- **HashMap** – used for fast retrieval using unique identifiers
- **ArrayList** – used to store commands in the order they are read

---

### NarrowBodyAirplane and WideBodyAirplane

These classes represent specific aircraft types and extend the base **Airplane** class.

They override the `toString()` method to display aircraft information and manage takeoff and landing times according to the assignment requirements.

---

### Runway

The **Runway** class models a runway used for aircraft takeoff and landing.

It stores information such as:

- runway ID
- runway status (occupied or available)
- usage details

A **TreeSet** is used to manage airplanes waiting for takeoff or landing.

The `TreeSet` is sorted based on:

- takeoff or landing time
- emergency status

This structure ensures:

- uniqueness
- automatic ordering
- efficient retrieval

---

## Additional Classes

### Command

The **Command** class implements all functionalities required by the assignment.

Each functionality is implemented as a separate method that interacts with other classes in the project.

Responsibilities include:

- executing commands from the input file
- managing airplanes and runways
- handling specific exceptions

---

### Utils

The **Utils** class provides helper methods used throughout the project.

It includes a parsing method used to read commands from the input file and store them in an `ArrayList`.

This allows commands to be processed efficiently and in the order they were read.

---

### Custom Exceptions

Two custom exceptions are implemented:

**IncorrectRunwayException**

Thrown when an aircraft is assigned to an invalid runway.

**UnavailableRunwayException**

Thrown when a requested runway is not available.

These exceptions are handled and logged according to the assignment requirements.

---

## Data Structures Used

The project uses several efficient data structures:

### HashMap

Used to store airplanes and runways, allowing fast access using unique keys.

### TreeSet

Used to manage airplanes waiting for runway operations.  
Maintains sorted order based on priority criteria such as takeoff/landing time and emergency status.

### ArrayList

Used to store and process commands sequentially.

These structures ensure efficient management of system components.

---

## Coding Style

The project follows common coding conventions:

- camelCase naming convention
- private and protected variables
- public methods for controlled access
- clear separation of responsibilities between classes

Encapsulation is respected by restricting direct access to internal data.

Command arguments are stored in **String arrays** after splitting each command, which simplifies parameter handling.

---
