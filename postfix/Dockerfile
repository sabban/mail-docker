# Alpine 3.13 ships with Postfix 3.5.10
FROM debian:latest

# Install dependencies
RUN apt-get update && \
    apt-get install postfix netcat-traditional -y && apt-get clean

RUN mkdir /config
# Mark used folders
#VOLUME [ "/var/spool/postfix", "/etc/postfix" ]

# Expose mail submission agent port
EXPOSE 587
EXPOSE 25

# Start postfix in foreground mode
#CMD ["nc", "-l", "-p", "25"]
CMD ["postfix", "start-fg"]
