# Trajectory Planning
The goal of this project is to train a neural network for driving a car in the [Udacity self-driving simulator](https://github.com/udacity/self-driving-car-sim) and help it keep on the road.

## List of contents
- Prerequisites
- What is in each file?
- Training the model
- [Testing the model](#testing-the-model)
    - [No traffic](#no-traffic)
    - [Dynamic traffic](#dynamic-traffic)
- Further work

## Prerequisites
- Python 3
- Tensorflow
- OpenCV

## What is in each file?
#### DataProc
- Contains the code to load and process the data from the simulator.
#### Model
- Functions to make the convolutional and fully connected layers.
- A network function which defines the neural network architecture.
#### Train
- This is the main file that is used to train the model and save it.

## Training the model
The data file created by the Udacity simulator should be saved in the same directory as the python files, as in the repo. All the images should be saved in the `images` folder.
The data file should contain either the relative or absolute paths to the images.
The command to be used to train the model is as follows
`python3 Train.py --datafile <path_to_datafile> --save_dir <dir_to_save_tf_model> --summary_dir <dir_to_save_tf_summary>`
Some optional arguments with the default values in the parenthesis-
- `--num_epochs` the number of epochs (200)
- `--minibatch_size` size of the minibatch to be used (128)
- `--log_file` path to an existing or new file - a log of training is written in this file (log.txt).

## Testing the model

### No traffic
[Download](https://github.com/udacity/self-driving-car-sim) the Udacity simulator Version 2 and make the file executable:
```shell
sudo chmod +x beta_simulator.x86_64
```
Run the simulator, choose the `Jungle` track and `Autonomous Mode`.  
Run the pre-trained model:
```shell
python3 test_h5.py model.h5
```

### Dynamic traffic

Download the Term 3 simulator from the latest [release](https://github.com/udacity/self-driving-car-sim/releases) and make the file executable:

```shell
sudo chmod +x term3_sim.x86_64
```

Install dependencies:
```shell
cd test
sh install-ubuntu.sh
```

The testing code is present in [main.cpp](test/src/main.cpp)  
From the main directory, follow these commands to compile the code:
```shell
cd test/build
cmake .. && make
```
Start the Udacity simulator by running `term3_sim.x86_64`
Run the testing code from inside the build folder:
```shell
./path_planning
```

## Further Work
- Switch to a better simulator, with traffic and realistic conditions.
- Use Reinforcement Learning instead of Supervised Learning.