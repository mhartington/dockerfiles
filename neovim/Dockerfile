# Taken from erroneousboat/neovim
#
#  docker run \
#    -it \
#    -v /Users/Jeff/tmp/nvim-typescript-troubleshooting/:/data
#    -v /Users/Jeff/tmp/nvim-typescript-troubleshooting/init.vim:/root/.config/init.vim
#    neovim \
#    -u /root/.config/init.vim
#
FROM ubuntu:latest

MAINTAINER deltaskelta <jrwillette88@gmail.com>


# cmdtest uses `yarn` in path takes over yarn namespace
RUN apt-get update && \
    apt-get install -y software-properties-common && \
    add-apt-repository -y ppa:neovim-ppa/stable && \
    apt-get update && \
    apt remove cmdtest yarn && \
    apt-get install -y \
        neovim python-dev python-pip python3-dev python3-pip nodejs curl git npm  && \
    pip install neovim && \
    pip3 install neovim && \
    pip install --upgrade neovim && \
    pip3 install --upgrade neovim && \
    npm install -g neovim

RUN apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

WORKDIR /data
ENTRYPOINT [ "nvim" ]
