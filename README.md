# prometheus

**homework**  
Настроить дашборд с 4-мя графиками (память, процессор, диск, сеть) с помощью prometheus - grafana.

---
Тестовый стенд запущен в докере: 

![](https://github.com/MaxOOOOON/prometheus/blob/main/Screenshot%202021-09-13%20215944.png)
prometheus

    docker run -d -p 9090:9090 --name prometh prom/prometheus

ubuntu

    docker run -d -it --name ubuntu1 --ip 172.17.0.4 ubuntu /bin/bash

grafana

    docker run -d -p 3000:3000 --ip 172.17.0.3 --name graf grafana/grafana

Устанавливаем и запускаем node exporter на ubuntu 

    wget https://github.com/prometheus/node_exporter/releases/download/v*/node_exporter-*.*-amd64.tar.gz
    tar xvfz node_exporter-*.*-amd64.tar.gz
    cd node_exporter-*.*-amd64
    ./node_exporter

Так же необходимо скопировать конфиг  

    docker cp prometheus.yml prometh:/etc/prometheus

И перезагрузить контейнер 

    docker restart prometh

Дашборд:
![](https://github.com/MaxOOOOON/prometheus/blob/main/Screenshot%202021-09-14%20003908.png)
