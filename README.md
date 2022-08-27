# Team Fruit Basket - Drug Presence Detection using OpenCV2
## Summary
Our project uses python and OpenCV2 along with green light detection to detect a person's heartbeat. Using the heartbeat we are able to approximate the presence of drugs in the users body and accordingly carry out other tasks.


Video Magnification Source - https://people.csail.mit.edu/mrub/vidmag/

# Process to run
- git clone into the repository
- open terminal on your operating system (CMD for windows, terminal for MACOS)
- Ensure python 3 is installed on your system, you can do this by running 
- ```python -- version```
- cd into the folder example 
 ``` cd C:/users/username/fruit-basket-hackJBCNOsh```
- then run python get_pulse.py to start the detection process

# How it works:

-----------------

This project locates the user's face using [OpenCV](http://opencv.org/), after which it isolates the forehead area. The user's heart rate is calculated using data that is gathered over time from this place. To do this, the green channel of the subimage alone is used to measure the average optical intensity at the forehead location (a better colour mixing ratio may exist, but the blue channel tends to be very noisy). The optical absorption properties of (oxy-) haemoglobin (see http://www.opticsinfobase.org/oe/abstract.cfm?uri=oe-16-26-21434) allow for the estimation of physiological parameters in this method.

In roughly 15 seconds, a stable heartbeat should be isolated with good lighting and little motion-related noise. The raw data stream should also show other physiological waveforms, such as [Mayer waves](http://en.wikipedia.org/wiki/Mayer waves)]. Real-time phase variation related to this frequency is also calculated after the user's heart rate has been determined. This makes it possible to amplify the heartbeat in the post-process frame rendering, which makes the highlighted area of the forehead pulse in time with the user's own heartbeat.

Although it is possible to support detection on many individuals at once in an image stream from a single camera, only one face's worth of data is currently extracted for analysis.

The real-time signal processing's entire dataflow and execution sequence looks like:
