# An Evaluation of Deep Learning Models for Multi-Class Brain Tumor Classification Using MRI Images

# Author : 
Surya Kiran Gogula 
# Enrollment Id :
34049061
## Project Overview

This dissertation evaluates Deep Learning models for multi-class brain
tumour classification using Magnetic Resonance Imaging (MRI) images. The
classification task contains four categories: Glioma Tumor, Meningioma
Tumor, Pituitary Tumor, and No Tumor.

The project evaluates Custom CNN, DenseNet121, Xception, and
InceptionV3. Default and fine-tuned configurations are compared, with
F1-score used as the primary measure for selecting the best-performing
model. The selected model is also evaluated using previously unseen MRI
images, followed by human evaluation using predefined criteria.

## Aim

The aim is to develop and evaluate Deep Learning models for multi-class
brain tumour classification using MRI images, apply hyperparameter
tuning to investigate performance improvement, and evaluate the selected
model using previously unseen MRI images and human feedback.

## Objectives

1.  Prepare and preprocess the MRI dataset using image resizing,
    normalisation, data augmentation, and dataset splitting.
2.  Develop and evaluate multiple Deep Learning models for Glioma Tumor,
    Meningioma Tumor, Pituitary Tumor, and No Tumor classification.
3.  Apply hyperparameter tuning and model optimisation to investigate
    whether performance can be improved.
4.  Compare default and fine-tuned models under consistent evaluation
    conditions and identify the best-performing model using F1-score and
    other selected measures.
5.  Evaluate the selected model using previously unseen MRI images and
    collect human feedback using predefined criteria.

## Dataset

The Brain Tumor MRI Dataset was obtained from Kaggle:

https://www.kaggle.com/datasets/masoudnickparvar/brain-tumor-mri-dataset

The dataset contains 8,800 MRI images, with 2,200 images in each of four
categories:

-   Glioma
-   Meningioma
-   No Tumor
-   Pituitary

The demonstrated MRI inputs had a shape of 512 x 512 x 3, with
normalised pixel values generally ranging from 0.0 to 1.0.

## Dataset Split

The final dataset split used for model development was:

  Dataset        Images
  ------------ --------
  Training        7,128
  Validation        792
  Testing           880
  Total           8,800

The testing set was kept separate from model training and was used for
the main model evaluation.

## Data Preprocessing

The MRI images were prepared using image resizing, pixel normalisation,
data augmentation, and dataset splitting. The preprocessing workflow was
designed to create consistent inputs for all selected architectures. The
same required input preparation was applied when evaluating previously
unseen MRI images.

## Deep Learning Models

#### Custom CNN

A Custom Convolutional Neural Network was developed as a baseline model.
It provided a comparison point against the pretrained transfer-learning
architectures.

#### DenseNet121

DenseNet121 was evaluated as a transfer-learning architecture and
provided a strong default baseline for the classification task.

#### Xception

Xception was evaluated as a second transfer-learning architecture to
provide architectural diversity in the model comparison.

#### InceptionV3

InceptionV3 was evaluated as a transfer-learning architecture and was
subsequently fine-tuned. Fine-Tuned InceptionV3 produced the highest
F1-score and was selected as the best-performing model.

## Evaluation Metrics

The following measures were used:

-   Accuracy
-   Precision
-   Recall
-   F1-score
-   ROC-AUC
-   Cohen's Kappa
-   Confusion Matrix

F1-score was given particular importance because it provides a balance
between Precision and Recall.

## Default Model Results

  Model           Accuracy   Precision   Recall   F1-score
  ------------- ---------- ----------- -------- ----------
  DenseNet121       0.8886      0.8907   0.8886     0.8893
  Xception          0.8898      0.8915   0.8898     0.8888
  InceptionV3       0.8636      0.8788   0.8636     0.8672
  Custom CNN        0.6898      0.6980   0.6898     0.6790

#### Default ROC-AUC

  Model           ROC-AUC
  ------------- ---------
  DenseNet121      0.9840
  Xception         0.9820
  InceptionV3      0.9781
  Custom CNN       0.8932

#### Default Cohen's Kappa

  Model           Cohen's Kappa
  ------------- ---------------
  DenseNet121            0.8515
  Xception               0.8530
  InceptionV3            0.8182
  Custom CNN             0.5864

DenseNet121 achieved the highest default F1-score of 0.8893, closely
followed by Xception at 0.8888.

## Fine-Tuned Model Results

  Model                      Accuracy   Precision   Recall   F1-score
  ------------------------ ---------- ----------- -------- ----------
  Fine-Tuned InceptionV3       0.8977      0.9003   0.8977     0.8983
  Fine-Tuned Xception          0.8205      0.8247   0.8205     0.8200
  Fine-Tuned DenseNet121       0.8148      0.8153   0.8148     0.8137
  Fine-Tuned Custom CNN        0.7284      0.7354   0.7284     0.7050

Fine-Tuned InceptionV3 produced the strongest tuned performance. Its
F1-score increased from 0.8672 to 0.8983.

## Default Versus Fine-Tuned Comparison

Fine-Tuned InceptionV3 improved across all four reported measures:

  Metric        Default InceptionV3   Fine-Tuned InceptionV3
  ----------- --------------------- ------------------------
  Accuracy                   0.8636                   0.8977
  Precision                  0.8788                   0.9003
  Recall                     0.8636                   0.8977
  F1-score                   0.8672                   0.8983

The Custom CNN also improved after fine-tuning, with Accuracy increasing
from 0.6898 to 0.7284 and F1-score increasing from 0.6790 to 0.7050. In
contrast, Xception and DenseNet121 performed better in their default
configurations. Therefore, fine-tuning had different effects across the
architectures.

