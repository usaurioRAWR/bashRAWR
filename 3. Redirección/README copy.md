### **3. Redirección de Entrada y Salida**

El sistema de redirección en Linux permite canalizar la salida o entrada de un comando hacia otro lugar, 
como un archivo. Esto es útil para realizar tareas automatizadas o para manipular datos de manera eficiente.

Los tipos de redirección son; 

#### 3.1. **Salida (`>`)**
   - Usa `>` para reemplazar el valor actual de la salida estándar.
   - Ejemplo: 
     ```bash
     cat Fich1 Fich2 > FicheroResultante.txt
     ```
     - Si `FicheroResultante.txt` no existe, se crea.
     - Si existe, se sobreescribe sin preguntar.

  - #### **Ejemplo Práctico**

    **Sitúa:**
    ```bash
    F1	    F2	    >F3
    1Hola	2Adiós
            3Hola
            4Adiós
    ```

    **Resultado:**  
    El archivo `F3` contará con el texto:
    ```
    1Hola
    2Adiós
    3Hola
    4Adiós
    ```

#### 3.2. **Concatenación de Salida (`>>`)**
   - Usa `>>` para añadir la salida actual a un archivo que ya exista.
   - Ejemplo:
     ```bash
     echo "Hola" >> Mensaje.txt
     ```
     - Si `Mensaje.txt` existe, el contenido se añade al final.
     - Si no existe, se crea.

#### 3.3. **Entrada (`<`)**
   - Usa `<` para obtener la entrada del usuario o de un archivo.
   - Ejemplo:
     ```bash
     wc -l < Fichero
     ```
     - Si `Fichero` no existe, pide la entrada por teclado.
     - Si existe, lea el contenido del archivo (stdin).

#### 3.4. **Error (`2>`)**
   - Redirección de la salida estándar al archivo de diario de errores ( stderr).
   - Ejemplo:
     ```bash
     ls noexistente 2> /tmp/errores.log
     ```
     - Muestra un mensaje de error en la terminal.
     - Escribe el mensaje también en `/tmp/errores.log`.

#### 3.5. **Error y Salida (`2>>`)**
   - Combina stderr y stdout en un solo archivo, por defecto `stderr` primero.
   - Ejemplo:
     ```bash
     cat F1 F2 >> F3
     ```
     - Si `F3` no existe, se crea.
     - Si existe, se añaden los contenidos al final.

### **Conclusión**
La redirección es una herramienta poderosa para trabajar con datos en Linux. Conoce sus opciones y utiliza la combinación adecuada según tus necesidades, ya sean de entrada, salida o error manejo. ¡Practícale y descubre cómo simplifica tu trabajo diario! 😊

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