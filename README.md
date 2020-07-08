Raspberry pi avec raspbian installé


sudo apt-get install libasound2-dev

sudo python2 -m pip install Mopidy-AlsaMixer

sudo mkdir -p /opt/musicbox/webclient/

sudo chown -R  mopidy /opt/musicbox

alsamixer pour monter le son de sortie.

sudo bash -c 'cat > /etc/udev/rules.d/99-input.rules' << EOF
KERNEL=="event*", NAME="input/%k", MODE="660", GROUP="audio"
EOF

##Troubleshooting

sudo mopidyctl config

WARNING  /etc/mopidy/mopidy.conf has errors, line 4, 8, 14, 16, 57, 61, 63, 65, 67, 69, 94 has been ignored.
ERROR    Loading logging config '/etc/mopidy/logging.conf' failed. unexpected EOF while parsing (<string>, line 1)

[podcast]
enabled = false  ; Extension disabled due to config errors.

cat /var/log/mopidy/mopidy.log 
