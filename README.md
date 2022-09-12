<!-- # Introduction
This repository contains a version of WavLM that can be trained using adapters.
Adapters are lightweight modules that can be inserted into some intermediate layers of a frozen pre-trained model. We proposed a novel adapter architecture for multiple speech processing tasks. The proposed adapter architecture produces effective features for downstream tasks to use a weighted sum of outputs of intermediate layers of WavLM encoder. -->
# Abstract
Fine-tuning of self-supervised models is a powerful transfer learning method in a variety of fields, including speech processing, since it can utilize generic feature representations obtained from large unlabeled data. Fine-tuning, however, requires a new parameter set for each downstream task, which is parameter inefficient. Adapter architectures can improve the parameter efficiency by inserting lightweight learnable modules into a frozen pre-trained model. However, existing adapter architectures fail to adaptively leverage low- to high-level features stored in different layers, which is necessary for tasks other than automatic speech recognition. Thus, we propose a new adapter architecture to acquire feature representations more flexibly for various speech tasks. In experiments, we applied this adapter to WavLM on four speech tasks. It performed on par or better than na ̈ıve fine-tuning, with less than 10% of learnable parameters. It also outperformed an existing adapter architecture.

# Adapter Architecture
<!-- ![layeradapter5](https://user-images.githubusercontent.com/48460458/189691649-a3fd4264-3de6-4e61-abe5-3c60a67b07ac.png) -->
<!-- The proposed adapter architecture incorporates two types of adapters, namely Layer adapters (L-adapters) and Encoder adapter (E-adapters), into a frozen backbone. The L-adapters bridge each intermediate layer and the top layer as shown in Figure 1a. They help the model to quickly adapt speech rep- resentations to various downstream tasks, and also to reduce dependency on the initialization of adapter parameters. The E-adapters are inserted to each encoder layer in a similar way as previous work ([EFFICIENT ADAPTER TRANSFER OF SELF-SUPERVISED SPEECH MODELS FOR AUTOMATIC SPEECH RECOGNITION](https://arxiv.org/pdf/2202.03218.pdf)) as shown in Figure 1b. In contrast to the previous work, our architecture does not have adapters after the multi-head self-attention (MHSA) modules, and alternatively has L-adapters. -->

# Experiment and Results
<!-- ![result](https://user-images.githubusercontent.com/48460458/189693661-3563b6c1-853c-493c-bdac-a3a0f53358f1.png) -->
We demonstrate the effectiveness of the proposed method on
four downstream tasks: automatic speaker verification (ASV), emotion recognition (ER), automatic speech recognition (ASR) and intent classification (IC). 
We conduct experiments to compare the performance of different five training methods in four tasks.