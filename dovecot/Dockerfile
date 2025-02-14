# Alpine 3.13 ships with Postfix 3.5.10
FROM debian:latest

# Install dependencies
RUN apt-get update && \
    apt-get install dovecot-imapd netcat-traditional -y && apt-get clean

# Mark used folders
#VOLUME [ "/var/spool/postfix", "/etc/postfix" ]

# Expose mail submission agent port
EXPOSE 993

# Start postfix in foreground mode
#CMD ["nc", "-l", "-p", "993"]
CMD ["dovecot", "-F", "-c", "/config/dovecot.conf" ]
#CMD ["nc", "-l", "-p", "25"]
