FROM elasticsearch:2.4

RUN echo "xpack.security.enabled: false" >> /usr/share/elasticsearch/config/elasticsearch.yml
RUN bin/plugin install analysis-icu && \
    bin/plugin install analysis-phonetic

ADD docker-healthcheck.sh /docker-healthcheck.sh

HEALTHCHECK --retries=3 CMD ["sh", "/docker-healthcheck.sh"]

EXPOSE 9200 9300
