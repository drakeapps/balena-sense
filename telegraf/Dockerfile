FROM balenalib/raspberry-pi:buster

COPY ./*.sh /usr/src/app/
RUN chmod +x /usr/src/app/*.sh

RUN install_packages wget

RUN /usr/src/app/download.sh "%%BALENA_ARCH%%"

RUN dpkg -i /tmp/telegraf.deb && rm /tmp/telegraf.deb
COPY telegraf.conf /etc/telegraf/telegraf.conf

CMD ["bash","/usr/src/app/entry.sh"]
