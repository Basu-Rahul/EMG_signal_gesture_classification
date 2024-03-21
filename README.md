# EMG_signal_gesture_classification

Introduction :

Hand gesture classification breathes life into hand movements, enabling them to control devices, navigate interfaces, or even translate sign language.
Imagine using your hand to flip through virtual channels, play music, or have a conversation without speaking. This technology captures hand movements through cameras or sensors, extracts key features like finger positions and palm orientation, and then uses machine learning to decipher the intended gesture.
This holds immense potential. From controlling devices without buttons to creating a more interactive virtual reality experience, hand gesture classification is paving the way for intuitive and natural communication between humans and technology. It even holds promise for bridging the gap between the hearing and deaf communities through sign language recognition. 
Measuring muscle activation via electric potential, referred to as electromyography (EMG), with the advent of ever shrinking yet more powerful microcontrollers and integrated circuits, EMG circuits and sensors have found their way into prosthetics, robotics and other control systems. 
Our particular interest is to see how to do gesture classification which can be later used as input for design of control systems for rehabilitation and making of prosthetic arm(forearm).


Methodology :

The aim of the project is classification of dynamic hand gestures using EMG signals as input and ML implementation to run the analysis . Input is taken using electrodes and muscle sensor and analog signals are collected using Aduino UNO. 

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



Method 1:

Frequency-domain analysis

Next we preprocess the data, based on our conditions we found a frequency domain representation gave much better output than time domain. So, we took 240 point DFT of the signal and then normalised it to be used as model input. So we had 120 features(one-sided dft) and 1 target were the gesture observed was given an ordinal encoding. For our model, we took Random Forest Classifier and final result we took as a confusion matrix, to measure the ability to classify the gestures.

Method 2:

Time-domain analysis

we tried to focus on first 400 samples of each reading and made 20 length 20 boxes for each we are calculating RMS, variance, absolute mean, integrated emg. Next, we are grouping them based on each subject; trial wise. Later for first trial of each of the gestures we are modifying the array size from (5,20,4) to (100,4). 
Later we divided the collected data in train and test. And train data further into train and validation.
next we are using it as dataset for models and training it with svc, random forest classifier and cnn and compared the accuracies we obtain from them. 
 



Observations & Results:

From both the methods, we could only achieve around 40% to 45% accuracy. We realise the data points are overlapping thus not giving good results.
But, we realise this is due to constraints we unknowingly set before the sample collection was done:

a.  Using combination of two or four instead of one electrode, would have been better for getting unique signatures among the different gestures.

b.  The muscle sensor we used gives rectified and smoothed EMG signal (instead of raw EMG signal), which is easier to work with Arduino UNO, but affects greatly in our 
    classification.

c.  The rectified and smoothed EMG signal works quite well for static gesture detection but for dynamic, makes certain features absent. 


Conclusion:

We got to learn a whole lot of stuff in domains like biomedical signals, machine learning, CNN and likewise. We do get a much clearer picture on real world signals and how hard it is to formulate it into some fixed constraints. We get a good idea of why sophisticated equipments are essential for better feature/signature detection. But it was a somewhat full-filling experience for our first time venturing into this domain. We expect our project can help others who are starting it new. 



