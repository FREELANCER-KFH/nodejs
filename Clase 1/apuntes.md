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


___________________________________________________________________________________________________________
Variables globales:
si nos fijamos bien, no tuvimos que importar la funcion console.log para ejecutarla en nuestro archivo javascript (esto pasa de igual modo en el navegador). esto se debe a que cuando creamos un archivo de javascript y lo ejecutamos en el navegador o en node, se carga por defecto en el proyecto una variable de tipo objeto, que contiene todos los metodos, propiedades y palabras clave del lenguaje para de ese modo poder codear no solo con las palabras clave del lenguaje, sino con un sin numero de herramientas que nos ahorran codigo y tener que reinventar la rueda.

Esta variable tiene un nombre para node y otro para el navegador.
1) para node la variable se llama "global"
2) para el navegador se llama "window"
3) en la nueva especificacion de javascript (la recomendada), debemos utilizar la variable llamada "globalThis" (tambien para los proyectos basados en frameworks y librerias como react, angular, vue, etc).

Por ejemplo, si en la terminal o consola del navegador web, ejecutamos el siguiente codigo: "console.log(typeof window)", nos mostrara el siguiente resultado (ver la imagen a continuacion):

Sin envargo, si intentamos ejecutar el mismo comando en node, se mostrara en pantalla el siguiente error: undefined (ver la imagen a continuacion). 

Esto es debido a que el objeto "window" no esta definido en el codigo que estamos ejecutando en node (no se declaro, no existe en el objeto globar de node o no es una palabra clave del lenguaje) y por ende no tiene tipado de datos por lo que el metodo log del objeto console entiende que dicha expresion es indefinida y procede a mostrar dicho resultado en la consola o terminal.

Para evitarnos el dolor de cabeza de tener que utilizar el objeto "global" en node o el objeto "windows" en el navegador web, la nueva especificacion de javascript nos recomienda que utilicemos un nuevo objeto que es comun para ambas plataformas, que tiene por nombre "globalThis".

De modo que, si ahora tanto en el navegador como en node, ejecutamos el siguiente codigo: "console.log(typeof globalThis)", se nos mostrara el siguiente resultado (ver la imagen a continuacion):

___________________________________________________________________________________________________________
Profundizando sobre el objeto "globalThis":
Es una variable global (de tipo objeto) en toda nuestra aplicacion. significa que podemos acceder a dicha variable no importando si estamos dentro de una funcion, dentro de un bloque conqueto.

En el navegador, globalThis apunta a la variable "window", mientras que en node, globalThis apunta a su objeto nativo "global". 

Recomendacion: Lo recomendable es siempre implementar el objeto globalThis ya que es la forma correcta especificada en especificacion actual de javascript a la hora de referirnos a la variable global en los proyecto y ademas, nos permite tener un codigo mas uniforme y por ende, dicho codigo puede ser mantenido de mejor manera e inclusive, el proyecto puede ser adaptado para correr en diferentes dispositivos sin tener que alterar el codigo o tener que programar diferentes modulos segun sea el caso.

por ejemplo, es un error semantico a nivel de eficientizar el codigo y por los parametros recomendados por desarrolladores, el tener que utilizar el objeto window para proyectos que se ejecuten en el navegador web y el objeto global para los proyectos que se ejecuten en node o bien, intentar validar la existencia de cada objeto global nativo segun sea el caso.

console.log(window) //para el browser
console.log(global) //para node
console.log(typeof window === 'undefined' && global.this === this)

Importante:
Te haz preguntado de donde salen las propiedades y metodos como por ejemplo console, fetch, promise, etc?
La respuesta es que dichas propiedades con sus metodos pertenecen al objeto globalThis y como dicho objeto se carga en nuestro proyecto desde su creacion, podemos desde un inicio utilizar todas las propiedades que dicho objeto trae consigo.

Nota: por ultimo, no tenemos que escribir la palabra clave "globalThis" para invocar las propiedades y metodos que este objeto trae, sino que dichas propiedades y metodos las podemos declarar directamente y al momento de compilar e interpretar el codigo, en entorno de ejecucion (sea el navegador o sea node), se encargara de llamar al objeto globalThis para realizar las operaciones necesarias de modo que al final nuestra aplicacion se ejecute de manera exitosa.

Curiosidad:
Tambien podemos crear nuestras propiedades y metodos e insertarlas dentro del objeto globaThis, de modo que podemos tener dicho codigo reservado desde la inicializacion del proyecto pero esto no suele ser la mejor practica ya que lo recomendable es tener nuestro codigo a reutilizar siempre en un archivo o carpeta separada que luego podamos importar al proyecto utilizando una de las siguientes opciones (las cuales veremos en detalle en los siguientes modulos):

1) commonjs
2) EMScript
3) empaquetando o publicando el codigo en un repositorio y luego instalarlo mediante un gestor o git

Las opciones anteriores obedecen a un patron de diseno llamado "modulo" que nos permite separar el codigo dependiendo de la funcion o rol que valla a tener en nuestro proyecto, de ese modo nuestro proyecto estara mejor organizado y por ende sera mas facil escalarlo y darle mantenimiento e inclusive, tomar parte del proyecto como plataforma o servicio para otros proyectos futuros. por lo que es uno de los patrones de diseno mas utilizados hoy en dia y recomendados por la gran mayoria de desarrolladores. asi que tomando en cuenta lo antes mencionado, vamos a utilizar como patron de diseno modulo para los proyectos desarrollados en este repositorio (mas detalles sobre el patron de diseno modulo en el siguiente bloque).

