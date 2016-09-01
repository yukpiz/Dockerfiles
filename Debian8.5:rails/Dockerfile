# Docker image build file.
# TAG:   yukpiz/debian:rails
# BUILD: docker build -t debian:rails ./
# RUN: docker run --name [name] -it -p 8080:80 debian:rails /bin/bash

FROM debian
MAINTAINER yukpiz<yukpiz@gmail.com>

CMD /bin/bash

RUN cat /etc/debian_version
RUN apt-get update
RUN apt-get upgrade -y
RUN apt-get install -y nginx
RUN apt-get install -y git wget bzip2 gcc libssl-dev libreadline-dev nginx libcurl4-openssl-dev g++ make

RUN git clone https://github.com/sstephenson/rbenv.git /root/.rbenv
RUN git clone https://github.com/sstephenson/ruby-build.git /root/.rbenv/plugins/ruby-build
RUN ./root/.rbenv/plugins/ruby-build/install.sh

ENV PATH $PATH:/root/.rbenv/bin
RUN echo $PATH
RUN echo 'eval "$(rbenv init -)"' >> /etc/profile.d/rbenv.sh
RUN echo 'eval "$(rbenv init -)"' >> .bashrc
RUN rbenv --version && rbenv --help
RUN rbenv install --list | grep 2.3
RUN rbenv install 2.3.1
RUN rbenv global 2.3.1
RUN rbenv versions
RUN ruby --version

RUN gem install passenger
RUN passenger-install-nginx-module --auto
ADD nginx.conf /etc/nginx/
RUN /etc/init.d/nginx start

EXPOSE 80
