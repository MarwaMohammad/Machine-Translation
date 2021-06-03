# Introduction
In this notebook, I build a deep neural network that functions as part of an end-to-end machine translation pipeline. 
My completed pipeline will accept English text as input and return the French translation.

The goal from this project is to build many deep newtork architectures, and see its effect on the translation task from english to France.
I build the Machine Translation pipline which consists of:
- Preprocessing which consists of tokenizing, padding.
- Models
- Prediction

# Models
I have bul=ilt many models to see their performance on the task of machine translation as follows:
To figure out the max preformance of the model we should train until the taining loos and validation loss become very near not to overfit. 
But here, I want to show difrence model archtecture performance, so I used the same hyper parametrs for all, 
learning rate = 0.0005 since 0.0001 will take more time in training to reach to the best performance.  
epochs=40
- Simple RNN using LSTM which conists of two hiddien layers, and one fully conncetd layers. 
  The performance in case this settings:
  training_acc = 0.7144 val_acc: 0.7454d
  Since the model is very simple, compare to following ones, it gives a moderate performance using the 40 epochs,
  but if incerese the epoch number, it will give better performance.
  
- Embedding: where I used embedding in addition to simple Rnn.  
  We can notice that the embidding RNN model, gives us a better performance, after 9 epochs, it gives the performance of the simple RNN.
  We can notice that using the above hyper parameters, it gives us the performance of:
  acc: 0.9155 - val_loss: nan - val_acc: 0.9279
  
- Bidirectional model using RNN without embeddings:
  We can notice that the embidding RNN model, gives us a better performance, after 20 epochs, it gives the performance of the simple RNN.
  we can say, that the bidrectional RNN with out embedding layer performance is between the simple RNN and Embedding RNN.
  We can notice that using the above hyper parameters, it gives us the performance of:
  acc: 0.7823 val_acc: 0.8164
  
- Encoder-Decoder model, I didn't find a time to implement it and compare its performance to others, it will be nice if anyone could try it and give me the results.  

  
- Final_model: which includes both embedding and bidirectional model.
  This model gives us:
  acc: 0.9534 - val_loss: nan - val_acc: 0.9655
  This is the best and fastest performance.
  

# Setup

This project requires GPU acceleration to run efficiently. 
Support is available to use either of the following two methods for accessing GPU-enabled cloud computing resources.

- Create a new enviroment use: create conda -n mt_env
- install all required packages inside env.txt file, pip install -r env.txt
- run the jupyter note book cells.

## Install
- Python 3
- NumPy
- TensorFlow 1.x
- Keras 2.x

- Notice, I used the Udacity workspace after enabling GPU to execute the project. I tried to execute it in my lab, I couldn't because of lacking GPU.
