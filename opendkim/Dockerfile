# Alpine 3.13 ships with Postfix 3.5.10
FROM debian:latest

# Install dependencies
RUN apt-get update && \
    apt-get install opendkim netcat-traditional -y && apt-get clean

RUN mkdir /config
# Mark used folders
#
RUN groupadd -r opendkim && \
    useradd -r -g opendkim -d /var/run/opendkim -s /usr/sbin/nologin opendkim

RUN mkdir -p /var/run/opendkim && \
    chown -R opendkim:opendkim /var/run/opendkim

# Expose opendkim submission agent port
EXPOSE 8891

USER opendkim
# Start postfix in foreground mode
#CMD ["nc", "-l", "-p", "25"]
CMD ["opendkim", "-f", "/config/opendkim.conf"]
