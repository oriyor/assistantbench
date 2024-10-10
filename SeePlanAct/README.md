[//]: # (# SeePlanAct <br> Augmenting SeeAct with planning abilities)

<h1 align="center">SeePlanAct <br> Augmenting SeeAct with planning abilities </h1>

SeePlanAct is a system for <a href="https://osu-nlp-group.github.io/Mind2Web/">generalist web agents</a> based on the SeeAct system. 
Each SeeAct step has two main stages:  
(1) The agent looks at a webpage's screenshot and explains what the next action should be
(2) The explanation is then grounded into an action on an HTML element of the webpage.

SeePlanAct equips SeeAct with two specialized components: planning and memory modules. SeePlanAct has 5 stages:  
(1) The agent analyzes the screenshot of the webpage  
(2) The agent adds to the memory the analysis  
(3) The agent plans the execution of the task  
(4) The agent explains what the next action should be  
(5) The explanation is then grounded into an action on an HTML element of the webpage

SeePlanAct backbone uses LLM models with multi-modal abilities. We currently support using GPT-4V and Claude-3.5 as backbone model, and we plan on extending it to Open-Source models.

<p align="center">
  <img src="https://github.com/oriyor/assistantbench/blob/main/images/spa.png" />
</p>

<p align="center">
<a href="https://osu-nlp-group.github.io/SeeAct/](https://assistantbench.github.io/">Website</a> •
<a href="https://arxiv.org/abs/2401.01614](https://arxiv.org/abs/2407.15711">Paper</a> •
<a href="https://x.com/OriYoran/status/1815379062677762073">Twitter</a>
</p>


## Setup Environment

1. Create a conda environment and install dependency:
```bash
conda create -n seeact python=3.10
conda activate seeact
pip install -r requirements.txt
```

2. Set up PlayWright and install the browser kernels.
```bash
playwright install
```


## Running Web Agent
**To run with GPT-4V, please fill your API key in the configuration file at `src/config/demo_mode.toml` before running SeeAct. To run with Claude-3.5 please [configure Boto3](https://boto3.amazonaws.com/v1/documentation/api/latest/guide/quickstart.html) before running.** 

### Demo Mode

You can run the Demo Mode using

```bash
cd src
python seeplanact.py
```
You will then be asked to enter a `task description`. If you press enter, the task accomplished will be the task in the default configuration. Demo mode will use the default configuration file at `src/config/demo_mode.toml`. 

### Auto Mode

You can also automatically run SeePlanAct on a list of tasks and websites in a JSON file. 
Run SeeAct with the following command:

```bash
cd src
python seeplanact.py -c config/auto_mode.toml
```
In the configuration file, `task_file_path` defines the path of the JSON file.
It is default to `../data/online_tasks/sample_tasks.json`, which contains a variety of task examples.

## Credits

SeePlanAct and its code base is based on the great work SeeAct. [[1]](#1).

## Contact

Questions or issues? File an issue or contact 
[Ori Yoran](mailto:ori.yoran@cs.tau.ac.il),
[Samuel Joseph Amouyal](mailto:samuel.amouyal@cs.tau.ac.il)

## Citation Information

If you find this work useful, please consider citing our paper: 

```
@article{Yoran2024AssistantBenchCW,
  title={AssistantBench: Can Web Agents Solve Realistic and Time-Consuming Tasks?},
  author={Ori Yoran and Samuel Joseph Amouyal and Chaitanya Malaviya and Ben Bogin and Ofir Press and Jonathan Berant},
  journal={ArXiv},
  year={2024},
  volume={abs/2407.15711},
  url={https://api.semanticscholar.org/CorpusID:271328691}
}
```

## References
<a id="1">[1]</a> 
Zheng, B., Gou, B., Kil, J., Sun, H., & Su, Y. (2024).
GPT-4V(ision) is a Generalist Web Agent, if Grounded.
Arxiv.
