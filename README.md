EZProxy Logstash
========

Ezproxy logstash configuration to be used in a ckortekaas/logstash-contrib (based on pblittle/docker-logstash) docker container at https://registry.hub.docker.com/u/ckortekaas/logstash-contrib

Example run configuration:

docker run -d --name logstash_sources -v sinet.csv:/sinet/sinet.csv -v espace.csv:/espace/espace.csv -p 9200:9200 -p 9292:9292 -p 514:514 -e LOGSTASH_CONFIG_URL=https://raw.githubusercontent.com/ckortekaas/logstash-ezproxy-docker/master/logstash-sources.conf ckortekaas/logstash-contrib