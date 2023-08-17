Que es Node.js? 
Es un entorno de ejecucion de javascript (un sitio o espacio donde se ejecuta codigo javascript)

Caracteristicas:
1) Es multiplataforma
2) Es asincrono
3) Es orientado a eventos
4) Utiliza como motor el V8 de chrome
5) Es de codigo abierto
6) Es el mismo motor, pero no el mismo entorno.
7) Es monohilo
8) Es monoproceso
9) no se limita solo al backend
10) es la base o uno de los componentes del stack mean o mern

por que aprender node.js?
1) la demanda del mercado
2) puedes utilizar todos tus conocimientos de javascript en el entorno de node.js
3) puedes crear aplicaciones web, apis, scrapping, servicios, utilidades, etc..
4) una comunidad y ecosistema mas grande del mundo (npm).
5) rapido, escalable, barato, desplegable.

Historia:
se creo en el 2009 por el desarrollador ryan dart quien creo deno que es una alternativa a node
su razon fue estaba limitado apache http server al manejar peticiones concurrentes de conexiones.

Requisitos:
1) fundamentos de javascript

___________________________________________________________________________________________________________
Instalacion de node (tradicional):
1) entrar a nodejs.org
2) elegir la version a descargar (siempre elige la version estable o LTS (Long Term Suport))
3) hacer click en descargar

Desventajas de instalar node de forma tradicional:
1) solo te instala node una ves o solo una version de node.
esto significa que en caso de estar trabajando con diferentes proyectos que corren en diferentes versiones de node, solo correran de manera exitosa aquellos proyectos que esten desarrollados bajo la version de node instalada y los demas proyectos dejaran de funcional en parte o en su totalidad.
Para evitar este problema, tenemos algunas alternativas que dan solucion a este problema pero su implementacion depende del escenario en el que te puedas encontrar al momento de poner en marcha dicha solucion (detalles de las alternativas a continuacion).

Dockerizar node:
1) 

Gestor de versiones de node (nvm) la mas conocida en la comunidad de developers:
1) instalar la terminal nvm-windows
2) 

Gestor de versiones de node (fnm) favorita para midudev:
1.1) para linux o macOS, en la terminal, ejecuta el comando: curl -fsSL https://fnm.vercel.app/install | bash (debes tener instalado rust)
1.2) para windows, en la terminal, ejecuta el comando: winget install Schniz.fnm (debes tener winget instalado y actualizado)
2) luego de concluir la instalacion, en la terminal, ejecuta el comando: fnm --version

Errores al ejecutar fnm:
en ocaciones, presenta problemas con la ejecucion debido al path, para solucionarlo ejecuta una de las siguientes opciones a continuacion:
1) reinicia la terminal
2) reinicia el equipo
3) verifica que el path que apunta a la aplicacion este global y en caso de no estarlo, activalo a dicho modo.

Comandos de fnm (solo algunas):
1) verificar la version actual: fnm --version
2) listar las versiones de node instaladas: fnm list
3) instalar una version de node: fnm install (numero de version)
4) cambiar entre versiones de node: fnm use (numero de version)
5) desinstalar una version de node: fnm uninstall (numero de version)
6) configurar una version de node por defecto: fnm alias (numero de version) defaul

___________________________________________________________________________________________________________

Ejecutando node en la terminal:
1) ejecutamos el REPL con el comando: node
2) ejecutamos el comando help para ver las opciones basicas de navegacion (el REPL es parecido a la consola del devtools en el navegador)
3) podemos ejecutar tanto codigo de manera directa como tambien podemos ejecutar codigo desde un archivo con la extension .js o con las extensiones .cjs y (para ello debemos ejecutar el comando: node (ruta y nombre del archivo con la extension)).
ejemplo: node index.js

___________________________________________________________________________________________________________
Primeros pasos con node:
1) creamos un archivo llamado index.js y escribimos el siguiente codigo: console.log('klk con klk')
2) desde la terminal, ejecutamos el archivo con el comando node index.js


