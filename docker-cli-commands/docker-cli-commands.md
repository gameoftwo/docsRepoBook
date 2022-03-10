---
description: Mostraremos los comandos mas comunes de docker desde la consola.
cover: >-
  https://images.unsplash.com/photo-1552664730-d307ca884978?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=2970&q=80
coverY: 0
---

# Docker CLI Commands

## CLI Commands

* `docker images` - ver imagenes
* `docker ps` - ver contenedores activos
* `docker ps -a` - ver todos los contenedores, incluye inactivos
* `docker system prune` - borra contenedores inactivos
* `docker build -f [imagen]` - contruye la imagen
* `docker run -it -p 80:80 [id]` - inicia un contenedor utilizando una imagen
