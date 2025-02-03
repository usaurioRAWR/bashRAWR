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