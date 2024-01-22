# Joint-GAN

Implementation of [Joint GAN](https://arxiv.org/abs/1806.02978) which is implemented based on [StackGAN](https://arxiv.org/abs/1612.03242) ([github](https://github.com/hanzhanggit/StackGAN)).


## Background Setup

1. Setup the python version: <br>
`sudo apt-get install python3.7` <br>
`sudo apt-get update -y` <br>
`sudo update-alternatives --install /usr/bin/python3 python3 /usr/bin/python3.7 1` <br>
`sudo update-alternatives --config python3 <<< '2'` 

2. Setup the compatible pip: <br>
`sudo apt install python3-pip` <br>
`python -m pip install --upgrade --force-reinstall pip` 


3. Install the python dependencies and requirements: <br>
`sudo apt install python3.7-distutils` <br>
`pip3 install -r requirements.txt`

4. Set the following variables in .env file: <br>
`HOME_PATH=/path/to/Joint-GAN` <br>
`PRETRAIN_PATH=/path/to/Joint-GAN/pretrain`

[Note: Python environment can be used if you don't want to mess up with the versions on your system.]


## Dataset Setup

1. Download the [birds](https://drive.google.com/file/d/1eyBpuwjKUhTUtkPPyadDbEuVugRKwbGI/view?usp=sharing) image data and extract to `Data/birds/`.

2. Preprocess images: [needs to be run for once] <br>
`python3 misc/preprocess_birds.py`


## Pretrained Model

Download the [pretrained LSTM decoder](https://drive.google.com/file/d/1v5kAw9BeCL45SxVgtZGbRt1gge5q-860/view?usp=sharing)  for bird and unzip all files to `pretrain/`.


## Training

Train the Joint GAN model on the CUB dataset using the preprocessed data for birds: `python3 Main.py`


## Results

Generated results can be find in `ckt_logs/birds/`
- `fake_images.jpg`: generated images from noise
- `gen_fake_sentences.txt`: conditionally generated sentences based on `fake_images.jpg`
- `fake_sentences.txt`: generated sentences from noise
- `gen_fake_images.jpg`: conditionally generated images based on `fake_sentences.txt`

Images in the very left column of each file are the sample real images. The rest 16 images are paired with the first 16 sentences in the corresponding text file. 
