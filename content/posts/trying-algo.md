---
title: "Trying Algo"
date: 2020-01-22T18:46:03Z
showDate: true
draft: true
tags: ["blog"]
---

## Do I need a VPN?

I probably don't need a personal VPN. I don't travel a great deal but, if I do, the company I work for takes care of a VPN for me. For personal use, I don't regularly find myself needing or wanting to connect to public wifi -- a 4G phone connection provides most of what I need.

I was listening to an episode of [Changelog](https://changelog.com/podcast/377) with the creator of [Algo](https://github.com/trailofbits/algo), and heard quite a few arguments against a lot of people's (or VPN companies') reasons *for* using a VPN. It's an interesting discussion and I won't do it justice by talking about it here so listen to it if you're interested. Anyway, whilst I probably don't need a VPN, Algo sounded interesting and useful in case my situation changed, so I thought I'd give it a go.

## Set up on ChromeOS

The GitHub page for Algo contains great documentation, but I did hit a snag trying to set it up on my Pixelbook. Although I have Python 3 installed, the default setup only includes python-3.5.3, but Algo requires 3.6 or later. 

There are a couple of options for installing a later version of Python. Unfortunately, I couldn't find Python 3.6 in the Debian repos, so I considered building it from source, or installing a package like [Anaconda](https://www.anaconda.com/).

### Building from source

This was easier than I thought. Download the source from [python.org](https://www.python.org) (I got python-3.8.1), extract the files, compile and make. I followed [this guide](https://gist.github.com/uogbuji/435d86684894997dc3d8d46da7da1ea9) which installs Python locally.

The only gotcha with this method is that without changing the bash environment the `python3` command defaults to the system python-3.5 installation.

### Using Anaconda

I first found out about Anaconda when I was interested in scientific applications of Python. It is a self-contained environment that is quite portable -- it allows me to install a full Python environment on my locked-down corporate Windows laptop. It also supports multiple Python environments and has a package manager called Conda. Download and setup is easy -- just grab the shell installer from the website and run it. 

## Setting up Algo

With a suitable version of Python installed, the instructions on the Algo GitHub page should work without any problems. Without changing any bash environment variables I modified the virtual environment setup command to:

```
$HOME/.local/bin/python3 -m virtualenv .env &&
source .env/bin/activate &&
python3 -m pip install -U pip virtualenv &&
python3 -m pip install -r requirements.txt
```
