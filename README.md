# Dreambooth-style fine tuning of Stable Diffusion models

Link to notebook for classic Dreambooth:

[![Train In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/brian6091/Dreambooth/blob/main/Dreambooth_colab.ipynb)

If you're looking to fine-tune using [Low-rank Adaptation (LoRA)](https://github.com/cloneofsimo/lora), you can find a notebook on [this branch](https://github.com/brian6091/Dreambooth/tree/lora), or follow this link:

[![Train In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/brian6091/Dreambooth/blob/lora/LoRA_colab.ipynb)

Tested with Tesla T4 and A100 GPUs on Google Colab.

Tested with [Stable Diffusion v1-5](https://huggingface.co/runwayml/stable-diffusion-v1-5) and [Stable Diffusion v2-base](https://huggingface.co/stabilityai/stable-diffusion-2-base).

There are lots of notebooks for Dreambooth-style training. This one borrows elements from [
ShivamShrirao's](https://github.com/ShivamShrirao/diffusers) implementation, but is distinguished by some additional features:
* based on [Hugging Face](https://huggingface.co/) [Diffusers🧨](https://github.com/huggingface/diffusers) implementation so it's easy to stay up-to-date
* exposes lesser-explored parameters for experimentation (ADAM optimizer parameters, [cosine_with_restarts](https://huggingface.co/transformers/v2.9.1/main_classes/optimizer_schedules.html#transformers.get_cosine_with_hard_restarts_schedule_with_warmup) learning rate scheduler, etc), all of which are dumped to a json file so you can remember what you did
* possibility to drop some text-conditioning to improve classifier-free guidance sampling (e.g., how [SD V1-5 was fine-tuned](https://huggingface.co/runwayml/stable-diffusion-v1-5))
* training loss and prior class loss are tracked separately (can be visualized using tensorboard)
* option to generate exponentially-weighted moving average (EMA) weights for the unet
* easily switch in different variational autoencoders (VAE) or text encoders
* inference with trained models is done using [Diffusers🧨](https://github.com/huggingface/diffusers) pipelines, does not rely on any web-apps


[<a href="https://www.buymeacoffee.com/jvsurfsqv" target="_blank"><img src="https://cdn.buymeacoffee.com/buttons/v2/default-yellow.png" height="45px" width="162px" alt="Buy Me A Coffee"></a>](https://www.buymeacoffee.com/jvsurfsqv)
