---
layout: post
title:  "利用强化学习（DQN, DDPG）玩转 GYM GAMES"
date:   2018-07-30 09:07:30 +0800
tags: 
  - Gym
  - Games
  - DQN
  - DDPG
---


这个项目主要用于记录利用增强学习算法玩转 GYM 游戏的实现过程。

## 环境准备

利用 ALIYUN ECS 机器搭建了一个 Jupyter 平台，可以方便的在线编辑代码并进行训练，更重要的是价格还便宜。一个抢占式的实例每小时只需要0.17元。


<!--more-->

## Gym Games


### FlappyBird-v0

[Source Code](https://github.com/lxiongh/RL-Gym/tree/master/FlappyBird-v0)

目前实现了 DQN 算法玩 FlappyBird-v0, 迭代了400+的模型能够完成 5 分钟的自主飞行。


{% asset_img FlappyBird-v0-dqn_agent.gif flappybird agent %}


### CartPole-v1


DQN 算法迭代学习过程.

{% asset_img CartPole-v1-dqn_agent.gif  cartpole %}

### LunarLander-v2

[Source Code](https://github.com/lxiongh/RL-Gym/tree/master/LunarLander-v2)


{% asset_img LunarLander-v2-dqn_agent.gif lunarlander %}


### Pendulum-v0

[Source Code](https://github.com/lxiongh/RL-Gym/tree/master/Pendulum-v0)


DDPG 算法实现连续动作空间的学习

{% asset_img Pendulum-v0-ddpg_agent.gif pendulum %}
