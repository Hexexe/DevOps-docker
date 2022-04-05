FROM ubuntu:20.04
COPY script.sh .
RUN apt update && apt install -y curl && chmod +x script.sh
CMD ./script.sh
