# guided-diffusion-ft-ddpm
This fork of OpenAI's guided diffusion was created to fine tune the pytorch implementation of (Denoising Diffusion Probabilistic Models) DDPM whose checkpoints would be compatible with Denoising Diffusion Restoration Models (DDRM). The pytorch model for DDPM is inserted into Guided Diffusion's training loop. Links to those repositories below.

1. [openai/guided-diffusion](https://github.com/openai/guided-diffusion)
1. [Denoising Diffusion Restoration Models](https://github.com/bahjat-kawar/ddrm)
1. [pytorch_diffusion](https://github.com/pesser/pytorch\_diffusion)

# Getting started
1. Download the pretrained checkpoints for LSUN bedroom model from https://heibox.uni-heidelberg.de/f/b95206528f384185889b/?dl=1
1. Run guided_diffusion/image_train.py with the following arguments for bedrooms

        "args": [
            // BEDROOMS
            "--image_size",
            "256",
            "--data_dir",
            "<folder name of the dataset for fine tuning>,
            "--lr",
            "2e-5",
            "--diffusion_steps",
            "1000",
            "--noise_schedule",
            "linear",
            "--batch_size",
            "4",
            "--save_interval",
            "2000",
            "--log_interval",
            "50",
            "--resume_checkpoint",
            "<path_to_pretrained_checkpoints>
        ]