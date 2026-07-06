# CV-AI-task-2

RL RACING CAR USING PPO

A simple autonomous racing car simulation built using Python, Gymnasium, and Stable-Baselines3 (PPO). The project demonstrates how a reinforcement learning (RL) agent interacts with a custom racing environment to navigate a race track while avoiding collisions.

Project Overview:
This project implements a custom racing environment where an AI-controlled car learns to drive on a user-designed race track.
The environment was built from scratch using Gymnasium and trained using the **Proximal Policy Optimization (PPO)** algorithm from Stable-Baselines3.
Although the agent is trained for a limited number of timesteps in this version, the project demonstrates the complete reinforcement learning pipeline, including environment creation, training, testing, and visualization.

Features:
•	Custom Gymnasium Environment
•	Custom Race Track using OpenCV
•	PPO Reinforcement Learning Agent
•	Virtual LiDAR (Ray-Casting) Sensors
•	Expanded Observation Space
•	Checkpoint-Based Navigation
•	Reward Shaping
•	Collision Detection
•	Finish Line Detection
•	Environment Rendering
•	Episode Reward Visualization
GIF Generation of Agent Navigation

ENVIRONMENT:
1. Observation Space:
  The agent observes:
    •	 Car X Position 
    •	 Car Y Position 
    •	 Car Orientation (Angle) 
    •	 Front Sensor 
    •	 Front-Left Sensor 
    •	 Front-Right Sensor 
    •	 Left Sensor 
    •	 Right Sensor
2. Action Space: 
   0-forward
   1-turn left
   2-turn right
   3-brake
3. Reward Function:
   •	Survive one step:  +1
   •	Drive too close to wall:	 -2 (if close) and -5 (if extremely close)
   •	Reach checkpoint: +50
   •	Complete lap:	+500
   •	Collision / Out of bounds: -100
   The reward function was redesigned using reward shaping to encourage the agent to complete the full track instead of simply searching for the finish line.

4. VIRTUAL SENSORS:
   The project includes five virtual LiDAR (ray-casting) sensors that help the agent detect nearby walls.
   These sensors provide distance information in the following directions:
   Front, Front Left, Front Right, Left, Right
   The sensor readings are included in the observation space, allowing the PPO agent to make better driving decisions.

REINFORCEMENT LEARNING (RL) ALGORITHM:
The agent is trained using Proximal Policy Optimization (PPO).
Training parameters include:
•	Policy: MLP (Multi-Layer Perceptron) 
•	Learning Rate: 0.0003 
•	Gamma: 0.99 
•	Batch Size: 64 
•	Number of Epochs: 10 
•	GAE Lambda: 0.95 
•	Clip Range: 0.2 
•	Entropy Coefficient: 0.01 
•	Training Timesteps: 200,000 (can be increased further for improved performance) 

  
 RESULTS:
The project demonstrates:
•	 Autonomous navigation on a custom race track 
•	 Obstacle detection using virtual sensors 
•	 Checkpoint-based path following 
•	 Collision avoidance 
•	 PPO-based policy learning 
•	 Performance evaluation using episode reward graphs 
•	 GIF visualization of the learned path



AUTHOR: Adyasha Sahani
