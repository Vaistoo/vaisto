---

title: 在vercel上部署deeplx
published: 2025-05-26
tags:
  - 有趣的项目
  
lang: es

---
#### Prólogo

Recientemente encontré un proyecto que permite desplegar deeplx en Vercel. Después de probarlo, descubrí que es muy estable. Si antes tuviste problemas con errores frecuentes al desplegar deeplx, te recomiendo probar este.

[Proyecto original](https://github.com/un-ts/deeplx), puedes darle una estrella al autor como muestra de agradecimiento.

Haz un fork del repositorio del autor y luego impórtalo en Vercel para desplegarlo.

#### Consejillos

1. Si te preocupa que la URL de tu despliegue se filtre, puedes cambiar la ruta de traducción.
   
   - En `api/translates.ts`, cambia el nombre de `translates.ts` a **el nombre que prefieras**, y también actualiza la línea 29 que dice `POST {"text": "have a try", "source_lang": "auto", "target_lang": "ZH"} to /translate`, cambiando `translate` por el mismo nuevo nombre.
   
   - Luego modifica la línea 2 en `packages/@deeplx/core/src/api.ts` y la línea 3 del archivo `index.js` en el mismo directorio.
   
   - También renombra `translate.ts` en ese directorio a `el_nombre_que_quieras.ts`.

2. Después de hacer los cambios y desplegar, podrás usar la ruta que elijas, por ejemplo: `xxx.vercel.app/tu_ruta`.

#### 😉