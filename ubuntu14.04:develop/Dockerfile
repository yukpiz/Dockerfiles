# Docker image build file.
# TAG: yukpiz/ubuntu:develop

FROM yukpiz/ubuntu:base
MAINTAINER yukpiz<yukpiz@gmail.com>

RUN apt-get install -y lua5.1
RUN apt-get install -y lua5.1-dev

RUN mkdir -pv /workspace/repository/watch
RUN hg clone https://vim.googlecode.com/hg /workspace/repository/watch/vim

# Vim compiling.
RUN cd /workspace/repository/watch/vim/; ./configure --with-features=huge --with-compiledby="yukpiz <yukpiz@gmail.com>" --with-lua-prefix=/usr --enable-fail-if-missing --enable-multibyte --enable-luainterp --disable-darwin --disable-selinux; make; make install;

