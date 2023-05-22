## Chrome Dino-AI

This repository contains code for training a Reinforcement Learning agent to play the dinosaur game using the DQN algorithm. The DQN model is implemented using the stable-baselines3 library.

#Dinosaur Game Environment

The Dinosaur Game environment is defined in the dino class, which is a subclass of the Env class from the OpenAI Gym library. The environment provides an interface for interacting with the game and captures screen images to be used as observations. Here are some key features of the environment:

#Observation Space: The observation space is defined as a grayscale image with dimensions (1, 83, 100). Each observation is a 1-channel image of size 83x100 pixels.

#Action Space: The action space consists of three discrete actions: 'space', 'down', and 'no_op' (no operation). The agent can press the corresponding keys to perform these actions in the game.

#Capture and Preprocessing: The environment captures the game screen using the mss library and performs preprocessing on the captured images. The images are converted to grayscale, resized to (100, 83), and reshaped to match the observation space dimensions.

#Game Over Detection: The environment uses optical character recognition (OCR) with the pytesseract library to detect if the game is over. It captures a portion of the screen that displays the game over message and checks if the recognized text matches predefined strings ('GAME' or 'GAHE').
Step and Reset: The step method takes an action as input, simulates the action in the game, captures a new observation, checks if the game is done, and returns the new observation, reward (always 1), done status, and an empty info dictionary. The reset method resets the environment by simulating a click and pressing the 'space' key.
Render and Close: The render method displays the game screen using OpenCV, and the close method closes the display window.
Training the DQN Model

To train the DQN model, the DQN class from the stable-baselines3 library is used. Here's an example of how to initialize the model:
model = DQN('CnnPolicy', env, verbose=1)

Make sure to replace env with an instance of the dino class, which represents the Dinosaur Game environment.

#Installation and Usage
To run the code in this repository, follow these steps:

#Clone the repository:
git clone https://github.com/VibhuRaj01/Chrome-Dino-AI
cd Chrome-Dino-AI

#Contact
If you have any questions or inquiries, please contact @vibhuraj01.
