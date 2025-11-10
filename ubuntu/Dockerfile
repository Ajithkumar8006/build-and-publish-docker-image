# Use the official Ubuntu base image
FROM ubuntu:latest

# Set environment variables to avoid interactive prompts during build
ENV DEBIAN_FRONTEND=noninteractive

# Update and upgrade all packages, then clean up
RUN apt-get update && \
    apt-get -y upgrade && \
    apt-get -y dist-upgrade && \
    apt-get autoremove -y && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# Set default working directory
WORKDIR /root

# Optional: show the Ubuntu version
CMD ["bash", "-c", "cat /etc/os-release && bash"]
