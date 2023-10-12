FROM docker.io/tensorflow/tensorflow:2.13.0-gpu

RUN apt-get update && DEBIAN_FRONTEND="noninteractive" TZ="Europe/Stockholm" apt-get install -y python3 python3-pip wget git
RUN python3 -m pip install --upgrade pip
RUN pip3 install matplotlib pycolonies

# Install Colonies
ENV PATH="$PATH:/root/go/bin" 
RUN cd /root; wget https://go.dev/dl/go1.20.7.linux-amd64.tar.gz; tar -xzf go1.20.7.linux-amd64.tar.gz;git clone https://github.com/colonyos/colonies.git; cd colonies; make; make install; cd ..; rm -rf go; rm -rf colonies; rm go1.20.7.linux-amd64.tar.gz
