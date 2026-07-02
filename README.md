digit recognizer (numpy only)

neural network for recognizing handwritten digits, built from scratch with just numpy. no tensorflow, no pytorch, no sklearn - wanted to actually understand backprop instead of calling .fit().

trained on the kaggle digit recognizer dataset (mnist digits, basically).

setup

bashpip install numpy pandas matplotlib

running it


grab train.csv from kaggle: https://www.kaggle.com/competitions/digit-recognizer/data
change the path at the top of the script to point at it
run


bashpython digit_recognizer.py

prints training accuracy every 5 iterations so you can watch it converge.

the network


784 inputs (28x28 pixels, flattened, normalized to 0-1)
1 hidden layer, 10 units, relu
output layer, 10 units, softmax
he init for the weights
plain batch gradient descent, no fancy optimizer


default is 500 iterations at lr 0.1, both set in the gd() call at the bottom if you want to mess with them.

data split

first 1000 columns held out as a dev set, rest is training. (heads up: right now the script only trains on it, doesn't actually score the dev set at the end)
