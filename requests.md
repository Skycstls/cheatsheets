# Requests

```python
import requests
```

## GET

```python
response = requests.get("https://api.github.com")
response.status_code
response.text
```

Otras propiedades de `response`:

```python
response.json()
response.headers
response.headers["Content-Type"]
response.body
response.content
response.encoding
response.url
response.cookies
response.history
response.is_redirect
response.links
response.ok
response.reason
response.request
response.text
response.elapsed
response.elapsed.total_seconds()
```

### Query parameters

```python
response = requests.get("https://sample.xyz", params={"key1": "value1", "key2": "value2"})
response.url
response = requests.get("https://sample.xyz?key1=value1&key2=value2")
response.url
```

## POST

### Form

```python
# equivalent to curl -X POST https://httpbin.org/post -d "key=value"
# or typing in a form in a browser and hitting submit
response = requests.post("https://sample.xyz/post", data={"key": "value"})
response.json()
```

### JSON

```python
response = requests.post("https://sample.xyz/post", json={"key": "value"})
response.json()
```

### Files

```python
files = {"file": open("file.txt", "rb")}
response = requests.post("https://sample.xyz/post", files=files)
response.json()
```

## PUT

```python
response = requests.put("https://sample.xyz/put", data={"key": "value"})
response.json()
```

## Proxy

```python
# pip install pysocks

import requests

proxies = {
    "http": "socks5://127.0.0.1:9050",
    "https": "socks5://127.0.0.1:9050"
}

respuesta = requests.get("abcdefg.onion", proxies=proxies)

print(respuesta.text)
```