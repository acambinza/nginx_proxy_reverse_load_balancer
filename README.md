# nginx_proxy_reverse_load_balancer

Nginx aplicando - Proxy Reverse and Load Balancer

## as configurações foram testadas no ficheiro : /etc/nginx/nginx.conf


# Como usar?

- clone o repo -- https://github.com/acambinza/nginx_proxy_reverse_load_balancer.git

- docker-compose build --parallel

- docker-compose up -d

## APP start in port 80









# O que é nginx?

- webserver
- proxy reverso
- caching
- load balancer
- media streaming
- proxy serviço de email


## Principais características 

- + potentes do mercado
- performa + que o Apache
- alto volume de conexões simultâneas
- baixa memória e suporta alta concorrência
- assíncrono
- event-driven - escuta com um evento
- não bloqueante
- 1 worker por core

## Como funciona ?

- tem um arquivo de configuração
- processo *MASTER* - single thread
- dentro dos processos tem os workers - para cada CORE da máquina 


## PROXY REVERSO

### como funciona 

- é um serviço intermediário que recebe as requisições de diversos clients, as processa e as encaminha ao serviço correspondente


### LOAD BALANCING

- helpcheck passivo
- helpcheck activo - ver a saúde da máquina - versão paga
- definir a percentagem de carga para cada service




## CMD
- nginx -t : verifica se os arquivos de configuração do nginx estão ok



## CODE LOAD BALANCER ##

upstream nodes {
    server node2;
    server node3;
}

server {
    listen       80;
    server_name  localhost;


    location / {
        proxy_pass http://nodes;
        proxy_set_header X-Real-IP $remote_addr;

    }

    access_log /var/log/nginx/nginx-access.log main;

}




-- just it -- 



