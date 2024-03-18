<div id="top"></div>

[![Contributors][contributors-shield]][contributors-url]
[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]
[![PUll Request][pr-shield]][pr-url]
[![MIT License][license-shield]][license-url]


<br />
<div align="center">
  <a href="https://github.com/Thytu/SLAM">
    <img src="https://i.ibb.co/CvLbGX6/SLAM-ASR-logo-v2.png" alt="Logo" width="200" height="200">
  </a>

  <h3 align="center" style="font-size: 200%">SLAM</h3>

  <p align="center">
    <b> Bringing audio to LLM </b>
    <br />
    <br />
    <a href="#getting-started"><strong>Explore the docs</strong></a>
    <br />
    <br />
    <a href="#about-the-project">View Demo</a>
    · <a href="#about-the-project">More about SLAM</a>
    · <a href="https://github.com/Thytu/SLAM/issues">Report Bug / Request Feature</a>
  </p>
</div>

<br/>

<details>
  <summary>Table of Contents</summary>
  <ol>
    <li><a href="#about-the-project">About The Project</a></li>
    <li><a href="#getting-started">Getting Started</a></li>
    <li><a href="#usage">Usage</a></li>
    <li><a href="#roadmap">Roadmap</a></li>
    <li><a href="#contributing">Contributing</a></li>
    <li><a href="#acknowledgments">Acknowledgments</a></li>
    <li><a href="#contact">Contact</a></li>
  </ol>
</details>

<br/>


## About The Project

SLAM is a tool to simplify the process of adding audio modality to your LLMs offering a seamless solution with just a single config file. Say goodbye to complex setups and hello to effortlessly enhancing your models with audio capabilities!

<p align="right">(<a href="#top">back to top</a>)</p>


## Getting Started

SLAM currently provides a `requirements.txt`, you're invited to use a virtualenv in order to avoid any dependency conflict.
```sh
git clone https://github.com/Thytu/SLAM/
cd SLAM

pip3 install -r requirements.txt
```

Once the dependencies installed you can either launch the default example or custom your own LLM by writing a [config file](TODO)  or using the [CLI](TODO).

```py
python src/training.py
```

<p align="right">(<a href="#top">back to top</a>)</p>


## Usage

SLAM simplifies the process of enhancing your LLM with audio capabilities, following the principles outlined in the [SLAM-ASR](https://arxiv.org/abs/2402.08846) paper. By linking a speech encoder to an decoder using a trainable linear projector adding to your LLM the audio modality. SLMA automates the integration process by making it as easy as configuring a single file.

To use SLAM, simply define your desired configurations in the provided config file, it will then handle the rest, seamlessly incorporating the audio modality into your models.

## Contributing

Contributions are what make the open source community such an amazing place to learn, inspire, and create. Any contributions you make are **greatly appreciated**.\
If you have a suggestion that would make this better, please fork the repo and create a pull request.

Don't forget to give the project a star! 🌟 Thanks again!

<p align="right">(<a href="#top">back to top</a>)</p>

## Acknowledgments

This project draws significant inspiration from the [An Embarrassingly Simple Approach for LLM with Strong ASR Capacity](https://arxiv.org/pdf/2402.08846.pdf) paper. I thank the authors for sharing their expertise. Huge thanks to the CoolKids for their  help in debugging some pesky issues I ran into. And last but definitely not the least, a massive thank you to Oursin – this project simply wouldn't exist without you!

<p align="right">(<a href="#top">back to top</a>)</p>



## Contact

Valentin De Matos - [@ThytuVDM](https://twitter.com/ThytuVDM) - vltn.dematos@gmail.com

<p align="right">(<a href="#top">back to top</a>)</p>


<!-- MARKDOWN LINKS & IMAGES -->
[contributors-shield]: https://img.shields.io/github/contributors/Thytu/SLAM-ASR.svg?style=for-the-badge&color=blue
[contributors-url]: https://github.com/Thytu/SLAM/graphs/contributors
[pr-shield]: https://img.shields.io/github/issues-pr/Thytu/SLAM-ASR.svg?style=for-the-badge
[pr-url]: https://github.com/Thytu/SLAM/pulls
[issues]: https://img.shields.io/github/issues/Thytu/SLAM-ASR
[forks-shield]: https://img.shields.io/github/forks/Thytu/SLAM-ASR.svg?style=for-the-badge&color=blue
[forks-url]: https://github.com/Thytu/SLAM/network/members
[stars-shield]: https://img.shields.io/github/stars/Thytu/SLAM-ASR.svg?style=for-the-badge&color=yellow
[stars-url]: https://github.com/Thytu/SLAM/stargazers
[issues-shield]: https://img.shields.io/github/issues/Thytu/SLAM-ASR.svg?style=for-the-badge&
[issues-url]: https://github.com/Thytu/SLAM/issues
[license-shield]: https://img.shields.io/github/license/Thytu/SLAM-ASR.svg?style=for-the-badge&color=indigo
[license-url]: https://github.com/Thytu/SLAM/blob/master/LICENSE

## TODO List

### Model
- [X] `SLAM` must accepts a batched tensor as input (currently expects a list representing a single audio sample)
- [ ] `SLAM.encoder` should not have to use the fined-tunable version of `hubert-large-ls960`
- [X] `SLAM.generate_transcript` method must be autoregressive and fully transcribe the input audio

### Data
- [X] Write the data-preprocessing functions
- [X] data-preprocessing must capitalize the text properly (not all cap)
- [X] Export processed dataset locally to be loaded at training time
- [ ] Reduce number of samples for continous training
- [ ] Link hydra to data_handler
- [ ] Support other datasets
- [ ] Create audio instruct dataset

### Training
- [X] Write the training functions
- [X] Overfeat the model on a subset of librispeech
- [X] Train the model on the full set of librispeech
- [X] Fix why the model doesn't procudes EOS (or issue on inference fn?)
- [X] Padding should be set to max(len_of_inputs) instead of always 2048
- [ ] Pre-training on projector
- [ ] Support other LLM
- [ ] Support other speech encoder

### Evaluation
- [X] Evaluate on librispeech
- [ ] Check if it impacts phi2 results on OpenLLM-Leaderboard

### Distribution
- [ ] Use [hydra-zen](https://mit-ll-responsible-ai.github.io/hydra-zen/) to create a user CLI
- [ ] Write a proper README
- [ ] Write a "How to use the model" doc with everything required for inference (i.e using feature_extractor)
- [X] Upload model to Hugging-Face
- [ ] Create a Hugging-Face Space for the model
- [ ] Record a Video reproducing the projects
- [ ] Share over HF's discord in i-made-this channel
- [ ] Write a blog post presenting the projects and its inner working
- [ ] Present the project over twitter

<p align="right">(<a href="#top">back to top</a>)</p>
