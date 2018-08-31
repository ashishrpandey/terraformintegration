FROM node:8.9.4
RUN mkdir /root/packer
WORKDIR /root/packer
RUN wget https://releases.hashicorp.com/packer/1.1.3/packer_1.1.3_linux_amd64.zip
RUN wget https://releases.hashicorp.com/terraform/0.11.1/terraform_0.11.1_linux_amd64.zip
RUN apt-get update
RUN apt-get install unzip -y
RUN unzip packer_1.1.3_linux_amd64.zip
RUN unzip terraform_0.11.1_linux_amd64.zip
RUN mv packer /usr/local/bin/packer
RUN mv terraform /usr/local/bin/terraform
RUN rm packer_1.1.3_linux_amd64.zip
RUN rm terraform_0.11.1_linux_amd64.zip
RUN mkdir /root/git
WORKDIR /root/git
RUN apt-get install build-essential libssl-dev libcurl4-gnutls-dev libexpat1-dev gettext unzip -y
RUN wget https://github.com/git/git/archive/v2.9.5.zip -O git.zip
RUN unzip git.zip
WORKDIR /root/git/git-2.9.5
RUN make configure
RUN ./configure --prefix=/usr
RUN make all
RUN make install