__________________________________________________________________________________________________________
Patron de diseno Modulo:
es un patron que nos permite separar nuestro codigo en varios ficheros de modo que luego podamos importarlo y exportarlo dependiendo de lo que necesitemos ejecutar y por ende evitamos repetir codigo y podemos tener nuestro proyecto mucho mas organizado y legible.

Para poder implementar este patron, debemos tener como minimo dos ficheros (donde uno requiera del otro para funcional o reusar su codigo).

Ejemplo (demostracion):

1) tenemos un fichero llamado peticioes.js con el siguiente codigo:

/*
const numero1 = 5
const numero2 = 5

console.log(suma(numero1, numero2))
console.log(resta(numero1, numero2))
console.log(multiplicacion(numero1, numero2))
console.log(division(numero1, numero2))
console.log(modulo(numero1, numero2))
*/

2) tenemos en otro fichero llamado operaciones.js ubicado en el mismo directorio con el siguiente codigo:

/*
function suma (n1, n2){
    return n1+n2
}

function resta (n1, n2){
    return n1-n2
}

function multiplicacion (n1, n2){
    return n1*n2
}

function division (n1, n2){
    return n1/n2
}

function modulo (n1, n2){
    return n1%n2
}

module.exports{
    suma,
    resta,
    multiplicacion,
    division,
    modulo
}
*/

Si ejecutamos el codigo en node, nos mostrara un error indicando que las funciones invocadas dentro de la funcion log del objeto console, no estan definidas (no existen).

Este error es debido a que no hemos creado dichas funciones dentro del codigo o como veremos a continuacion, no hemos importado el archivo o fichero que contiene la definicion de dichas funciones.

Para importar dicho fichero, debemos agregar al inicio del archivo que esta llamando las funciones, el siguiente codigo (dependiendo del sistema de modulos que se este configurado en el proyecto):

1) forma clasica (commonJS): const { suma, resta, multiplicacion, division, modulo } = require('./operaciones')
2) forma recomendable (EMscript): import { suma, resta, multiplicacion, division, modulo } from './operaciones.js'

Para exportar el contenido de un fichero (funcion, variable, objeto, etc), debemos de implementar una de las siguientes opciones (dependiendo del sistema de modulos que se este configurado en el proyecto):

1) forma clasica (commonJS):
debemos crear un objeto al final del archivo con la siguiente estructura:

    1.1) module.exports{
        funciones a exportar (siguiendo la sintaxis de los objetos).
    }

    1.2) module.exports = funcion, variable u objeto a exportar

Ejemplo: 
    1.1) module.exports{
         suma,
         resta
    }

    1.2) module.exports = suma
         module.exports = resta


2) forma recomendable (EMscript): 
debemos colocar la palabra clave export antes de cada funcion (sea por expresion, por listado, por agregacion o por defecto):

Ejemplo:
    2.1) // Exporting declarations
    export let name1, name2/*, … */; // also var
    export const name1 = 1, name2 = 2/*, … */; // also var, let
    export function functionName() { /* … */ }
    export class ClassName { /* … */ }
    export function* generatorFunctionName() { /* … */ }
    export const { name1, name2: bar } = o;
    export const [ name1, name2 ] = array;

    2.2) // Export list
    export { name1, /* …, */ nameN };
    export { variable1 as name1, variable2 as name2, /* …, */ nameN };
    export { variable1 as "string name" };
    export { name1 as default /*, … */ };

    2.3) // Default exports
    export default expression;
    export default function functionName() { /* … */ }
    export default class ClassName { /* … */ }
    export default function* generatorFunctionName() { /* … */ }
    export default function () { /* … */ }
    export default class { /* … */ }
    export default function* () { /* … */ }

    2.4) // Aggregating modules
    export * from "module-name";
    export * as name1 from "module-name";
    export { name1, /* …, */ nameN } from "module-name";
    export { import1 as name1, import2 as name2, /* …, */ nameN } from "module-name";
    export { default, /* …, */ } from "module-name";
    export { default as name1 } from "module-name";

De esta manera (segun la eleccion tomando en cuenta la configuracion de modulos del proyecto), el fichero peticiones.js esta conectado al fichero operaciones.js que es donde estan definidas las operaciones a ejecutar (es como el modelo cliente/servidor en redes informaticas y servidores). Por ende si ahora volvemos a ejecutar nuestra aplicacion, se mostraran en pantalla los resultados deseados.

para los primeros proyectos que desarrollaremos durante el curso, vamos a seguir la especificacion de commonJS y cuando estemos mas avanzados y con proyectos de mucha mayor envergadura, procederemos a seguir la espeficicacion EMscript.

_________________________________________________________________________________________________________
extenciones de archivos para indicar la especificacion del patron modulo en node:

En node, podemos indicarle de manera explicita que especificacion de modulos utilizar en nuestros proyectos.

para ello podemos implementar una de las siguientes opciones:
1) cambiar la extension de los ficheros siguiendo la leyenda a continuacion:

    1.1) .js --> por defecto utiliza commonJS (la clasica)
    1.2) .cjs --> para utilizar commonJS (la clasica)
    1.3) .mjs --> para utilizar ES Modules (la recomendada y actual)

2) modificando el archivo package.json, indicandole en el apartado de module la especificacion que necesitamos implementar en nuestro proyecto (como se muestra a continuacion).

    2.1) module{
            ES Modules: true
         }

__________________________________________________________________________________________________________
Modulos nativos en node:



