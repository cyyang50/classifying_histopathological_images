# classifying_histopathological_images
This study aims to propose a CNN model for the classification of lung cancer subtype based on histopathological images that is trained on a limited set of domains and is expected to predict images from unexplored domains. For the purposes of the current study, three types of classification frameworks are introduced in this study, including the baseline CNN framework, the Domain Adversarial Neural Network (DANN), and Margin Disparity Discrepancy (MDD) framework. The dataset at the source domain is either without pre-processing or with data augmentation, and the dataset at the target domain is processed with or without staining normalization.

## Methods
This study utilized Google Colab as the working platform equipped with GPU. In the preparation stage, the whole-slide images at the target domain are cropped into patches and processed with staining normalization. *OpenSlide Python* was used to extract tiles from the overall whole-slide image. Patches were saved only when the sum of white/black pixels did not exceed 50% of the range of the read region to reduce noise and redundancy. The approach for achieving staining normalization in the histopathology images of the target domain was utilizing the CycleGan. During the training process, the dataset of the source domain used could be augmented or unaugmented, and the dataset of the target domain used is adapted with or without staining normalization. The dataset of the source domain was augmented randomly by the spatial and color augmentations, including horizontal and vertical flips, brightness, and hue adjustment. They were executed by *OpenCV*, *ImageDataGenerator*, and *tf.image*.

The experiment design is shown as below.

<img src="https://user-images.githubusercontent.com/80690817/172627806-24c6a407-b2b0-40ad-bd61-7264c4ff10ef.png" width="70%" height="70%">


