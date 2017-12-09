# RL with Atari

## Install

First, install gym and atari environments. You may need to install other dependencies depending on your system.

```
pip install gym
```

and then install atari with one of the following commands
```
pip install "gym[atari]"
pip install gym[atari]
```

We also require you to use a version greater than 1 for Tensorflow.


## Environment

### Pong-v0

- We play against a decent AI player.
- One player wins if the ball pass through the other player and gets reward +1 else -1.
- Episode is over when one of the player reaches 21 wins
- final score is between -21 or +21 (lost all or won all)

```python
# action = int in [0, 6)
# state  = (210, 160, 3) array
# reward = 0 during the game, 1 if we win, -1 else
```

We use a modified env where the dimension of the input is reduced to

```python
# state = (80, 80, 1)
```

with downsampling and greyscale.

## Training

Once done with implementing `q2_linear.py` (setup of the tensorflow necessary op) and `q3_nature` make sure you test your implementation by launching `python q2_linear.py` and `python q3_nature.py` that will run your code on the Test environment.

You can launch the training of DeepMind's DQN on pong with

```
python q5_train_atari_nature.py
```

The default config file should be sufficient to reach good performance after 5 million steps.

You can monitor your training with Tensorboard by doing, on Azure

```
tensorboard --logdir=results
```

and then connect to `ip-of-you-machine:6006`




**Credits**
Assignment code written by Guillaume Genthial and Shuhui Qu.# DQN-cs234