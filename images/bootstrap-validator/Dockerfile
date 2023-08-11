# Use a base image
FROM ubuntu:latest

# Install necessary software
RUN apt update && apt install -y curl vim bzip2

# Install Solana and set PATH
RUN sh -c "$(curl -sSfL https://release.solana.com/v1.16.5/install)"
#RUN export PATH="/root/.local/share/solana/install/active_release/bin:$PATH"
#RUN echo 'export PATH="/root/.local/share/solana/install/active_release/bin:$PATH"' >> ~/.bashrc
#RUN /bin/bash -c "source ~/.bashrc"
ENV PATH="${PATH}:/root/.local/share/solana/install/active_release/bin"

# Copy the local folder into the image
COPY ./workspace /workspace

# Set the working directory
WORKDIR /workspace

RUN echo "hey"

# Run your application or set other instructions
CMD ["./start-bootstrap-validator.sh"]
