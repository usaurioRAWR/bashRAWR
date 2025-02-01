# bashRAWR
Este curso básico de Bash cubre los comandos y conceptos fundamentales para manipular el sistema operativo mediante la terminal. ¡Sigue practicando y explorando más comandos avanzados! 😊

## **Curso Básico de Bash**

### **1. Introducción al Shell**

#### **1.1. ¿Qué es el Shell?**
El **Shell** es un programa interpretador de comandos que actúa como intermediario entre el usuario y el sistema operativo. Su propósito principal es ejecutar comandos y acceder a funciones del sistema para realizar tareas diarias.

Al abrir la terminal, veías esto:
```bash
user@pc:~ $
```
Este es el **prompt** o línea de comando, donde escribe y ejecutas los comandos.

#### **1.2. Composición del Prompt**
El prompt consiste en:
1. Tu nombre de usuario (`user`).
2. El nombre del sistema operativo y la máquina (`pc`).
3. El directorio actual (`~`), que es el directorio home del usuario.
4. El símbolo `$`, que indica que estás listo para recibir una orden.

#### **1.3. Sintaxis de Comandos**
Los comandos se estructuran como:
```bash
comando [-flags] [argumentos]
```
> (Las partes que están entre corchetes (`[]`) son opcionales.)
- **Comando**: Es la acción que deseas ejecutar.
- **Flags**: Modificadores opcionales que se pueden agregar a los comandos para alterar su comportamiento o formato. 
- **Argumentos**: Los objetos sobre los que actúa el comando.
> Las flags empiezan con un prefijo de `-` (menos) seguido de una letra mayúscula o minúscula, representando un determinado opción o ajuste. Su uso puede hacer la diferencia entre una tarea sencilla y una tarea más eficiente o personalizada.

#### **Ejemplo de Comando**
```bash
ls   # Muestra los archivos y directorios en el directorio actual
ls -l  # Muestra formato largo de los archivos
cat archivo.txt  # Muestra el contenido de archivo.txt
mv archivo1.txt archivo2.txt  # Cambia el nombre de archivo1.txt a archivo2.txt
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


#### d) clear
- **Sintaxis**: `clear`
- **Ejemplo**: `clear`

`clear` limpia la pantalla del terminal, ofreciendo un nuevo entorno de trabajo limpio.

---

### **3. Redirección de Entrada y Salida**

El sistema de redirección en Linux permite canalizar la salida o entrada de un comando hacia otro lugar, 
como un archivo. Esto es útil para realizar tareas automatizadas o para manipular datos de manera eficiente.

#### **Tipos de Redirección**
1. **Salida (`>`)**
   - Usa `-` para reemplazar el valor actual de la salida estándar.
   - Ejemplo: 
     ```bash
     cat Fich1 Fich2 > FicheroResultante.txt
     ```
     - Si `FicheroResultante.txt` no existe, se crea.
     - Si existe, se sobreescribe sin preguntar.

2. **Concatenación de Salida (`>>`)**
   - Usa `-` para añadir la salida actual a un archivo que ya exista.
   - Ejemplo:
     ```bash
     echo "Hola" >> Mensaje.txt
     ```
     - Si `Mensaje.txt` existe, el contenido se añade al final.
     - Si no existe, se crea.

3. **Entrada (`<`)**
   - Usa `-` para obtener la entrada del usuario o de un archivo.
   - Ejemplo:
     ```bash
     wc -l < FicheroEnTaller
     ```
     - Lectura desde el teclado si no se proporciona un archivo.
     - Puede reemplazar a stdin en comandos más avanzados.

4. **Error (`2>`)**
   - Redirección de la salida estándar al archivo de diario de errores ( stderr).
   - Ejemplo:
     ```bash
     ls noexistente 2> /tmp/errores.log
     ```
     - Muestra un mensaje de error en la terminal.
     - Escribe el mensaje también en `/tmp/errores.log`.

5. **Error y Salida (`2>>`)**
   - Combina stderr y stdout en un solo archivo, por defecto `stderr` primero.
   - Ejemplo:
     ```bash
     ls noexistente 2>> /tmp/errores.txt
     ```
     - Muestra mensajes de error y éxito en `/tmp/errores.txt`.

---

#### **Ejemplo Práctico**

**Sitúa:**
```bash
F1	F2	>F3
Hola	Adiós
		Hola
		Adiós
```

**Resultado:**  
El archivo `F3` contará con el texto:
```
Hola
Adiós
Hola
Adiós
```

---

#### **Uso de Redirección en Comandos de Concatenación**
```bash
A	B	>F3
1	3	1
2	4	2
		3
		4
```
- Resultado en `F3`:
  ```
  A B
  1 3 1
  2 4 2
    3
    4
  ```

---

#### **Entrada y Redirección**
**Ejemplo de Conteo de Líneas:**
```bash
wc -l < FicheroEnTaller
```
- Si `FicheroEnTaller` no existe, pide la entrada por teclado.
- Si existe, lea el contenido del archivo.

---

#### **Redirección y Eliminación de Archivos**
**Ejemplo de Concatenación y Creación de Archivo:**
```bash
cat F1 F2 >> F3
```
- Si `F3` no existe, se crea.
- Si existe, se añaden los contenidos al final.

**Ejemplo de Redirección y Sobreescritura:**
```bash
echo "Datos" > /tmp/file.txt
```
- El archivo `/tmp/file.txt` se sobreescribe con el mensaje "Datos".

---

### **Conclusión**
La redirección es una herramienta poderosa para trabajar con datos en Linux. Conoce sus opciones y utiliza la combinación adecuada según tus necesidades, ya sean de entrada, salida o error manejo. ¡Practícale y descubre cómo simplifica tu trabajo diario! 😊
