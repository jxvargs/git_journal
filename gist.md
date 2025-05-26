# Guía para crear un Gist en GitHub

⸻

## 📌 ¿Qué es un `Gist`?

Un Gist es una forma rápida de compartir fragmentos de código, notas o scripts. Pueden ser públicos o secretos.

---

## 🧭 Pasos para crear un `Gist`

1. Inicia sesión en GitHub:

   • Ve a [Gist](https://gist.github.com) e inicia sesión con tu cuenta de GitHub.

2. Crea un nuevo Gist:
   •Haz clic en “+” en la esquina superior derecha de GitHub y selecciona “New Gist”, o ve directo a gist.github.com.

3. Completa los campos:
   • Descripción (opcional): Breve texto explicando el propósito del Gist.

   • Nombre del archivo: Ej. script.py, notas.txt, etc.

   • Contenido: Escribe o pega tu código.

4. Privacidad:

   • Public: cualquier persona puede verlo.

   • Secret: solo quienes tengan el enlace pueden verlo (no es realmente privado).

5. Guarda el Gist:

   • Haz clic en “Create public gist” o “Create secret gist” según el caso.

## 🧷 Extra

• Puedes editar, clonar, comentar y compartir los Gists.

• Tiene su propio URL que puedes compartir fácilmente.

## Aquí tienes un ejemplo básico de un Gist que contiene un script en Python

✏️ Descripción del Gist:

```text
Script básico en Python para saludar al usuario por su nombre.
```

📄 Nombre del archivo:

`saludo.py`

🧩 Contenido del archivo:

```Python
def saludar(nombre):
    print(f"Hola, {nombre}! Bienvenido al mundo de Python.")

if __name__ == "__main__":
    nombre_usuario = input("¿Cuál es tu nombre? ")
    saludar(nombre_usuario)
```

⸻

🔗 ¿Cómo se vería ya creado?

Una vez creado, el Gist tendría una URL como:

```bash
https://gist.github.com/usuario/abc1234567890abcdef
```

> (Ese enlace es un ejemplo ficticio).

Con ese enlace, cualquiera puede ver o descargar tu fragmento de código. Si lo hiciste privado, solo quienes tengan el link podrán verlo.

Si necesitas mas informacion de como crear un `Gist`, puedes consutar la documentación - [Gist Documentation](https://docs.github.com/es/get-started/writing-on-github/editing-and-sharing-content-with-gists/creating-gists)

[Contenido](README.md)
