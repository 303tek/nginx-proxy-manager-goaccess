# nginx-proxy-manager-goaccess

run "docker-compose up -d"

stop the goaccess container

**Edit the following file: ./goaccess/storage/goaccess.conf** *(I've included my goaccess configuration)*

verify:
- real-time-html true

comment out:
- log-format COMBINED

add:
- log-format [%d:%t %^] %s - %m %^ %v "%U" [Client %h] [Length %b] [Gzip %^] "%u" "%R"
- time-format %T
- date-format %d/%b/%Y

update:
- log-file /opt/log/default.log

start the goaccess container

visit goaccess at: http://[ip]:7889


> props to ( and me too :P ): https://github.com/hectorm/docker-goaccess and https://forums.unraid.net/topic/103977-view-nginx-proxy-manager-access-logs-in-a-beautiful-dashboard-with-goaccess/
