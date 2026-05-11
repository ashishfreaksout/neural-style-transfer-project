# Neural Style Transfer Project

Author: Ashish Ashish  
Date: May 11, 2026

This project applies neural style transfer to a green sea turtle image using the visual style of Hokusai's *The Great Wave off Kanagawa*. It also includes a DALL-E 3 generated image for the text-to-image generative AI portion of the assignment.

## Project Files

- `neural_style_transfer_Ashish_Ashish_2026-05-11.ipynb` - main Python notebook.
- `neural_style_transfer_Ashish_Ashish_2026-05-11_submission.html` - standalone HTML submission generated from the notebook.
- `assets_notebook/` - content and style images used by the notebook.
- `style-transfer-notebook-output/` - generated neural style transfer outputs.
- `31e5125c-5155-46b1-bba5-01aced4d5758.png` - DALL-E 3 generated image.
- `docs/PROJECT_DOCUMENTATION.md` - project explanation, algorithm notes, and run instructions.
- `requirements.txt` - Python dependencies.

## Quick Start

1. Create and activate a Python environment.
2. Install dependencies:

```bash
pip install -r requirements.txt
```

3. Open the notebook:

```bash
jupyter notebook neural_style_transfer_Ashish_Ashish_2026-05-11.ipynb
```

4. Run all cells. The final cell creates:

```text
neural_style_transfer_Ashish_Ashish_2026-05-11_submission.html
```

## Notes

- The notebook uses TensorFlow/Keras with pretrained VGG19 ImageNet weights.
- The VGG19 model weights are not committed because they are downloaded into `.keras/`.
- The DALL-E 3 image is embedded inside the notebook as an attachment and is also present as a PNG file.

