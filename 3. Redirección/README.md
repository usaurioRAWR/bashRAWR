# **3. Redireccionamiento**
El redireccionamiento es una herramienta poderosa que permite canalizar la entrada o salida de comandos hacia archivos u dispositivos específicos, en lugar de utilizar la terminal por defecto.

#### **Dispositivos de Redirección Estándar (File Descriptors - FD)**
- **`stdin` (FD 0):** Entrada estándar (teclado).
- **`stdout` (FD 1):** Salida estándar (terminal/pantalla).
- **`stderr` (FD 2):** Salida de errores estándar (terminal/pantalla).

#### **Propósito del Redireccionamiento**
- Redirigir la salida de un comando a un archivo.
- Redirigir la entrada de un comando desde un archivo.
- Combinar múltiples comandos en una misma salida.

---

### **3.1. Redireccionamiento de Salida Estándar (stdout)**

- **`>` (Sobreescribe):**
   - Redirecciona `stdout` a un archivo, creándolo si no existe y sobrescribiéndolo.
   - **Ejemplo:**
     ```bash
     ls -l > listado.txt
     ```
     - Si `listado.txt` no existe, se crea.
     - Si existe, se sobreescribe.

- **`>>` (Concatena):**
   - Redirecciona `stdout` a un archivo, concatenando su contenido al final del archivo existente.
   - **Ejemplo:**
     ```bash
     echo "Hola" >> mensaje.txt
     ```
     - Si `mensaje.txt` existe, el texto se agrega al final.
     - Si no existe, se crea y se escribe el texto.

### **3.2. Redireccionamiento de Entrada Estándar (stdin)**

- **`<` (Entrada desde un archivo):**
   - Redirecciona `stdin` desde un archivo en lugar de stdin por defecto.
   - **Ejemplo:**
     ```bash
     sort < lista_de_datos.txt
     ```
     - Lee la entrada del archivo `lista_de_datos.txt`.
### **3.3. Redireccionamiento de Error Estándar (stderr)**
- **`2>` y `2>>` (Redirección de `stderr`):**
   - Redirigen `stderr` a un archivo.
   - **Ejemplo:**
     ```bash
     cp archivo1 archivo2 2> errores.txt
     ```
     - Muestra mensajes de error en la terminal y los redirecciona a `errores.txt`.

5. **Redirección a `/dev/null`:**
   - Redirige la salida o entrada al dispositivo virtual que descarta toda la información.
   - **Ejemplo:**
     ```bash
     script.sh > /dev/null
     ```
     - La salida del script no se muestra en la terminal.

---

#### **3. Combinación de Comandos con Redirección**

1. **Redirección de Salida a un Archivo y Concatenación:**
   - **Ejemplo:**
     ```bash
     date +’%F’ > formatado.txt >> formato_anterior.txt
     ```
     - El comando `date` redirige su salida a `formatado.txt`, y luego se concatena el contenido de `formatado.txt` al final de `formato_anterior.txt`.

2. **Uso de Pipas (`|`) para Enrutamiento:**
   - La salida de un comando puede ser la entrada de otro.
   - **Ejemplo:**
     ```bash
     ls -l | grep "\.txt" > archivos_txt.txt
     ```
     - `ls` lista todos los archivos, y `grep` filtran aquellos que terminan en `.txt`, redirigiendo la salida a `archivos_txt.txt`.

3. **Redirección de Entrada desde un Archivo y Procesamiento:**
   - **Ejemplo:**
     ```bash
     sort < lista_de_datos.txt | head -n 5 > primeros_5.txt
     ```
     - `sort` lee los datos del archivo `lista_de_datos.txt`, los ordena, y la salida se redirige al comando `head`, que muestra las primeras 5 líneas, y luego a `primeros_5.txt`.

---

#### **4. Redirección de Entrada y Salida en el Mismo Comando**

- **Redirección de `stdout` y `stderr` al mismo archivo:**
  ```bash
  comando > salida.txt 2>&1
  ```
  - Ambas salidas (`stdout` y `stderr`) se redirigen a `salida.txt`.

- **Redirección de `stdout` a un archivo y `stderr` a otro:**
  ```bash
  comando > stdout_file.txt 2> stderr_file.txt
  ```

---

#### **5. Redirección con Combinación de Subshells**

- **Grupo de Comandos en un Solo Redireccionamiento:**
  ```bash
  (comando1; comando2) > resultado.txt
  ```
  - Los comandos se ejecutan en orden, y su salida se redirige al archivo `resultado.txt`.

---

#### **6. Redirección con Archivos Virtuales**

- **Dispositivo de Null (`/dev/null`):**
  ```bash
  echo "Mensaje" > /dev/null
  ```
  - El mensaje no se muestra en la terminal ni se crea un archivo.

- **Dispositivo de Cero (`/dev/zero`):**
  ```bash
  echo "Mensaje" >> /dev/zero
  ```
  - Similar al null device, pero también elimina los archivos temporalmente creados.

---

#### **7. Redirección con Comentarios y Aquí-Documentos**

- **Redirección de un Bloque de Texto (HereDoc):**
  ```bash
  wc << fin
  linea1
  linea2
  fin
  ```
  - El contenido entre `<` y `>` se redirige al comando `wc`.

- **Redirección de una Cadena (HereString):**
  ```bash
  bc <<< "5*4"
  ```
  - Ejecuta el comando `bc` con la cadena `"5*4"` como entrada.

---

#### **8. Uso Práctico de Redirección**

**Ejemplo Clásico: Concatenar Archivos y Moverlos**
```bash
# Concatena archivo1.txt y archivo2.txt en resultado.txt
cat archivo1.txt archivo2.txt > resultado.txt

# Mueve el archivo resultado.txt a un directorio diferente
mv resultado.txt /tmp/
```

**Ejemplo de Redirección de Entrada:**
```bash
# Cuenta las líneas de un archivo
wc -l < archivo_entrada.txt
```

---

### **Practícas Interactivas**

1. **Redirección de Salida a un Archivo:**
   ```bash
   # Ejemplo:
   echo "Hola, mundo" > mensaje.txt
   ```

2. **Redirección de Entrada desde un Archivo:**
   ```bash
   # Ejemplo:
   sort < archivos/lista.csv
   ```

3. **Concatenación de Archivos con Redirección:**
   ```bash
   # Ejemplo:
   cat archivo1.txt >> archivo_resultado.txt
   ```

4. **Redirección de Errores a un Archivo:**
   ```bash
   # Ejemplo:
   cp archivo_noexistente.txt /tmp/ 2> errores.txt
   ```

5. **Uso de Pipas para Enrutamiento:**
   ```bash
   # Ejemplo:
   ls -l | grep "\.txt" > archivos_texto.txt
   ```

6. **Redirección de Salida y Entrada en un Solo Comando:**
   ```bash
   # Ejemplo:
   (ls -l; head -n 5) > primeros_5.txt 2>&1
   ```

---

### **Conclusión**

El redireccionamiento es una herramienta fundamental para trabajar eficientemente con el shell en Linux. Dominar los operadores de redirección y sus combinaciones te permitirá realizar tareas más rápido y con mayor precisión. ¡Sigue practicando y explorando diferentes ejemplos! 😊