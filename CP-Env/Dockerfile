# Pull the ubuntu base image
FROM ubuntu:22.04

# Set the noninteractive flag, to disable user interaction for inputs
ENV DEBIAN_FRONTEND=noninteractive

# Install required packages for development
RUN apt-get update && apt-get install -y \
    build-essential \
    g++ \
    gcc \
    cmake \
    gdb \
    golang \
    curl \
    wget \
    git \
    software-properties-common \
    unzip \
    python3 \
    python3-pip \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*


# Install VS code server
RUN curl -fsSL https://code-server.dev/install.sh | sh


# Install the libs for cpp and golang
RUN curl -L -o cpptools.vsix https://github.com/microsoft/vscode-cpptools/releases/download/v1.16.3/cpptools-linux.vsix
RUN code-server --install-extension ./cpptools.vsix

# Set environment variables
ENV PATH="/usr/local/go/bin:${PATH}"

# Set the working directory
WORKDIR /workspace

# Expose port for VS Code server
EXPOSE 8080

# Default command to start VS Code server
CMD ["code-server", "--bind-addr", "0.0.0.0:8080", "--auth", "none", "/workspace"]