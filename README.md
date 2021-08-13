# Imagens e Containers Docker em hd externo. (apenas para linux)

**Usar docker em hd externo**

usar o comando ```mount``` para identificar o caminho do hd externo (após conectado)

montar o hd externo abaixo do /mnt: 
```
chown -R root:root /mnt/<hd-externo>/docker-base/
```
conceder permissão de acesso ao diretório:
```
chmod 701 /mnt/<hd-externo>/docker-base/
```
criar um daemon.json:
```
touch /etc/docker/daemon.json
```
adicionar o seguinte conteúdo:
```
{
    "graph": "/run/media/<hd-externo>/docker-base/"
}
```

reiniciar os serviço do docker:

```
sudo systemctl restart docker.service
```

agora pode executar os comandos docker, ele estará executando a criação de imagens e containers no hd externo.
