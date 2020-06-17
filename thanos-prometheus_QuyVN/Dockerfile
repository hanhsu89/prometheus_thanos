FROM quay.io/prometheus/busybox:latest


COPY thanos-0.7.0.linux-amd64/thanos /bin/thanos
RUN chmod +x /bin/thanos
ENTRYPOINT [ "/bin/thanos" ]