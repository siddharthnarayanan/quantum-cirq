# QSVM

For details read: https://medium.com/analytics-vidhya/quantum-computing-machine-learning-a987957e885d

QVSM is a variational quantum algorithm. The variational method in quantum theory is a classical method for finding low energy states of a quantum system. The rough idea of this method is that one defines a trial wave function (ansatz) as a function of some parameters, and then one finds the values of these parameters that minimize the expectation value of the energy with respect to these parameters.

To obtain the value of the objective function:
1. Prepare the ansatz state.
2. Make a measurement which samples from mapping of classical problem onto the quantum problem of minimizing the expectation value of the observable).
3. Repeat

One always needs to repeat the measurements to obtain an estimate of the expectation value. Quantum computers can provide estimates of the objective function for the ansatz, which in turn can be plugged into an outer loop to try to obtain parameters for the lowest value of the objective function. For these values, one can then use that best ansatz to produce samples of solutions to the problem which obtain a hopefully good approximation for the lowest possible value of the objective function.

## SVM
In a classical SVM, we have a set of points that are in either one group or another and we want to find a line that separates these two groups. This line can be linear, but it can also be much more complex, which can be achieved by the use of Kernels.

In the case of a quantum SVM, quantum feature maps are used to translate the classical data into quantum states and build the Kernel of the SVM out of these quantum states. After calculating the Kernel matrix on the quantum computer we can train the Quantum SVM the same way as the classical SVM.

First we need to install the required libraries. I tried several different libraries and found IBM’S Qiskit the easiest to get up and running for machine learning experiments. I have placed the full experiment code in this notebook.

Qiskit quantum circuits can be executed on a local simulator or a real quantum computer using IBMQ. This code does not use IBMQ and is executed on a local QASM Simulator. Qiskit aqua provides a predefined function to train the whole QSVM. Where we only have to provide the feature map, a training and a test set and Qiskit will do all the work for us.

Kindly note, apart from finding the quantum Kernel the QSVM algorithm does only classical optimization. In the end there is no difference to the classical SVM, except that the Kernels are coming from a quantum distribution.
