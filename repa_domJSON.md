***que es el DOM?

    El dom es nada mas ni nada menos que un objeto, es el objeto donde vive nuestra pagina web y sus metodos
    DOM significa Document Object Model (Modelo de Objetos del Documento), y es una estructura que representa el contenido de una página web como un árbol de objetos.

    El DOM vive dentro de un objeto mas grande llamado window, Y que es window?

    window es el punto de partida JS y tambien es un objeto global, es el objeto global en JavaScript cuando se ejecuta en un navegador!!!!, asi que por ejemplo en node JS no existe window. Representa la ventana del navegador y actúa como el punto de entrada para acceder a muchas funcionalidades del entorno web.

    veamos las partes mas importantes o destacadas de window y que contienen

    📄 window.document
    - Contenido: El DOM (estructura HTML de la página).
    - Uso: Manipular elementos HTML, estilos, eventos, etc.

    🌐 window.location
    - Contenido: Información sobre la URL actual.
    - Uso: Redirigir, recargar o acceder a partes de la URL.

    🧠 window.console
    - Contenido: Herramientas de depuración.
    - Uso: Mostrar mensajes (console.log()), errores, advertencias.

    ⏱️ window.setTimeout() / setInterval()
    - Contenido: Temporizadores.
    - Uso: Ejecutar funciones después de un tiempo o repetidamente.

    💬 window.alert() / confirm() / prompt()
    - Contenido: Cuadros de diálogo.
    - Uso: Interactuar con el usuario (mensajes, confirmaciones, entradas).

    🗂️ window.localStorage / sessionStorage
    - Contenido: Almacenamiento de datos en el navegador.
    - Uso: Guardar información persistente o temporal.

    📜 window.history
    - Contenido: Historial de navegación.
    - Uso: Navegar hacia atrás o adelante sin recargar la página.

    🧭 window.navigator
    - Contenido: Información del navegador (idioma, plataforma, etc.).
    - Uso: Detectar características del entorno del usuario.

    🖼️ window.screen
    - Contenido: Datos de la pantalla (resolución, tamaño).
    - Uso: Adaptar el diseño a diferentes dispositivos.

    🔄 window.open() / window.close()
    - Contenido: Control de ventanas emergentes.
    - Uso: Abrir nuevas pestañas o cerrar ventanas abiertas por script.

    Asi que el DOM es un atributo del Objeto global window y para acceder a el lo hacemos como cualquier otro objeto y propidad
    desde la consola ejecutamos 
        window.document

    Cuales son las partes mas importante de document?

    - getElementById()
    Busca un elemento por su ID para modificarlo o leer su contenido.
    
    - querySelector() / querySelectorAll()
    Selecciona uno o varios elementos usando selectores CSS avanzados.
    
    - createElement()
    Crea dinámicamente nuevos nodos HTML.
    
    - document.body
    Representa el contenido de la etiqueta <body> del HTML; permite agregar o modificar elementos.
    
    - document.title
    Accede o modifica el título que aparece en la pestaña del navegador.
    
    - document.readyState
    Indica el estado de carga del documento (loading, interactive, complete).
    
    - document.forms
    Colección de todos los formularios del documento.
    
    - document.images
    Lista de todas las imágenes incluidas en el documento.
    
    - document.links
    Colección de todos los enlaces <a> presentes.
    
    - addEventListener("DOMContentLoaded", ...)
    Detecta cuándo el DOM está completamente cargado y listo para usarse.

    -document.styleSheets
    Permite acceder a la hoja de estilo

    Como document es una estructura que representa a la pagina web como un árbol de objetos, tendra algunas partes caracteristicas de ese tipo de grafo, en este caso tendra nodos y elementos 

   Los elementos son las etiquetas html y los contenidos son nodos, pero algunos nodos tambien son eelementos pero  algunos no 
   veamos este ejemplo:

   <div> 
        <h1>  "esto es solo un nodo" </h1>
   </div>

    En este caso div es un elemento y h1 es su nodo, peroooo, h1 es tambien un elemento que contiene un nodo, el cual es el contenido de h1, este contenido ("esto es solo un nodo") es solamnte un nodo.


    Que se puede hacer con el dom?

    Bueno basicamente puedo crear toda una pagina web completa usando solo JS y sin escribir casi nada de html dentro del body

    ***Modificando el DOM usando JS

    // Creamos el <article>
    const article = document.createElement("article");

    // Estilos para el artículo

    article.style.border = "2px solid #2e8b57"; // Marco sólido verde oscuro
    article.style.backgroundColor = "#d0f0c0"; // Verde muy claro
    article.style.padding = "20px";
    article.style.margin = "20px auto";
    article.style.width = "fit-content";
    article.style.borderRadius = "10px";
    article.style.fontFamily = "'Segoe UI', 'Roboto', 'Helvetica Neue', sans-serif"; // Fuente moderna

    // Creamos el título <h2>
    const titulo = document.createElement("h2");
    titulo.textContent = "Este es el título del artículo";
    titulo.style.marginBottom = "10px";

    // Creamos la imagen <img>
    const imagen = document.createElement("img");
    imagen.src = "https://via.placeholder.com/300x200";
    imagen.alt = "Imagen de ejemplo";
    imagen.style.width = "300px";
    imagen.style.display = "block";

    // Agregamos el título y la imagen al artículo
    article.appendChild(titulo);
    article.appendChild(imagen);

    // Buscamos el contenedor con id="root"
    const root = document.getElementById("root");

    // Insertamos el artículo en el DOM
    root.appendChild(article);



    Y si los estilos vienen desde una styleSheet?
    primero creo la hoja de estilo

    /* estilos.css */
    article.mi-articulo {
    border: 2px solid #2e8b57;
    background-color: #d0f0c0;
    padding: 20px;
    margin: 20px auto;
    width: fit-content;
    border-radius: 10px;
    font-family: 'Segoe UI', 'Roboto', 'Helvetica Neue', sans-serif;
    }

    article.mi-articulo h2 {
    margin-bottom: 10px;
    }

    article.mi-articulo img {
    width: 300px;
    display: block;
    }

    luego link con mi pagina html

    <link rel="stylesheet" href="estilos.css">

    y ahora el codigo JS usando esos estilos

    // Creamos el <article>
    const article = document.createElement("article");
    article.classList.add("mi-articulo"); // Le agregamos la clase para estilos y con esto ya toma los estilos de la hoja CSS

    // Creamos el título
    const titulo = document.createElement("h2");
    titulo.textContent = "Este es el título del artículo";

    // Creamos la imagen
    const imagen = document.createElement("img");
    imagen.src = "https://via.placeholder.com/300x200";
    imagen.alt = "Imagen de ejemplo";

    // Agregamos los elementos al artículo
    article.appendChild(titulo);
    article.appendChild(imagen);

    // Lo insertamos en el <body>
    const root = document.getElementById("root");
    root.appendChild(article);

    *** los eventos del DOM

    Eventos de interacción del usuario
    - click: cuando el usuario hace clic en un elemento.
    - dblclick: doble clic.
    - mouseover / mouseout: cuando el cursor entra o sale de un elemento.
    - mousedown / mouseup: cuando se presiona o suelta un botón del mouse.
    - mousemove: cuando el mouse se mueve sobre un elemento.
    ⌨️ Eventos del teclado
    - keydown: cuando se presiona una tecla.
    - keyup: cuando se suelta una tecla.
    - keypress: cuando se presiona una tecla que produce un carácter (menos usado hoy en día).
    📦 Eventos de formulario
    - submit: cuando se envía un formulario.
    - change: cuando cambia el valor de un input, select, etc.
    - input: cuando el usuario escribe en un campo de texto.
    - focus / blur: cuando un elemento gana o pierde el foco.
    📄 Eventos del documento y ventana
    - load: cuando la página o un recurso ha terminado de cargarse.
    - DOMContentLoaded: cuando el DOM ha sido completamente cargado y parseado.
    - resize: cuando se cambia el tamaño de la ventana.
    - scroll: cuando se hace scroll en la página.
    🔄 Eventos personalizados y otros
    - contextmenu: cuando se abre el menú contextual (clic derecho).
    - touchstart / touchend / touchmove: para dispositivos táctiles.
    - animationstart / animationend / animationiteration: relacionados con animaciones CSS.
    - transitionend: cuando termina una transición CSS.

    Ejemplo con Onclick

    <!DOCTYPE html>
    
    <html lang="es">
    <head>
    <meta charset="UTF-8">
    <title>Ejemplo de onclick</title>
    <script>
        function saludar() {
        alert("¡Hola! Has hecho clic en el botón.");
        }
    </script>
    </head>
    <body>

    <button onclick="saludar()">Haz clic aquí</button>

    </body>
    </html>