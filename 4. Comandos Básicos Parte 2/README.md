# **4. Comandos Básicos Parte 2**

## **4.1. Grep**
El comando `grep` es utilizado para buscar patrones en archivos de texto. Es una herramienta muy poderosa para filtrar información y encontrar coincidencias específicas.

### **Sintaxis**
```bash
grep [opciones] patrón [ficheros…]
```

### **Modificadores**
- **`-v`**: Muestra las líneas que no coinciden con el patrón.
- **`-c`**: Cuántas líneas coincidieron con el patrón.
- **`-n`**: Muestra el número de línea en la que apareció la coincidencia.
- **`-i`**: Ignora las distinciones entre mayúsculas y minúsculas.
- **`-e`**: Indica que lo siguiente es una expresión regular y no un criterio.

### **Ejemplo**
```bash
grep -n "gato" /home/usuario/datos
```
Este comando buscará la palabra "gato" en el archivo `/home/usuario/datos` y mostrará la línea número 1 donde aparece, junto con el número de línea.

---

## **4.2. Wc**
El comando `wc` (word count) sirve para contar líneas, palabras y caracteres en un archivo de texto.

### **Sintaxis**
```bash
wc [opciones] [ficheros…]
```

### **Modificadores**
- **`-c`**: Contar caracteres.
- **`-w`**: Contar palabras.
- **`-l`**: Contar líneas.

### **Ejemplo**
```bash
wc -l /home/usuario/datos
```
Este comando mostrará el número total de líneas en el archivo `/home/usuario/datos`.

---

## **4.3. Echo**
El comando `echo` es utilizado para escribir mensajes en la salida estándar. Es muy útil para mostrar información al usuario o feedear entradas en scripts.

### **Sintaxis**
```bash
echo [opciones] mensaje
```

### **Modificadores**
- **`-n`**: Evita que el mensaje se imprima seguido de un salto de línea.

### **Ejemplo Básico**
```bash
echo "Hola mundo"
```
Esto mostrará en la terminal:  
`Hola mundo`

### **Ejemplo con Transformación**
```bash
echo "Esto es una prueba" | tr a 3
```
Este comando reemplazará todas las 'a's por '3's y mostrará:
`Esto es un3 prueb3`

---

## **4.4. Combinaciones Prácticas**
- **Filtrar y Contar en Un Solo Comando**
```bash
grep -c "gato" /home/usuario/datos
```
Este comando mostrará el número de líneas que contienen la palabra "gato".

- **Escribir y Contar en Un Archivo**
```bash
echo "Hola mundo" > mensaje.txt && wc -l mensaje.txt
```
Primero, el mensaje se escribe en `mensaje.txt`, luego se cuenta las líneas del archivo.

---

## **4.5. Uso en Scripts**
Los comandos `grep`, `wc` y `echo` son extremadamente útiles en scripts para procesar información de manera automática. Por ejemplo:
```bash
echo "Hola" > mensaje.txt && grep -w "hola" mensaje.txt
```
Este script escribe "Hola" en un archivo y luego busca la palabra "hola" en el mismo archivo, mostrando las líneas que contienen dicha palabra.

---

Con estos comandos, puedes manipular información de texto de manera eficiente en Linux, filtrar, contar y presentar datos de manera clara.