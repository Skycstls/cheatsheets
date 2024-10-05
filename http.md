# HTTP

HTTP es un protocolo de comunicación que permite la transferencia de información en la World Wide Web. HTTP define la estructura de las peticiones y respuestas que se intercambian entre el cliente y el servidor.

[![](https://mermaid.ink/img/pako:eNplk92OmzAQhV_F8lVWSlCgiRrlou0qqbq9iSKFu7oXEzwBqzBGxrCtUJ6tUp-sYyDNRkUC7MN3jsc_9DKzGuVWXkr7mhXgvEj3ihQ17Tl3UBdiBw0oEnwRdLMDdJiDtu5p1LLSIHmczXZj42nSnW09um_j6_uoaWr6fn84Xa-3PN_3h-f01tdFVjPwsjsGBUmHOsYEsVgsgv9NX0BjcgLR8m1qUbfn0mTAHz6E4EcjByuaSh0UnspbQZxQZJYw8yBgAEa3omANwPN9sK9HUTvTgR4Hm1IUcWYgv3xOxav5YWrUBiLr8oEaaufHjYg36yheR-tNlCSre9H8CISS8fskSt5FyTKONktF_4UqOZgadJ3h3ZidpoZ4SdMj74G2WVtxXbb51IumgBq3grVmLko4Y7nlIfb_ECV5vW9RYXxeC8-zwrH0O0cP2ELY2htLca_kn98pUm6FIkMaf0aFr8qPQ66iiQrBjRkiXdyzJ1kumbgGHakzVtyt04p0D2ayozkJ5tVy9WhG56x7MMu5rNBVYDSf7z6cMSV9gRUqGeav8QJt6ZVUdGUUWm9PvyiTW-9anEs-AXkhtxcoG-61tQaPewP8U1Qjcv0L_OUTkg?type=png)](https://mermaid.live/edit#pako:eNplk92OmzAQhV_F8lVWSlCgiRrlou0qqbq9iSKFu7oXEzwBqzBGxrCtUJ6tUp-sYyDNRkUC7MN3jsc_9DKzGuVWXkr7mhXgvEj3ihQ17Tl3UBdiBw0oEnwRdLMDdJiDtu5p1LLSIHmczXZj42nSnW09um_j6_uoaWr6fn84Xa-3PN_3h-f01tdFVjPwsjsGBUmHOsYEsVgsgv9NX0BjcgLR8m1qUbfn0mTAHz6E4EcjByuaSh0UnspbQZxQZJYw8yBgAEa3omANwPN9sK9HUTvTgR4Hm1IUcWYgv3xOxav5YWrUBiLr8oEaaufHjYg36yheR-tNlCSre9H8CISS8fskSt5FyTKONktF_4UqOZgadJ3h3ZidpoZ4SdMj74G2WVtxXbb51IumgBq3grVmLko4Y7nlIfb_ECV5vW9RYXxeC8-zwrH0O0cP2ELY2htLca_kn98pUm6FIkMaf0aFr8qPQ66iiQrBjRkiXdyzJ1kumbgGHakzVtyt04p0D2ayozkJ5tVy9WhG56x7MMu5rNBVYDSf7z6cMSV9gRUqGeav8QJt6ZVUdGUUWm9PvyiTW-9anEs-AXkhtxcoG-61tQaPewP8U1Qjcv0L_OUTkg)

## Métodos HTTP

### GET

El método `GET` se utiliza para solicitar información de un recurso. Las peticiones `GET` son idempotentes, lo que significa que no tienen efectos secundarios en el servidor.

```http
GET /index.html HTTP/1.1
Host: www.example.com
```

### POST

El método `POST` se utiliza para enviar datos al servidor. Las peticiones `POST` no son idempotentes, lo que significa que pueden tener efectos secundarios en el servidor.

```http
POST /login HTTP/1.1
Host: www.example.com
Content-Type: application/x-www-form-urlencoded

username=johndoe&password=password123
```

### PUT

El método `PUT` se utiliza para actualizar un recurso en el servidor. Las peticiones `PUT` son idempotentes.

```http
PUT /users/123 HTTP/1.1
Host: www.example.com
Content-Type: application/json

{"name": "John Doe"}
```

### DELETE

El método `DELETE` se utiliza para eliminar un recurso en el servidor. Las peticiones `DELETE` son idempotentes.

```http
DELETE /users/123 HTTP/1.1
Host: www.example.com
```

### PATCH

El método `PATCH` se utiliza para actualizar parcialmente un recurso en el servidor. Las peticiones `PATCH` son idempotentes.

```http
PATCH /users/123 HTTP/1.1
Host: www.example.com
Content-Type: application/json

{"name": "Jane Doe"}
```

### HEAD

El método `HEAD` es similar al método `GET`, pero el servidor solo devuelve los encabezados de la respuesta, sin el cuerpo de la respuesta.

```http
HEAD /index.html HTTP/1.1
Host: www.example.com
```

### OPTIONS

El método `OPTIONS` se utiliza para obtener información sobre las opciones de comunicación disponibles para el recurso de destino.

```http
OPTIONS /index.html HTTP/1.1
Host: www.example.com
```

### TRACE

El método `TRACE` se utiliza para realizar una prueba de bucle de retorno de mensaje a lo largo de la ruta al recurso de destino.

```http
TRACE /index.html HTTP/1.1
Host: www.example.com
```

### CONNECT

El método `CONNECT` se utiliza para establecer una conexión de túnel con el servidor identificado por el recurso de destino.

```http
CONNECT www.example.com:443 HTTP/1.1
Host: www.example.com:443
```

## Códigos de estado HTTP

Los códigos de estado HTTP indican el resultado de una operación HTTP. Los códigos de estado se dividen en cinco clases:

- **1xx**: Respuestas informativas.
- **2xx**: Respuestas satisfactorias.
- **3xx**: Redirecciones.
- **4xx**: Errores del cliente.
- **5xx**: Errores del servidor.

### 2xx: Respuestas satisfactorias

- **200 OK**: La solicitud se ha completado con éxito.
- **201 Created**: La solicitud se ha completado y se ha creado un nuevo recurso.
- **204 No Content**: La solicitud se ha completado con éxito, pero no hay contenido para enviar en la respuesta.

### 3xx: Redirecciones

- **301 Moved Permanently**: El recurso solicitado se ha movido permanentemente a una nueva ubicación.
- **302 Found**: El recurso solicitado se ha movido temporalmente a una nueva ubicación.
- **304 Not Modified**: El recurso no ha sido modificado desde la última solicitud, la caché del cliente puede ser utilizada.

### 4xx: Errores del cliente

- **400 Bad Request**: La solicitud no se pudo entender debido a una sintaxis incorrecta.
- **401 Unauthorized**: Se requiere autenticación para acceder al recurso.
- **403 Forbidden**: El servidor se niega a completar la solicitud.
- **404 Not Found**: El recurso solicitado no se ha encontrado en el servidor.
- **429 Too Many Requests**: El cliente ha realizado demasiadas solicitudes en un período de tiempo.
- **451 Unavailable For Legal Reasons**: El contenido ha sido eliminado debido a una orden judicial o legal.

### 5xx: Errores del servidor

- **500 Internal Server Error**: El servidor ha encontrado una situación inesperada que le impide completar la solicitud.
- **502 Bad Gateway**: El servidor actuó como una puerta de enlace y recibió una respuesta no válida del servidor ascendente.
- **503 Service Unavailable**: El servidor no está listo para manejar la solicitud.
- **504 Gateway Timeout**: El servidor actuó como una puerta de enlace y no recibió una respuesta a tiempo.
- **511 Network Authentication Required**: El cliente necesita autenticarse para obtener acceso a la red.
- **599 Network Connect Timeout Error**: El cliente no pudo establecer una conexión con el servidor.
- **598 Network Read Timeout Error**: El servidor no respondió a tiempo a la solicitud de lectura del cliente.
- **599 Network Connect Timeout Error**: El cliente no pudo establecer una conexión con el servidor.

## Encabezados HTTP

### Encabezados de Request

#### Host

El encabezado `Host` especifica el nombre de dominio del servidor y el número de puerto al que se dirige la solicitud.

```http
Host: www.example.com
```

#### User-Agent

El encabezado `User-Agent` especifica información sobre el agente de usuario que realiza la solicitud.

```http
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/58.0.3029.110 Safari/537.3
```

```http
User-Agent: curl/7.68.0
```

#### Accept

El encabezado `Accept` especifica los tipos de contenido que el cliente puede procesar.

- `text/html`: HTML.
- `application/json`: JSON.
- `application/xml`: XML.
- `image/png`: PNG.

```http
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,image/apng,*/*;q=0.8
```

#### Content-Type

El encabezado `Content-Type` especifica el tipo de contenido del cuerpo de la solicitud.

- `application/x-www-form-urlencoded`: Formulario codificado en URL, por ejemplo, `?name=user&password=password123`.
- `application/json`: JSON, por ejemplo, `{"name": "User"}`.
- `multipart/form-data`: Formulario de datos múltiples, por ejemplo, un archivo adjunto.

```http
Content-Type: application/json
```

#### Authorization

El encabezado `Authorization` especifica las credenciales de autenticación para acceder al recurso.

Puede ser un token de autenticación:

```
Authorization Bearer <token>
```

#### Cookie

El encabezado `Cookie` especifica las cookies que se deben enviar al servidor.

```http
Cookie: name=value; name2=value2
```