# Configuración de SSH en GitHub para MacOS

## Verificar si tienes una clave SSH existente

Abre la terminal y ejecuta el siguiente comando para verificar si ya tienes claves SSH configuradas en tu Mac:

```bash
~$ ls -al ~/.ssh
```

Si ves archivos como id_ed25519 y id_ed25519.pub, ya tienes una clave SSH.

## Generar una nueva clave SSH utilizando ED25519

Si no tienes una clave SSH o deseas crear una nueva, puedes generar una con el siguiente comando:

```bash
~$ ssh-keygen -t ed25519 -C "tu-email@ejemplo.com"
```

Este comando genera una clave ED25519, que es más segura y eficiente que RSA, y la asocia con tu correo electrónico de GitHub.

- Presiona Enter cuando se te pida una ubicación para guardar la clave (o presiona Enter para usar la ubicación predeterminada).

- Introduce una passphrase (opcional, pero recomendable para mayor seguridad).

## Iniciar el agente SSH

Asegúrate de que el agente SSH esté corriendo para gestionar las claves. Ejecuta:

```bash
~$ eval "$(ssh-agent -s)"
```

## Agregar la clave SSH al agente

Agrega tu clave SSH privada al agente con el siguiente comando (asegúrate de reemplazar el nombre de tu archivo de clave si es diferente):

```bash
~$ ssh-add ~/.ssh/id_ed25519
```

## Como agregar la llave SSh a GitHub?

- Abrir el archivo de la llave pública (id_ed25519.pub) y copia el contenido.
- En GitHub, ve a Settings > SSH and GPG keys > New SSH key y pega la llave.
- Nombra la llave de acuerdo a la computadora en la que estás configurándola.

## Configuración adicional en MacOS

Crear el archivo de configuración SSH: Abre o crea el archivo `config` dentro del directorio `.ssh`.

```bash
~$ cd .ssh
~$ vim config
```

Agrega los siguientes parametros especificos de Mac.

```bash
Host github.com
   AddKeysToAgent yes
   UseKeychain yes
   IdentityFile ~/.ssh/id_ed25519
```

## Añadir la llave al agente SSH con Keychain: Usa el comando:

```bash
~$ ssh-add --apple-use-keychain ~/.ssh/id_ed25519
```

## Verrificar La conexión con GitHub

Ejecuta el siguiente comando.

```bash
~$ ssh -T git@github.com
```

- Escribe "yes" para confirmar la conexión.
- Recibiras en la terminal un mensaje de GitHub que confirma la autenticidad.

## Clonado un repositorio usando SSH

En GitHub, selecciona el repositorio deseado, elige la opción de clonación por SSH y copia la URL.
En la terminal, ejecuta:

```bash
~$ git clone git@github.com:usuario/repositorio.git
```

## Conclusión

Mediante estos pasos descritos anteriormente, podemos concluir lo siguiente:

1. Verificar si ya tienes claves existentes.
2. Generar una nueva clave con ssh-keygen -t ed25519.
3. Iniciar el agente SSH y agregarle tu clave.
4. Copiar la clave pública y agregarla en tu cuenta de GitHub.
5. Probar la conexión con `ssh -T git@github.com`
6. (Opcional) Configurar tu nombre y correo en Git.
7. Clonar repos usando el formato SSH.

Con estos pasos, tendrás una conexión segura y sin necesidad de ingresar usuario/contraseña cada vez que uses GitHub desde tu terminal.

[Contenido](README.md)
