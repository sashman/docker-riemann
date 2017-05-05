FROM java:8

MAINTAINER Matthias Nüßler <m.nuessler@web.de>

ENV RIEMANN_VERSION 0.2.13

ADD https://github.com/riemann/riemann/releases/download/${RIEMANN_VERSION}/riemann_${RIEMANN_VERSION}_all.deb /tmp/
RUN dpkg -i /tmp/riemann_${RIEMANN_VERSION}_all.deb && \
    rm /tmp/riemann* && \
    mkdir -p /etc/riemann/conf.d

COPY riemann.config /etc/riemann/

EXPOSE 5555 5556

CMD ["start"]
ENTRYPOINT ["/usr/bin/riemann"]
