# **3. Redireccionamiento Y Tuberías**
## **3.1. Redireccinamiento**
El redireccionamiento es una herramienta poderosa que permite canalizar la entrada o salida de comandos hacia archivos u dispositivos específicos, en lugar de utilizar la terminal por defecto.

#### **Dispositivos de Redirección Estándar (File Descriptors - FD)**
- **`stdin` (FD 0):** Entrada estándar (teclado).
- **`stdout` (FD 1):** Salida estándar (terminal/pantalla).
- **`stderr` (FD 2):** Salida de errores estándar (terminal/pantalla).

#### **Propósito del Redireccionamiento**
- Redirigir la salida de un comando a un archivo.
- Redirigir la entrada de un comando desde un archivo.
- Combinar múltiples comandos en una misma salida.

### **3.1.1. Redireccionamiento de Salida Estándar (stdout)**

- #### **`>` (Sobreescribe):**
   - Redirecciona `stdout` a un archivo, creándolo si no existe y sobrescribiéndolo.
   - **Ejemplo:**
     ```bash
     ls -l > listado.txt
     ```
     - Si `listado.txt` no existe, se crea.
     - Si existe, se sobreescribe.

- #### **`>>` (Concatena):**
   - Redirecciona `stdout` a un archivo, concatenando su contenido al final del archivo existente.
   - **Ejemplo:**
     ```bash
     echo "Hola" >> mensaje.txt
     ```
     - Si `mensaje.txt` existe, el texto se agrega al final.
     - Si no existe, se crea y se escribe el texto.

### **3.1.2. Redireccionamiento de Entrada Estándar (stdin)**

- #### **`<` (Entrada desde un archivo):**
   - Redirecciona `stdin` desde un archivo en lugar de stdin por defecto.
   - **Ejemplo:**
     ```bash
     sort < lista_de_datos.txt
     ```
     - Lee la entrada del archivo `lista_de_datos.txt`.
### **3.1.3. Redireccionamiento de Error Estándar (stderr)**
- #### **`2>` y `2>>` (Redirección de `stderr`):**
   - Redirigen `stderr` a un archivo.
   - **Ejemplo:**
     ```bash
     cp archivo1 archivo2 2> errores.txt
     ```
     - Muestra mensajes de error en la terminal y los redirecciona a `errores.txt`.

### **3.1.4. Redireccionamiento Combinado (stdout y stderr)**
- #### **`&>` y `&>>` (Redirección de `stdout` y `stderr`):**
   - Redirige tanto la salida estándar `stdout` como el error estándar `stderr` a un archivo.
   - **Ejemplo:**
     ```bash
     comando &> salida_y_errores.txt
     ```

### **3.1.5. Redirección a `/dev/null`:**
   - Redirige la salida o entrada al dispositivo virtual que descarta toda la información.
   - **Ejemplo:**
     ```bash
     script.sh > /dev/null
     ```
     - La salida del script no se muestra en la terminal.


## **3.2. Tuberías o Cauces (Pipes)**

Las tuberías (pipes) se representa mediante el símbolo `|` y nos permite canalizar la salida de un comando 
como entrada para otro comando, sin necesidad de intermediar con archivos. Permitendonos asi combinar comandos 
en una misma secuencia.

### **Ejemplo Básico**
```bash
ls | grep archivos
```
- `ls` lista los archivos en el directorio actual.
- `grep archivos` filtra la salida de `ls` buscando las líneas que contienen la palabra "archivos".


> Las tuberías son una herramienta versátil en el manejo de flujos de datos en Linux, permitiendo crear scripts más eficientes y automáticos.
