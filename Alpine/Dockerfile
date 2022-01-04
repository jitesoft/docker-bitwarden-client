# syntax = docker/dockerfile:experimental
FROM registry.gitlab.com/jitesoft/dockerfiles/alpine:3.14
ARG VERSION
LABEL maintainer="Johannes Tegnér <johannes@jitesoft.com>" \
      maintainer.org="Jitesoft" \
      maintainer.org.uri="https://jitesoft.com" \
      com.jitesoft.project.repo.type="git" \
      com.jitesoft.project.repo.uri="https://gitlab.com/jitesoft/dockerfiles/bitwarden-client" \
      com.jitesoft.project.repo.issues="https://gitlab.com/jitesoft/dockerfiles/bitwarden-client/issues" \
      com.jitesoft.project.registry.uri="registry.gitlab.com/jitesoft/dockerfiles/bitwarden-client" \
      com.jitesoft.app.bitwarden.version="${VERSION}"

ARG TARGETARCH

RUN --mount=type=bind,source=./artifacts,target=/tmp/artifacts \
    mv /tmp/artifacts/bw-${TARGETARCH} /usr/local/bin/bw \
 && mv /tmp/artifacts/entrypoint /usr/local/bin/entrypoint \
 && chmod +x /usr/local/bin/bw \
 && chmod +x /usr/local/bin/entrypoint \
 && addgroup -g 1000 bitwarden \
 && adduser -u 1000 -G bitwarden -s /bin/sh -D bitwarden

USER bitwarden

ENTRYPOINT ["entrypoint"]
CMD ["bw", "--help"]
