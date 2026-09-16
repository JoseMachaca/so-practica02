# Ejecución del comando `ls` en xv6

El comando `ls` se utiliza para listar los archivos y directorios del sistema de archivos actual. Una ejecución correcta en el shell de xv6 genera una salida estructurada en cuatro columnas con el siguiente formato:

```text
[Nombre] [Tipo] [Inodo] [Tamaño]
```

## Estructura de la Salida

* **Nombre del archivo / directorio:** Primera columna. Muestra el identificador del elemento en el directorio actual (por ejemplo: `.`, `..`, `README`, `cat`, `ls`).
* **Tipo de archivo:** Segunda columna. Representa la naturaleza del archivo mediante un identificador numérico entero:
  * `1` (T_DIR): Directorio.
  * `2` (T_FILE): Archivo regular o ejecutable.
  * `3` (T_DEV): Dispositivo especial (como `console`).
* **Número de Inodo:** Tercera columna. Muestra el identificador único del nodo de índice (`inode`) asignado al archivo dentro del sistema de archivos de xv6.
* **Tamaño:** Cuarta columna. Indica el tamaño del archivo expresado en **bytes**. Los archivos de tipo dispositivo (`3`) suelen mostrar un tamaño de `0`.

## Ejemplo de Salida Correcta

Al ejecutar `$ ls` en el directorio raíz, deberías observar una estructura similar a la siguiente:

```text
.              1 1 1024
..             1 1 1024
README         2 2 2441
cat            2 3 36728
ls             2 10 42880
console        3 23 0
```

![Arranque de xv6 y comandos de la Parte A](img/ParteA_01.png)
