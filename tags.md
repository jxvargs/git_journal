# tags y checkout

`git tag` se usa para marcar puntos específicos en la historia del repositorio, comúnmente usado para versiones (por ejemplo, v1.0).
`git checkout` permite cambiar entre ramas, commits o tags específicos. También se usa para restaurar archivos a un estado anterior.

Estos dos comandos facilita son piezas claves para una gestion efectiva y ordenada de los cambios en el codigo, normalmente los tags se utilizan en principalmente en *GitHub* y no en *Git*. Cuando borramos un tag en local, no se borra en el repositorio remoto.

- Crear un tag: Crea un tag ligero llamado v1.0 apuntando al commit actual.

```bash
~$ git tag v1.0
```

- Crear un tag con mensaje (annotated): Crea un tag v1.0 con anotación y mensaje. Se recomienda para releases.

```bash
`$ git tag -a v1.0 -m "Primera versión estable"
```

- Listar todos los tags - Muestra todos los tags existentes en el repositorio local.

```bash
git tag
```

- Cambiarse a un tag específico - Posiciona el HEAD en el commit del tag (modo *detached*).

```bash
git checkout v1.0
```

- Crear un tag en un commit específico - Donde `abc1234` es el hash parcial o completo del commit deseado.

```bash
git tag -a v1.1 abc1234 -m "Tag a commit específico"
```

- Publicar un tag en el repositorio remoto - Envía el tag `v1.0` al servidor remoto (por ejemplo GitHub).

```bash
git push origin v1.0
```

- Publicar todos los tags - Sube todos los tags locales al repositorio remoto.

```bash
git push origin --tags
```

Ejemplo completo en `git_journal`

```bash
cd ~/git_journal
git tag -a v1.0 -m "Primer release estable"
git push origin v1.0
```

Si se requiere eliminar:

   ```bash
   git tag -d v2.0
   git push origin :refs/tags/v2.0
   ```

---

## Conclusión

El uso de *tags* en Git es fundamental para marcar puntos importantes en la historia del repositorio, como versiones estables o lanzamientos de producción. A través de comandos como `git tag` y `git checkout`, se puede organizar, identificar y acceder fácilmente a estados específicos del proyecto. Publicar estos *tags* en el repositorio remoto garantiza que estén disponibles para todo el equipo y herramientas externas como CI/CD. Implementar esta práctica mejora la trazabilidad, control de versiones y colaboración en proyectos de software.

[Contenido](README.md)
