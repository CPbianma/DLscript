---
type: lab
specialization: Machine Learning Specialization
course: Unsupervised Learning, Recommenders, Reinforcement Learning
week: 3
section: State-action value function
item_title: State-action value function (optional lab)
source_url: https://www.coursera.org/learn/unsupervised-learning-recommenders-reinforcement-learning/ungradedLab/X09lt/state-action-value-function-optional-lab
notebook_path: State-action value function example.ipynb
language: en
extracted_at: 2026-10-10T01:36:06+08:00
status: success
---
# State-action value function (optional lab)

# State Action Value Function Example

In this Jupyter notebook, you can modify the mars rover example to see how the values of Q(s,a) will change depending on the rewards and discount factor changing.

```python
import numpy as np
from utils import *
```

```python
# Do not modify
num_states = 6
num_actions = 2
```

```python
terminal_left_reward = 100
terminal_right_reward = 40
each_step_reward = 0

# Discount factor
gamma = 0.5

# Probability of going in the wrong direction
misstep_prob = 0
```

```python
generate_visualization(terminal_left_reward, terminal_right_reward, each_step_reward, gamma, misstep_prob)
```

