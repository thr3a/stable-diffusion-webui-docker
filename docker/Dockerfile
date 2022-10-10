# Source: https://github.com/AbdBarho/stable-diffusion-webui-docker/blob/master/services/AUTOMATIC1111/Dockerfile
FROM thr3a/torch:latest

ENV COMMANDLINE_ARGS="--deepdanbooru"

RUN git clone https://github.com/AUTOMATIC1111/stable-diffusion-webui.git \
  && cd stable-diffusion-webui \
  && git reset --hard 0609ce06c0778536cb368ac3867292f87c6d9fc7

WORKDIR /app/stable-diffusion-webui

# RUN sed -i '/^if __name__/d' launch.py
# RUN sed -i '/^    start_webui/d' launch.py
RUN COMMANDLINE_ARGS="${COMMANDLINE_ARGS} --skip-torch-cuda-test --exit"  python launch.py && pip cache purge
RUN pip install opencv-python-headless && pip cache purge
