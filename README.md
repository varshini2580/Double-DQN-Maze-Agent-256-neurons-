# Maze Navigation with Deep Q-Learning

This project implements a Deep Q-Network (DQN) agent that learns to navigate through a maze environment using reinforcement learning. The agent uses a neural network to approximate the Q-function and learns to find the optimal path from a starting point to a destination in a maze.

## Project Structure

```
Model C/
├── neurons/
│   └── mazegame_modified/
│       ├── simulations/
│       │   ├── agents/          # RL agent implementations
│       │   ├── envs/            # Environment definitions
│       │   ├── Utils/           # Utility functions
│       │   ├── connected_maze_training.py  # Main training script
│       │   ├── maze_simulation.py         # Simulation visualization
│       │   ├── config.json      # Configuration parameters
│       │   ├── dqn_model.pth    # Trained model weights
│       │   └── training_data.xlsx # Training metrics and logs
```

## Features

- Customizable maze environment
- Deep Q-Network (DQN) implementation with Double DQN improvements
- Training visualization
- Performance metrics tracking
- Pre-trained model included

## Neural Network Architecture

The DQN uses the following architecture:

```
Input Layer:  N×N neurons (where N is the maze size, one-hot encoded state representation)
Hidden Layer 1: 256 neurons with ReLU activation
Hidden Layer 2: 256 neurons with ReLU activation
Output Layer: 4 neurons (one for each possible action: up, down, left, right)
```

Key parameters:
- Input dimension: N×N (where N is the maze size)
- Hidden layers: 2 fully connected layers with 256 neurons each
- Output dimension: 4 (one for each action)
- Activation: ReLU for hidden layers, linear output

## Prerequisites

- Python 3.6+
- PyTorch
- NumPy
- Matplotlib
- OpenCV (for visualization)
- Pandas (for data logging)

## Installation

1. Clone the repository:
   ```bash
   git clone [your-repository-url]
   cd Model-C
   ```

2. Install the required packages:
   ```bash
   pip install -r requirements.txt
   ```

## Usage

### Training the Agent
To train the DQN agent on the maze environment:

```bash
python neurons/mazegame_modified/simulations/connected_maze_training.py
```

### Running the Simulation
To visualize the trained agent navigating the maze:

```bash
python neurons/mazegame_modified/simulations/maze_simulation.py
```

## Configuration

Modify `config.json` to adjust training parameters:
- `learning_rate`: Learning rate for the optimizer
- `gamma`: Discount factor for future rewards
- `epsilon`: Exploration rate (initial value)
- `epsilon_min`: Minimum exploration rate
- `epsilon_decay`: Rate at which exploration decreases
- `batch_size`: Size of training batches
- `episodes`: Number of training episodes

## Results

Training progress and metrics are saved in `training_data.xlsx`, including:
- Episode rewards
- Steps per episode
- Epsilon values
- Loss values

## Visualization

Use `generate_all_plots.py` to generate performance plots from the training data.

## License

[Specify your license here]

