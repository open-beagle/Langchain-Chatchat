# Langchain-Chatchat

## python venv

```bash
## init venv
. .venv/bin/activate
```

## startup

```bash
# startup
python startup.py -a
```

## init

```bash
# copy config
python copy_config_example.py

# edit configs/model_config.py
sed -i --expression "s?MODEL_ROOT_PATH = .*?MODEL_ROOT_PATH = \".cache\"?" configs/model_config.py

# install libs
pip install jq
sudo apt-get update && sudo apt-get install ffmpeg libsm6 libxext6  -y

# init db
python init_database.py --recreate-vs
```

## download models

<https://hf-mirror.com/>

```bash
# install huggingface-cli
pip install -U huggingface_hub

mkdir -p .cache

# git clone https://huggingface.co/THUDM/chatglm3-6b
export HF_ENDPOINT=https://hf-mirror.com && \
huggingface-cli download --resume-download THUDM/chatglm3-6b --local-dir .cache/THUDM/chatglm3-6b

# git clone https://huggingface.co/BAAI/bge-large-zh
export HF_ENDPOINT=https://hf-mirror.com && \
huggingface-cli download --resume-download BAAI/bge-large-zh --local-dir .cache/BAAI/bge-large-zh
```

## install libs

```bash
## install jq for train models
pip install jq

## install pytorch with cpu
# https://pytorch.org/
pip install torch==2.1.2 torchvision==0.16.2 torchaudio==2.1.2 --index-url https://download.pytorch.org/whl/cpu

# test pytorch installation
python -m torch.utils.collect_env

## install pytorch plugins xformers with cpu
# https://github.com/facebookresearch/xformers
pip install xformers==0.0.23.post1

# test xformers installation
python -m xformers.info

## install project libs
pip install -r requirements.txt
pip install -r requirements_api.txt
pip install -r requirements_webui.txt
```

## python

```bash
# python 3.11
python3.11 -m venv $PWD/.venv

pip config set global.index-url https://mirrors.aliyun.com/pypi/simple/
```

## git

<https://github.com/chatchat-space/Langchain-Chatchat>

```bash
git remote add upstream git@github.com:chatchat-space/Langchain-Chatchat.git

git fetch upstream

git merge v0.2.10
```
