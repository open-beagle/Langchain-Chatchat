# Langchain-Chatchat

## Startup

```powershell
# venv
.venv\Scripts\activate

# startup
python startup.py -a
```

## init

```powershell
# init db
python copy_config_example.py
python init_database.py --recreate-vs
```

## windows allow ps scripts

```powershell
# https://learn.microsoft.com/zh-cn/powershell/module/microsoft.powershell.core/about/about_execution_policies?view=powershell-7.4
Get-ExecutionPolicy -Scope CurrentUser
Set-ExecutionPolicy -ExecutionPolicy Bypass
```

## python

```powershell
# python 3.11
python3.11 -m venv $PWD/.venv

.venv\Scripts\activate

pip config set global.index-url https://mirrors.aliyun.com/pypi/simple/
```

## pytorch on windows

```powershell
# Nvidia cuda11.8
# https://developer.nvidia.com/cuda-toolkit-archive
# torch2.2.1
# https://pytorch.org/
pip install torch torchvision torchaudio xformers --index-url https://download.pytorch.org/whl/cu118

# Mac or CPU
pip install torch torchvision torchaudio xformers
```

## install libs

```powershell
# delete torch torchvision torchaudio
# delete xformers
pip install -r .beagle\requirements.txt 
pip install -r .beagle\requirements_api.txt
pip install -r .beagle\requirements_webui.txt  

# test pytorch installation
python .beagle\pytorch.py

# test xformers installation
python -m xformers.info
```

## git

<https://github.com/chatchat-space/Langchain-Chatchat>

```bash
git remote add upstream git@github.com:chatchat-space/Langchain-Chatchat.git

git fetch upstream

git merge v0.2.10
```
