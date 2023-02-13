# Neural Network project of Luca Murra (1920342)
Based on E. Moliner, J. Lehtinen, V. Välimäki, "SOLVING AUDIO INVERSE PROBLEMS WITH A DIFFUSION MODEL"

## The model

The model purpose is to solve some inverse audio problem, as denoising, impainting and bandwidth extension.

It works with convolutional layers, so the audio input is converted in a 2d domain with a Constant-Q Transform, and the model takes the name of CQT-Net because this is the real difference between the other models that use Fourier Transform instead.

## My work

I built the CQT network from scratch and I managed to test it only in the denoising task, because other problems should be tackled after the signal has been denoised, but my network can't manage even the first step, due to poor resource for training.

## How to run

I designed the notebook 'NN_project.ipynb' to work in Colab, so if you run it from Colab you can 'Run everything' and the network is ready to be tested (in fact it loads the pre-trained weights automatically).
If you don't run the notebook in Colab you need to install some libraries, other than PyTorch:

- dotmap, needed for passing parameters to the model
- librosa, needed for dealing with audio files
- ffmpeg, needed for mp3 files if in a Linux environment

And this repo should be cloned, as it contains the dataset, the weights and some files needed for some computation, like the CQTransform.

Of course, some path variables should be changed since they are defined following the Colab scheme.

## How to test

Since the task is of denoising, the testing phase is subjective, so in the last part of the notebook some audio player are shown to evaluate the performance. It's sufficient to re-run the "Evaluation" section to listen to different sample in the dataset.

An objective evaluation should be done with a ground truth of MIDI files, but I don't have them for the dataset and it's not really useful for evaluating live performances.

## My results

Since Colab can't handle the deep of the CQT-Net I had to make a shrinker version of it, in fact the deeper I can get is less than 10% of the depth of the paper network.

This should justify the fact that my network can handle just the denoising part and it's far from been perfect.
