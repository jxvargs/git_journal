# Sincroniza los repositorios utlizando `git pull` `git push` `git fetch`

Los siguientes caracteristicas son escenciales en la sincronización de repositorios.

- Colaborar en equipo manteniendo el código sincronizado entre varios usuarios.
- Evitar conflictos, al traer primero los cambios remotos (fetch o pull) antes de subir los propios.
- Revisar cambios remotos sin alterar su entorno local (fetch).
- Actualizar su rama local fácilmente con lo más reciente del equipo (pull).
- Publicar su trabajo para que otros lo vean o revisen (push).

• git fetch: descarga los cambios del repositorio remoto pero no los aplica al trabajo actual. Solo actualiza las referencias remotas.
• git pull: combina fetch + merge. Descarga y fusiona automáticamente los cambios del remoto en tu rama local.
• git push: envía tus cambios locales (commits) al repositorio remoto.

## Comandos en acción - Terminal 💻

```bash
~$ git push -u origin main
```

Si como resultado al ejecutar el comando `git push` tienes problemas y se te pide `username` y `password` es (quizás) porque el url del repositorio esta configurado con HTTPS. Para comprobarlo usar el comando:

```bash
~$ git config --list
user.name=juanperez
user.email=juanperez@example.com
color.ui=auto
core.repositoryformatversion=0
core.filemode=true
core.bare=false
core.logallrefupdates=true
remote.origin.url=git@github.com:juanperez/mi-proyecto.git
remote.origin.fetch=+refs/heads/*:refs/remotes/origin/*
branch.main.remote=origin
branch.main.merge=refs/heads/main
```

Una vez confirmada la url se cambia a SSH de la siguiente manera:

```bash
~$ git remote -v
origin  https://github.com/juanperez/mi-proyecto.git (fetch)
origin  https://github.com/juanperez/mi-proyecto.git (push)

~$ git remote set-url origin git@github.com:juanperez/mi-proyecto.git

~$ git remote -v
origin  git@github.com:juanperez/mi-proyecto.git (fetch)
origin  git@github.com:juanperez/mi-proyecto.git (push)

# Después ejecuta el siguiente comando

~$ git push -u origin main
ERROR: Repository not found.
fatal: Could not read from remote repository.

Please make sure you have the correct access rights
and the repository exists.
```

Para solucionar el `ERROR` anterior initialice un nuevo repositorio en [GitHub](https://github.com/) con el nombre exacto del repositorio local. Una vez creado ejecutamos el/los comandos siguientes.

```bash
$ git push -u origin main
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 4 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (5/5), 500 bytes | 500.00 KiB/s, done.
Total 5 (delta 0), reused 0 (delta 0)
remote: Resolving deltas: 100% (0/0), done.
To github.com:juanperez/mi-proyecto.git
 * [new branch]      main -> main
branch 'main' set up to track 'origin/main'.
```

El comando `git pull` se usa para actualizar tu rama local con los últimos cambios del repositorio remoto. Combina dos acciones: primero descarga los cambios (fetch) y luego los fusiona (merge) automáticamente en tu rama actual. Es útil para mantener tu trabajo al día cuando colaboras con otros desarrolladores. Antes de hacer push, es **buena práctica hacer un** `pull` para evitar conflictos.

```bash
$ git pull origin main
remote: Enumerating objects: 3, done.
remote: Total 3 (delta 1), reused 3 (delta 1)
Unpacking objects: 100% (3/3), done.
From github.com:juanperez/mi-proyecto
 * branch            main       -> FETCH_HEAD
   abc1234..def5678  main       -> origin/main
Updating abc1234..def5678
Fast-forward
 archivo.txt | 2 +-
 1 file changed, 1 insertion(+), 1 deletion(-)
```

El comando git fetch se utiliza para descargar los cambios más recientes del repositorio remoto sin modificar tu rama actual. A diferencia de git pull, que también hace un merge, fetch solo actualiza las referencias remotas. Esto permite revisar primero qué ha cambiado antes de aplicar los cambios. Puedes comparar tu rama local con la remota o ver los cambios con git log o git diff.

```bash
~$ git fetch origin

~$ git log HEAD..origin/main --oneline
def5678  Actualización en archivo.txt
cba4321  Corrección de errores menores

# También puedes utilizar el siguiente comando.

~$ git log main..origin/main
commit def5678abc1234567890abcdef1234567890abcd
Author: Ana López <ana@example.com>
Date:   Fri May 10 09:15:32 2025 -0700

    Agregada validación de entradas en formulario

commit cba4321def9876543210fedcba9876543210dcba
Author: Luis Torres <luis@example.com>
Date:   Thu May 9 14:02:11 2025 -0700

    Corrección de errores en la función de login

# Si quieres ver las diferencias - sigue el siguente comando -

~$ git diff HEAD origin/main
diff --git a/formulario.py b/formulario.py
index 8c3d5a1..f5e4c2b 100644
--- a/formulario.py
+++ b/formulario.py
@@ def validar_datos(entrada):
-    if entrada:
+    if entrada and len(entrada) > 3:
         return True
     return False
```

Después de evaluar los cambion y diferencias y estas deacuerdo en fucionar los eso nuevos cambios, ejecuta el siguiente comando.

```bash
~$ git merge origin/main
Updating abc1234..def5678
Fast-forward
 archivo.py | 3 ++-
 1 file changed, 2 insertions(+), 1 deletion(-)
```

Fusiona los cambios descargados desde origin/main (remoto) a tu rama actual (local), sin necesidad de hacer git pull. Es útil después de un git fetch para tener control sobre cuándo y cómo aplicar los cambios remotos.

En resumen:

• fetch = ver cambios remotos sin aplicar

• pull = traer y aplicar cambios

• push = subir tus cambios al remoto

[Contenido](README.md)
