FROM alpine:3.7
LABEL maintainer "Adrian B. Danieli - https://github.com/sickp"
ENTRYPOINT ["/entrypoint.sh"]
EXPOSE 22
COPY rootfs /

RUN apk add --no-cache openssh \
  && sed -i s/#PermitRootLogin.*/PermitRootLogin\ yes/ /etc/ssh/sshd_config \
  && echo "root:root" | chpasswd

# Originally from
# https://github.com/sickp/docker-alpine-sshd
# docker build -t wlovins/sshserver:1.0.0 .
# docker run --rm --publish=2222:22 wlovins/sshserver:1.0.0
