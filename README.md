# Grasp Type Classifier and missing data prediction
 
 This project uses data pertaining to human grasping.
 With a subject grasping a sequence of objects, we collected data containing their hand joint angles (as measured by a Cyberglove), forearm EMG (collected by a Myo armband) and their true labels.

 The programmed ROS node analysis.py does the following predictions:

 1) If the object label is missing, predict it based on glove data (if present) or EMG data (if glove data is not present).
 2) If the glove data is missing, predict it based on EMG data.
 3) If the glove data is present but the low-dimensional glove data is missing, fill in the low-dimensional glove data by projecting the incoming full-dimensional glove data into a 2D linear subspace that approximates the full-dimensional space as well as possible.
 4) If you only receive low-dimensional glove data, fill in the high-dimensional glove data (msg.glove) field with an inverse projection.
