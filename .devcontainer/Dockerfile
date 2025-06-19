FROM ghcr.io/prefix-dev/pixi:latest

WORKDIR /repo

RUN apt-get update && apt-get install -y git

COPY pyproject.toml /repo/pyproject.toml
COPY pixi.lock /repo/pixi.lock

RUN /usr/local/bin/pixi install --manifest-path pyproject.toml

COPY .devcontainer/entrypoint.sh /repo/entrypoint.sh
RUN chmod 700 /repo/entrypoint.sh

ENTRYPOINT ["/repo/entrypoint.sh"]




