# Additional Steps

## Add below text to ~/.bash_profile or ~/.bashrc

```sh
# >>> conda initialize >>>
# !! Contents within this block are managed by 'conda init' !!
__conda_setup="$('/d/conda/Scripts/conda.exe' 'shell.bash' 'hook' 2> /dev/null)"
if [ $? -eq 0 ]; then
    eval "$__conda_setup"
else
    if [ -f "/d/conda/etc/profile.d/conda.sh" ]; then
        . "/d/conda/etc/profile.d/conda.sh"
    else
        export PATH="/d/conda/bin:$PATH"
    fi
fi
unset __conda_setup
# <<< conda initialize <<<
```

## Install Jupyter in the Conda Environment

Ensure Jupyter is installed in your Conda environment

```sh
conda install jupyter
```

## Install FFmpeg Using Conda

You can install FFmpeg directly within your Conda environment using the conda-forge channel.

```sh
conda install -c conda-forge ffmpeg
```

## Verify Installation:

After installation, verify that FFmpeg is correctly installed and accessible from your Conda environment.

```sh
ffmpeg -version
```

## fix AttributeError: partially initialized module 'charset_normalizer' has no attribute 'md__mypyc' (most likely due to a circular import)

```sh
pip uninstall charset-normalizer
pip install charset-normalizer
```

##  fix ImportError: cannot import name 'DisabledRepoError' from 'huggingface_hub.utils._errors

```sh
conda install -c conda-forge huggingface_hub
```

##  fix ImportError: openai

```sh
pip install --upgrade openai
```

## Install PyTorch with CUDA Support

```sh
pip install nvidia-pyindex nvidia-cuda-runtime-cu12
conda install cuda -c nvidia
conda install -c conda-forge cudatoolkit=11.2 cudnn=8.1.0
conda install pytorch torchvision torchaudio cudatoolkit=11.2 -c pytorch -c nvidia
```

```sh
 nvcc --version
 # Ensure that the correct NVIDIA drivers compatible with your CUDA version are installed.
 nvidia-smi
 ```

pip uninstall torch torchvision torchaudio
pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu117

conda install pytorch torchvision torchaudio cudatoolkit=11.8 -c pytorch

export CUDA_PATH="/c/Program Files/NVIDIA GPU Computing Toolkit/CUDA/v12.5/bin"
export LD_LIBRARY_PATH="/c/Program Files/NVIDIA GPU Computing Toolkit/CUDA/v12.5/lib/x64"
export PATH="${CUDA_PATH}:~/utils/php-8.1.22-nts-Win32-vs16-x86/:~/AppData/Local/ComposerSetup/bin:/c/Users/bilgr/AppData/Roaming/Composer/vendor/bin:$PATH"


ldconfig -p | grep cuda


### Make sure to check below link to check version compatiblity

https://pytorch.org/get-started/previous-versions/

<!-- conda install pytorch==1.13.1  pytorch-cuda=11.8 -c pytorch -c nvidia -->
<!-- conda install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu118  -->

```sh
conda install pytorch==2.3.0 torchvision==0.18.0 torchaudio==2.3.0 pytorch-cuda=11.8 -c pytorch -c nvidia
```