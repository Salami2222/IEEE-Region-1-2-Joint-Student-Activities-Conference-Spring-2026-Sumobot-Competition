# Sumobot Champion 🏆
![Placement](https://img.shields.io/badge/Placement-1st_Place-gold) ![Platform](https://img.shields.io/badge/Platform-Arduino-blue)

> 1st place winner out of 16 teams at the IEEE Region 1 & 2 Joint SAC — Spring 2026 sumobot competition.

## About This Project
Our tournament run as roommates and teammates didn't start the way we planned. We lost our very first match and were immediately dropped into the losers bracket. However, from there we went on an 8-win streak, reverse-sweeping the entire tournament to take 1st place. 

We also built the robot twice. The first build broke apart from how much we stress-tested it before we rebuilt it stronger for competition day.

## The Team
| Name | Roles |
| :--- | :--- |
| **Tommy Pham** | Hardware, Software, Strategy |
| **Jacob Lontoc** | Hardware, Firmware |
| **Isaac Boteler** | Software |

## How It Works: The "Seek & Destroy" Strategy
Every sumobot has IR proximity sensors, but in practice these are unreliable in a two-robot match. IR rays deflect and interfere between competing robots' black chassis designs, so relying on IR alone means guessing at the opponent's position. 

**Our Secret Sauce:** Instead of guessing, our strategy was to consistently cover as much of the ring as possible and actively seek contact. We only committed to a direct attack once we were close enough to be confident. This is what separated us from teams that leaned purely on sensor readings.

### Software Architecture (State Machine) 
Our robot's logic is driven by a 5-stage state machine:
* **Countdown + Opening Scan:** A brief delay, then a directional sweep to locate the opponent.
* **Cross-Ring Drive:** An aggressive forward push to force early contact.
* **Bounce Search:** An oscillating search pattern when no opponent is detected.
* **Attack + Reacquire:** A multi-phase attack routine that re-locks onto the opponent after evasion.
* **Boundary Detection:** Reflectance-based edge detection to stay inside the ring.

## Hardware
* **Platform:** Pololu Zumo 32U4
* **Ring:** 30-inch diameter sumo ring
* **Sensors:** IR proximity (opponent detection), reflectance array (boundary detection)
* **Motors:** Built-in dual gear motors via Zumo motor driver

## Getting Started

To run this code locally and test our "seek and destroy" logic on your own hardware:

1. **Install the IDE:** Download and install the [Arduino IDE](https://www.arduino.cc/en/software).
2. **Install Dependencies:** Open the IDE, navigate to the Library Manager (`Sketch` > `Include Library` > `Manage Libraries`), and install the **Pololu Zumo 32U4** library.
3. **Download the Code:** Clone or download this repository to your local machine.
4. **Maintain Directory Structure:** Navigate into the project folder. Ensure that the main sketch (`sumobot-code.ino`) and the local header file (`turn-sensor.h`) are kept together inside a folder named `sumobot-code`.
5. **Upload:** Open `sumobot-code.ino` in the Arduino IDE. Connect your Zumo 32U4 via USB, select the appropriate board and port from the `Tools` menu, and click **Upload**.
