# FoAM Benchmark: 

The first open-source simulated dual-arm system with rich tasks, manipulation scenarios, and the same physics as the real UR3e robot. 
The main body of this dual-arm robot was built by [Yifan Han](https://github.com/HUSTers1). 

## Installation
```bash
# Create a Conda environment
conda env create -f environment_foam-benchmark.yaml

```

## Scenarios 
This project has a total of 12 open source scenarios, each with a different number of subtasks, and is divided into four levels based on the difficulty and type of the tasks.
Each scenario's folder has a similar file structure. Take the example of opening the cabinet drawer in the normal scenarios.
The simulation demos can be generated by running the script `record_sim_episodes.py`. Alternative command lines are provided in `README.md`.
Episodes that meet the successful conditions will be saved in the `data` folder in `.hdf` format.

The initialization position of the manipulated objects can be changed in the `utils.py` file. 
For example, in the open the cabinet drawer scenarios, the pose of the cabinet is controlled by the function `sample_cabinet_pose` in the `utils.py` file.

The motion trajectory of the robot arm can be customized in the file `scripted_policy.py`.
For example, in the open the cabinet drawer scenarios, the motion trajectory of the arm is controlled by the function `generate_trajectory` of the Class `PickAndTransferPolicy` in the `scripted_policy.py` file.

The physical models required for each scenario are stored in the folder `\assets`. The `XML` files of the robot and the background are stored in the `\model` folder. The integrated scenarios are stored in `sim_ee_env.xml` and `sim_env.xml`. They can be directly visualized by `MuJoCo` software. 
You can customize the scenarios by modifying the files in the `/assets` and `/models`.


## Citation

If you find our work helpful, please cite us:

```bibtex
@misc{liu2024foamforesightaugmentedmultitaskimitation,
            title={FoAM: Foresight-Augmented Multi-Task Imitation Policy for Robotic Manipulation},
            author={Litao Liu and Wentao Wang and Yifan Han and Zhuoli Xie and Pengfei Yi and Junyan Li and Yi Qin and Wenzhao Lian},
            year={2024},
            eprint={2409.19528},
            archivePrefix={arXiv},
            primaryClass={cs.RO},
            url={https://arxiv.org/abs/2409.19528},
        }
```

Thank you! If you have any questions about the use of this benchmark, please feel free to contact [Litao Liu](mailto:liulitao6688@gmail.com).


## License

All the code, model weights, and data are licensed under [MIT license](./LICENSE).
