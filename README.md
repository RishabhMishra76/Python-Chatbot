# Python-Chatbot
A chatbot made for disease and healtcare assistance using python.

## Prerequisite
To install the required libraries run the following command:

`pip install tensorflow keras pickle nltk`

## How to run?
 1. Install the above metioned libraries.
 
 2. Run train_chatbot.py to train the model over the intents(Every time we add a new intent we need to retrain model).</br>
 `python train_chatbot.py`
 
 3. It will create the file chatbot_model.h5(it contains model architecture with weights which can be loaded and used later without retraining).
 
 4. Now run the gui_chatbot.py for running the interface for chatbot.</br>
 `python gui_chatbot.py`

## How do chatbots work?
All chatbots come under the _NLP (Natural Language Processing)_ concepts. NLP is composed of two things:

- _NLU (Natural Language Understanding)_: The ability of machines to understand human languages like English, French or Hindi.

- _NLG (Natural Language Generation)_: The ability of a machine to generate text similar to human written sentences.

Example:- Imagine a user asking a question to a chatbot: 
> “Hey, what’s on the news today?”

The chatbot will break down the user sentence into two things: _intent and an entity_. 
- **Intent** : The intent refers to an action the user wants to perform. For this sentence _get_news_ is used as intent.
- **Entity** : The entity tells specific details about the intent, so "today" will be the entity.

## File Structure

1. Gui_Chatbot.py — This file is where we will build a graphical user interface to chat with our trained chatbot (Tkinter module is used for that).

2. Intents.json — The intents file has all the data that we will use to train the model. It contains a collection of tags with their corresponding patterns (inputs) and responses (outputs).

3. Chatbot_model.h5 — This is a hierarchical data format file in which we have stored the weights and the architecture of our trained model.

4. Classes.pkl — The pickle file can be used to store all the tag names to classify when we are predicting the message.

5. Words.pkl — The words.pkl pickle file contains all the unique words that are the vocabulary of our model.

## Model

1. The architecture of our model will be a neural network consisting of 3 dense layers. 

2. The first layer has 128 neurons, the second one has 64 and the last layer will have the same neurons as the number of classes.

3. The dropout layers are introduced to reduce overfitting of the model.

4. We have used the SGD optimizer and fit the data to start the training of the model.

5. After the training of 200 epochs is completed, we then save the trained model using the Keras `model.save(“chatbot_model.h5”)` function.
