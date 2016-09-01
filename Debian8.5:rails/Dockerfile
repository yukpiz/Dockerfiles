# Docker image build file.
# TAG: yukpiz/debian:rails

FROM debian
MAINTAINER yukpiz<yukpiz@gmail.com>

RUN cat /etc/debian_version
RUN apt-get update
RUN apt-get upgrade -y
RUN apt-get install -y nginx
RUN apt-get install -y git wget bzip2 gcc libssl-dev libreadline-dev nginx libcurl4-openssl-dev g++

RUN git clone https://github.com/sstephenson/rbenv.git ~/.rbenv
RUN git clone https://github.com/sstephenson/ruby-build.git ~/.rbenv/plugins/ruby-build

RUN echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bash_profile
RUN echo 'eval "$(rbenv init -)"' >> ~/.bash_profile
RUN source ~/.bash_profile
RUN rbenv --version && rbenv --help
RUN rbenv install --list | grep 2.3
RUN rbenv install 2.3.1
RUN rbenv global 2.3.1
RUN ruby --version

RUN gem install passenger
RUN passenger-install-nginx-module --auto

EXPOSE 80
