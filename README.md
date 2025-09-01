# La línea de comandos de Bash
=====================

![*Tux, el pingüino de Linux*](images/tux.png)

Este tutorial te familiariza con **bash**, la línea de comandos de Linux. Aprenderás a:

* navegar por directorios
* manipular archivos
* ejecutar programas

Si no tienes experiencia previa con sistemas tipo Unix o conoces algunos comandos pero quieres aprender más, este tutorial es para ti.

### Requisitos previos

*Este tutorial fue preparado para Ubuntu Linux, pero también funciona en MacOS, Cygwin y Git Bash, siempre que tengas instalado Python 3 en tu sistema.*

----

## Objetivo

En este tutorial, estarás buscando una palabra con 22 caracteres:

![](images/solution.png)

Todos los caracteres están ocultos en los ejercicios siguientes.

## Preparativos

* clona el repositorio o descarga el código como un archivo ZIP  
* localiza la carpeta `exercises/`  
* abre una terminal `bash`  

![](preparations.png)

----

## 1. Directorios y archivos

### 1.1. Navegar entre directorios

El **primer carácter** está oculto en un archivo en algún lugar del árbol de directorios *exercise1*. Usa los comandos

```bash
cd <nombre_directorio>
```

(no escribas los corchetes, solo el nombre del directorio) y

```bash
ls
```

para moverte de un directorio a otro. Revisa los subdirectorios hasta encontrar uno con el nombre `solution_1.1` y lista su contenido.  
Si entraste en un directorio equivocado, puedes retroceder un nivel escribiendo:

```bash
cd ..
```

o volver a tu carpeta principal:

```bash
cd
```

### 1.2. Mostrar un archivo oculto

Algunos archivos no son visibles de inmediato. Para verlos necesitas el comando

```bash
ls -a
```

El **segundo carácter** está en el mismo directorio que el primero, pero dentro de un archivo oculto.

### 1.3. Ejecutar un programa

Usa `cd ..` para volver al directorio `exercise_1/directoryB/`. Al listar su contenido deberías ver un **archivo de script shell** `program.sh`. Para encontrar el **tercer carácter**, debes ejecutar el programa. En bash, esto se hace escribiendo `source` seguido del nombre del programa:

```bash
source program.sh
```

### 1.4. Saber qué tamaño tiene un archivo

Ve a la carpeta `exercise_1/directoryC/`. Para encontrar el **cuarto carácter**, necesitas saber qué tamaño tiene el archivo de texto en el directorio. Esto se hace con el comando:

```bash
ls -l
```

En la tabla que produce este comando, encontrarás el tamaño del archivo en bytes, el propietario del archivo, los permisos para leer y modificarlo, y la fecha/hora de la última modificación.  

