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
