FROM ubuntu:22.04

# Copies your code file from your action repository to the filesystem path `/` of the container
COPY entrypoint.sh /entrypoint.sh

# Code file to execute when the docker container starts up (`entrypoint.sh`)
ENTRYPOINT ["/entrypoint.sh"] 
RUN chmod +x /entrypoint.sh

# Update new packages
RUN apt-get -qq update

RUN apt-get install -y \
    build-essential \
    curl \
    pkg-config \
    libssl-dev

# Get Rust
RUN curl https://sh.rustup.rs -sSf | bash -s -- -y

ENV PATH="/root/.cargo/bin:${PATH}"

RUN cargo install cargo-generate