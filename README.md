# Communication Design for Robot and Station

## Background
This project is a charging network that includes:
- multiple robots, which are equipped with RF MCU A moving around
- stations, which are equipped with RF MCU B staying on the ground.

The procedure steps are stated below.
1. Robot and Station have no info exchanged if no charging requested.
2. If charging is required, robots need to find the unoccupied station.
3. A robot moves to a station and tries to establish communication with it.
4. They exchange handshake message(payload 100 bytes) to confirm the session.
5. They must continuously exchange real-time messages (each with a payload of 50 bytes) at intervals of less than 100 ms until the session concludes.
6. Robot finishes the session and the Station becomes available again.

Note:
- RF modules use 802.15.4 as the basic communication standard.
- Multiple stations may be located only one meter away from each other.

## System Requirements
Specific requirements and constraints that the communication system between the robots (RF MCU A) and the stations (equipped with RF MCU B).

### Hardware Specifications
- Robots (RF MCU A): Equipped with RF modules supporting the 802.15.4 communication standard. Mobility of the robot is not covered in this document.
- Stations (RF MCU B): Stationary units equipped with RF modules that also support the 802.15.4 standard. A station could charge a robot one at a time.

### Communication Standards: LR-WPAN
Both robots and stations communicate via low-rate wireless personal area network (LR-WPAN) is a 802.15.4 Protocol.

### Data Exchange
- Handshake Message: Initiate session between a robot and a station. A handshake message with a payload of 100 bytes.
- Real-Time Messages: During the session, real-time messages with a payload of 50 bytes is exchanged.

### Timing Constraints
The interval for real-time message exchange should not exceed 100 milliseconds.

### Station Discovery
Available stations regularly broadcast their availability. The broadcast packet has each of the station's unique identity.
Assume that each of the station position is fixed.
Assume that the robot is able to scan the availability broadcast from the station.
Assume that the robot could move to the available station.

### Error Handling during session
The system could handle following errors: incomplete packet & timeout.

### Scalability
The design should able to easily new robots & stations.

## Communication Architecture
TBD: high-level architecture of the system, including how robots and stations interact. I could give data flow diagram

## Protocol Design
TBD: communication protocol between robots and stations

## Data Structures
TBD: data structure

## Station Discovery Algorithm
TBD: algo for robots to find unoccupied stations

## Handshake and Communication Process
TBD: process for establishing a session and exchanging messages.

## Error Handling and Reliability
TBD: error handling

## Testing and Validation
TBD: testing