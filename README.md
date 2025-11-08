# Template for Isaac Lab Projects

## 概要

本パッケージは、強化学習を行うためのテンプレートとして用意している。
作成手順も記述しているため、こちらのテンプレートを使用しなくても再現することが可能となる。

## 作成手順

1. プロジェクトを作成する

   ```bash
   cd ~/IsaacLab
   ./isaaclab.sh --new
   ```

2. 以下のように設定する

   ```bash
   [INFO] Installing template dependencies...

   [INFO] Running template generator...

   ? Task type: External
   ? Project path: /home/yuma/
   ? Project name: template_isaac_lab

         RL environment features support according to Isaac Lab workflows
   ┏━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┳━━━━━━━━┳━━━━━━━━━━━━━━━┓
   ┃ Environment feature                             ┃ Direct ┃ Manager-based ┃
   ┡━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━╇━━━━━━━━╇━━━━━━━━━━━━━━━┩
   │ Single-agent                                    │  yes   │      yes      │
   │ Multi-agent                                     │  yes   │      no       │
   │ Fundamental/composite spaces (apart from 'Box') │  yes   │      no       │
   └─────────────────────────────────────────────────┴────────┴───────────────┘
   ? Isaac Lab workflow: Manager-based | single-agent

                                   Supported RL libraries
   ┏━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┳━━━━━━━━━━┳━━━━━━━━━┳━━━━━━━━━━━━━━━━━━━━━━━┳━━━━━━━━━┓
   ┃ RL/training feature          ┃ rl_games ┃ rsl_rl  ┃ skrl                  ┃ sb3     ┃
   ┡━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━╇━━━━━━━━━━╇━━━━━━━━━╇━━━━━━━━━━━━━━━━━━━━━━━╇━━━━━━━━━┩
   │ ML frameworks                │ PyTorch  │ PyTorch │ PyTorch, JAX          │ PyTorch │
   │ Relative performance         │ ~1X      │ ~1X     │ ~1X                   │ ~0.03X  │
   │ Algorithms                   │ PPO      │ PPO     │ AMP, IPPO, MAPPO, PPO │ PPO     │
   │ Multi-agent support          │ no       │ no      │ yes                   │ no      │
   │ Distributed training         │ yes      │ no      │ yes                   │ no      │
   │ Vectorized training          │ yes      │ yes     │ yes                   │ no      │
   │ Fundamental/composite spaces │ no       │ no      │ yes                   │ no      │
   └──────────────────────────────┴──────────┴─────────┴───────────────────────┴─────────┘
   ? RL library: rsl_rl

   Validating specification...
   Generating external project...
     |-- Copying repo files...
     |-- Copying scripts...
     |-- Copying extension files...
     |-- Generating tasks...
     |    |-- Generating 'Template-Template-Isaac-Lab-v0' task...
     |-- Copying vscode files...
   Setting up git repo in /home/yuma/template_isaac_lab path...
     |  Initialized empty Git repository in /home/yuma/template_isaac_lab/.git/

   --------------------------------------------------------------------------------
   Project 'template_isaac_lab' generated successfully in /home/yuma/template_isaac_lab path.
   See /home/yuma/template_isaac_lab/README.md to get started!
   --------------------------------------------------------------------------------
   ```

## 環境構築手順

```bash
pip install -e source/template_isaac_lab/
```

## 実行手順

- 利用可能なタスクを一覧表示する

  ```bash
  python scripts/list_envs.py
  ```

- タスクを実行する

  ```bash
  python scripts/rsl_rl/train.py --task=<TASK_NAME>
  ```

## 開発者用

- `pre-commit`の導入

  ```bash
  pip install pre-commit
  pre-commit install
  ```
