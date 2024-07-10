# Slides
[Building Custom LLMs.pdf](https://github.com/amaung-us/presentations/blob/KCDC24---Building-Custom-LLMs/Building%20Custom%20LLMs.pdf)

# Requirements
[requirements.txt](https://github.com/amaung-us/presentations/blob/KCDC24---Building-Custom-LLMs/Demo/requirements.txt) Required python libraries.

# Conversions
1. [convert_llama_weights_to_hf.ipynb](https://github.com/amaung-us/presentations/blob/KCDC24---Building-Custom-LLMs/Demo/conversions/convert_llama_weights_to_hf.ipynb)
    - This notebook file uses [convert_llama_weights_to_hf.py](https://github.com/amaung-us/presentations/blob/KCDC24---Building-Custom-LLMs/Demo/conversions/convert_llama_weights_to_hf.py) to convert Meta's LLama models to HuggingFace format.
2. [convert-hf-to-mlx.ipynb](https://github.com/amaung-us/presentations/blob/KCDC24---Building-Custom-LLMs/Demo/conversions/convert-hf-to-mlx.ipynb)
    - This notebook will convert HuggingFace format to MLX format which can then be used on the Apple Silicon. To explore further on MLX refer to this git [ml-explore](https://github.com/ml-explore/mlx)
    - You will need to download a HuggingFace model or convert one to huggingface format. *hf_converted_model_path* is used for the path of the HuggingFace model. *mlxModelPath* is the MLX format output path.


# Finetunes
1. [KCDC-Linux-FineTune8B.ipynb](https://github.com/amaung-us/presentations/blob/KCDC24---Building-Custom-LLMs/Demo/finetune/KCDC-Linux-FineTune8B.ipynb) Used to finetune Llama3 8b on 2 x RTX4090s
2. [KCDC-Mac-llama3-8b.ipynb](https://github.com/amaung-us/presentations/blob/KCDC24---Building-Custom-LLMs/Demo/finetune/KCDC-Mac-llama3-8b.ipynb) this demonstrates finetuning Llama3 8b on Apple Silicon
3. [KCDC-Mac-Phi3-Medium128k.ipynb](https://github.com/amaung-us/presentations/blob/KCDC24---Building-Custom-LLMs/Demo/finetune/KCDC-Mac-Phi3-Medium128k.ipynb) this demonstrates finetuning Phi3 Menium128k on Apple Silicon

