# bashRAWR
Este curso básico de Bash cubre los comandos y conceptos fundamentales para manipular el sistema operativo mediante la terminal. ¡Sigue practicando y explorando más comandos avanzados! 😊

## **Curso Básico de Bash**

### **1. Introducción al Shell**

#### **¿Qué es el Shell?**
El **Shell** es un programa interpretador de comandos que actúa como intermediario entre el usuario y el sistema operativo. Su propósito principal es ejecutar comandos y acceder a funciones del sistema para realizar tareas diarias.

Al abrir la terminal, veías esto:
```bash
user@pc:~ $
```
Este es el **prompt** o línea de comando, donde escribe y ejecutas los comandos.

#### **Composición del Prompt**
El prompt consiste en:
1. Tu nombre de usuario (`user`).
2. El nombre del sistema operativo y la máquina (`pc`).
3. El directorio actual (`~`), que es el directorio home del usuario.
4. El símbolo `$`, que indica que estás listo para recibir una orden.

#### **Sintaxis de Comandos**
Los comandos se estructuran como:
```bash
comando [opciones] [argumentos]
```
- **Comando**: Es la acción que deseas ejecutar.
- **Opciones**: Modificadores que modifican el comportamiento del comando.
- **Argumentos**: Los objetos sobre los que actúa el comando.

#### **Ejemplo de Comando**
```bash
ls   # Muestra los archivos y directorios en el directorio actual
cat archivo.txt  # Muestra el contenido de archivo.txt
mv archivo1.txt archivo2.txt  # Cambia el nombre de archivo1.txt a archivo2.txt
```

#### **Manejo de la Sintaxis**
- Los comandos son case-sensitive, es decir, son sensibles a mayúsculas y minúsculas.
- Las opciones y argumentos son obligatorios o opcionales según se indica.
- Las partes que están entre corchetes (`[]`) son opcionales.

#### **Ejemplo Complejo**
```bash
ls -l  # Muestra formato largo de los archivos
```

---

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

### **2.3. Manejo de Archivos y Directorios**
Estos comandos son esenciales para interactuar con archivos y directorios en `bash`.

#### a) Ls
- **Sintaxis**: `ls [modificadores] [ficheros]`
- **Modificadores**:
  - `-l`: Muestra formato detallado de los archivos.
  - `-a`: Mostrar archivos y directorios ocultos.
  - `-R`: Listar desde el principio del árbol.
  - `-F`: Indica tipo de archivo (archivos, directorios, enlaces, etc.).
- **Ejemplo**: `ls –l /home/user/Documentos`

`ls` lista los archivos y directorios en el directorio especificado. Los modificadores pueden ayudarte a ver la información de manera más detallada.

#### b) Cat
- **Uso**: Visualizar, crear o concatenar archivos.
  - **Visualizar contenido de un archivo**:
    - **Sintaxis**: `cat [archivo]`
    - **Ejemplo**: `cat Fich1`
  - **Crear un nuevo archivo**:
    - **Sintaxis**: `cat > [nomb_fichero]`
    - **Ejemplo**: `cat > Fich1`
  - **Concatenar archivos**:
    - **Sintaxis**: `cat [archivo1] [archivo2]`
    - **Ejemplo**: `cat Fich1 Fich2 > Concatenado.txt`

#### c) More
- **Sintaxis**: `more [archivo]`
- **Ejemplo**: `more Fich1`

`more` divide el archivo en páginas para que sea más fácil de leer. Usa las teclas:
- Barra espaciadora: Ir a la siguiente página.
- Enter: Ir a la línea siguiente.
- `q`: Salir del visualizador.
- **Modificadores**:
  - `-###`: Indica el número de líneas por página.
  - `+###`: Indica desde qué línea comenzar.
  - `+/:` Busca una cadena y comienza desde su primera aparición.
  - `-p`: Evita que las páginas se desplacen.

#### d) Clear
- **Sintaxis**: `clear`
- **Ejemplo**: `clear`

`clear` limpia la pantalla del terminal, ofreciendo un nuevo entorno de trabajo limpio.
