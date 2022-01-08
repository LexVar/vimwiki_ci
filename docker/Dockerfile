FROM docker.io/library/alpine:3.15 as builder

## Install vimwiki_markdown
RUN apk add --update py3-pip && \
pip3 install --user vimwiki_markdown

## Install vimwiki
RUN apk add git && \
git clone https://github.com/vimwiki/vimwiki.git $HOME/.vim/pack/plugins/start/vimwiki

ADD .vimrc /root/

FROM docker.io/library/alpine:3.15
COPY --from=builder \
	/root			\
	/root

# Install vim and python3
RUN apk add --update --no-cache vim python3

CMD ["/usr/bin/vim", "+VimwikiIndex", "+VimwikiAll2HTML", "+q"]
