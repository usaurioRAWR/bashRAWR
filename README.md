# bashRAWR
Este curso básico de Bash cubre los comandos y conceptos fundamentales para manipular el sistema operativo mediante la terminal. ¡Sigue practicando y explorando más comandos avanzados! 😊

> 🌟 Nota importante 🌟
> 
> En este curso, nos referiremos a ciertos comandos como "comandos básicos". 🛠️
>
> ¿Por qué? Porque son las herramientas esenciales que todo usuario necesita para dar sus primeros pasos en la terminal. 🐚✨ No los llamamos "básicos" porque sean simples o menos importantes, ¡todo lo contrario! Son los cimientos sobre los cuales se construyen habilidades más avanzadas en el uso de Bash. 🚀
>
> Dominar estos comandos es clave para manejar sistemas Unix/Linux de manera eficiente y desbloquear todo el potencial de la línea de comandos. 💻🔑

## **Indice**
1. [Introducción al Shell](/1.%20Introducción%20al%20Shell#1-introducción-al-shell)
   - 1.1. [¿Qué es el Shell?](/1.%20Introducción%20al%20Shell#12-composición-del-prompt)
   - 1.2. [Composición del Prompt](/1.%20Introducción%20al%20Shell#13-sintaxis-de-comandos)
   - 1.3. [Sintaxis de Comandos](/1.%20Introducción%20al%20Shell#13-sintaxis-de-comandos)

2. [Tipo de Comandos (Comandos Básicos Parte 1)](/2.%20Tipo%20de%20Comandos%20(Comandos%20Básicos%20Parte%201)#2-tipo-de-comandos-comandos-básicos-parte-1)
   - 2.1. [AYUDA](/2.%20Tipo%20de%20Comandos%20(Comandos%20Básicos%20Parte%201)#21-ayuda)
      - [Man](/2.%20Tipo%20de%20Comandos%20(Comandos%20Básicos%20Parte%201)/README.md#a-man)
      - [Apropos](/2.%20Tipo%20de%20Comandos%20(Comandos%20Básicos%20Parte%201)/README.md#b-apropos)
      - [Whatis](/2.%20Tipo%20de%20Comandos%20(Comandos%20Básicos%20Parte%201)/README.md#c-whatis)
   - 2.2. [Control de Sesión](/2.%20Tipo%20de%20Comandos%20(Comandos%20Básicos%20Parte%201)#22-control-de-sesión)
      - [Exit](/2.%20Tipo%20de%20Comandos%20(Comandos%20Básicos%20Parte%201)/README.md#a-exit)
      - [Su](/2.%20Tipo%20de%20Comandos%20(Comandos%20Básicos%20Parte%201)/README.md#b-su)
      - [logout](/main/2.%20Tipo%20de%20Comandos%20(Comandos%20Básicos%20Parte%201)#c-logout)
      - [clear](/2.%20Tipo%20de%20Comandos%20(Comandos%20Básicos%20Parte%201)#d-clear)
   - 2.3. [Manejo de Archivos y Directorios](/2.%20Tipo%20de%20Comandos%20(Comandos%20Básicos%20Parte%201)#23-manejo-de-archivos-y-directorios)
      - [ls](/2.%20Tipo%20de%20Comandos%20(Comandos%20Básicos%20Parte%201)/README.md#a-ls)
      - [cat](/2.%20Tipo%20de%20Comandos%20(Comandos%20Básicos%20Parte%201)/README.md#b-cat)
      - [more](/2.%20Tipo%20de%20Comandos%20(Comandos%20Básicos%20Parte%201)/README.md#c-more)

3. [Redireccionamiento Y Tuberías](/3.%20Redirección/README.md#3-redireccionamiento-y-tuberías)
   - 3.1. [Redireccinamiento](/3.%20Redirección/README.md#31-redireccinamiento)
      - [Dispositivos de Redirección Estándar (File Descriptors - FD)](/3.%20Redirección/README.md#dispositivos-de-redirección-estándar-file-descriptors---fd)
      - [Propósito del Redireccionamiento](/3.%20Redirección/README.md#propósito-del-redireccionamiento)
      - 3.1.1. [Redireccionamiento de Salida Estándar (stdout)]()
         - [`>` (Sobreescribe)](/3.%20Redirección/README.md#-sobreescribe)
         - [`>>` (Concatena)](/3.%20Redirección/README.md#-concatena)
      - 3.1.2. [Redireccionamiento de Entrada Estándar (stdin)](/3.%20Redirección/README.md#312-redireccionamiento-de-entrada-estándar-stdin)
         - [`<` (Entrada desde un archivo)](/README.md#-entrada-desde-un-archivo)
      - 3.1.3. [Redireccionamiento de Error Estándar (stderr)](/README.md#313-redireccionamiento-de-error-estándar-stderr)
         - [`2>` y `2>>` (Redirección de `stderr`)](/3.%20Redirección/README.md#2-y-2-redirección-de-stderr)
      - 3.1.4. [Redireccionamiento Combinado (stdout y stderr)](/3.%20Redirección/README.md#314-redireccionamiento-combinado-stdout-y-stderr)
         - [`&>` y `&>>` (Redirección de `stdout` y `stderr`)](/3.%20Redirección/README.md#-y--redirección-de-stdout-y-stderr)
      - 3.1.5. [Redirección a `/dev/null`](/main/3.%20Redirección/README.md#315-redirección-a-devnull)
   - 3.2. [Tuberías o Cauces (Pipes)](/3.%20Redirección/README.md#32-tuberías-o-cauces-pipes)