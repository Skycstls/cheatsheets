# Hashcat

```bash
hashcat --identify hash.txt                        # Identificar tipo de hash
hashcat -m 0 hash.txt rockyou.txt                  # Ataque de diccionario
hashcat -m 0 -a 3 hash.txt '?a?a?a?a'              # Ataque de máscara
hashcat -m 0 -a 0 hash.txt ?d?d?d?d?d?d            # Ataque de fuerza bruta
hashcat -m 0 -a 1 hash.txt ?d?d?d?d?d?d            # Ataque de fuerza bruta incremental
hashcat -m 0 -a 3 hash.txt 'user?d?d?d?d' --stdout # Generar diccionario
```

## Máscaras

```bash
?d # Dígitos (0-9)
?l # Minúsculas (a-z)
?u # Mayúsculas (A-Z)
?s # Símbolos (!"#$%&'()*+,-./:;<=>?@[\]^_`{|}~)
?a # Todos los anteriores
?b # Espacios en blanco
?h # Caracteres hexadecimales (0-9, a-f)
```

## Hash-types

```bash
hashcat --help | grep <hash-type> # Buscar hash-type
```

## Hash-types más comunes

```bash
MD5     # 0
MD4     # 900
SHA1    # 100
SHA-256 # 1400
SHA-512 # 1700
BCrypt  # 3200
```

## To testtttt

```bash
seq 0 9999 > numeros
```

Y luego generar las combinaciones con hashcat:
```bash
hashcat --stdout -a 1 passwords numeros > new-passwords
```

Tambien podemos usar el modo de ataque 3 para generar combinaciones:

```bash
hashcat -a 3 --increment 'julia?d?d?d?d' --stdout
