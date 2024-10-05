# Burp

## Instalar

1. Descargar Burp Suite Community Edition desde [aquí](https://portswigger.net/burp
2. Una vez instalado lo puedes lanzar con `BurpSuiteCommunity` desde la terminal o `nohup BurpSuiteCommunity &` para lanzarlo en segundo plano.

## Configurar

Para configurar el proxy:

1. Descarga [FoxyProxy](https://addons.mozilla.org/es/firefox/addon/foxyproxy-standard/) para Firefox o Chrome.
2. Añade una configuración dentro de FoxyProxy con los siguientes datos:
   - **Titulo**: Burp
   - **Hostname**: 127.0.0.1
   - **Puerto**: 8080
   - **Tipo de proxy**: HTTP

## Añade tu certificado

1. Abre burpsuite y ve a la pestaña `Proxy`.
2. Ve al navegador y navega a `127.0.0.1:8080` y descarga el certificado.
3. Ve a la configuracion del navegador, busca `certificados` y añade el certificado descargado a `Autoridades de certificación`.
4. Reinicia el navegador.
5. Ahora puedes interceptar el trafico con Burp.

## Interceptando tráfico

1. Asegúrate de que el proxy de Burp está activado.
2. Asegúrate de que el interceptador está activado.
3. Asegúrate de que FoxyProxy está configurado correctamente y activo.
4. Navega a la página que quieres interceptar.
5. Burp interceptará la petición y te la mostrará.
6. Puedes enviar la petición al servidor o al repeater para modificarla.

## Repeater

1. Una vez interceptada la petición, puedes enviarla al repeater.
2. En el repeater puedes modificar la petición y enviarla al servidor.

## Intruder

1. Una vez interceptada la petición, puedes enviarla al intruder.
2. En el intruder puedes automatizar ataques de fuerza bruta, fuzzing, etc.
3. Selecciona el campo que quieres modificar y haz click en `Add` para añadir payloads.
4. Puedes añadir payloads de diferentes tipos, como listas, números, etc.
