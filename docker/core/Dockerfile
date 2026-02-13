FROM parrotsec/core

ARG USERNAME=hacker
ARG USER_ID=1000
ARG GROUP_ID=1000

RUN apt-get update && \
    apt-get install -y ffuf && \
    rm -rf /var/lib/apt/lists/*

RUN groupadd -g ${GROUP_ID} ${USERNAME} && \
    useradd -m -u ${USER_ID} -g ${GROUP_ID} -s /bin/bash ${USERNAME}

WORKDIR /work

USER $USERNAME
