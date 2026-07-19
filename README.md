# Sumobot Champion 🏆
![Placement](https://img.shields.io/badge/Placement-1st_Place-gold) ![Platform](https://img.shields.io/badge/Platform-Arduino-blue)

> 1st place winner out of 16 teams at the IEEE Region 1 & 2 Joint SAC — Spring 2026 sumobot competition.[cite: 1]

## About This Project
Our tournament run as roommates and teammates didn't start the way we planned. We lost our very first match and were immediately dropped into the losers bracket.[cite: 1] However, from there we went on an 8-win streak, reverse-sweeping the entire tournament to take 1st place.[cite: 1] 

We also built the robot twice.[cite: 1] The first build broke apart from how much we stress-tested it before we rebuilt it stronger for competition day.[cite: 1]

## The Team
| Name | Roles |
| :--- | :--- |
| **Tommy Pham** | Hardware, Software, Strategy[cite: 1] |
| **Jacob Lontoc** | Hardware, Firmware[cite: 1] |
| **Isaac Boteler** | Software[cite: 1] |

## How It Works: The "Seek & Destroy" Strategy
Every sumobot has IR proximity sensors, but in practice these are unreliable in a two-robot match.[cite: 1] IR rays deflect and interfere between competing robots' black chassis designs, so relying on IR alone means guessing at the opponent's position.[cite: 1] 

**Our Secret Sauce:** Instead of guessing, our strategy was to consistently cover as much of the ring as possible and actively seek contact.[cite: 1] We only committed to a direct attack once we were close enough to be confident.[cite: 1] This is what separated us from teams that leaned purely on sensor readings.[cite: 1]

### Software Architecture (State Machine)
Our robot's logic is driven by a 5-stage state machine:[cite: 1]
* **Countdown + Opening Scan:** A brief delay, then a directional sweep to locate the opponent.[cite: 1]
* **Cross-Ring Drive:** An aggressive forward push to force early contact.[cite: 1]
* **Bounce Search:** An oscillating search pattern when no opponent is detected.[cite: 1]
* **Attack + Reacquire:** A multi-phase attack routine that re-locks onto the opponent after evasion.[cite: 1]
* **Boundary Detection:** Reflectance-based edge detection to stay inside the ring.[cite: 1]

## Hardware
* **Platform:** Pololu Zumo 32U4[cite: 1]
* **Ring:** 30-inch diameter sumo ring[cite: 1]
* **Sensors:** IR proximity (opponent detection), reflectance array (boundary detection)[cite: 1]
* **Motors:** Built-in dual gear motors via Zumo motor driver[cite: 1]

## Media Gallery
![Team photo holding trophy](./media/team-photo.jpg)[cite: 1]
![Robot on the sumo ring](./media/robot.jpg)[cite: 1]
<!-- TODO: Add match video/GIF -->[cite: 1]

## Getting Started
1. Install the Arduino IDE[cite: 1]
2. Install the Pololu Zumo 32U4 library[cite: 1]
3. Open `sumobot-starter-code/sumobot-starter-code.ino`[cite: 1]
4. Connect your Zumo 32U4 via USB and upload[cite: 1]

## Acknowledgments
* IEEE Region 1 & Region 2 Joint Student Activities Conference — Spring 2026[cite: 1]
