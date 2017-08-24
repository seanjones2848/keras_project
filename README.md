##Keras project

Keras is a python machine learning library built for Tensorflow and Theano.

This project will go over installation with Docker and basic use of the Keras library through text generation and image manipulation.

Example scripts for LSTM text generation, deep dreaming, and neural style transfer adapted from https://github.com/fchollet/keras/examples

## Keras environment installation for OSX with Docker

Git clone this folder:
"git clone https://seanjones2848/keras_project.git"

Install Brew:
"mkdir $HOME/.brew && curl -fsSL https://github.com/Homebrew/brew/tarball/master | tar xz --strip 1 -C $HOME/.brew"
"mkdir -p /tmp/.$(whoami)-brew-locks"
"mkdir -p $HOME/.brew/var/homebrew"
"ln -s /tmp/.$(whoami)-brew-locks $HOME/.brew/var/homebrew/locks"
"export PATH="$HOME/.brew/bin:$PATH""
"brew update && brew upgrade"


Install Docker-machine and Docker:
"brew install docker-machine"
"brew install docker"

## Running Keras

Create docker-machine instance to house keras docker image:
"docker-machine create keras"

Set Keras Docker-machine as current environment:
"eval $(docker-machine env keras)"

Pull and run latest Keras Docker image from Dockerhub:
"docker run -d -p=6006:6006 -p=8888:8888 -v=/srv/notebooks:/srv gw000/keras-full"

Access the jupyter notebook at:
"http://192.168.99.100:8888"
password: "keras"

If 192.168.99.100 isn't working, use result from command:
"docker-machine ip keras"

Make 4 folders in Python GUI, text, pics, scripts, and results
Upload example text, pictures, and scripts into Jupyter using GUI

Start a new terminal in Jupyter and try out:
"python scripts/deep_dream pics/sample.png results/deep_"
"python scripts/lstm_text_generation"





