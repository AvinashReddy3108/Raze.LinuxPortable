# Set the base image to use for subsequent instructions
FROM debian:stable-slim

# Ensure non-interactive environment
ENV DEBIAN_FRONTEND=noninteractive

# Install dependencies
RUN apt-get update && \
    apt-get upgrade -y && \
    apt-get install --no-install-recommends -y g++ make cmake libsdl2-dev git zlib1g-dev \
                       libbz2-dev libjpeg-dev libfluidsynth-dev libgme-dev libopenal-dev \
                       libmpg123-dev libsndfile1-dev libgtk-3-dev timidity nasm \
                       libgl1-mesa-dev tar libsdl1.2-dev libglew-dev libvpx-dev

# Copy any source file(s) required for the action
COPY entrypoint.sh /entrypoint.sh

# Set the working directory inside the container
WORKDIR /github/workspace

# Configure the container to be run as an executable
ENTRYPOINT ["/entrypoint.sh"]
