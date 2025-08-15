# AMPLS
AMPLS: Autonomous helicopter landing on naval vessels in severe sea states (6.5-7). Built in Unity 3D with ML-Agents (IL/RL), it uses LSTM for ship motion prediction &amp; quiescent periods, ensuring precise 3-point touchdowns. Models exported in ONNX for real-world integration. Revolutionizing maritime safety.

# Autonomous Maritime Precision Landing System (AMPLS)

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/6a33c702-50a9-465d-ad6c-54871e8be970" />

Table of Contents

1. Overview

2. (#2-the-challenge-conquering-the-high-seas)

3. (#3-our-solution-ampls)

4. (#4-technical-deep-dive)

(#41-unity-3d-simulation-environment)

(#42-predicting-the-calm-lstm-for-quiescent-periods)

Learning Paradigms with ML-Agents

Imitation Learning (IL)

(#reinforcement-learning-rl)

(#44-the-critical-touchdown-ensuring-a-three-point-landing)

Model Export: ONNX Format

5. Key Features & Advantages

6. (#6-getting-started-simulation)

7. (#7-future-work)

8. Contributing

9. License

10. Contact

1. Overview
The Advanced Maritime Precision Landing System (AMPLS) is an innovative autonomous solution designed to enable helicopters to perform safe and precise landings on naval vessels, even in extremely challenging sea conditions (Sea State 6.5-7). Leveraging cutting-edge AI techniques, including Long Short-Term Memory (LSTM) networks for ship motion prediction, and a combination of Imitation Learning (IL) and Reinforcement Learning (RL) within a high-fidelity Unity 3D simulation, AMPLS aims to achieve "beyond human" capabilities, significantly enhancing maritime safety and operational resilience.

2. The Challenge: Conquering the High Seas
Landing a helicopter on a ship's flight deck is one of the most complex and hazardous maneuvers in aviation. This challenge is dramatically amplified in severe weather, where the ocean churns into a furious Sea State 6.5 or 7, characterized by towering waves (20-30 feet) and near-gale force winds.

In such conditions, the ship's flight deck becomes a violently pitching, rolling, and heaving target. Traditional methods, even with advanced systems like the 'bear trap' (RAST), still require human intervention at critical junctures. Brave flight deck crews are exposed to immense danger, pushing the very limits of human endurance and safety. The unpredictable motion, reduced visibility from spray, and the sheer physical demands make precise control incredibly difficult for human pilots.

![Image](https://github.com/user-attachments/assets/35482eb6-9e65-433e-8723-e42a52cfff83)                ![Image](https://github.com/user-attachments/assets/f616d3cf-52ed-480f-8313-0672b9b6fcad)

Our audacious goal with AMPLS was to develop an autonomous system that could not only match, but surpass human precision, ensuring safe landings even when conditions render human intervention too risky.

3. Our Solution: AMPLS
AMPLS addresses these challenges by integrating advanced AI models into a robust simulation environment. Our system learns to predict ship movements, identify optimal landing windows, and execute flawless, stable touchdowns, all while adapting to the chaotic dynamics of the open ocean.

4. Technical Deep Dive
4.1. Unity 3D Simulation Environment
Our journey began in a meticulously crafted, high-fidelity Unity 3D simulation. This wasn't merely a game; it was a precise digital twin of the real-world maritime environment. We developed detailed models of the USS Lassen (DDG-82) and our Sikorsky MH60 r helicopter, incorporating realistic physics for aerodynamics, ocean dynamics (waves, wind, currents), and ship motion. This virtual proving ground allowed us to safely conduct millions of landing attempts in extreme, reproducible conditions that would be impossible or prohibitively expensive in the real world.

# Screenshot from simulation having fully developed sea with USS Lassen DDG (82) an Arleigh Burke Destroyer with  Sikorsky MH60 r Helicopter in Unity 3d version 6

<img width="2559" height="1495" alt="Image" src="https://github.com/user-attachments/assets/7f39a3d3-a29c-40ec-a34a-de2ed237050b" />

<img width="15360" height="8640" alt="Image" src="https://github.com/user-attachments/assets/ffe4399e-1f1e-40f7-91f1-c071de6f5cf1" />

4.2. Predicting the Calm: LSTM for Quiescent Periods
One of the most critical aspects of safe shipboard landings is timing. Even in the most violent storms, there are fleeting moments when the ship momentarily achieves a relatively stable state – these are known as "quiescent periods." During these precious intervals, the amplitude of the ship's motion (its heave, pitch, and roll) significantly decreases, providing the most favorable conditions for a safe touchdown. For a helicopter to land safely, these motions must fall within strict limits, such as a roll of 2.5°, a pitch of 1.5°, and a vertical velocity (heave) of 1.0 m/s.

To precisely identify and predict these elusive windows of calm, AMPLS incorporates an advanced Long Short-Term Memory (LSTM) neural network model. LSTMs are a type of recurrent neural network particularly adept at processing and learning from sequential data, making them ideal for predicting time-series data like ship motion. Our LSTM model continuously analyzes the ship's real-time motion data (heave, pitch, and roll) and, with remarkable accuracy, forecasts these movements over an 8-second horizon. This foresight is crucial, as a minimum of six seconds is necessary for a helicopter to execute a safe landing maneuver. By predicting these quiescent periods, AMPLS can guide the helicopter to initiate its final approach only when the deck is most stable, significantly enhancing safety and efficiency.



4.3. Learning Paradigms with ML-Agents
With the ability to predict the ship's movements, the next step was to teach our AI how to fly and land with unparalleled precision. We leveraged Unity's ML-Agents toolkit to implement a powerful two-stage learning process:

Imitation Learning (IL)
We first employed Imitation Learning (IL). In this phase, our AI agent observed and learned from expert human demonstrations within the simulation. We meticulously recorded countless successful landings performed by skilled virtual pilots. The agent's neural network was trained to mimic these expert behaviors, allowing it to grasp the fundamental nuances of helicopter control, approach trajectories, and dynamic ship compensation. This phase provided the foundational "muscle memory" for the AI, teaching it the art of a safe, controlled descent. It's akin to teaching a complex skill by showing, rather than just telling.



Reinforcement Learning (RL)
However, to truly achieve "beyond human" capabilities in Sea State 6.5-7, mere imitation was not enough. The unpredictable chaos of extreme weather demanded a level of adaptability and optimization that only true learning could provide. This led us to the Reinforcement Learning (RL) phase.

Building upon the knowledge gained from IL and armed with the LSTM's predictive power, our agent was unleashed into the simulated storms. Through millions of trials and errors, guided by carefully crafted reward functions (where successful maneuvers earned "points" and errors incurred "penalties"), the AI began to discover novel control strategies. It learned to anticipate the ship's violent pitches and rolls, to compensate for sudden wind gusts, and to execute landings with a precision and resilience that surpassed even the most seasoned human pilots. The agent wasn't just mimicking; it was innovating, finding optimal solutions in scenarios where human intuition might falter. It learned to dance with the waves, not just fight them.



4.4. The Critical Touchdown: Ensuring a Three-Point Landing
The final moments of a helicopter landing are arguably the most critical. Unlike fixed-wing aircraft, helicopters often have three landing gear points (typically two main gears and one nose/tail gear). For a safe and stable landing, it is absolutely imperative that all three landing gears touch down simultaneously and level.

An uneven touchdown, even by a fraction of a second or a slight tilt, can lead to severe and potentially catastrophic problems:

Tail Rotor Strike: If the helicopter's nose pitches forward due to an uneven main gear touchdown, the tail rotor, which is often the lowest point at the rear, can strike the deck. This can cause immediate and severe damage to the helicopter, leading to a loss of control and a forward pitching moment of the nose.

Instability and Rollover: Landing with one or two gears touching first can create an unstable pivot point. In the dynamic environment of a moving ship deck, this instability is greatly amplified, increasing the risk of the helicopter tipping over or rolling, especially if there's any sideward movement.

Structural Damage: The landing gear is designed to absorb the energy of touchdown when the force is distributed evenly. An uneven landing concentrates immense stress on a single gear or a limited part of the airframe, potentially leading to gear collapse, structural damage, or even a "gear-up" or "partially extended" landing scenario.

Loss of Control: Any damage or instability upon touchdown can quickly escalate into a loss of control, endangering both the aircraft and personnel on deck.

AMPLS's advanced control algorithms, meticulously informed by the LSTM's predictions and refined through RL, are specifically designed to ensure this perfect, three-point touchdown, minimizing stress on the airframe and maximizing safety.



4.5. Model Export: ONNX Format
The culmination of this intensive training is AMPLS: a robust, intelligent agent capable of navigating the most treacherous maritime conditions. To ensure its real-world applicability and efficient deployment, the trained AI model is then exported into the industry-standard ONNX (Open Neural Network Exchange) format. This allows for seamless integration into various hardware platforms, paving the way for future real-world testing and eventual operational use, ensuring that our research can transition from simulation to practical application.



5. Key Features & Advantages
Autonomous Operation: Enables helicopters to land without direct human piloting in extreme conditions.

Enhanced Safety: Minimizes human exposure to hazardous flight deck environments.

Precision Landing: Utilizes LSTM for accurate prediction of ship quiescent periods, optimizing touchdown timing.

"Beyond Human" Capabilities: Achieves superior performance in Sea State 6.5-7 through advanced RL.

Robustness: Combines Imitation Learning for foundational skills with Reinforcement Learning for adaptability.

Critical Touchdown Assurance: Ensures simultaneous, level three-point landing gear touchdown to prevent damage and instability.

High-Fidelity Simulation: Developed and tested in a realistic Unity 3D environment.

Deployment Ready: Exported to ONNX format for broad compatibility and future real-world integration.

6. Getting Started (Simulation)


To run the AMPLS simulation environment and observe the autonomous landing agent:

Prerequisites:

Unity Hub and Unity Editor (Version 6)

Mlagents version 2.1.1

Python (Version 3.9 or higher)

mlagents package installed: pip install mlagents

Clone the Repository:

Bash

git clone https://github.com/kulkarni618/AMPLS.git
cd AMPLS
Open in Unity:

Open Unity Hub, click "Add Project," and navigate to the cloned AMPLS directory.

Open the project in the Unity Editor.

Run the Simulation:

Navigate to the Assets/Scenes/ folder and open the AMPLS_Landing_Scene.

Press the "Play" button in the Unity Editor.

(Optional: If you have a pre-trained model to load, you have a seperate section in behavior paramaters section in inference mode in inspector tab.)

Observe: The simulation will begin, and the autonomous helicopter agent will attempt landings on the dynamically moving ship.

7. Future Work
The AMPLS project is a foundational step towards fully autonomous maritime aviation. Future work includes:

Real-World Validation: Transitioning the trained models from simulation to physical hardware for real-world flight testing.

Sensor Integration: Developing robust sensor fusion techniques for real-time environmental perception on physical platforms.

Adaptive Control: Further enhancing the AI's adaptability to unforeseen environmental variables and emergency scenarios.

Multi-Agent Coordination: Exploring scenarios involving multiple autonomous aircraft or coordinated ship-helicopter maneuvers.

Long-Term Autonomy: Researching methods for continuous learning and adaptation in operational environments.

8. Contributing
We welcome contributions to the AMPLS project! If you're interested in improving the simulation, enhancing the AI models, or exploring new features, please refer to our(CONTRIBUTING.md) for guidelines.

9. License
This project is licensed under the(LICENSE) 

10. Contact
For any inquiries or collaborations, please reach out to:

Your Name/Team Name:

LinkedIn (Optional): [www.linkedin.com/in/mandar-kulkarni-78474918a]
