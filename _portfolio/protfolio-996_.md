---
title: "Markerless pose tracking and anlaysing"
excerpt: "<br/><img src='/images/pose.gif'  width='600'>"
collection: portfolio
---

Traditionally, gait parameters analysis needs expensive equipment and professionals to gather data from patients, which means they are time-consuming and expensive tasks. Therefore, a system that can analyse gait parameters using light vision based approach is desired.

This project is led by Xuqi Zhu who is a final year CSEE student at University of Essex, and jointly supervised by Dr Bernard Liew and myself, it is about building a reliable computer vision based processing system to analyse human gait parameters using Mediapipe (A Python library for extracting body joint points provided by Google), which will provide basic clinical data for specialists to have further analysis, for example, providing a rough estimate the recovery progress for the patient with related disease. 

## BlazePose
The joint angle is one of the important kinematic parameters in human gait analysis, we use [BlazePose](https://arxiv.org/abs/2006.10204) (i.e. a dedicated lightweight deep learning architecture) to predict key points of human body in this project.

<img src="/images/body_landmarks.png" width="400">
<img src="/images/skeleton.png" width="400">
<img src="/images/walking2.gif" width="400">


## Kalman Filter
Due to limited accuracy of the prediction model and body overlapped, it is inevitable to avoid detection failed during target movement. But most of the time, the target loss only occurs in a short period of time, therefore, a Kalman filter is introduced to correct the target's state prediction.

<img src="/images/KF.png" width="400">

KF performance with different α and β (joint visibility threshold = 0.4

<img src="/images/KF_knee_left_24.png" width="400">
<img src="/images/KF_knee_left_35.png" width="400">

## Filter based on Discrete Time Fourier Transform
Although the KF algorithm can solve joint angle loss when joint visibility below the threshold, it has limited effects on removing extreme values and waveform distortion. Thus, the time series signal needs further filtering to drop noise and smooth the curve. Usually, the extreme values and waveform distortion were caused by noises with relative low energy in energy density spectrum. In order to pick the necessary frequency components and reduce the noise. The Fast Fourier Transform (FFT) is applied to transform time series signal into frequency domain for constructing a filter based on energy density distribution. After filtering the noise, the signal needs be recovered from frequency domain, that required inverse option of the FFT to reconstruct the filtered signal in time
domain. 

<img src="/images/DTFTIDTFT.png" width="400">

F_PG1_Subject_40_L knee joint angle signal on frequency domain

<img src="/images/FrequencyDomain_40_Left.png" width="400">
<img src="/images/FrequencyDomain_40_right.png" width="400">

Compare performance of two strategies(Pick 5 frequency components)

<img src="/images/DFT_F_v3d_Subject_39.png" width="400">
<img src="/images/DFT_F_v3d_Subject_40.png" width="400">


## News


