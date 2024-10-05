# SSH

SSH (Secure Shell) es un protocolo criptográfico que permite la comunicación segura entre dos sistemas. SSH se utiliza para acceder de forma remota a servidores y dispositivos de red, así como para transferir archivos de forma segura.

## Conexión SSH

Para conectarse a un servidor remoto a través de SSH, podemos usar:

### Autenticación con contraseña

```bash
ssh username@hostname
```

### Autenticación con clave privada

```bash
ssh -i path/to/private_key username@hostname
```

### Especificar puerto

```bash
ssh -p port username@hostname
```

## Transferencia de archivos

Para transferir archivos de forma segura entre dos sistemas, podemos usar `scp` (Secure Copy Protocol): 

### Subir un archivo