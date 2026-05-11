# Project Documentation

## Overview

This project demonstrates neural style transfer using TensorFlow and Keras. The content image is a green sea turtle, and the style image is Hokusai's *The Great Wave off Kanagawa*. The result is a stylized turtle image that keeps the turtle structure while borrowing the wave-like blue linework from the painting.

The project also includes a DALL-E 3 generated image for the text-to-image generative AI requirement.

## Step 1: Find The Pictures

Content image:

- Green sea turtle grazing underwater.
- Stored at `assets_notebook/green_sea_turtle.jpg`.

Style image:

- Hokusai's *The Great Wave off Kanagawa*.
- Stored at `assets_notebook/great_wave.jpg`.

DALL-E 3 generated image:

- Stored at `31e5125c-5155-46b1-bba5-01aced4d5758.png`.
- Embedded in the notebook as an attachment.

## Step 2: Replace `sf.jpg` And Run Style Transfer

The notebook replaces the original sample `sf.jpg` content image with the turtle image. It uses `iterations = 200` so the code can be run as a practical test. The final generated file is:

```text
style-transfer-notebook-output/turtle_great_wave_iteration_0200.png
```

## Algorithm Research

Neural style transfer was introduced by Leon A. Gatys, Alexander S. Ecker, and Matthias Bethge in the paper *A Neural Algorithm of Artistic Style*.

The algorithm uses a pretrained convolutional neural network to compute:

- Content loss: preserves the structure of the content image.
- Style loss: matches feature correlations from the style image using Gram matrices.
- Total variation loss: reduces noisy pixel artifacts.

In this project, VGG19 is loaded with pretrained ImageNet weights. The VGG19 weights are frozen. TensorFlow optimizes the generated image pixels directly using `GradientTape`.

## Keras Implementation

The notebook uses:

```python
tf.keras.applications.VGG19(include_top=False, weights="imagenet")
```

Selected VGG19 layers provide style and content features:

- Content layer: `block5_conv2`
- Style layers: `block1_conv1`, `block2_conv1`, `block3_conv1`, `block4_conv1`, `block5_conv1`

The generated image starts as the content image, then it is updated for 200 iterations.

## HTML Submission

The notebook includes a final section named **Create HTML File For Submission**. Running the notebook all the way through creates:

```text
neural_style_transfer_Ashish_Ashish_2026-05-11_submission.html
```

That HTML file embeds the images directly as base64 data, so it can be submitted as a standalone file.

## Text-To-Image Generative AI Product

The text-to-image tool used was DALL-E 3.

Prompt used:

```text
Create a green sea turtle swimming underwater, painted in the style of a Japanese woodblock print with curling blue waves, crisp ink outlines, and dramatic ocean motion.
```

## Reproducibility Notes

Install dependencies with:

```bash
pip install -r requirements.txt
```

Then open and run the notebook. The first run may download VGG19 weights into the local `.keras/` folder.

## Sources

- TensorFlow neural style transfer tutorial: https://www.tensorflow.org/tutorials/generative/style_transfer
- Gatys, Ecker, and Bethge paper: https://arxiv.org/abs/1508.06576
- OpenAI image generation docs: https://platform.openai.com/docs/guides/image-generation

