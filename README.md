# Cyclic GANs Monet

This project implements a CycleGAN model to translate images between two domains: photographs and Monet-style paintings. The approach is inspired by the [Kaggle GANs Getting Started Competition](https://www.kaggle.com/competitions/gan-getting-started), which provides a dataset of landscape photographs and Monet paintings.

## Table of Contents

- [Overview](#overview)
- [Dataset](#dataset)
- [Model Architecture](#model-architecture)
- [Installation](#installation)
- [Usage](#usage)
- [Results](#results)
- [References](#references)
- [Acknowledgements](#acknowledgements)

## Overview

The goal of this project is to use CycleGANs to perform style transfer, learning to translate photographs of landscapes into Monet-style paintings and vice versa, without paired examples. CycleGANs achieve this by enforcing cycle-consistency, ensuring that an image translated to the target domain and then back to the original domain returns the original image.

![Uploading Screenshot from 2025-08-15 14-21-44.png…]()

## Dataset

- **Source:** [Kaggle GANs Getting Started Competition](https://www.kaggle.com/competitions/gan-getting-started)
- **Domains:**
  - `photo_jpg/`: Real-world landscape photographs.
  - `monet_jpg/`: Monet-style landscape paintings.
- **Format:** JPEG images, 256x256 pixels.

To use the dataset, download it from the Kaggle competition page and place the folders in the project root or a specified `data/` directory.

## Model Architecture

This project uses the CycleGAN architecture, which consists of:

- Two Generators (Photo→Monet and Monet→Photo)
- Two Discriminators (Distinguishing real Monet/Photo images from generated ones)
- Cycle-consistency loss to enforce the correct mapping between domains

The model is implemented using TensorFlow/Keras (or PyTorch, if applicable).

## Installation

1. Clone this repository:
   ```bash
   git clone https://github.com/atheendre130505/cyclic-gans-monet.git
   cd cyclic-gans-monet
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. (Optional) Set up a virtual environment.

## Usage

1. Download and extract the dataset into a `data/` directory.
2. Train the model:
   ```bash
   python train.py --data_dir ./data --epochs 100
   ```
3. Generate Monet-style images from photographs:
   ```bash
   python generate.py --input_dir ./data/photo_jpg --output_dir ./output/monet
   ```

4. Visualize results:
   ```bash
   python visualize_results.py --input_dir ./output/monet
   ```

## Results

Sample outputs, training curves, and evaluation metrics can be found in the `results/` directory.

| Photograph | Monet-style Output |
|------------|-------------------|
| ![Photo](results/photo_sample.jpg) | ![Monet](results/monet_sample.jpg) |

## References

- [CycleGAN Paper](https://arxiv.org/abs/1703.10593)
- [Kaggle GANs Getting Started](https://www.kaggle.com/competitions/gan-getting-started)
- [TensorFlow CycleGAN Tutorial](https://www.tensorflow.org/tutorials/generative/cyclegan)

## Acknowledgements

- Kaggle for the competition and dataset
- Authors of the CycleGAN architecture
- Open-source contributors in the GAN community

---

Feel free to open issues or submit pull requests to improve the project.
