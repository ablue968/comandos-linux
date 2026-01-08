# 🐧 Resumen de Teoría y Comandos Linux

Este documento es una guía rápida de los comandos fundamentales de la shell de Linux, basada en el material de estudio proporcionado.

---

## 🛠️ Ayuda e Información del Sistema

### 1. `man`
Accede a las páginas de manual para conocer opciones y argumentos.
* **Ejemplo:** `man ls`
* **Resultado:** Muestra el manual detallado del comando `ls`. (Pulsa `q` para salir).

### 2. `pwd`
Muestra la ruta absoluta del directorio donde te encuentras.
* **Ejemplo:** `pwd`
* **Resultado:** `/home/cresino/proyectos`

### 3. `history`
Lista los comandos ejecutados recientemente.
* **Ejemplo:** `history | tail -n 5`
* **Resultado:**
    ```bash
    501  ls -la
    502  mkdir datos
    503  cd datos
    504  touch notas.txt
    505  history
    ```

### 4. `date`
Muestra o configura la fecha y hora del sistema.
* **Ejemplo:** `date +"%A, %d de %B"`
* **Resultado:** `jueves, 08 de enero`

---

## 📂 Gestión de Archivos y Directorios

### 5. `ls`
Lista el contenido de un directorio.
* **Ejemplo:** `ls -lh` (Formato largo y tamaño legible)
* **Resultado:**
    ```bash
    drwxr-xr-x 2 user user 4,0K may  9 20:04 Descargas
    -rw-r--r-- 1 user user 150K may 16 20:08 reporte.pdf
    ```

### 6. `cd`
Cambia el directorio de trabajo.
* **Ejemplo:** `cd /etc` (Ruta absoluta) o `cd ..` (Subir un nivel).

### 7. `mkdir` y `rmdir`
Crean y eliminan directorios (rmdir solo si está vacío).
* **Ejemplo:** `mkdir -p curso/linux/modulo1`
* **Resultado:** Crea toda la estructura de carpetas de forma recursiva.

### 8. `touch`
Crea archivos vacíos o actualiza marcas de tiempo.
* **Ejemplo:** `touch archivo{1..3}.txt`
* **Resultado:** Crea `archivo1.txt`, `archivo2.txt` y `archivo3.txt`.

### 9. `cp` y `mv`
Copian o mueven/renombran archivos.
* **Ejemplo:** `cp -r /origen /destino` (Copia recursiva).
* **Ejemplo:** `mv viejo.txt nuevo.txt` (Renombrar).

### 10. `rm`
Elimina archivos o directorios permanentemente.
* **Ejemplo:** `rm -rf carpeta_con_contenido`
* **Resultado:** Borra la carpeta y todo lo que hay dentro sin preguntar.

---

## 🔍 Búsqueda y Localización

### 11. `find`
Busca archivos según criterios (nombre, tamaño, fecha).
* **Ejemplo:** `find . -name "*.txt" -size +1M`
* **Resultado:** Lista archivos `.txt` mayores a 1MB en el directorio actual.

### 12. `which` y `type`
Localizan binarios e indican el tipo de comando.
* **Ejemplo:** `which python3` -> `/usr/bin/python3`

---

## 📄 Manipulación de Texto y Contenido

### 13. `cat`, `head` y `tail`
Visualizan contenido de archivos.
* **Ejemplo:** `tail -f /var/log/syslog`
* **Resultado:** Muestra las últimas líneas y se actualiza en tiempo real.

### 14. `grep`
Busca patrones de texto.
* **Ejemplo:** `grep -i "error" log.txt`
* **Resultado:** Muestra todas las líneas de `log.txt` que contienen "error".

### 15. `cut`
Extrae columnas o campos.
* **Ejemplo:** `echo "admin:x:0:0" | cut -d ':' -f 1`
* **Resultado:** `admin`

### 16. `tr`
Traduce o borra caracteres.
* **Ejemplo:** `echo "linux" | tr 'a-z' 'A-Z'`
* **Resultado:** `LINUX`

---

## 📤 Redirecciones y Canales
* `>` : Sobrescribe archivo con la salida.
* `>>` : Añade al final del archivo.
* `2>` : Redirige errores.
* `|` (Pipe) : Pasa la salida de un comando a otro.

**Ejemplo combinado:**
`ls -l /etc 2> errores.log | grep "conf" > resultados.txt`
