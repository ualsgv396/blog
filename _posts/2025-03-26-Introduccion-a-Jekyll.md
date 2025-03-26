---
layout: post
title:  " 📌 Introducción a Jekyll!"
date:   2025-03-26 13:43:17 +0100
categories: jekyll update
---

# Introducción a Jekyll

Jekyll es un **SSG** de código abierto elaborado y ejecutado sobre el lenguaje **Ruby**.  
Se puede utilizar para crear varios tipos de **sitios estáticos**, como un **blog** (objetivo de esta sesión) o un **sitio web de portafolio**, sin necesidad de una **BBDD** o un **sistema de gestión de contenidos**.  

![Introducción a Jekyll](/assets/jekyll.png)


Esto hace que destaque entre los SSG debido a su:  
- **Facilidad de uso**  
- **Rapidez y seguridad**  
- **Facilidad de personalización**  
- **Despliegue sencillo**  


## **I. ¿Cómo instalar Jekyll para crear sistios?**
### **1. Instalación de Jekyll**  
Primero, necesitas instalar Ruby y Bundler.  

🔹 En Windows:  
```sh
gem install jekyll
```

## **II. Verificar que Jekyll se ha instalado en el sistema correctamente**
  
Para verificar que Jekyll está instalado correctamente en tu máquina, abre tu terminal y ejecuta el siguiente comando:
 
```sh
jekyll -v
```



## **III. Crear un nuevo sitio Jekyll**  
Para comenzar un nuevo proyecto en Jekyll, abre una terminal y ejecuta el siguiente comando:  

```sh
jekyll new "nombre-de-mi-blog"
cd "nombre-de-mi-blog"
```


## **IV. Realizar el serve localmente**  
Para comenzar un nuevo proyecto en Jekyll, abre una terminal y ejecuta el siguiente comando:  

```sh
bundle exec jekyll serve
```

## **V. Personalización del blog**  
Para comenzar un nuevo proyecto en Jekyll, abre una terminal y ejecuta el siguiente comando:
📝 Jekyll permite personalizar el sitio editando diferentes archivos y configuraciones:

- **📂 Añadir contenido:**  
  Escribe entradas de blog en la carpeta `_posts/`, usando archivos Markdown (`*.md`).

  ![Introducción a Jekyll](/assets/md.png)


- **⚙️ Modificar la configuración:**  
  Edita `_config.yml` para cambiar el título, la descripción y otros ajustes del sitio.

  ![Introducción a Jekyll](/assets/configyml.png)


- **🎨 Personalizar el diseño:**  
  Usa la carpeta `_layouts/` para definir la estructura de tus páginas y `_includes/` para fragmentos reutilizables.


  ## **¡LISTO! Ya tienes tu blog disponible**
  Una vez realizados estos pasos ya puedes personalizar tu blog añadiendo entradas a la página y personalizar a tu gusto.  

    ![Introducción a Jekyll](/assets/jekyll2.png)


