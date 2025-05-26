
# Configuración del Archivo `.gitignore`

⸻

## Crear el archivo .gitignore

En la raíz del repositorio:

```bash
~$ touch .gitignore
```

## Editar el archivo `.gitignore`

Abrir con cualquier editor de texto, por ejemplo:

```bash
~$ vim .gitignore
```

## Agregar archivos del sistema macOS a ignorar

```bash
# Archivos del sistema macOS
.DS_Store
.AppleDouble
.LSOverride

# Archivos de íconos
Icon?

# Miniaturas
._*

# Spotlight
.Spotlight-V100

# Papelera
.Trashes

# Atributos de carpetas en macOS
.DS_Store
```

Guardar y cerrar

```bash
:wq! 
```

## Aplicar los cambios (si esos archivos ya estaban siendo rastreados)

```bash
~$ git rm -r --cached .
~$ git add .
~$ git commit -m "Agregar .gitignore y remover archivos del sistema macOS"
```

## Resumen

Para más información sobre como agregar y configurar archivos `.gitignore` en tus repositorios puedes consultar la documentación para los diferentes lenguajes de programación que eestes trabajando - [GitHub .gitignore](https://github.com/github/gitignore)

[Contenido](README.md)
