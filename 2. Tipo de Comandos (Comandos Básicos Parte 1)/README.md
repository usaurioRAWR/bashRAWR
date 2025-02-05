### **2. Tipo de Comandos (Comandos Básicos Parte 1)**

### **2.1. AYUDA**
Estos comandos proporcionan información sobre cómo usar otros comandos en `bash`.

#### a) Man
- **Sintaxis**: `man [comando]`
- **Ejemplo**: `man ls`

El comando `man` abre la página de manual del sistema y muestra la documentación detallada del comando especificado. Es útil para aprender cómo usar comandos específicos.

#### b) Apropos
- **Sintaxis**: `apropos [comando]`
- **Ejemplo**: `apropos ls`

`apropos` muestra una breve descripción del comando en la pantalla, lo que te permite conocer rápidamente su propósito y uso.

#### c) Whatis
- **Sintaxis**: `whatis [comando]`
- **Ejemplo**: `whatis ls`

`whatis` ofrece una rápida información sobre el comando, incluyendo su función y cómo usarlo.

### **2.2. Control de Sesión**
Estos comandos te permiten gestionar tu sesión en el terminal.

#### a) Exit
- **Uso**: `exit` o presionar `Ctrl + Z`
- **Ejemplo**: Presiona `Ctrl + Z` para salir del terminal.

El comando `exit` cierra tu sesión actual, cerrando la terminal y volviéndose al estado anterior.

#### b) Su
- **Sintaxis**: `su [nombre_usuario]`
- **Ejemplo**: `su pepe`

Con `su`, puedes iniciar una nueva sesión como otro usuario. Si no especificas un nombre de usuario, te redirigirá a tu cuenta por defecto.

#### c) logout
- **Ejemplo**: `logout`

Cierrar la sesión de usuario.

#### d) clear
- **Ejemplo**: `clear`

`clear` limpia la pantalla del terminal, ofreciendo un nuevo entorno de trabajo limpio.

### **2.3. Manejo de Archivos y Directorios**
Estos comandos son esenciales para interactuar con archivos y directorios en `bash`.

#### a) ls
- **Sintaxis**: `ls [modificadores] [ficheros]`
- **Modificadores**:
  - `-l`: Muestra formato detallado de los archivos.
  - `-a`: Mostrar archivos y directorios ocultos.
  - `-R`: Listar desde el principio del árbol.
  - `-F`: Indica tipo de archivo (archivos, directorios, enlaces, etc.).
- **Ejemplo**: `ls –l /home/user/Documentos`

`ls` lista los archivos y directorios en el directorio especificado. Los modificadores pueden ayudarte a ver la información de manera más detallada.

#### b) cat
El comando `cat` nos permite la visualizar, creacion o concatenar de archivos.
  - **Visualizar contenido de un archivo**:
    - **Sintaxis**: `cat [archivo]`
    - **Ejemplo**: `cat Fich1`
  - **Crear un nuevo archivo**:
    - **Sintaxis**: `cat > [nomb_fichero]`
    - **Ejemplo**: `cat > Fich1`
  - **Concatenar archivos**:
    - **Sintaxis**: `cat [archivo1] [archivo2]`
    - **Ejemplo**: `cat Fich1 Fich2 > Concatenado.txt`

#### c) more
- **Sintaxis**: `more [archivo]`
- **Modificadores**:
  - `-###`: Indica el número de líneas por página.
  - `+###`: Indica desde qué línea comenzar.
  - `+/:` Busca una cadena y comienza desde su primera aparición.
  - `-p`: Evita que las páginas se desplacen.
- **Ejemplo**: `more Fich1`
`more` divide el archivo en páginas para que sea más fácil de leer. Usa las teclas:
- Navegación en el comando more
  - Barra espaciadora: Ir a la siguiente página.
  - Enter: Ir a la línea siguiente.
  - `q`: Salir del visualizador.

---