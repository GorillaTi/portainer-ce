# Portainer CE

Portainer - Gestión contenedores Commynity Edition 

## Docker compose

### Volumen

Crear volumen para `portainer_data`

```bash
docker volume create portainer_data
```

### Puertos:

[ip_server]:9000 -    puerto comunicación http

[ ip_server ]:8000    - puerto de comunicación de nodos

[ ip_server ]:9443    - puerto de comunicación https

## Usuario (opcional)

### Crear usuario `portainer`

```bash
sudo useradd -M -s /usr/sbin/bash -d /opt/portainer portainer 
```

### No login

Editar el archivo `passwd`

```bash
sudo vim /etc/passwd
```

La línea que contiene el usuario `portainer`

```sh-session
portainer:x:1000:1000::/opt/portainer:/bin/bash
```

Cambie el campo "x" por "N"

```sh-session
portainer:N:1000:1000::/opt/portainer:/bin/bash
```

### Asignando Permisos

Al directorio raíz del usuario

```bash
sudo chown portainer:portainer /opt/portainer
```

Al grupo `docker`

```bash
sudo usermod -aG docker portainer
```
