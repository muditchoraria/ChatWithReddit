nmt-chatbot
===================

Introduction
-------------

nmt-chatbot is the implementation of chatbot using seq2seq. 


Setup
-------------

Steps to setup project for your needs:
It is *highly* recommended that you use Python 3.6+. 

 1. ```$ git clone --recursive https://github.com/daniel-kukiela/nmt-chatbot```  
 2. ```$ cd nmt-chatbot```
 3. ```$ pip install -r requirements.txt``` 
 4. ```$ cd setup```
 5. Place training data inside "new_data" folder.
 6. ```$ python prepare_data.py``` ...Run setup/prepare_data.py - a new folder called "data" will be created with prepared training data
 7. ```$ cd ../```
 8. ```$ python train.py``` Begin training


Inference
-------------

Whenever a model is trained, `inference.py`, when directly called, allows to "talk to" AI in interactive mode. It will start and setup everything needed to use trained model (using saved hparams file within the model folder and setup/settings.py for the rest of settings or lack of hparams file).

For every question will be printed up to a number of responses set in setup/settings.py. Every response will be marked with one of three colors:

 - green - first one with that color is a candidate to be returned. Answers to the color passed blacklist check (setup/response_blacklist.txt)
 - orange - still proper responses, but with lower than maximum score
 - red - improper response - below threshold
