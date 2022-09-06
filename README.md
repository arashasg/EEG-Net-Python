# EEG-Net-Python

> Disclaimer: The code was first implemented by M-CNN and C-CNN paper author. I adapted the code to our dataset and made improvements by using channel selection.

In this repository, I used M-CNN and C-CNN architectures to train
a model for the detection of steady-state visually evoked potentials.

The dataset was collected by our group and was funded by the Telecommunication Company of Iran.

The SSVEP dataset contained five classes flickering in different frequencies.
Our sampling frequency was 512hz, and the flickering duration was 5 seconds.
The user interface included icons of an IOT-based automated home. The application had two menus. 
In the first menu, the user could select his task related to which part of the home, and In the second one, they could
choose the change they wanted to make(e.g., turning on or off the lights).

We gathered our data in two phases: 1- Offline mode and 2- Online mode.

### Offline mode
In this phase of data gathering, we asked the subject to concentrate on a specific stimulus.
This phase contained five trials. In each trial, we asked the subject to see all of the stimuli in a random order for 5 seconds.
As a result, for each subject, our offline dataset contained five five-second EEG data for each stimulus.

### Online mode
After training our model using the offline data, five tasks were generated randomly in the online phase, and the subject was asked to see the stimuli corresponding to that task.
The main difference between the online and offline mode is that in the online mode, the second menu is shown to the subject
based on the model's classification using the first menu's EEG data.

### evaluation
Finally, after training our models using the offline data and evaluating it on 
online data, we reached the average accuracy mentioned in the table below.

| Model | Segment Length | Average Accuracy |
|-------|----------------|------------------|
| MCNN  | 1s             | 90%              |
| CCNN  | 1s             | 91%              |
| MCNN  | 2s             | 91%              |
| CCNN  | 2s             | 93%              |
| MCNN  | 3s             | 95%              |
| CCNN  | 3s             | 95%              |


## Refrences

Ravi, Aravind, et al. "Comparing user-dependent and user-independent training of CNN for SSVEP BCI." Journal of neural engineering 17.2 (2020): 026028.
