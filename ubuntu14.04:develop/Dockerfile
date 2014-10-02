# Docker image build file.
# TAG: yukpiz/ubuntu:develop

FROM yukpiz/ubuntu:base
MAINTAINER yukpiz<yukpiz@gmail.com>

WORKDIR ~
RUN apt-get install -y lua5.1
RUN apt-get install -y lua5.1-dev

RUN mkdir -pv ~/workspace/repository/watch
WORKDIR ~/workspace/repository/watch
RUN hg clone https://vim.googlecode.com/hg vim
RUN git clone https://yukpiz@bitbucket.org/yukpiz/dotfiles.git dotfiles.git

WORKDIR ~/workspace/repository/watch/vim
RUN cp ~/workspace/repository/watch/dotfiles.git/vim-configure ~/workspace/repository/watch/vim/
RUN ./vim-configure
RUN make
RUN make install

WORKDIR ~
RUN mkdir -pv ~/.vim/bundle
RUN mkdir -pv ~/.vim/colors

RUN git clone https://github.com/Shougo/neobundle.vim.git ~/.vim/bundle/neobundle.vim
RUN git clone https://github.com/Shougo/vimproc.vim.git ~/.vim/bundle/vimproc.vim

WORKDIR ~/.vim/bundle/vimproc.vim/
RUN make

RUN cp ~/workspace/repository/watch/dotfiles.git/vimrc ~/.vimrc
RUN cp ~/workspace/repository/watch/dotfiles.git/bashrc ~/.bashrc
RUN cp ~/workspace/repository/watch/dotfiles.git/colors/railscasts.vim ~/.vim/colors/
# Logined run :NeoBundleInstall
