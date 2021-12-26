FROM docker.io/library/alpine:3.15

# Install dependencies
## Install vim
RUN apk update
RUN apk add vim

## Install git
RUN apk add git
## Install pip
RUN apk add py3-pip

ADD .vimrc /root/

## Install vimwiki_markdown
RUN pip3 install vimwiki_markdown

## Install vimwiki
RUN git clone https://github.com/vimwiki/vimwiki.git $HOME/.vim/pack/plugins/start/vimwiki
