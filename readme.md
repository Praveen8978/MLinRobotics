# 7-DOF Robotic Arm Simulation with Gymnasium and Mujoco

This project simulates a 7-degree-of-freedom (7-DOF) robotic arm using the Gymnasium framework and the Mujoco physics engine. The setup includes a customized push task environment, where the robotic arm interacts with a golf ball and a target.

## Requirements

To run this project, ensure you have the following software installed:

- Python version 3.9 or above

### Libraries Used

The following libraries are required:

- **Gymnasium + Gymnasium Robotics**: For environment creation and interaction with agents.
- **Mujoco**: For physics-based simulations involving robotics.
- **NumPy**: For numerical operations and data management.



Install the necessary libraries using pip:

```bash
pip install gymnasium[robotics] mujoco numpy
```
### Project Structure

    base.py - base script adapted from MujocoRobotEnv from gymnasium-robotics to build our PushingBallEnv environment with Mujoco simulator

    push.py - Defines our custom simulation environment PushingBallEnv() using Gymnasium

    PPO_network.py: This file defines the learning agent using Proximal Policy Optimization (PPO). It includes the neural network architecture and the agent class that performs action selection, policy evaluation, and network updates.

    setup_PPO.py: This is the setup script that integrates the PPO_network.py learning agent with the simulation environment. It configures the environment, runs training episodes, and visualizes the results.

    setup_sb3.py : This is the setup script that trains our environment with the stable baselines3 PPO agent.

    evaluate_model.py - Tests our trained policy in the simulation environment to evaluate performance, visualize rewards and track success rate.

    evaluate_model_sb3.py - Test a policy trained using stable-baseslines3 PPO on the simulation environment

    trained_policy_densenonrandom_1000.pth - our custom policy

    ppo_pushing_ball3.zip - stable_baselines policy

    

#### Running the Project

To run the project:

    Ensure all dependencies are installed.
    Navigate to the directory containing the Python files.
    Run the setup_PPO.py script to register the environment, set up the learning agent, and train the agent using PPO.


This will simulate the robotic arm pushing the ball towards the target using a trained policy. The simulation runs for a specified number of episodes, with policy updates based on the PPO algorithm.
Key Features

    Implements a 7-DOF robotic arm using the Mujoco engine for high-fidelity physics simulation.
    Uses Gymnasium for environment management and agent interactions.
    Integrates a PPO-based learning agent for robust and stable training.
    Visualizes training performance with plots of total rewards, policy loss, value loss, and total loss over time.