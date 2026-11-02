AEYE – Custom AI Camera Trainer

AEYE is a browser-based AI image recognition tool that allows users to train their own object classes using a device camera.

How it works

Name an item
 Enter the name of the object you want AEYE to recognise.

Add training samples
 Point the camera at the object and press Add Sample multiple times. For better recognition, capture the object from different angles, distances, positions and backgrounds.

Press Done
 When enough samples have been collected, press Done. The item moves to Previously Trained Items, and a new item is created automatically.

Train more items
 Repeat the process for as many different objects as required.

Start Predicting
 Press Start Predicting and AEYE will analyse the live camera feed. The predicted item name and confidence are displayed directly over the camera image.

Recognition Threshold

AEYE includes an adjustable confidence threshold.

For example, with the threshold set to 75%:

Bottle at 94% → Bottle
Calculator at 87% → Calculator
Best match at 54% → Unrecognized Item

A higher threshold makes recognition stricter, while a lower threshold accepts weaker matches.

Save & Load Training

AEYE training does not save the original camera photographs.

When Add Sample is pressed, MobileNet converts the camera image into numerical feature data which is used by the KNN classifier.

The Save Training Data function downloads these trained features into a JSON file together with information such as:

Item names
Training samples/features
Sample counts
Recognition threshold

The saved JSON can later be restored using Load Training Data, so objects do not have to be trained again after the browser is refreshed or closed.

Trainer and Recognizer

AEYE can also be separated into two interfaces:

Trainer

Plain Text
Camera
↓
Name Item
↓
Add Sample × multiple times
↓
Done
↓
Save Training Data

Recognizer

Plain Text
Load Training Data
↓
Camera
↓
AI Recognition
↓
Item Name + Confidence

This means training can be performed once, while a separate simplified webpage can use the saved training data purely for object recognition.

Technology

AEYE currently uses:

TensorFlow.js
MobileNet for image feature extraction
KNN Classifier for custom object classification
HTML, CSS and JavaScript
Device front/rear camera through the browser
GitHub Pages for web hosting
Privacy

AEYE performs the training and recognition within the browser. The training-data file produced by the current application contains numerical AI feature data rather than the original camera photographs.

Recommended Training

For better results:

Collect multiple samples for each item
Show different sides and angles
Vary the distance from the camera
Vary object position
Include different lighting/background conditions
Avoid training visually very similar objects with nearly identical samples

AEYE's confidence threshold helps reduce incorrect classifications, but an unfamiliar object can still resemble a trained object. The threshold therefore provides a practical Unrecognized Item mechanism rather than a guarantee that every completely new object will be rejected.

Writing changes: I turned our development discussion into user-facing documentation, separated the training and recognition workflows, and clearly explained what is and is not stored so the GitHub page can serve as both an introduction and basic user guide.
