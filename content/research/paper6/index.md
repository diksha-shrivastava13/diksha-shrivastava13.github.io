---
title: "Analysis of Neural Correlates of Different Music Genres using Machine Learning" 
date: 2022-06-12
lastmod: 2024-07-12
tags: ["Cognitive Science","f-MRI","Machine Learning","Psychophysics"]
author: ["Diksha Shrivastava", "Dr. Anuj Bharti"]
description: "" 
summary: "We apply SVM-based classification to fMRI data, analyzing superior temporal gyrus (STG) activity across ten music genres. Preprocessing is done in SPM12, with feature extraction using an STG mask and classification via PRONTO V3.0. Results reveal distinct genre-specific neural patterns, enabling accurate decoding of music perception and bridging neuroscience with AI." 
cover:
    image: "paper1.png"
    relative: false
editPost:
    URL: https://www.fechnerday.com/fd2022/
    Text: "Fechner Day 2022, International Society for Psychophysics (later withdrawn)"
---

##### Abstract [(pdf)](Diksha_abstract.pdf)

Human brain follow a modular approach, i.e. different classes of stimuli are process in
different brain regions. Auditory stimuli processing is also dependent on the category
(e.g. sentences and music are having different neural patterns) (Rogalasky et al., 2011).
Further to add, music perception is highly dependent on behavioural traits such
experience of the music (Chapin et al., 2010). <br><br>
Nakai, Koide-Majima, and Nishimoto (2020) has experiment with 10 music genres and
processed the fMRI scans of 5 subjects. They have reported that superior temporal
region (STG) was having different pattern for different music genres, which was
capable of classifying the neural activity through data analysis approach. <br><br>
We have acquired the fMRI data of their experiment (from
https://openneuro.org/datasets/ds003720/versions/1.0.0) and applied machine learning
for automatic classification of neural activity for different music genres. The data
contains fMRI scans for 5 subjects and each subject gone through 12 training runs and 6
test runs. In each training run 10 music genre played in random order for 15 seconds
each, after intimating the genre name. In test run, 10 music genres were played for
15 seconds each but without intimating the name of genre. <br><br>
The preprocessing of the data is done in SPM 12 and for machine learning, PRONTO
V3.0 was used. To make the feature efficient we limited the feature calculation to STG
only. The STG mask was created SPM anatomy toolbox. For each training run, a voxel
based feature set was prepared. Using the label from design matrix, a supervised
machine learning algorithm (support vector machine-SVM) has been applied. <br><br>
The results shows that SVM was able to classify the music genres with significantly
better accuracy.
