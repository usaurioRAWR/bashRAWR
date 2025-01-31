# bashRAWR
Este curso básico de Bash cubre los comandos y conceptos fundamentales para manipular el sistema operativo mediante la terminal. ¡Sigue practicando y explorando más comandos avanzados! 😊

### **Curso Básico de Bash**

#### **1. Introducción al Shell**
- **¿Qué es el Shell?**
  - Un interpretador de comandos que permite interactuar con el sistema operativo.
  - Ejemplo: `ls`, `cat`, `mv`, etc.

- **Comandos básicos del prompt:**
  ```
  $ ls
  $ cat
  $ mv
  $ cp
  $ chmod
  $ su
  ```

---

#### **2. Comandos Básicos**
**1. Muestra los archivos y directorios en un directorio:**
```bash
ls [opciones]
```
   - `-l`: Muestra información detallada de los archivos.
   - `-a`: Muestra archivos ocultos que comienzan con punto (.`).
   - `-R`: Muestra los contenidos de manera recursiva.

Ejemplo:
```bash
ls -l      # Muestra formato largo
ls -a      # Muestra archivos ocultos
ls /home/  # Muestra contents del directorio home
```

**2. Visualiza el contenido de un archivo:**
```bash
cat [archivo]
```
Ejemplo:
```bash
cat README.md    # abre el archivo README.md
cat > nuevo.txt  # crea un nuevo archivo y escribe en él
```

---

#### **3. Manejo de Sesión**
- **Salir del sistema:**
  ```bash
  exit
  ```
- **Entrar como usuario root:**
  ```bash
  su [usuario]
  ```

---

#### **4. Manejo de Archivos y Directorios**
**1. Copiar archivos:**
```bash
cp [origen] [destino]
```
Ejemplo:
```bash
cp archivo1.txt /home/user/  # copia archivo1.txt al directorio home del usuario
```

**2. Mover archivos:**
```bash
mv [archivo] [nuevo-nombre]
```
Ejemplo:
```bash
mv archivo1.txt archivo2.txt   # cambia el nombre de archivo1.txt a archivo2.txt
```

**3. Crear directorios:**
```bash
mkdir [opciones] [directorio]
```
   - `-p`: Crea los directorios intermediarios si no existen.

Ejemplo:
```bash
mkdir -p /var/www/html  # crea los directorios /var/www/html y sus padres
```

**4. Eliminar archivos y directorios:**
```bash
rm [archivo]
rmdir [directorio]
```
   - `–i`: Pregunta antes de eliminar.
   - `-f`: No muestra mensajes de error si el archivo no existe.

Ejemplo:
```bash
rm –i archivo.txt     # pregunta antes de borrar
rm -f /tmp/file.txt  # borra el archivo sin mensaje de error
```

---

#### **5. Permisos en Linux**
- **Ver permisos de un archivo:**
  ```bash
  ls -l [archivo]
  ```
  Ejemplo:
  ```
  ls -l archivo.txt
      drwxr-xr-- 1 user group   0 enero 15 12:34 archivo.txt
  ```

- **Cambiar permisos de un archivo:**
  ```bash
  chmod [opción] [archivo]
  ```
   - Opciones numéricas (octales):
     ```
     chmod 755 archivo.txt    # d=7, g=5, u=4, r=0
     ```
   - Opciones simbólicas:
     ```
     chmod g+x archivo.txt   # agrega ejecución al grupo
     ```

---

#### **6. Comodines y Búsqueda de Archivos**
- **Caracteres comodines:**
  - `*`: Cantidad de caracteres (ejemplo: `*a` busca archivos que terminan en "a").
  - `[ ]`: Busca exactamente los caracteres dentro del corchete.
  - `?`: Busca un solo carácter.
  - `^$`: Busca al inicio o final de la línea.

- **Busca en archivo:**
  ```bash
  grep [opciones] [patrón] [archivo]
  ```
   - `-i`: Ignora mayúsculas y minúsculas.
   - `-n`: Muestra el número de línea donde se encuentra el patrón.

Ejemplo:
```bash
grep -i "error" archivo.log    # busca "error" sin distinguir mayúsculas
grep -n "mensaje" archivo.txt  # muestra las líneas con "mensaje"
```

---

#### **7. Redirección de Entrada y Salida**
- **Redirección a archivo:**
  ```bash
  comando > archivo.txt
  ```

  Ejemplo:
```bash
  cat archivos/* > todos_lecturas.txt   # concatena todos los archivos en "archivos/" en "todos_lecturas.txt"
```

- **Concatenar archivos:**
  ```bash
  cat archivo1.txt archivo2.txt > resultado.txt
  ```

---

#### **8. Pipes para Enrutamiento de Comandos**
- Ejemplo:
  ```bash
  ls -l | grep "d"    # muestrea los archivos que comienzan con "d"
  ```
  Explicación:
  - `ls -l` muestra los archivos en formato largo.
  - `grep "d"` filtran los archivos que empiecen con "d".
  - La salida de `ls` se envía como entrada a `grep`.

---

#### **9. Contar y Verificar Archivos**
- **Contar palabras, líneas y caracteres:**
  ```bash
  wc [archivo]
  ```
   - Opciones:
     ```
     wc -l     # cuenta líneas
     wc -w     # cuenta palabras
     ```

- **Verificar si existe un archivo:**
  ```bash
  if [ -f archivo.txt ]; then
    echo "El archivo existe."
  fi
  ```

---

#### **10. Variables de Entorno y Scripts**
- **Variables de entorno:**
  ```bash
  echo $SHELL       # muestra el interprete actual (ejemplo: /bin/bash)
  echo $HOME       # directorio home del usuario
  ```
  
- **Variables locales:**
  ```bash
  variable="valor"
  echo "$variable"
  ```

- **Scripts con parámetros:**
  ```bash
  #!/bin/bash
  echo "Hola $1!"
  ```
  
Ejemplo de ejecución:
```bash
bash script.sh nombre usuario
```

---

#### **11. Estructuras de Control en Bash**
**1. If y Case:**
```bash
if [ condición ]; then
  # comando
fi

case en "condición" in
  valor1)
    # comando
    ;;
  *)
    # mensaje por defecto
    ;;
esac
```

Ejemplo:
```bash
echo "¿Borrar archivo?"
read respuesta

case $respuesta in
  [Yy]* | ok) echo "Borrando archivo..."
  rm archivo.txt
  ;;
*) echo "No se borró el archivo."
  ;;
esac
```

**2. Bucles For y While:**
```bash
for variable en lista; hacer:
  # comando
done

while condición; hacer:
  # comando
done
```

Ejemplo de bucle for:
```bash
for i in 1 2 3; do
  echo $i
done
```

---

#### **12. Operaciones Aritméticas**
- **Expresión:**
  ```bash
  valor=`expr "3*4+2"`
  echo $valor
  ```
  Opción alternativa:
  ```bash
  valor=$[3*4+2]
  ```

---

#### **13. Diseño de Menú en Bash**
```bash
echo "Menú principal"
echo "1) Opcción 1"
echo "2) Opcción 2"
read respuesta

case $respuesta in
  1*) echo "Se ha seleccionado la opcción 1."
  ;;
  2*) echo "Se ha seleccionado la opcción 2."
  ;;
esac
```

---

### **Pruebas y Ejercicios**
**Ejercicio 1: Muestre los archivos ocultos en el directorio actual.**
```bash
ls -a
```

**Ejercicio 2: Crea un nuevo archivo y escribe dentro de él.**
```bash
cat > nuevoarchivo.txt
Escribiendo... finalizo con Enter.
Mensaje del archivo:
Hola, mundo!
```

---
