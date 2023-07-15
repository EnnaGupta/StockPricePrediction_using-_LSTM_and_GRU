# Long Short Term Memory and Gated Recurrent Units
## Objective
To predict stock prices of IBM  for the year 2017 using LSTM and GRU models.
## Why LSTM and GRU ?
Even though RNNs work with Time series Data , they suffer from Vanishing gradient Problem which hinders them from using long term information so we don't just use regular 
RNNs. Instead we use better variaton :LSTM. GRU is also there, both have comparable performance which are easier to train than LSTMs.
## Methodoloogy
### 1. Long Short Term Memory(LSTM)
A RNN composed of LSTM units is often called an LSTM network.A common LSTM unit is composed of a cell, an input gate, an output gate and a forget gate.The cell is responsible for "remembering" values over arbitrary time intervals; hence the word "memory" in LSTM. Each of the three gates can be thought of as a "conventional" artificial neuron, as in a multi-layer (or feedforward) neural network: that is, they compute an activation (using an activation function) of a weighted sum.There are connections between these gates and the cell.
### Components of LSTMs
 LSTM cell contains the following components
Forget Gate “f” ( a neural network with sigmoid)
Candidate layer “C"(a NN with Tanh)
Input Gate “I” ( a NN with sigmoid )
Output Gate “O”( a NN with sigmoid)
Hidden state “H” ( a vector )
Memory state “C” ( a vector)
Inputs to the LSTM cell at any step are Xt (current input) , Ht-1 (previous hidden state ) and Ct-1 (previous memory state).
Outputs from the LSTM cell are Ht (current hidden state ) and Ct (current memory state)
### Working of gates in LSTMs
First, LSTM cell takes the previous memory state Ct-1 and does element wise multiplication with forget gate (f) to decide if present memory state Ct. If forget gate value is 0 then previous memory state is completely forgotten else f forget gate value is 1 then previous memory state is completely passed to the cell ( Remember f gate gives values between 0 and 1 ).
Ct = Ct-1 * ft
Calculating the new memory state:
Ct = Ct + (It * C`t)
Now, we calculate the output:
Ht = tanh(Ct)
### 2.Gated Recurrent Units(GRUs)
GRU unit can directly makes use of the all hidden states without any control. GRUs have fewer parameters. They are almost similar to LSTMs except that they have two gates: reset gate and update gate. Reset gate determines how to combine new input to previous memory and update gate determines how much of the previous state to keep. Update gate in GRU is what input gate and forget gate were in LSTM. We don't have the second non linearity in GRU before calculating the output, .neither they have the output gate.
## Results
##### The root mean squared error for LSTM is 3.7600990386344963.
##### The root mean squared error for GRU  is 2.5199307606135726.





