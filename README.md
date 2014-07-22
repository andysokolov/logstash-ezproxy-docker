EZProxy Logstash
========

Ezproxy logstash configuration to be used in a ckortekaas/logstash-contrib-pr (based on pblittle/docker-logstash) docker container at https://registry.hub.docker.com/u/ckortekaas/logstash-contrib-pr

Example run configuration:

For the sources container:
=====
    docker run -d --name logstash-sources -v /opt/logstash/data/sinet.csv:/sinet/sinet.csv -v /opt/logstash/data/espace.csv:/espace/espace.csv -p 9201:9200 -e LOGSTASH_CONFIG_URL=https://raw.githubusercontent.com/ckortekaas/logstash-ezproxy-docker/master/logstash-sources.conf ckortekaas/logstash-contrib-pr

For the ezproxy container:
=====
    
    docker run -d --name logstash-ezproxy -v /opt/logstash/data/ezproxy1.res:/ezproxy/ezproxy1.res --link logstash-sources:logstash-sources -p 9200:9200 -p 9292:9292 -p 514:514 -e LOGSTASH_CONFIG_URL=https://raw.githubusercontent.com/ckortekaas/logstash-ezproxy-docker/master/logstash.conf ckortekaas/logstash-contrib-pr
    
    
    