# Crema (Modified for CCM Course)

**Convolutional and Recurrent Estimators for Music Analysis** - Edited Version

This version of the CREMA project has been modified for a **Computational Cognitive Modeling** course project. The modifications include the addition of **experimental stimuli**, changes in **model analysis**, and the introduction of **custom scripts** to examine the alignment between human perception of musical chords and the CREMA chord recognition model's feature representations.

[![Testing](https://github.com/bmcfee/crema/actions/workflows/ci.yml/badge.svg)](https://github.com/bmcfee/crema/actions/workflows/ci.yml)  
[![codecov](https://codecov.io/gh/bmcfee/crema/branch/main/graph/badge.svg?token=3FujfyA0jz)](https://codecov.io/gh/bmcfee/crema)  
[![GitHub license](https://img.shields.io/badge/license-BSD-blue.svg)](https://raw.githubusercontent.com/bmcfee/crema/master/LICENSE)  
[![Documentation Status](https://readthedocs.org/projects/crema/badge/?version=latest)](http://crema.readthedocs.io/en/latest/?badge=latest)  
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.1010486.svg)](https://doi.org/10.5281/zenodo.1010486)

---

## Overview

The original CREMA model, developed by McFee and Bello (2017), is a deep neural network built for musical chord recognition using convolutional and recurrent layers. It is designed to learn how to classify chords by being trained on complete songs paired with labeled chord annotations. This modified version aims to assess how human perception of chord similarity aligns with the internal feature representations of the CREMA model.

**Reference Paper**: Carone, B. J., et al. *"Do You Hear What I Hear? Assessing the Alignment of Human Perception for Musical Chords with Deep Network Features Using the CREMA Chord Recognition Model"* [2024].  
This project was implemented as a final project for a Computational Cognitive Modeling course.

---

## Usage Options

The usage options remain similar to the original implementation with a few modifications that allow users to interact with the modified CREMA model:

### From the Command-Line
To analyze an audio file in **JAMS** format and display results:

```bash
python -m crema.analyze file.mp3
```

or save to a file:

```
python -m crema.analyze file.mp3 -o file.jams
```


From within python:

```python
from crema.analyze import analyze

jam = analyze(filename='/path/to/file.mp3')
```

or if you have an audio buffer in memory, librosa-style:

```python
jam = analyze(y=y, sr=sr)
```

## Project Modifications and Additions

### 1. Experiments and Stimuli
- The **`experiments/`** folder contains the stimuli used for this project, including 48 versions of a common ii-V-I progression recorded on guitar and piano.
- The reference recordings are Gmaj7 and Cmaj7, while the test stimuli include variations of the final chord in different conditions (e.g., root variations, out-of-key substitutions).
- The experimental files were generated to assess how **human perception** of chord similarity compares to the model's interpretation.

### 2. Course Context
This project was carried out as a final project for a **Computational Cognitive Modeling** course at New York University. The goal was to explore the intersection of **machine learning** and **human auditory perception**, using the CREMA chord recognition model as a basis for comparison against human participants' similarity judgments.

### 3. Custom Analysis Code
- **Modified Analysis Pipeline**: We adapted the analysis scripts to batch process stimuli (instead of analyzing single files) and extract hidden feature representations from the model for each audio file.
- **Experimental Data Collection**: Data on human similarity judgments were collected and stored in the **`experiments/`** directory, alongside the stimuli used in the study.
- **Distance Metrics**: Custom Python scripts were added to calculate the **sum of absolute differences** and **Frobenius norm** between the CREMA model's feature representations and human judgments.

---

## Results Summary

The results of the project show a generally inverse relationship between human similarity ratings and the CREMA model's distance metrics. Specifically:

- The **CREMA model** provides more granular distinctions between chords, likely due to its ability to directly analyze spectrogram features.
- Participants with higher **musical sophistication** showed greater discrimination between out-of-key and in-key chords, aligning more closely with the model's outputs.

For further details on the results, please reach out to me at bcarone@nyu.edu.

