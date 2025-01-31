# Using EpyMARL for RWARE

To register a custom RWARE environment, go to epymarl-rware/src/marl.py file and give the layout of the custom environment. To register the environment just run marl.py file.

To train a RL algorithm on the environment use the command.

```shell
python src/main.py --config=qmix --env-config=gymma with env_args.time_limit=500 env_args.key="marl:your-env-name" save_model=True
```

If common reward is insufficient and individual rewards are needed, ```common_reward=False```.

```shell
python src/main.py --config=qmix --env-config=gymma with env_args.time_limit=500 env_args.key="marl:your-env-name" save_model=True common_reward=False
```


To generate plots of results, run from the root folder, after selecting the required metric.

```shell
 python3 plot_results.py --path ./results/sacred/qmix/your-env-name --metric test_return_mean --save_dir ./plots
```

To render results, run from the root folder, after selecting the required model.

```shell
 python src/main.py --config=qmix --env-config=gymma with env_args.time_limit=25 env_args.key="marl:r-tiny-2ag-v2" checkpoint_path="./results/models/your-model-folder" evaluate=True render=True
```

For readme of EpyMARL, visit [https://github.com/uoe-agents/epymarl/blob/main/README.md](url)
 
