FROM parrotsec/core

ARG USERNAME=hacker
ARG USER_ID=1000
ARG GROUP_ID=1000

COPY --from=ghcr.io/astral-sh/uv:latest /uv /uvx /usr/local/bin/

RUN apt-get update && apt-get install -y \
    ffuf \
    gobuster \
    unzip \
    httpie \
    && rm -rf /var/lib/apt/lists/*

RUN groupadd -g ${GROUP_ID} ${USERNAME} && \
    useradd -m -u ${USER_ID} -g ${GROUP_ID} -s /bin/bash ${USERNAME}

ENV COLORTERM=truecolor
ENV TERM=xterm-256color

WORKDIR /work

USER $USERNAME
