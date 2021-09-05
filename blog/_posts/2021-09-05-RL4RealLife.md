---
layout: post
date: Sun Sep 05
title: Paper Accepted in 2021 Reinforcement Learning for Real Life Spotlight Session
name: Paper Accepted in 2021 Reinforcement Learning for Real Life Spotlight Session
---

The joint work of Professer Xinyun Chen, Pengyi Shi and Our PhD student
Xiuwen Wang, *Data-Pooling Reinforcement Learning for Personalized
Healthcare Intervention*, was accepted by 2021 Reinforcement Learning
for Real life Workshop and presented in the spotlight session on July
23, 2021.

![Presentation. Recording can be found at
https://slideslive.com/38964693/spotlight](/images/blog/RL4RealLife/screen.png)

Reinforcement learning (RL) is a general learning, predicting, and
decision making paradigm and applies broadly in many disciplines,
including science, engineering and humanities, which has seen prominent
successes in many problems, such as games, robotics, recommender
systems. However, applying RL in the real world remains challenging. In
our work, we focus on personalized post-discharge intervention problem
modeled by Markov decision process(MDP). It is a cost minimization
problem to prevent patients' readmission with intervention followup call
to increase patient's adherence to medical advice.

![Illustrate of 30-day post-discharge intervention
problem.](/images/blog/RL4RealLife/hospital.png)

To tackle the small data issue and increase sample efficiency in
personalized intervention problem, we propose a data-pooling RL
algorithm that perform well in a case study on personalized
post-discharge intervention management, with and without budget
constraints, using real hospital data.

![Illustrate of the data-pooling
algorithm.](/images/blog/RL4RealLife/algorithm2.png)

The following figure shows the practical benefits of data-pooling
compared to other benchmarks with data collected in an Asian hospital
between July 2010 and March 2011. 11048 samples in year 2011 are
classified into 21 classes based on the significant medical features to
build the true environments. Then, we learn the intervention policies
for the 21 patient classes pooling with 19013 historical samples of year
2010. The average regret of our method decreases much faster than the
benchmarks, especially in the first 10 iterations.

![Total Regret of 21 patient
classes](/images/blog/RL4RealLife/emp_regret.png)

Moreover, the proposed method can be extended to solve the multipatient
problem with a finite total budget for intervention, which is a common
challenge faced by many hospitals and healthcare organizations. In the
simulation, we applied learning result of data-pooling method with
Whittle index policies, which prioritize the processes with the highest
state dependent indices based on Lagrangian relaxation. Under optimal
intervention, the hospital has 1369 patients to follow up each week. But
we consider that there are at most $N_t$ patients can be followed up.

![Total regret under different level of budget constraint estimated via
1000 rounds of simulation over 8
weeks.](/images/blog/RL4RealLife/BatchVarying_Nt.png)

The above figure shows that the result of data-Pooling method still
outperforms the benchmarks and closest to that of the true value. Base
on those results, we believe that the data-pooling RL algorithm can be
successfully applied to the real life problems and it will provide
guidance to the personalized intervention.

