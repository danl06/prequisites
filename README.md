# EFREI-CAMP setup tutorial <a name="home"></a>

## Table of contents
1. [Installations / setups](#1)

## 1.   Installations / setups <a name="1"></a>
#### a. Per user
1. Docker : [installation link](https://docs.docker.com/get-docker/)

    ```
    docker pull heartexlabs/label-studio:1.4.0
    ```
    Check if your docker is functioning:
    ```
    cd labelstudioUI
    docker run -it -p 9999:9999 -v "%cd%"/mydata:/label-studio/data heartexlabs/label-studio:1.4.0 /bin/bash -c "label-studio start --port 9999"
    ```
    - For Linux / Mac, you need to change `%cd%` with `$pwd` or `$PWD`
    
    Note : for Windows, if it doesn't work you need to activate virtualization in the Bios (if not activated):
   - Check this url https://2nwiki.2n.cz/pages/viewpage.action?pageId=75202968
   - Pull this image:
- Make sure the Labelstudio Web app is accessible here http://localhost:9999, (check screen below)
<img src="doc-imgs/ls_welcome.PNG" width=500px/>

3. One Gmail account per user (will be used when working with COLAB)
 - Make sure you have free space in Google Drive if you do training with COLAB (at least 8 Gb)

5. Setup Python Env in local PC - open new terminal and run these lines :
    ```
    conda create -n labelstudioml python=3.8
    conda activate labelstudioml
    conda install nb_conda
    pip install jupyter git+https://github.com/amtam0/flair.git tensorboard
    cd ML_backend/label-studio-ml-backend
    pip install -U -e .
    ```
    
#### a. Per Team
1. `Ngrok` is used to convert local url to https for free, it will be used to share Webapp and Model's Api during labelling and evaluation process

    - You need to create **2 different accounts** per Team (1 acount per email) from this [LINK](https://ngrok.com/)
    - Validate your Ngrok verification by email
    - Download Ngrok depending on your OS, and add it to the home folder (unzipped Drive)

2. Download unzip the Project and upload it in your Google Drive (and COLAB) and share it with your Team
    - COLAB will be used for collaborative working on notebooks and folders sharing (can also be used for model training but not recommended)
    NOTE : at least 8 Gb free space in your Google Drive
