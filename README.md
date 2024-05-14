# Data Retraction and Ensuring Model Integrity

This project focuses on addressing data leaks, privacy issues, and poisoning attacks in machine learning models, particularly in the domain of computer vision. It introduces a method for unlearning features and labels from learning models, leveraging influence functions to estimate the influence of training data on the model and translate it into a form of unlearning.

## Introduction

Machine learning models can inadvertently capture sensitive information from the training data, raising privacy concerns. Existing methods for unlearning in machine learning focus on removing individual data points but struggle with scalability when larger groups of features and labels need to be reverted. This project presents a versatile approach that enables closed-form updates of model parameters, allowing retrospective adaptation of training data influence on the model.

## Methodology

The unlearning method operates along an orthogonal dimension of the data, focusing on correcting privacy issues in feature values and labels (rows) instead of within data instances (columns). It formulates unlearning as a closed-form update of the model, enabling the correction of features and labels at arbitrary positions in the training data.

Two strategies are employed for calculating the closed-form update:

1. **First-order update**: Builds on the gradient of the loss function and can be applied to any model with a differentiable loss.
2. **Second-order update**: Incorporates second-order derivatives and is applicable to loss functions with an invertible Hessian matrix.

## Experiments

The effectiveness of the approach is validated through case studies on unlearning label poisoning in computer vision using the CIFAR-10 dataset. A convolutional neural network (CNN) with approximately 1.8 million parameters is trained, and label poisoning is simulated by flipping a fraction of labels between classes. The unlearning task aims to correct these flipped labels using both first-order and second-order update methods.

## Results

The project successfully implemented unlearning on the CIFAR-10 image dataset, preserving the model's accuracy after a poisoning attack. While the unlearning process restored accuracy to 78.30% (compared to the initial 87.86% before the attack), further refinement is needed to achieve near-accurate scores.

## Limitations

The effectiveness of unlearning diminishes as the number of affected features and labels increases. Additionally, the method relies on knowing which data to remove, as detecting privacy leaks in learning models is a challenging task beyond the scope of this work.

## Conclusion

The unlearning approach presented in this project can be adapted to work on a wide range of applications, including addressing unintended memorization in language models based on recurrent neural networks.


## Requirements

- tensorflow==2.7.0
- scikit-learn==1.0.2
- nltk==3.8.1
- tqdm==4.65.0
- click==8.1.3
- matplotlib==3.5.3
- pandas==1.3.5
- seaborn==0.12.2

## Usage

1. Clone the repository: `git clone [https://github.com/your_username/project_name.git](https://github.com/utkarsh231/DL-Major-Project.git)`
2. Install the required dependencies: `pip install -r requirements.txt`
3. Run the file to prepare dataset: `python example_notebooks/Cifar_data.ipynb`
4. Run the experiments: `python example_notebooks/Backdoor-Unlearning.ipynb`

## License

This project is licensed under the [MIT License](LICENSE).

## Acknowledgments

- [Utkarsh Prakash Srivastava](https://github.com/utkarsh231)
- [Srushti Jagtap](https://github.com/Srushti2602)
- [Raghav Rawat](https://github.com/rawatraghav)
