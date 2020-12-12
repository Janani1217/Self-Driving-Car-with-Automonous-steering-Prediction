# Self-Driving-Car-with-Automonous-Steering-Prediction

In this project, Udacity driving simulator has been used which has two different tracks. One of them was used for collecting training data, and the other one — never seen by the model — as a substitute for the test set.
The driving simulator would save frames from three front-facing “cameras”, recording data from the car’s point of view; as well as various driving statistics like throttle, speed, and steering angle. We are going to use camera data as model input and expect it to predict the steering angle in the [-1, 1] range.

Environment and Tools
 > matplotlib
 > keras
 > numpy
 > pandas
 > scikit-learn

The Udacity provided dataset works well but it is not enough to get the car running in difficult terrain (like the second track in Udacity simulator). To gather the data from track 2, we would first need to create a folder in our project directory. Let’s call this folder- data. Now, fire up our simulator. Select the second track from the menu and go to the training mode option.Once you enter the training mode, you shall see a record option on the top right corner of the screen. Click on the icon and browse to the data folder. Press select.
You can start recording your ride once you press the record icon again! Now, if you are a novice gamer like me, I would suggest to take things slow and try to make sure your car stays at the center of the road as much possible, even during the turns. This would help to get better training data that will eventually make a good model. We will record 2 laps driving in one direction of the track and also 2 more laps driving in the opposite direction to make sure the turns are reversed. This would make sure our model does not overfit and make better left and right turns.
The training data is now stored in the data folder. Inside, there is one folder and one file: IMG and driving_log.csv. Our next job is to read from the CSV file, the names of the images and their related steering data and load the respective image from the IMG folder in Python.

The dataset has 6 columns — center, left, right (camera image paths), steering, throttle, reverse, speed (values). 

The first step was to split the data using the 80–20 rule which means using 80% of the data for training while the rest for testing the model on unseen images. I cropped the image to remove the unnecessary features, changes the images to YUV format, used gaussian blur, decreased the size for easier processing and normalized the values.To compare and visualize I plotted the original and the pre-processed image.Next, I converted all the images into numpy array. Also have to define some augmenting processes. Build the model based on nvidia model.

fter the training is complete, we save the model to use it for driving the car autonomously in our simulator. We begin testing our model, we need a file that will load our model, get the frames of the track from the simulator to process through our model and send the steering prediction back to the simulator, which is drive.py.

Open the simulator again and now choose the autonomous mode. The car should drive on its own like a boss!
  
