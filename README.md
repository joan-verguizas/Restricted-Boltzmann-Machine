# Restricted Boltzmann machines as a Generative model for generic protein structure

This project was made in the context of a of a mid-term group project for the subject of Laboratory of Computational Physics mod B with the supervision of professor Marco Baiesi. A first year course of the Physics of Data Masters held in the University of Padova. The repository therefore, contains the implementation in Python of a Restricted Boltzmann Machine (RBM) to model and generate linear protein structures consisting of polar and non-polar amino acids.

The goal of this project is to investigate modern optimization techniques for Restricted Boltzmann Machines (RBMs) and their impact on model quality when generating protein sequences. We focus on a simplified one-dimensional problem—linear chains of amino acids—using binary encoding to differentiate between polar and non-polar amino acids.

Key objectives of the project include:

    Testing different optimization techniques, including Vanilla Stochastic Gradient Descent (SGD) and Adam.
    Exploring the effect of Contrastive Divergence steps and the Centering Trick on the training and performance of the RBM.
    Evaluating model performance using metrics such as the difference in energy and log-likelihood between original and generated data, as well as the second-moment error.

## Data

The project has consisted in taking a set of data where each sample represents a linear chain of aminoacids that can be either polar or non-polar. Every single chain contains 5 aminoacids (that represents a proteine) and as a result forms an alternating polar and non-polar pattern of ACs. The model aims to reproduce the alternating polar and non-polar patterns observed in real protein sequences.

## Methods

Key Components:

    - RBM Model: A neural network-based generative model with binary neurons and restricted connections between visible and hidden layers.
    - Energy Function: The energy of the model is defined based on the interactions between visible and hidden units.
    - Contrastive Divergence (CD): The training algorithm used to approximate the log-likelihood gradient by generating visible and hidden samples.
    - Optimization Techniques: We compare the performance of Vanilla-SGD and Adam for RBM training and experiment with different mini-batch sizes.
    - Centering Trick: This method is implemented to improve gradient stability and model performance.

## Results

    Optimization Comparison: Adam provides better stability but slower convergence compared to Vanilla-SGD. Smaller mini-batches allow faster convergence.
    Contrastive Divergence: Increasing the number of CD steps improves the quality of the generated data up to a point, with diminishing returns beyond 3 steps.
    Centering Trick: Applying the Centering Trick enhances convergence speed and stability but shows little improvement in final model performance once convergence is reached.

## Key Findings

    A single hidden layer is sufficient to capture the alternating pattern of amino acids.
    The binary encoding using {0,1} provides a clearer representation of the alternating polar/non-polar pattern compared to the {-1,1} encoding.
    Adam optimization with smaller mini-batches strikes a balance between convergence speed and model stability.
    The Centering Trick significantly improves the training process by reducing gradient variance but does not drastically alter the final solution.

