FROM alpine:latest

ENV TZ=Asia/Seoul
RUN set -x \
&& apk add --no-cache \
    tzdata \
    openssh \
    && cp /usr/share/zoneinfo/$TZ /etc/localtime\
    && echo $TZ > /etc/timezone \
    && apk del tzdata \
    && ssh-keygen -A \
    && echo 'root:dev' | chpasswd

COPY sshd_config /etc/ssh/sshd_config
COPY id_rsa.pub /tmp/id_rsa.pub

RUN mkdir -p ~/.ssh && cat /tmp/id_rsa.pub >> ~/.ssh/authorized_keys

EXPOSE 22

CMD ["/usr/sbin/sshd","-D"]
