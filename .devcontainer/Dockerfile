
FROM debian:9

RUN \
  apt-get update \
  && apt-get install -y curl \
  && curl -sL https://deb.nodesource.com/setup_12.x | bash - \
  && apt-get install -y \
    git \
    nodejs \
    libnss3 \
    libxss1 \
    libatk-bridge2.0-0 \
    libgtk-3-0 \
    libasound2 \
    locales \
    zsh \
    procps \
    libx11-xcb-dev \
    xdg-utils \
  && localedef -i en_US -c -f UTF-8 -A /usr/share/locale/locale.alias en_US.UTF-8

ENV \
  LANG=en_US.utf8 \
  SHELL=/usr/bin/zsh

RUN \
  sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)" \
  && git clone --depth 1 https://github.com/junegunn/fzf.git ~/.fzf \
  && ~/.fzf/install --all

CMD ["/usr/bin/zsh"]
