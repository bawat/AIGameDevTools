FROM pytorch/pytorch:2.1.0-cuda11.8-cudnn8-devel
RUN apt update
RUN apt install -y git
RUN pip install transformers>=4.33.0 optimum>=1.12.0
RUN pip install auto-gptq --extra-index-url http://huggingface.github.io/autogptq-index/whl/cu118/  # Use cu117 if on CUDA 11.7

RUN git clone --single-branch --branch main http://huggingface.co/TheBloke/Wizard-Vicuna-13B-Uncensored-GPTQ
COPY GPTQRun.py /workspace/GPTQRun.py
COPY LlamaRun.sh /workspace/LlamaRun.sh
WORKDIR Wizard-Vicuna-13B-Uncensored-GPTQ
RUN apt install -y git git-lfs
RUN git lfs pull
WORKDIR ..
RUN git clone http://github.com/turboderp/exllamav2
WORKDIR exllamav2
RUN pip install -r requirements.txt
WORKDIR ..