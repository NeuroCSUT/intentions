# Do Deep Reinforcement Learning Agents Model Intentions?

This is the code for implementing the intention reading and generalization experiments in the paper:
[Do Deep Reinforcement Learning Agents Model Intentions?](https://arxiv.org/abs/1805.06020).
It is using the `simple_spread` environment from the
[Multi-Agent Particle Environments (MPE)](https://github.com/openai/multiagent-particle-envs).

## Installation

- To install, `cd` into the root directory and type `pip install -e .`

- Known dependencies: OpenAI gym, tensorflow, numpy, also Scikit-Learn and Matplotlib for plotting.

## Re-running the experiments

- Download and install the MPE code [here](https://github.com/openai/multiagent-particle-envs)
by following the `README`.

- To run the code, `cd` into the `experiments` directory and run `experiment.sh`:

  - ``./experiment.sh coop_navi_0`` - for basic MADDPG agents
  - ``./experiment.sh coop_navi_shared_0 --shared`` - for MADDPG + shared scheme, all agents use shared model
  - ``./experiment.sh coop_navi_shuffle_episode_0 --shuffle episode`` - for MADDPG + shuffle scheme, agents are shuffled for each episode
  - ``./experiment_ensemble.sh coop_navi_ensemble_episode_0 --ensemble-choice episode`` - for MADDPG + ensemble scheme, agents are sampled for each episode

## Individual scripts

- `train.py` - basic training script, also used for evaluation
- `ensemble.py` - ensemble training script, also used for evaluation
- `learning_curve.py` - plots learning curve of an experiment
- `statistics.py` - collects basic benchmark data from evaluation
- `prepare.py` - simplifies evaluation data for further processing
- `prepare_ensemble.py` - simplifies evaluation data for further processing, for ensemble results
- `accuracy.py` - calculates per-timestep target prediction accuracies
- `figure.py` - plots target prediction accuracies for all agents
- `sheldon.py` - runs evaluation against Sheldon agents (agents with fixed targets)
- `sheldon_ensemble.py` - runs evaluation against Sheldon agents, for ensemble results

For usage details refer to `experiment.sh` and `experiment_ensemble.sh` scripts and individual files.

## Paper citation

If you used this code for your experiments or found it helpful, consider citing the following paper:

<pre>
@article{matiisen2018do,
  title={Do deep reinforcement learning agents model intentions?},
  author={Matiisen, Tambet and Labash, Aqeel and Majoral, Daniel and Aru, Jaan and Vicente, Raul},
  journal={arXiv preprint arXiv:1805.06020},
  year={2018}
}
</pre>
