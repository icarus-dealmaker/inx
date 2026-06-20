FROM ubuntu:latest

RUN apt-get update && apt-get install -y \
    curl wget git python3 python3-pip lsb-release software-properties-common gnupg \
    && rm -rf /var/lib/apt/lists/*

# Install clang-format-21
RUN wget https://apt.llvm.org/llvm.sh && \
    chmod +x llvm.sh && \
    ./llvm.sh 21 && \
    apt-get install -y clang-format-21 && \
    rm llvm.sh && \
    rm -rf /var/lib/apt/lists/*

# Install PlatformIO
RUN pip install --upgrade platformio --break-system-packages

# Make clang-format-21 available as clang-format
RUN ln -sf /usr/lib/llvm-21/bin/clang-format /usr/local/bin/clang-format
