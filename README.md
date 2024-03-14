# Bitwise Neural Network

Bitwise Neural Network implemented in Rust

## Overview

This project implements a bitwise neural network in Rust. A bitwise neural network is a type of neural network specifically designed to learn and perform bitwise operations on binary inputs. This neural network architecture can be useful for tasks such as binary classification, logical operations, and pattern recognition in binary data.

## Features

- Matrix operations for feedforward and backpropagation.
- Support for customizable activation functions.
- Training method for learning from input-output pairs.
- Configurable network architecture (number of layers and neurons per layer).

## Usage

To use this bitwise neural network implementation, follow these steps:

1. **Define Network Parameters**: Create a new neural network by specifying the layers, learning rate, and activation function.

   ```rust
   // Example: Create a new network with 2 input neurons, 4 hidden neurons, and 1 output neuron
   let layers = vec![2, 4, 1];
   let learning_rate = 0.1;
   let activation = activations::SIGMOID; // or define your custom activation function
   let mut network = Network::new(layers, learning_rate, activation);
   ```

2. **Provide Training Data**: Define training data as input-output pairs.

   ```rust
   let inputs = vec![vec![0.0, 0.0], vec![0.0, 1.0], vec![1.0, 0.0], vec![1.0, 1.0]];
   let targets = vec![vec![0.0], vec![1.0], vec![1.0], vec![0.0]];
   ```

3. **Train the Network**: Train the neural network using the provided training data.

   ```rust
   let epochs = 1000;
   network.train(inputs, targets, epochs);
   ```

4. **Make Predictions**: Use the trained network to make predictions on new data.

   ```rust
   let test_inputs = vec![vec![0.0, 0.0], vec![0.0, 1.0], vec![1.0, 0.0], vec![1.0, 1.0]];
   for input in test_inputs {
       let output = network.feed_forward(input);
       println!("Input: {:?}, Output: {:?}", input, output);
   }
   ```

## Customization

Users can customize the network by adjusting parameters such as:
- Learning rate (`learning_rate`)
- Activation function (`activation`)
- Network architecture (`layers`)

## Performance

This implementation is designed for efficiency and scalability, making it suitable for training on large datasets and complex network architectures. However, users should consider the computational resources required for training, especially for larger networks and datasets.

## Dependencies

This project relies on the `rand` crate for random number generation.

## Credits

This project made with guidance from MathleteDev. Special thanks to the Rust community and contributors to the `rand` crate.
