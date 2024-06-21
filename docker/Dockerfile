# syntax=docker/dockerfile:1

# A Dockerfile that can be used without cloning the project manually. It uses
# malb/lattice-estimator at HEAD. This is appropriate for users who want to use
# malb/lattice-estimator but do not want to set up a local development
# environment.
FROM ubuntu:23.10

RUN apt update && apt upgrade -y
RUN apt install -y git sagemath python3-pip

RUN git clone https://github.com/malb/lattice-estimator.git /lattice-estimator
WORKDIR /lattice-estimator

RUN sage --pip install --break-system-packages -r /lattice-estimator/requirements.txt
CMD ["sage"]
