# GreenDrive

[![](https://img.shields.io/badge/made%20by-greendrive-blue.svg?style=flat-square)](https://greendrive.app/)
[![](https://img.shields.io/badge/project-glows.ai-blue.svg?style=flat-square)](http://glows.ai/)
[![total download count](https://img.shields.io/github/downloads/greendrive/greendrive/total.svg?style=flat-square&label=all%20downloads)](https://github.com/greendrive/greendrive/releases)

**GreenDrive is a [BNB Greenfield](https://greenfield.bnbchain.org/en) desktop application available on Windows, Mac, and Linux.**

| Files screen | Huggingface screen | Transfer screen | Uploading screen | Management screen|
|-------|---------|-------|----------|------|
| <img src="https://github.com/greendrive/greendrive/assets/109056914/0adc36dc-8e46-4d5d-a266-d505baf5b8d0" width="600" height="auto"/> | <img src="https://github.com/greendrive/greendrive/assets/109056914/ffc2296e-fed0-4ae7-889a-007e6ee96b18" width="600" height="auto"/> | <img src="https://github.com/greendrive/greendrive/assets/109056914/6456bbe4-2fd1-4de9-9748-b5f3d089ee2a" width="600" height="auto"/> | <img src="https://github.com/greendrive/greendrive/assets/109056914/8a332081-07cb-4dae-9d03-952ef3533d9a" width="600" height="auto"/> | <img src="https://github.com/greendrive/greendrive/assets/109056914/2c7471b9-15b7-4dca-b9ca-3501fd466cdb" width="600" height="auto"/> |

### Quick-install shortcuts

When in doubt, pick one of package formats with built-in automatic update mechanism:

- **Windows:** [greendrive_windows.zip](https://github.com/greendrive/greendrive/releases/download/v0.9.3/greendrive_windows.zip)
- **Linux:**  [greendrive_linux.zip](https://github.com/greendrive/greendrive/releases/download/v0.9.3/greendrive_linux.zip)

#### Example

1. Installing the greendrive app on Windows

<img src="https://github.com/greendrive/greendrive/assets/109056914/ad964935-2779-43e0-aa63-db826a3c87f0" width="600" height="auto"/>

Locate the winfsp-2.0.23075.msi file for installation at 
```
C:\Users\user\Downloads\greendrive\datasetfs\winfsp-2.0.23075.msi
```
<img src="https://github.com/greendrive/greendrive/assets/109056914/edcfcff0-9247-4b10-a0b3-6638446b2501" width="600" height="auto"/>

<img src="https://github.com/greendrive/greendrive/assets/109056914/52017d07-a53b-427e-9b81-ddeba5c4d386" width="300" height="auto"/>

If necessary, please set up the Greendrive proxy.

<img src="https://github.com/greendrive/greendrive/assets/109056914/9d73cfe2-ab08-484f-9ff0-d209743989f0" width="600" height="auto"/>

Click 'Mount' and the dataset folder for the remote connection will appear on the desktop.

2. Installing the greendrive app on Ubuntu

We update the system packages.
```
sudo apt update
sudo apt install libsnappy-dev libfuse-dev -y
echo "user_allow_other" | sudo tee -a /etc/fuse.conf
```

runs `./run.sh` directly in terminal

### Roadmap

We are building GreenDrive to combine GreenField storage technology with Glows.ai indexing engine.

![diagram](https://github.com/greendrive/greendrive/assets/109056914/d32bc939-5538-435e-9ba5-62ba522aeea5)
