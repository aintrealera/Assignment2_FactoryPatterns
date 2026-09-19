# Assignment 2 — Factory Method and Abstract Factory

## Project Purpose

This project is a Java logistics application that demonstrates two design patterns:

- Factory Method for creating delivery transports.
- Abstract Factory for creating matching UI components.

The application supports:

- Road delivery using a Truck.
- Sea delivery using a Ship.
- Windows UI components.
- macOS UI components.

The application is implemented as a console program using Java 17.

## Patterns

### Factory Method

The Factory Method pattern is used for transport creation.

The main classes are:

- `Transport` — product interface.
- `Truck` — concrete product for road delivery.
- `Ship` — concrete product for sea delivery.
- `Logistics` — abstract creator containing `createTransport()` and the shared `planDelivery()` workflow.
- `RoadLogistics` — creates `Truck`.
- `SeaLogistics` — creates `Ship`.

The shared delivery workflow does not depend on concrete transport classes.

### Abstract Factory

The Abstract Factory pattern is used for creating matching UI component families.

The main classes are:

- `Button` — abstract button product.
- `Checkbox` — abstract checkbox product.
- `WindowsButton` — Windows button.
- `WindowsCheckbox` — Windows checkbox.
- `MacOSButton` — macOS button.
- `MacOSCheckbox` — macOS checkbox.
- `GUIFactory` — abstract factory.
- `WindowsFactory` — creates Windows UI components.
- `MacOSFactory` — creates macOS UI components.

## Package Structure

```
src
├── factorymethod
│   ├── Transport.java
│   ├── Truck.java
│   ├── Ship.java
│   ├── Logistics.java
│   ├── RoadLogistics.java
│   └── SeaLogistics.java
│
├── abstractfactory
│   ├── Button.java
│   ├── Checkbox.java
│   ├── WindowsButton.java
│   ├── WindowsCheckbox.java
│   ├── MacOSButton.java
│   ├── MacOSCheckbox.java
│   ├── GUIFactory.java
│   ├── WindowsFactory.java
│   └── MacOSFactory.java
│
└── app
    ├── DeliveryApplication.java
    └── Main.java
```

## Prerequisites
JDK 17
IntelliJ IDEA or another Java IDE

No external libraries or services are required.

## How to Run
1. Open the project in IntelliJ IDEA.
2. Make sure JDK 17 is selected.
3. Open:

```src/app/Main.java```

4. Run the Main class.
5. Enter a delivery mode.
6. Enter a UI platform.

## Supported Input

Delivery modes
```
ROAD
SEA
```
UI platforms
```
WINDOWS
MACOS
```
The input is case-insensitive.

## Example Run

```Enter delivery mode (ROAD or SEA): ROAD
Enter UI platform (WINDOWS or MACOS): WINDOWS

Delivery mode: ROAD
UI platform: WINDOWS
Rendering Windows button
Rendering Windows checkbox
Truck delivers laboratory equipment to Aktau warehouse
```
## Invalid Input

For an unsupported delivery mode:

Enter delivery mode (ROAD or SEA): TRAIN
Enter UI platform (WINDOWS or MACOS): WINDOWS
Invalid delivery mode: TRAIN

For an unsupported UI platform:

Enter delivery mode (ROAD or SEA): ROAD
Enter UI platform (WINDOWS or MACOS): LINUX
Invalid UI platform: LINUX

## Verification

The application supports all four valid combinations:

ROAD + WINDOWS
SEA + WINDOWS
ROAD + MACOS
SEA + MACOS

It also validates unsupported delivery modes and unsupported UI platforms.

## Java Version

Java 17