Para obtener el cuarto carácter, busca el tamaño del archivo en la [Tabla de caracteres ASCII imprimibles](https://es.wikipedia.org/wiki/ASCII#Caracteres_imprimibles).

![](ASCII-Table-wide.svg)

*Tabla ASCII, Dominio Público*

<div class="admonition hint">

Cuando escribas nombres de directorios o archivos, presiona `[TAB]` después de las primeras letras. Unix intentará autocompletar lo que escribes.

</div>

----

## 2. Editar archivos de texto

Por favor usa `cd ..` para volver al directorio principal del material del tutorial. Luego, cambia al directorio `exercise_2`.

### 2.1. Ver el contenido de un archivo de texto

En el directorio *exercise_2/* encontrarás un archivo de texto *solution_2.1.txt*. El **quinto carácter** está dentro de ese archivo. Para ver su contenido, usa el comando:

```bash
less <nombre_archivo>
```

### 2.2. Editar archivos de texto

Para obtener el **sexto carácter**, deberás crear un archivo de texto en el directorio `exercise_2`. En Ubuntu, puedes usar el editor `nano`. Puedes iniciarlo escribiendo su nombre, o

```bash
nano <nombre_archivo>
```

**Para salir de nano, escribe Ctrl-X**  

Crea un archivo de texto con los caracteres que hayas encontrado hasta ahora.  

El **sexto carácter** es la tecla que debes presionar para guardar un archivo en `nano`.

<div class="admonition hint">

Si quieres saber más sobre un comando en particular, escribe:

```bash
man <comando>
```

Se abrirá una página de ayuda que puedes cerrar presionando 'q'.

</div>

----

## 3. Copiar y eliminar archivos

Por favor ve al directorio `exercise_3`.

### 3.1. Crear un directorio y copiar un archivo en él

Para encontrar los **caracteres siete y ocho**, debes crear un subdirectorio llamado *solution* en `exercise_3/` y copiar los archivos de las carpetas `part1/` y `part2/` dentro de él.

Para crear directorios, usa el comando:

```bash
mkdir <nombre_directorio>
```

Para copiar, puedes usar el comando:

```bash
cp <origen> <destino>
```

Escribe `ls -l solution/*` después para ver la solución.

### 3.2. Eliminar archivos

En el directorio `data`, todos los archivos que contengan una `Y` deben ser eliminados. Para hacerlo, usa el comando:

```bash
rm <nombre_archivo>
```

También hay más archivos que eliminar en el directorio *data*. Para borrar más de un archivo a la vez, puedes usar `*` como comodín, por ejemplo:

```bash
rm ju*
```

borrará todos: `junk.txt, juniper.txt` y `june.docx`.  

Para obtener los **caracteres nueve y diez**, mira los archivos que quedan después de eliminar todos los que contienen una `Y`.

<div class="admonition hint">

Para eliminar un directorio vacío, puedes usar:

```bash
rmdir <nombre_directorio>
```

El comando:

```bash
rm -r <nombre_directorio>
```

elimina un directorio y todo su contenido.

</div>

<div class="admonition warning">

En Unix, **no es posible recuperar archivos borrados**.  

Esto hace que eliminar archivos con el símbolo `*` sea **muy** peligroso, ya que podrías borrar todo de un directorio con un solo comando (por ejemplo, si escribes el directorio equivocado por accidente). Por eso, hacer respaldos se vuelve aún más importante después de aprender este comando.

</div>

----

## 4. Procesar datos de texto

Por favor ve al directorio `exercise_4`.

### 4.1. Comparar dos archivos

Hay dos versiones diferentes de una cita: `ai.txt` y `artificial_intelligence.txt`. Para saber en qué difieren, Unix proporciona el comando:

```bash
diff <archivo1> <archivo2>
```

Por supuesto, puedes mirar el texto primero con `less` o `nano`. El **carácter número 11** de la solución es el único carácter en el que difieren los dos archivos.

### 4.2. Ordenar un archivo de texto

Unix tiene un pequeño programa para ordenar archivos de texto alfabéticamente. Se llama así:

```bash
less <nombre_archivo> | sort
```

El símbolo `|` se llama *pipe* y se usa a menudo para conectar programas Unix entre sí. El **carácter número 12** de la solución es el primer carácter de la última palabra en el archivo `elephant.txt` ordenado alfabéticamente.

<div class="admonition hint">

Para almacenar las líneas ordenadas en un nuevo archivo, puedes añadir un archivo de salida así:

```bash
less <nombre_archivo> | sort -f > resultado.txt
```

</div>

### 4.3. Buscar palabras en un archivo de texto

Para buscar palabras específicas en un archivo de texto, usa el comando:

```bash
grep <palabra> <archivo>
```

Produce todas las líneas del archivo que contengan la palabra dada. El comando `grep` es muy potente y puede manejar Expresiones Regulares.  

Para encontrar el **carácter número 13**, busca la palabra **fire** en el archivo `datascience.txt` y toma el **primer** carácter de la salida.

<div class="admonition hint">

Puedes buscar en muchos archivos a la vez incluyendo un `*` en el nombre de archivo.

</div>

<div class="admonition warning">

Los dos últimos ejercicios pueden no funcionar en Git Bash.

</div>

----

## 5. Descomprimir archivos

Por favor ve al directorio `exercise_5`.

### 5.1. Descomprimir archivos

Descomprimir archivos es una tarea muy básica e importante. En Unix, a menudo encuentras archivos `.zip`, `.tar` y `.gz`. Para descomprimir un archivo zip, usa:

```bash
unzip <nombre_archivo>
```

Para `.tar` y `.tar.gz`:

```bash
tar -xf <nombre_archivo>
```

Y para `.gz`:

```bash
gunzip <nombre_archivo>
```

Los **caracteres 14 y 15** de la solución están dentro de un archivo comprimido varias veces en el directorio `exercise_5`.

<div class="admonition hint">

Para comprimir un directorio y todo su contenido, puedes usar el comando:

```bash
tar -cf respaldo.tar <directorio>
```

Para comprimirlo después, usa:

```bash
gzip respaldo.tar
```

</div>

----

## 6. Herramientas de línea de comandos

Por favor ve al directorio `exercise_6`.

### 6.1. Cambiar permisos de acceso a archivos

Cada archivo en Unix tiene permisos separados para lectura `r`, escritura `w` y ejecución `x`. Se muestran con:

```bash
ls -l
```

Hay un triplete de permisos para el propietario, otro para un grupo de usuarios, y otro para todos los demás. El comando `chmod` permite cambiarlos, por ejemplo:

```bash
chmod a+x <archivo>
```

otorga a todos los usuarios permiso para ejecutar un archivo, mientras que

```bash
chmod u-w <archivo>
```

prohíbe al usuario actual escribir en el archivo (protegiéndolo de ser borrado accidentalmente).

Para ver los **caracteres 16 y 17** de la solución, haz que el programa `permissions.sh` sea ejecutable y luego ejecútalo con:

```bash
./permissions.sh
```

<div class="admonition hint">

Puedes otorgar permisos a un árbol de directorios completo usando:

```bash
chmod -R a+x <directorio>
```

</div>

### 6.2. Saber cuánto espacio en disco me queda

Para saber cuánto espacio libre tienes, puedes usar el comando:

```bash
df
```

`df` lista todas las particiones de disco, CD-ROMs, memorias USB y algunas particiones lógicas que usa Unix. Todos los números se dan en kilobytes.  

Para obtener el **carácter número 18**, revisa la versión del programa `df`. Descubre cómo hacerlo con:

```bash
df --help
```

La solución es el último carácter del primer nombre de los autores.

### 6.3. Definir una variable de entorno

Para instalar algunos programas, es necesario definir variables de entorno. Estas se pueden definir con el comando:

```bash
export <nombre_variable>=<valor>
```

Puedes ver todas las variables con el comando:

```bash
env
```

Para obtener el **carácter número 19**, debes usar `export` para asignar a la variable *GIVEME* el valor **SOLUTION**.

```bash
echo $GIVEME
```

Encuentra la **posición del carácter en el alfabeto** con:

```bash
echo $GIVEME | wc -c
```

<div class="admonition hint">

Por defecto, los cambios en las variables de entorno solo afectan a la terminal actual.  

Si quieres que se definan automáticamente en cada ventana de consola, escribe el comando `export` en el archivo `.bashrc` en tu directorio personal (es un archivo oculto).

</div>

### 6.4. Verificar si tienes internet

La manera más sencilla de comprobar si tienes conexión a internet desde la línea de comandos de Unix es enviar una solicitud a un servidor conocido (por ejemplo, www.spiced-academy.com) con el comando:

```bash
ping <dirección_web>
```

El comando informa cuánto tarda un mensaje en ir y volver del servidor. Para interrumpirlo, presiona Ctrl+C. También puedes usar el programa:

```bash
./check_ping
```

El **carácter número 20** es la opción de `ping` que establece el número máximo de solicitudes enviadas. Revisa la documentación con:

```bash
man ping
```

### 6.5. Gestionar procesos

Para ver qué programas están corriendo en tu máquina, escribe:

```bash
top
```

Esto muestra una lista de todos los programas activos. *Shift+P* los ordena por uso de CPU, *Shift+M* por consumo de memoria (si no ves ninguno con mucho consumo, abre un navegador). Cierra `top` presionando *q*.  

Los **dos últimos caracteres** de la solución son las dos primeras letras de la segunda palabra en la línea que contiene las etiquetas de las columnas.

<div class="admonition hint">

Si quieres cerrar un programa que iniciaste (por ejemplo, porque se bloqueó), puedes hacerlo escribiendo:

```bash
kill -s 9 <pid>
```

</div>

El número *pid* está en la primera columna de la salida de `top`. Solo puedes cerrar tus propios programas, no los que pertenecen a *root*, el administrador del sistema.

----

### Licencia

**© 2024 Dr. Kristian Rother**  

Este tutorial se publica bajo la licencia Creative Commons Attribution Share-alike 4.0.  

Puedes encontrar el código fuente completo en [https://github.com/krother/bash_tutorial](https://github.com/krother/bash_tutorial).

### Agradecimientos

Gracias a muchos estudiantes por usar el tutorial en la práctica y encontrar errores. Gracias a `@zulcas` por contribuir con correcciones.  

Agradezco a Janusz M. Bujnicki, Allegra Via, Pedro Fernandes y Joachim Jacob por su ayuda en las pruebas y revisión del material. Un agradecimiento especial al Servicio Alemán de Intercambio Académico (DAAD) por su apoyo financiero.

### Contacto

`kristian.rother@posteo.de`
