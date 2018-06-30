### docker 部署命令
#### 配置文件路径
    /Users/prometheus
####  安装prometheus
    1.docker pull prom/promethues
    2. docker run --rm --name prometheus -p 9090:9090 -v /Users/prometheus/prometheus.yml:/etc/prometheus/prometheus.yml -v /Users/prometheus/node_down.yml:/etc/prometheus/node_down.yml -v /Users/prometheus/memory_over.yml:/etc/prometheus/memory_over.yml prom/prometheus

####  安装alertmanger
    1. docker pull prom/alertmanger
    2. docker run --rm -p 9093:9093 -v /Users/prometheus/alertmanger.yml:/etc/alertmanager/config.yml  prom/alertmanager

#### 安装 grafana
     1. docker pull grafana/grafana
     2.docker run -d -i -p 3000:3000 -e "GF_SERVER_ROOT_URL=http://grafana.server.name" -e "GF_SECURITY_ADMIN_PASSWORD=admin" --net=host grafana/grafana 