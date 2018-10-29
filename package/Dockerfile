FROM fyery/fluentd:v0.1

ENV FLUENTD_CONF="fluent.conf"

RUN mkdir -p /fluentd/etc/buffer
RUN mkdir -p /fluentd/etc/config/custom/cluster/
RUN mkdir -p /fluentd/etc/config/custom/project/
RUN mkdir -p /fluentd/etc/config/system/

COPY fluent.conf /fluentd/etc/
COPY custom_cluster.conf /fluentd/etc/config/custom/
COPY custom_project.conf /fluentd/etc/config/custom/
COPY metrics.conf /fluentd/etc/config/system/

EXPOSE 24224 5140

CMD exec fluentd -c /fluentd/etc/${FLUENTD_CONF}
