
Documentation:

The model:
This uses a multi-level perceptron. 
MLP with hidden layers have a non-convex loss function where there exists more than one local minimum. Therefore different random weight initializations can lead to different validation accuracy.However, sccikitlearn's implementaiton has a partial_fit for real time adjustment. 



Right now, there are 2 functions. 
1. /fraud - pass in the features that are listed in the documentation in fraud_API_endpoint.py and 
	get a 1.0 or 0.0 for banned or not 
	Output: 1.0 (banned) or 0.0 (unbanned)
2. /partial_fit - if the model is wrong, you can train it in real time by feeding it the features 
and the human-made classification

In the future, this model will have to be trained for a few more sports games, with the flow being below. When a 
suspicious box pops up, update the MongoDB, parse the data into the inputs to the model, and feed it through. 
Then partially fit it to train the model in real time.

SETUP:
In order to run this code, it needs to be run on python3 Flask.

1. Setup python3 flask to be run on virtual env: http://flask.pocoo.org/docs/0.12/installation/
2. Install anaconda: https://www.digitalocean.com/community/tutorials/how-to-install-the-anaconda-python-distribution-on-ubuntu-16-04
3. run requirements: pip install -r requirements.txt
4. if problem with PIL is show, try installing manually: pip install pillow
5. run 'source tutorial-env/bin/activate & python fraud_API_endpoint.py' from command line.


![Alt text](URM.jpg?raw=true "URM of prediction flow")
