# Revive Lives - Drug Presence Detection using Python + OpenCV2
## Summary
Our project uses python and OpenCV2 along with green light detection to detect a person's heartbeat. Using the heartbeat we are able to approximate the presence of drugs in the users body and accordingly carry out other tasks.


- Video Magnification Source: https://people.csail.mit.edu/mrub/vidmag/
- Python to MAC OS APP: https://py2app.readthedocs.io/en/latest/

## Download and use the .app file or follow the guide below to run it in python

# Process to run
- git clone into the repository
- open terminal on your operating system (CMD for windows, terminal for MACOS)
- Ensure python 3 is installed on your system, you can do this by running 
- ```python -- version```
- cd into the folder example 
 ``` cd C:/users/username/revive-lives```
- then run python get_pulse.py to start the detection process

# Running the Jupyter Notebook
- Import notebook into google colab
- Run ALL Cells

# How it works:

-----------------

This project locates the user's face using [OpenCV](http://opencv.org/), after which it isolates the forehead area. The user's heart rate is calculated using data that is gathered over time from this place. To do this, the green channel of the subimage alone is used to measure the average optical intensity at the forehead location (a better colour mixing ratio may exist, but the blue channel tends to be very noisy). The optical absorption properties of (oxy-) haemoglobin (see http://www.opticsinfobase.org/oe/abstract.cfm?uri=oe-16-26-21434) allow for the estimation of physiological parameters in this method.

In roughly 15 seconds, a stable heartbeat should be isolated with good lighting and little motion-related noise. The raw data stream should also show other physiological waveforms, such as [Mayer waves](http://en.wikipedia.org/wiki/Mayer waves)]. Real-time phase variation related to this frequency is also calculated after the user's heart rate has been determined. This makes it possible to amplify the heartbeat in the post-process frame rendering, which makes the highlighted area of the forehead pulse in time with the user's own heartbeat.

# Final Product Idea:
Since a large amount of the Indian population has access to a smartphone and an internet connection we wanted to make use of the resources at hand to help reduce drug abuse. 
- Rewarding Idealogy ('Make the User feel like they are getting something out of not taking drugs')
	- Current Plan: Allowing longer screen times
	- Future Plan: Partner with brands to give access to offers on medication and other goods and services
- Connect Patients directly to their doctors or help assign one if they're a recently discovered abuser
- Initial Questionnare to check if the user is sobre, if they don't check their devices and answer a set of basic questions the device will be locked. Failing to respond within a set amount of time, roughly an hour to half an hour would lead to an SOS message being sent to emergency services since it is likely the user is unconsious due to a drug overdose.
- We use a technique similar to what smartwatches use known as Photo-plethysmography
- Face and a fixed point is marked using OpenCV2 and the harr cascade facial features model
- Next the users heart rate is estimated, sustained low or high heartbeat's are an initial sign of drug abuse. For a recurring user, this will act as a trigger to send a warning to their doctors or one that is designated by us.
- Another thing to be added is the QSAR model (Quantitative Structure-Activity Relationship), each drug has it's own biological molecular descriptors. The presence of these descriptors can be defined by a binary value as shown in the dataset used. The CHEMBL database has descriptor's for each molecule known to mankind. Test's often reveal lot's of information that normal people find hard to understand. Using the Pa-DEL Descriptor, we carry out predictions on the basis of text files containing molecular structures. This may help doctors, labs and us, normal people(user) to understand test results better. Additionally, it can act as proof and track record of someone being 'clean' or 'sobre'. This is an aspect that requires more work from our part, however we managed to reach training a machine learning model.
- Combining the webcam based pulse rate measurement, questionnare, QSAR Model, rewards and direct connections with doctors was not feasible in the given time frame.
- Our initial goal is to target drug addicts, however our idea in general can be slightly remodelled to fit other addiction's as well. Such as Alcohol and more.
- We also would like to hire/partner with licensed psychologists and doctors to give our customers the help they need and at the time they need it.
- Since no app can be sustainable without a proper business model, for those who have assigned doctors; we would add a markup fee to generate revenue; However in the case of those that are new or clean, they may access the service entirely free of cost for a limited number of times.

Although it is possible to support detection on many individuals at once in an image stream from a single camera, only one face's worth of data is currently extracted for analysis.

# Reference Heart Rate Values:
<img src = "https://raw.githubusercontent.com/bebochakravarti/Revive-Lives-/main/heart%20rate%20.png"></img>

The real-time signal processing's entire dataflow and execution sequence looks like:
