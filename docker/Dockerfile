FROM nvcr.io/nvidia/cuda:11.8.0-cudnn8-devel-ubuntu22.04

RUN apt-get update \
    && apt-get install -y --no-install-recommends git git-lfs python3 python3-pip \
    && apt-get install -y --no-install-recommends libgl1-mesa-glx libglib2.0-0 \
    && curl -s https://packagecloud.io/install/repositories/github/git-lfs/script.deb.sh | bash \
    && git lfs install \
    && rm cuda-keyring_1.0-1_all.deb \
    && ln -s /usr/bin/python3 /usr/bin/python \
    && rm -rf /var/lib/apt/lists/*

RUN pip3 install --no-cache-dir torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu118

RUN git clone --depth 1 https://huggingface.co/spaces/black-forest-labs/FLUX.1-schnell \
    && cd FLUX.1-schnell && pip3 install --no-cache-dir -r requirements.txt

RUN pip3 install --no-cache-dir gradio spaces protobuf

RUN sed -i 's/pipe = DiffusionPipeline.from_pretrained("black-forest-labs\/FLUX.1-schnell", torch_dtype=dtype).to(device)/pipe = DiffusionPipeline.from_pretrained("Freepik\/flux.1-lite-8B-alpha", torch_dtype=dtype, device_map="balanced")/g' /FLUX.1-schnell/app.py

WORKDIR /FLUX.1-schnell