# Animal Image Classifier (CNN)

**English** · [Español](README.es.md)

A convolutional neural network built with Keras to classify images into 8 animal categories: birds, capybaras, elephants, cats, monkeys, meerkats, dogs and toads.

The main result of the project is not the accuracy itself but the **diagnosis**: why the model fails to generalize, and why making it smaller did not fix it.

![Training curves V1 vs V2](docs/comparison.png)

## What's inside

1. **Data preparation** — 1,567 images split 80/20 (1,254 for training, 313 for validation), resized to 200×200 px.
2. **Model V1** — four Conv2D + MaxPooling2D blocks with increasing filters (32 → 64 → 128 → 128), ~2.6M parameters.
3. **Overfitting analysis** — training and validation curves across 15 epochs.
4. **Prediction test** — softmax output on an image of Tom (from *Tom and Jerry*).
5. **Model V2** — constant 32 filters per block, ~619K parameters (75% fewer).
6. **Comparison** — both architectures side by side.

## Results

| Model | Parameters | Train accuracy | Validation accuracy | Validation loss |
|---|---|---|---|---|
| V1 | ~2.6M | 0.992 | 0.597 | 2.63 |
| V2 | ~619K | 0.994 | 0.585 | 2.57 |

The prediction test makes the problem visible: the cartoon cat was classified as a **bird with 70% confidence** ("cat" got 0%).

**Conclusion:** both models memorize the training set (~99%) while validation accuracy plateaus around 59%, and validation loss rises after epoch 6 — a classic overfitting pattern. Reducing parameters by 75% did not improve generalization, which points to the **dataset** (size and variety) as the bottleneck rather than the architecture.

**Next steps:** data augmentation and transfer learning from a pretrained model.

## Running it

The notebook is designed for **Google Colab**. The dataset is hosted on Google Drive — section 0 of the notebook explains how to add it to your Drive before running.

## Tech stack

Python · TensorFlow · Keras · NumPy · Matplotlib