## Best Performing Model

Fine-Tuned InceptionV3 was selected as the best-performing model based
primarily on F1-score.

Results:

-   Accuracy: 89.77%
-   Precision: 90.03%
-   Recall: 89.77%
-   F1-score: 0.8983

The F1-score of 0.8983 was the highest among all default and fine-tuned
model configurations.

## Generalisability Using Unseen MRI Images

The selected Fine-Tuned InceptionV3 model was evaluated using previously
unseen MRI images.

Five demonstrated images were correctly classified:

  Image   Ground Truth   Prediction     Confidence
  ------- -------------- ------------ ------------
  1       Glioma         Glioma                1.0
  2       Meningioma     Meningioma            1.0
  3       No Tumor       No Tumor              1.0
  4       Pituitary      Pituitary             1.0
  5       Pituitary      Pituitary             1.0

An additional new unseen MRI image from the Glioma category was also
correctly classified as Glioma with a confidence of 1.0.

These evaluations provided additional evidence that the selected model
could apply its learned classification patterns to new MRI inputs.

## Human Evaluation

Human evaluation involved 100 participants. Feedback was collected using
five predefined factors:

1.  Prediction Correctness
2.  Output Clarity
3.  Ease of Use
4.  System Usefulness
5.  Confidence in Output

Participants also provided an Overall Rating and Open Comments.

  Evaluation Factor          Mean Rating
  ------------------------ -------------
  Prediction Correctness        4.89 / 5
  Output Clarity                4.89 / 5
  Ease of Use                   4.89 / 5
  System Usefulness             4.78 / 5
  Confidence in Output          4.78 / 5
  Overall Rating                4.67 / 5

The open comments were generally positive and described the outputs as
clear, understandable, useful, simple, and easy to operate.

## Key Findings

1.  Transfer-learning models performed substantially better than the
    Custom CNN in the default evaluation.
2.  DenseNet121 achieved the highest default F1-score of 0.8893.
3.  Fine-tuning affected the selected architectures differently.
4.  Fine-Tuned InceptionV3 achieved the highest overall F1-score of
    0.8983.
5.  Fine-Tuned InceptionV3 achieved 89.77% Accuracy, 90.03% Precision,
    and 89.77% Recall.
6.  The selected model correctly classified the evaluated previously
    unseen MRI images.
7.  Human evaluation produced positive feedback across all five
    predefined factors.
8.  Fine-Tuned InceptionV3 was selected as the strongest model based
    primarily on F1-score.

## Software and Technologies

The project used:

-   Python
-   TensorFlow
-   Keras
-   NumPy
-   Pandas
-   Matplotlib
-   Scikit-learn
-   Jupyter Notebook
-   Google Colab
-   Google Drive
-   Kaggle

## Running the Project

#### Step 1: Download the Dataset

Download the Brain Tumor MRI Dataset from Kaggle and organise the four
class folders.

#### Step 2: Preprocess the Images

Run the preprocessing code to resize, normalise, augment, and split the
MRI images.

#### Step 3: Train the Models

Train Custom CNN, DenseNet121, Xception, and InceptionV3 using the
prepared training data.

#### Step 4: Evaluate Default Models

Calculate Accuracy, Precision, Recall, F1-score, ROC-AUC, Cohen's Kappa,
and Confusion Matrix results.

#### Step 5: Fine-Tune the Models

Apply the selected fine-tuning configuration and evaluate the resulting
models.

#### Step 6: Select the Best Model

Compare the default and fine-tuned results and select the model with the
highest F1-score.

#### Step 7: Test Unseen Images

Load Fine-Tuned InceptionV3 and evaluate previously unseen MRI images.

#### Step 8: Human Evaluation

Collect participant feedback using the five predefined evaluation
factors, Overall Rating, and Open Comments.

## Limitations

The dissertation used one publicly available MRI dataset and a limited
number of Deep Learning architectures. The unseen-image evaluation also
used a limited number of new MRI images. Human evaluation was based on
participant feedback using predefined criteria. These limitations
provide opportunities for future work using larger and more diverse
datasets, additional architectures, broader unseen-image testing, and
larger participant groups.

## Future Work

Future work could:

1.  Evaluate larger and more diverse MRI datasets.
2.  Test additional Deep Learning architectures.
3.  Explore more extensive hyperparameter optimisation.
4.  Expand unseen-image testing using a larger collection of new MRI
    images.
5.  Conduct human evaluation with a larger and more diverse participant
    group.
6.  Extend classification to additional brain tumour categories and MRI
    conditions.

## Dissertation Information

Title:

An Evaluation of Deep Learning Models for Multi-Class Brain Tumor
Classification Using MRI Images

Degree:

MSc Big Data Analytics

Classification categories:

-   Glioma Tumor
-   Meningioma Tumor
-   Pituitary Tumor
-   No Tumor

Best-performing model:

Fine-Tuned InceptionV3

Selection criterion:

Highest F1-score

Best F1-score:

0.8983

## Final Result

Fine-Tuned InceptionV3 was the best-performing model based on F1-score,
achieving an F1-score of 0.8983, Accuracy of 89.77%, Precision of
90.03%, and Recall of 89.77%. The model also correctly classified the
evaluated previously unseen MRI images. Human evaluation produced
positive feedback across the predefined criteria. The completed workflow
covers MRI preprocessing, model development, default evaluation,
fine-tuning, model comparison, unseen-image evaluation, and human
feedback collection.
