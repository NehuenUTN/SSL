## Con la previa instalación de Visual Studio Code y la extensión C/C++, asi es como configure todo para que el archivo se compile usando GCC y se debuggee correctamente con GDB de mingw-w64:
1) Descargue la última versión de MSYS2 utilizando este [enlace directo](https://github.com/msys2/msys2-installer/releases/download/2024-01-13/msys2-x86_64-20240113.exe).
2) Instale MinGW utilizando este comando en la consola de MSYS2 ``pacman -S --needed base-devel mingw-w64-ucrt-x86_64-toolchain``.
3) En Configuración de Windows edite las variables de entorno de mi usuario y añadí esta ruta a MinGW: ``C:\msys64\ucrt64\bin``.
4) Cree una carpeta en el escritorio para posteriormente añadir el archivo "hello.c" y abrirlo con Visual Studio Code.
5) Escribí dentro de ese archivo el código para que imprima exitosamente en pantalla "Hello World !".
6) Utilice ``gcc --version`` para conocer la versión de mi compilador **(la versión que yo utilizo es la 12.1)**.
7) Investigue los estandars de C que admite la versión 12.1 en este [manual](https://gcc.gnu.org/onlinedocs/gcc-12.1.0/gcc/Standards.html#C-Language).
8) Compile el código utilizando el estándar **C17** con este comando en la terminal de Visual Studio ``gcc hello.c -std=c17 -o hello``.
9) Se genero el archivo "tasks.json" y en los argumentos aproveché y le añadí el parámetro del estándar de C que voy a utilizar ``-std=c17``.
10) Siguiendo esta [pagina](https://code.visualstudio.com/docs/cpp/config-mingw#_run-helloworldcpp) termine de configurar el archivo tasks.json.
11) Dentro de la carpeta llamada ".vscode" cree el archivo "launch.json" y lo configure usando esta otra [pagina](https://code.visualstudio.com/docs/cpp/launch-json-reference#_configure-vs-codes-debugging-behavior).
12) Y finalmente con este comando ``./hello > output.txt`` ejecute el archivo .exe y la salida es redireccionada a un archivo .txt !!.
