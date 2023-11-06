FROM pytorch/pytorch:2.1.0-cuda12.1-cudnn8-devel
ENV DEBIAN_FRONTEND=noninteractive

RUN apt update
RUN apt install -y ffmpeg git

RUN pip install -U audiocraft  # stable release