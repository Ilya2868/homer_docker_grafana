{\rtf1\ansi\ansicpg1251\cocoartf2822
\cocoatextscaling0\cocoaplatform0{\fonttbl\f0\fswiss\fcharset0 Helvetica;\f1\fnil\fcharset0 .AppleSystemUIFontMonospaced-Regular;}
{\colortbl;\red255\green255\blue255;\red0\green0\blue0;\red24\green26\blue30;\red244\green246\blue249;
}
{\*\expandedcolortbl;;\csgray\c0\c0;\cssrgb\c12157\c13725\c15686;\cssrgb\c96471\c97255\c98039;
}
\paperw11900\paperh16840\margl1440\margr1440\vieww12380\viewh10920\viewkind0
\pard\tx566\tx1133\tx1700\tx2267\tx2834\tx3401\tx3968\tx4535\tx5102\tx5669\tx6236\tx6803\pardirnatural\partightenfactor0

\f0\fs24 \cf0 \cb2 1. \cf3 \expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec3 git clone https://github.com/sipcapture/homer7-docker
\f1\fs27\fsmilli13600 \cb4 \

\f0\fs24 \cf0 \cb1 \kerning1\expnd0\expndtw0 \outl0\strokewidth0 \
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