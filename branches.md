# Branches y Cambios - Fusiones

**Por que las ramas/branches son utiles en `git`?**

Las ramas en Git permiten trabajar en diferentes características o correcciones de manera aislada, sin afectar el código principal. Facilitan la colaboración, ya que cada desarrollador puede trabajar en su propia rama sin interferir con los demás.

Muestra todas las ramas del repositorio y mostrará con un asterisco en cual estas trabajando.

```bash
$ git branch
* main
  feature-login
  fix-header
  ```

  Crea una nueva rama y se cambia a ella.

  ```bash
  $ git checkout -b feature-navbar
Switched to a new branch 'feature-navbar'
```

Alternativa moderna a checkout -b, crea y cambia a una nueva rama.

```bash
$ git switch -c update-footer
Switched to a new branch 'update-footer'
```

Cambia a la rama main.

```bash
$ git switch main
Switched to branch 'main'
```

Combina los cambios de otra rama a la actual.

```bash
$ git switch main
$ git merge feature-navbar
Updating a1b2c3d..d4e5f6g
Fast-forward
```

Elimina una rama local ya fusionada.

```bash
$ git branch -D feature-navbar
Deleted branch feature-navbar (was d4e5f6g).
```

## 🧠 Conclusión - Summary: Uso de ramas en Git

El manejo de ramas en Git permite trabajar en nuevas funciones, correcciones o ideas sin afectar la rama principal (`main`). A continuación, se resumen los comandos clave utilizados:

- `git branch`: lista todas las ramas locales del repositorio.
- `git checkout -b <rama>` / `git switch -c <rama>`: crea una nueva rama y cambia a ella.
- `git switch <rama>`: cambia entre ramas existentes.
- `git merge <rama>`: fusiona los cambios de una rama a la actual (normalmente `main`).
- `git branch -D <rama>`: elimina una rama local ya fusionada.

Este flujo asegura un desarrollo organizado, colaborativo y seguro.

---
[Contenido](README.md)
