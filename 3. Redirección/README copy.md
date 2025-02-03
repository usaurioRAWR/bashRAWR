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