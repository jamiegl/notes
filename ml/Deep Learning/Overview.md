# Overview

## Deep Neural Network

Deep Neural networks contains input neurons, hidden layers and output neurons for each label class.

The nodes are called perceptrons and are approximations for axons in the human brain. If the nodes are all connected via all possible outputs and inputs then it is called fully connected.

<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/1/10/Blausen_0657_MultipolarNeuron.png/1920px-Blausen_0657_MultipolarNeuron.png" title="" alt="Blausen 0657 MultipolarNeuron.png" data-align="center">

Axons take inputs from other neurons via the dendrites and perform some weighted sum in the cell body. If this is past a threshold value, a signal is fired through the axon out the synapse. Otherwise they stay at rest.

### Training

- The training set is submitted to the input layer, often in batches (sometimes called mini-batches).

- The neurons then apply their *activiation/transfer function* to a weighted and biased combination of the their inputs. This function can either output 1 or 0. This will determine whether the neuron fires.

- When the output layers recieve their signals a metric is chosen to calculate the loss between the recieved and actual values. This can be a familiar one like $\ell_2$ or something information related like cross entropy. Your loss function choice is often a function of the activation function you chose and problem class, i.e. classification probably wont use norms.

- The weights and biases at each neuron are recalculated and *backpropogated* through the network based on this loss. This is implemented via a solver such as SGD which has step size represented by a hyperparameter called the learning rate.

- The next epoch commences and a new batch is passed through the revised weights and biases.

## 
