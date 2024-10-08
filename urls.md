# URL vs URI vs URN

Las URL, URI y URN son conceptos que se utilizan en la web para identificar recursos. Aunque a menudo se utilizan indistintamente, cada uno de ellos tiene un significado diferente.

Una uri es una cadena de caracteres que identifica un recurso en la web. Una uri puede ser una url o una urn.

## URI

```plaintext
mailto:admin@ejemplo.com
```
- mailto -> Protocolo/Esquema
- admin@ejemplo.com -> Path

```plaintext
idap://2001:db8::7/c=GB?objectClass?one
```
- idap -> Protocolo/Esquema
- 2001:db8::7 -> Host
- c=GB -> Ruta
- objectClass?one -> Parámetros Query

Podriamos encontrar esta uri en una URL como:

```plaintext
http://www.ejemplo.com/ldap/2001:db8::7/c=GB?objectClass?one
```

## URL

```plaintext
http://www.ejemplo.com:80/login.html?user=admin&password=1234
```

- http -> Protocolo/Esquema
- www.ejemplo.com -> Dominio
- 80 -> Puerto
- /login.html -> Ruta
- user=admin&password=1234 -> Parámetros Query
- www -> Subdominio
- com -> Dominio de nivel superior (TLD)


## URN

```plaintext
urn:isbn:0451450523
```

- urn -> Protocolo/Esquema
- isbn -> Namespace
- 0451450523 -> Identificador

En este caso identifica un libro con el ISBN 0451450523. Podriamos encontrar esta urn en una URL como:

```plaintext
http://www.ejemplo.com/libro/urn:isbn:0451450523
```