# Documentación

## Pandoc

```bash
pandoc -s file.md -o file.pdf  # Convierte un archivo Markdown a PDF
pandoc -s file.md -o file.html # Convierte un archivo Markdown a HTML
pandoc -s file.md -o file.docx # Convierte un archivo Markdown a DOCX
pandoc -s file.md -o file.epub # Convierte un archivo Markdown a EPUB
pandoc -s file.docx -o file.md # Convierte un archivo DOCX a Markdown
pandoc -s file.html -o file.md # Convierte un archivo HTML a Markdown
pandoc -s file.pdf -o file.md  # Convierte un archivo PDF a Markdown
pandoc -s file.epub -o file.md # Convierte un archivo EPUB a Markdown
```

## PDFtk

```bash
pdftk 1.pdf 2.pdf cat output merged.pdf   # Combina dos archivos PDF en uno solo
pdftk input.pdf cat 1-4 output output.pdf # Extrae las páginas 1 a 4 de un archivo PDF
pdftk input.pdf cat 1 output output.pdf   # Extrae la primera página de un archivo PDF
```

## Marp

```yml
---
marp: true
theme: default
class: invert
size: 16:9
style: |
  img {background-color: transparent!important;}
  a:hover, a:active, a:focus {text-decoration: none;}
  header a {color: #ffffff !important; font-size: 30px;}
  footer {color: #148ec8;}
header: '[&#9671;](#1 " ")'
footer: 'Marp Template'
---
```

## MKdocs

```bash
mkdocs new project    # Crea un nuevo proyecto
mkdocs serve          # Inicia el servidor de desarrollo
mkdocs build          # Genera el sitio estático
mkdocs gh-deploy       # Publica el sitio en GitHub Pages
mkdocs serve --dev-addr=0.0.0.0:8000 # exponer el servidor en todas las interfaces
```

## jq

```bash
jq "" stuff.json     # Lee el json completo
jq ".key" stuff.json # muestra el valor de una clave
jq "keys" stuff.json # muestra las claves del objeto
jq ".[] | .key" stuff.json # muestra el valor de una clave en un array
```
