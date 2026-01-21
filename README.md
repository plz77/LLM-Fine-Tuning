# LLM-Fine-Tuning
A little project to showcase AI function and ability to my student in all my class
LLM Fine-Tuning Project

LLM-Fine-Tuning: Local Development Guide
A comprehensive educational project designed to showcase the power of specialized AI to students using local hardware.

This project demonstrates how to "teach" Large Language Models (LLMs) to understand specific contexts (such as Indonesian educational curriculum) using advanced but accessible local optimization techniques.


1. Project Background
What problem are we solving? Most pre-trained AI models are "jacks-of-all-trades" but masters of none. They have broad general knowledge but often fail at understanding niche business logic, specific technical documentation, or private institutional instructions.

The main hurdle for students in the past was the massive cost of retraining these models. This project solves that by implementing Parameter-Efficient Fine-Tuning (PEFT). Instead of updating billions of parameters, we only train small "adapters." This makes LLM customization possible on a standard student laptop or PC equipped with a decent GPU.


2. Technology & Local Ecosystem
   This project is built using the Python ecosystem, optimized for local execution via NVIDIA CUDA:
        - NVIDIA CUDA: The engine that handles all the heavy lifting. It allows the software to bypass the CPU and use the                 thousands of cores in your GPU for lightning-fast math.
        - Hugging Face Transformers: Our library for downloading and managing base models like GPT-2, Llama, or Mistral.
        - PEFT (LoRA/QLoRA): This is the "magic" that makes fine-tuning possible on local hardware.
          It reduces memory usage by up to 90%.
        - BitsAndBytes: A library used for Quantization.
          It shrinks a large model (e.g., from 16GB to 4GB) so it can fit inside your GPU's VRAM.
        - Accelerate: Manages how the model uses your local hardware resources to prevent "Out of Memory" errors.


3. How to Use (Local Setup)
    - Hardware Preparation Ensure you have an NVIDIA GPU with CUDA support.
      - Recommendation: A GPU with 8GB of VRAM (like an RTX 3060) is the "sweet spot" for local training.
      - Software: Update your NVIDIA Drivers and install the CUDA Toolkit.
    - Clone the Repository Open your terminal and run:
      "git clone https://github.com/username/LLM-Fine-Tuning.git cd LLM-Fine-Tuning"
    - Install Dependencies Install the necessary libraries for local GPU training:
      "pip install -q -U bitsandbytes transformers peft accelerate datasets"
    - Execute the Notebook Open LLM_Fine_Tuning.ipynb in VS Code or Jupyter Lab. Run the cells one by one. If you use a gated          model (like Llama 3), make sure to paste your Hugging Face token when prompted.


4. Why Local Training?
   We focus on local development for three main reasons:
      - Zero Cost: Students don't need to pay for AWS or Google Colab subscriptions.
      - Privacy: Your training data stays on your hard drive—never uploaded to the cloud.
      - Hardware Literacy: You learn how to manage actual PC resources like VRAM and thermals.


⚠️ Solution for "Invalid Notebook" Error on GitHub
If you encounter the error message "the 'state' key is missing from 'metadata.widgets'" when viewing the file on GitHub, please follow these steps:
- In Google Colab, go to Edit > Notebook Settings.
- Check the box "Omit code cell output when saving this notebook".
- Click Save, then resave to GitHub (File > Save a copy in GitHub).
- This action clears the corrupted widget metadata, allowing GitHub to render your code correctly.
