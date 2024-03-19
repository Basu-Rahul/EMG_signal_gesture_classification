# EMG_signal_gesture_classification

Introduction 
Hand gesture classification breathes life into hand movements, enabling them to control devices, navigate interfaces, or even translate sign language.
Imagine using your hand to flip through virtual channels, play music, or have a conversation without speaking. This technology captures hand movements through cameras or sensors, extracts key features like finger positions and palm orientation, and then uses machine learning to decipher the intended gesture.
This holds immense potential. From controlling devices without buttons to creating a more interactive virtual reality experience, hand gesture classification is paving the way for intuitive and natural communication between humans and technology. It even holds promise for bridging the gap between the hearing and deaf communities through sign language recognition. 
Measuring muscle activation via electric potential, referred to as electromyography (EMG), with the advent of ever shrinking yet more powerful microcontrollers and integrated circuits, EMG circuits and sensors have found their way into prosthetics, robotics and other control systems. 
Methodology
The aim of the project is classification of dynamic hand gestures using EMG signals as input and ML implementation to run the analysis . Input is taken using electrodes and muscle sensor and analog signals are collected using Aduino UNO. 
Next we preprocess the data, based on our conditions we found a frequency domain representation gave much better output than time domain. So, we took 240 point DFT of the signal and then normalised it to be used as model input. So we had 120 features and 1 target were the gesture observed was given an ordinal encoding. For our model, we took 
Random Forest Classifier and final result we took as a confusion matrix, to measure the ability to classify the gestures.





Gestures we have focused on pattern of 1-2-1 were transition takes place in middle.
Each gesture sample is of average 30s with first 10s, in position '1', then 10s in position '2' and last 10s in position '1' again.
Dataset comprises of 22 samples each of 5 gesture patterns.
Data collection is done by the project mentees.
 The patterns we are detecting are:
a. Open palm - Closed fist - Open palm
b. Closed fist - Radial deviation - Closed fist
c. Extension - Flexion - Extension
d. Supination - Pronation - Supination
e. Pinch grip - Open palm - Pinch grip


