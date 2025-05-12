# Git Reset y Git Revert - Explicación y Ejemplos

## git reset

Revierte commits **moviendo el puntero HEAD** a un commit anterior. **No crea un nuevo commit.**

```bash
~$ git log --oneline
# e.g., a3c9f6c Commit C
#        b7d1e23 Commit B
#        91f2a1b Commit A

~$ git reset b7d1e23
```

---

## git reset --soft

Mueve HEAD al commit indicado, **conservando los cambios en el área de staging**.

```bash
~$ git reset --soft b7d1e23
```

> Commit C desaparece, pero los cambios están staged.

---

## git reset --mixed (por defecto)

Mueve HEAD y **quita los archivos del área de staging**, pero **conserva los cambios en el directorio de trabajo**.

```bash
~$ git reset --mixed b7d1e23
```

> Commit C desaparece, cambios visibles con `git status`.

---

## git reset --hard

Mueve HEAD y **borra todo lo que está staged y en el working directory**.

```bash

~$ git reset --hard b7d1e23
```

> Elimina completamente los cambios posteriores.

---

## git revert

Crea un **nuevo commit que revierte** los cambios de un commit anterior.

```bash
~$ git revert a3c9f6c
```

> Crea un nuevo commit que deshace "Commit C" sin alterar el historial.

---

## Nota

- `git reset` altera el historial (no usar en ramas compartidas).
- `git revert` es seguro para ramas públicas.

---

[Contenido](README.md)
