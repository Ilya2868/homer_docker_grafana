1. git clone https://github.com/sipcapture/homer7-docker
/
2. replace docker-compose.yml\
\
3. change drop_days for base(Loki,grafana) and add volumes\
\
4. docker compose up -d\
\
5. folder promtail  copy to asterisk server with ansible or manually\
\
systemctl enable \'97now promtail \
\
6. create alert rules and contacts points and notification templates in Grafana\
\
7. hep.conf and modules to your asterisk and replace names and IP in this files\
\
5. captagent if you need  this and if you use chan_sip\
\
git clone https://github.com/sipcapture/captagent.git /usr/src\
\
apt-get install libexpat-dev libpcap-dev libjson-c-dev libtool automake flex bison libgcrypt-dev libuv1-dev libpcre3-dev libfl-dev\
\
\
cp /usr/src/captagent/init/deb/debian/captagent.service /etc/systemd/system/captagent.service\
cp /captagent/socket_pcap.xml  /usr/local/captagent/etc/captagent/socket_pcap.xml \
\pard\tx566\tx1133\tx1700\tx2267\tx2834\tx3401\tx3968\tx4535\tx5102\tx5669\tx6236\tx6803\pardirnatural\partightenfactor0
\cf0 cp /captagent/transport_hep.xml  /usr/local/captagent/etc/captagent/transport_hep.xml\
\
systemctl enable \'97now captagent }

# homer_docker_grafana
homer stack in docker and grafana push
