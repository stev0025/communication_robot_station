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

