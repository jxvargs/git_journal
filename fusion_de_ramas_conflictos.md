# Notas de Clase: Fusion de Ramas y Resolución de Conflictos en Git

## Fusionar Ramas

Para fusionar una rama en Git usamos el comando:

```bash
git merge "nombre-de-la-rama"
```

- El merge ocurre en la rama en la que estemos situados.
- Se toma el último commit de la rama actual y el último commit de la rama que queremos fusionar.
- Se crea un nuevo commit en la rama actual que incluye los cambios de ambas ramas.

### Ejemplo:

```bash
~$ git checkout master
# Nos posicionamos en master

~$ git merge feature-xyz
# Fusionamos la rama feature-xyz en master
```

## Resolución de Conflictos

Un conflicto ocurre cuando dos ramas modifican la misma línea de un archivo de manera diferente.

### Pasos para resolver un conflicto -

1. Git marcará los archivos en conflicto.
2. Edita los archivos para decidir qué cambios conservar.
3. Una vez resuelto, marca el archivo como resuelto:

```bash
~$ git add nombre-del-archivo
```

4. Luego crea un commit de la fusión:

```bash
~$ git commit
```

### Ejemplo de flujo -

```bash
~$ git checkout master
~$ git merge feature-abc
# Conflicto detectado
# Editar archivos conflictivos

~$ git add archivo.txt
~$ git commit -m "Resolviendo conflictos de merge entre master y feature-abc"
```

## Tips

- Puedes usar editores como VSCode que facilitan resolver conflictos.
- Las ramas pueden fusionarse en cualquier dirección, depende en cuál hagas el `merge`.

---

[Contenido](README.md)
