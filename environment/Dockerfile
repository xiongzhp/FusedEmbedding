FROM registry.codeocean.com/codeocean/miniconda3:4.5.11-python3.7-cuda9.2-cudnn7-ubuntu18.04

ARG DEBIAN_FRONTEND=noninteractive

RUN apt-get update \
    && apt-get install -y --no-install-recommends \
      "python-qt4=4.12.1+dfsg-2" \
    && rm -rf /var/lib/apt/lists/*

RUN conda install --yes \
      --channel pytorch \
      --channel rdkit \
      --channel anaconda \
      cudatoolkit==10.0.130 \
      jupyter==1.0.0 \
      pytorch==1.1.0 \
      rdkit==2019.03.2.0 \
      seaborn==0.9.0 \
      torchvision==0.3.0 \
    && conda clean --yes --all

RUN pip install --upgrade --no-cache-dir --upgrade-strategy=only-if-needed \
      matplotlib==3.1.0 \
      sklearn==0.0
