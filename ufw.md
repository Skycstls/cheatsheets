# ufw

Firewall simple y fácil de usar para Ubuntu.

## Instalación

```bash
sudo apt install ufw
```

## Comandos

```bash
sudo ufw status # Muestra el estado del firewall
sudo ufw enable # Habilita el firewall
sudo ufw disable # Deshabilita el firewall
sudo ufw allow 22 # Permite el tráfico en el puerto 22
sudo ufw allow 22/tcp # Permite el tráfico TCP en el puerto 22
sudo ufw allow ssh # Permite el tráfico SSH
sudo ufw allow from <IP> # Permite el tráfico desde una IP
sudo ufw deny 22 # Deniega el tráfico en el puerto 22
sudo ufw delete allow 22 # Elimina la regla de permitir tráfico en el puerto 22
sudo ufw reset # Restablece las reglas a los valores predeterminados
```

## Configuración

```bash
sudo ufw default deny # Establece la política predeterminada en denegar
sudo ufw default allow # Establece la política predeterminada en permitir
sudo ufw default reject # Establece la política predeterminada en rechazar
```
