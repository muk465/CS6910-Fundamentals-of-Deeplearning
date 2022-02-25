For Q2 and Q3
0)Acess file neural_nw.ipynb
1)all the training ,testing and vlidation data is processed and before the main class.
2)Run the file neural_nw it has parameter layer_neurons which is a list containing number of hidden neurons for each layer.
3)all notations for forward and backpropagation are from lecture 4 slides of prof mitesh.
4)refrence for code for optimizers is taken from pseudo codes given in prof mitesh lec 5.
5)I have created sample example just below the class so you can just change the parameters and run any opimizer at any hyperparameter.
6)layer_neurons should have first entry as 784 and last as 10 this signifies input and output size.

For Q4-6
0)Acess file training_fmnist_sweep_wandb.ipynb
1)here we removed layer_neurons and instead used num_hidden_layers,num_hidden_neurons which takes no. of hidden layers 
and no of neurons in each layer,this was done so as to include these parameters as variables in wandb sweep.
2)Rest code structure of class is same as neural_nw.ipynb.
3)Here we created sweep config which has method i.e bayesian sweep here,metric is to maximize validation accuracy and parameters are given like different
optimizers,activations etc.
4)after that we created a train_nw function which contains network parameters whixh would be controlled by sweep.
5)After that sweep was ran for 100 runs but it ran for 54 runs only though it converged after 40 runs so it doesnt matter.

For Q7
0)Access file ConfusionMatrix.ipynb.
1)Here all paramters of code are same as Q4-6 file.
2)We ran the network for the best configuration after sweep i.e

#best configuration
num_hidden_layers=5
num_hidden_neurons=128
learning_rate=0.0001
optimizer='nadam'
batch_size=16
initializer='xavier'
lamda=0.0005
max_epochs=10
activation='tanh'
loss='cross

3)after this we calculated Y_pred_test for test data.
4)since this is in onehot encoded form we converted it back
5)Created confusion matrix out of the testy,y_pred_test_label.
6)found testing accuracy.

For Q8
0)Access mse_loss_fmnist.ipynb
1)here we changed output layer gradient: grad_A[num_layers - 1] = -(Y_train - Ypred)*(Ypred)*(1-Ypred)
    from grad_A[num_layers - 1] = -(Y_train - Ypred)
 2) and changed loss function from cross_entropy to mse_loss.
3)ran for bayesian sweep and noted the op.


For Q10
0) access Q-10training_mnist_sweep_wandb(1).ipynb.
1) Here we have considered another mnist dataset(handwriting dataset) using the same neural network.
2) We have considered best configuration combination from the fashion mnist dataset with variations to be considered in number of epoch, learning rate, number of neurons in hidden layers and accuracy changes are obersed and plotted in wandb.in.
3) Bayesian sweep was considered for the same.

