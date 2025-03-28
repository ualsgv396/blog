---
layout: post
title:  "Mejores prácticas para el control de versiones con Git"
date:   2025-03-26 13:35:09 +0100
categories: jekyll update
---

Git es una herramienta poderosa para el control de versiones, pero su uso efectivo requiere seguir buenas prácticas. A continuación, se presentan algunas recomendaciones para mejorar la gestión de proyectos con Git.

## Escribe mensajes de commit descriptivos
Cada commit debe responder a tres preguntas:
- ¿Qué se hizo?
- ¿Por qué se hizo?
- ¿Cómo se hizo? (opcional)

Ejemplo de buen mensaje de commit:
```sh
git commit -m "Corrige bug en validación de usuario (#123)"
```

De esta forma, tu equipo (y tu yo del futuro) no se calentará la cabeza de lo que se hace en cada commit.

## Realiza commits pequeños y atómicos
Los commits deben ser pequeños y contener cambios relacionados. Esto facilita la revisión y la reversión de cambios en caso de ser necesario.

## Usa ramas para desarrollo y pruebas
- **main/master**: Solo código estable.
- **develop**: Integración de nuevas funcionalidades.
- **feature/nueva-funcionalidad**: Desarrollo de una nueva funcionalidad.
- **fix/bug-nombre**: Corrección de errores.
- **hotfix/urgente**: Parches urgentes en producción.

## Mantén el historial limpio
Evita commits innecesarios, usa `git rebase` en lugar de `git merge` cuando sea posible, y elimina ramas que ya no se utilicen.

## Revisa cambios antes de hacer push
Antes de subir cambios, revisa qué archivos serán enviados:
```sh
git status
git diff
```

## Sincroniza antes de subir cambios
Antes de hacer `push`, asegúrate de obtener los últimos cambios:
```sh
git pull --rebase
```

## Usa .gitignore correctamente
Añade un archivo `.gitignore` para evitar subir archivos innecesarios, como archivos generados, configuraciones locales o credenciales.

Ejemplo básico:
```
node_modules/
.env
*.log
.DS_Store
```

## Protege la rama principal
Configura reglas para que los cambios en `main` o `master` solo se integren mediante pull requests revisados.

## Automatiza pruebas antes de fusionar cambios
Usa herramientas como GitHub Actions, GitLab CI/CD o Jenkins para ejecutar pruebas automáticamente en cada pull request.

Siguiendo estas mejores prácticas, mejorarás la colaboración, mantendrás un historial limpio y minimizarás errores en el control de versiones con Git.

## Sitios web para aprender Git

Sabemos que la mejor forma de aprender (sea lo que sea), es con la práctica. Por eso os dejamos 3 webs para aprender a mejorar, donde pondrán a prueba si realmente tienes un buen manejo (y si no lo tienes, ¡aprenderás!).

### 1. [Codecademy][codecademy]

Codecademy es una plataforma de cursos de desarrollo y uno de ellos permite aprender git con una consola online y contiene 12 capítulos con ejercicios para realizar.

![imagenCodecademi](/assets/codeAcademy.png)


### 2. [Oh my git][ohMyGit]

Es un juego interactivo, el cual es un desarrollo de código abierto y tiene como objetivo realizar diferentes desafios y aprender como trabajar con git.

![imagenohmygit](/assets/ohmygit.png)

### 3. [Learn Git Branching][learnGitBranching]

Esta aplicación te permite aprender de manera interactiva a trabajar con ramas en git.

![imagenlearning](/assets/learning.jpg)


[codecademy]: https://www.codecademy.com/learn/learn-git
[ohMyGit]: https://ohmygit.org/
[learnGitBranching]: https://learngitbranching.js.org/?locale=es_AR


