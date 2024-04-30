# What are we doing?
1. Training the dataset on VGG.
2.  A code to poision the CIFAR10 dataset ~ mislabelling the images in the dataset.
3. Performing Unlearning in 2 orders ~ First and Second Order

# How to run?

1. Run [Cifar-10.ipynb](example_notebooks/Cifar_data.ipynb) file to download and prepare data.
2. Run [Backdoor-Unlearning](example_notebooks/Backdoor-Unlearning.ipynb)

# Results:

Training the dataset on VGG:

Results:

    "accuracy": 0.8786
    "weighted avg": 
        "precision": 0.8781495815813348,
        "recall": 0.8786,
        "f1-score": 0.8779643124074801,
        "support": 5000
    
    "train_loss": 0.004181844647973776,
    "test_loss": 0.689379096031189,
    "epochs_for_min": 100,
    "time": 1229.8301207087934

Detailed Output Result [here](models/poisoning/clean/train_results.json)


## Unlearning Results
    
![Final Output](result/output.png)

[First order Training results :](models/poisoning/budget-10000/seed-42/first-order/unlearning_results.json)

    "acc_clean": 0.8786,
    "acc_before_fix": 0.7382000088691711,
    "acc_after_fix": 0.7685999870300293,
    "acc_perc_restored": 0.21652407465275797,
    "diverged": false,
    "n_gradients": 512,
    "unlearning_duration_s": 3327.0377593769986,
    "num_params": 1798282



[Second order Training results :](models/poisoning/budget-10000/seed-42/second-order/unlearning_results.json)

    "acc_clean": 0.8786,
    "acc_before_fix": 0.7382000088691711,
    "acc_after_fix": 0.7829999923706055,
    "acc_perc_restored": 0.3190882217342048,
    "diverged": false,
    "n_gradients": 3420,
    "unlearning_duration_s": 8428.704430253,
    "num_params": 1798282

