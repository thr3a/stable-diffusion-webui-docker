# Source: https://github.com/AbdBarho/stable-diffusion-webui-docker/blob/master/services/AUTOMATIC1111/Dockerfile
FROM thr3a/torch:latest

ENV COMMANDLINE_ARGS="--deepdanbooru"

RUN git clone https://github.com/AUTOMATIC1111/stable-diffusion-webui.git \
  && cd stable-diffusion-webui \
  && git reset --hard 36a0ba357ab0742c3c4a28437b68fb29a235afbe

WORKDIR /app/stable-diffusion-webui

RUN COMMANDLINE_ARGS="${COMMANDLINE_ARGS} --skip-torch-cuda-test --exit"  python launch.py && pip cache purge
RUN pip install --no-cache-dir opencv-python-headless
RUN pip install --no-cache-dir git+https://github.com/facebookresearch/xformers.git@v0.0.13#egg=xformers
