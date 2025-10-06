

#Vision Transformer: PaliGemma in PyTorch 🖼️
This repository contains a from-scratch implementation of PaliGemma, Google's powerful open-source vision-language model, built entirely in PyTorch.

## About The Project
PaliGemma is a multimodal model that combines a pre-trained SigLIP vision model with a Gemma language model to understand both images and text. This project provides a clean, commented, and self-contained codebase to explore the architecture and functionality of PaliGemma, allowing users to run inference on their own images and prompts.

The implementation includes:

SiglipVisionModel: A Vision Transformer (ViT) for processing images.

GemmaForCausalLM: A decoder-only language model for text generation.

PaliGemmaForConditionalGeneration: The main class that merges the vision and language components.

Custom Processor: A custom processor to correctly format image and text inputs for the model.

## Getting Started
Follow these steps to get a local copy up and running.

#### Prerequisites
Python 3.8+

PyTorch

Git and Git LFS

#### Installation
Clone the repository

Bash

git clone https://github.com/Cruciator18/Vision-_Transformer_PaliGemma.git
cd Vision-_Transformer_PaliGemma
Set up Git LFS to handle the large model weight files.

Bash

git lfs install
Create a virtual environment

Bash

python -m venv .venv
source .venv/Scripts/activate  # On Windows
# source .venv/bin/activate    # On macOS/Linux
Install the required packages

Bash

pip install torch transformers Pillow fire safetensors bitsandbytes accelerate
Download the Model Weights
Download the official paligemma-3b-pt-224 weights and place them in a directory inside the project, for example: paligemma-3b-pt-224/.

## Usage
To run inference, use the inference.py script. You can modify the launch_inference.sh script or run the command directly in your terminal.

Bash

python inference.py \
    --model_path "path/to/your/paligemma-3b-pt-224" \
    --prompt "What is in this image?" \
    --image_file_path "path/to/your/image.jpg" \
    --only_cpu "True"
Key Arguments:

--model_path: Path to the directory containing the model's .safetensors weight files and configuration.

--prompt: The text prompt you want to provide to the model.

--image_file_path: The path to the input image.

--only_cpu: Set to "True" to run on the CPU (slower) or "False" to use a GPU if available.

## Project Structure
.
├── paligemma-3b-pt-224/  # Directory for model weights
├── test_images/          # Sample images for testing
├── .gitignore            # Specifies files for Git to ignore
├── inference.py          # Main script to run the model for inference
├── launch_inference.sh   # Example bash script to launch inference
├── modeling_gemma.py     # Implements the Gemma language model architecture
├── modeling_siglip.py    # Implements the SigLIP vision model architecture
├── processing_paligemma.py # Custom processor for handling text and image inputs
└── utils.py              # Utility functions, including model loading logic
## License
This project is distributed under the MIT License. See LICENSE.txt for more information.

## Acknowledgments
This implementation is based on the official PaliGemma model by Google.

Thanks to the Hugging Face team for their libraries and documentation which inspired parts of this project.

