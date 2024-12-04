# FLUX.1-RealismLora docker

Dockerization of the [Hugging Face black-forest-labs/FLUX.1-schnell Space](https://huggingface.co/spaces/black-forest-labs/FLUX.1-schnell)

![FLUX.1-RealismLora](https://raw.githubusercontent.com/maximofn/FLUX.1-RealismLora-docker/refs/heads/main/assets/FLUX.1%20RealismLora.png)

 * Space: [https://huggingface.co/spaces/black-forest-labs/FLUX.1-schnell](https://huggingface.co/spaces/black-forest-labs/FLUX.1-schnell)

## Requisites

[Docker](https://docs.docker.com/desktop/) and [nvidia container toolkit](https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/latest/install-guide.html) must be installed.

## Usage

### Download the image from the Docker Hub

You can download the image and run it

```bash
docker pull maximofn/flux-1-realismlora:latest
./run_app.sh
```

### Build the image

Or you can build the image and run it

```bash
./build_docker_image.sh
./run_app.sh
```