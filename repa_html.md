***Repaso de Html una modificacion

Tipos de elementos (etiquetas) de html
    *Elementos de seccion
        nav, aside, div
    *Elementos de agrupacion
        fugure, main, div
    *Elementos de Titulo
        h1, h2, h3, hgroup
    *Elementos de Texto
        p, ul, li
    *Elementos de Incrustados
        img, video, audio
    *Elementos de Interactivos
        details
    *Elementos de Tablas
        table, td, th
    *Elementos de Formularios
        form, imput, buton
    *Elementos de Metadata
        charset, name

    ***Ejemplo de insercion de un JS directamente en html 

    <script> 
        
        function enviarWhatsApp() {
            
            var nombre = document.getElementById("nombre").value; 
            var mensaje = document.getElementById("mensaje").value; 
            var texto = "Nombre: " + nombre + "%0A" + "Mensaje: " + mensaje; 
            var numero = "5491163024688";// Reemplaza con el número de WhatsApp al que deseas enviar el mensaje 
            var url = "https://wa.me/" + numero + "?text=" + texto; 
            window.open(url, "_blank");
        } 
    
    </script>

    ***Algunos etiquetas de bloques

    ARTICLE
        Separa contenido por articulos donde cada elemento es distinto de otro
    SECTION
        Se usa para dividir pero entre elementos del mismo dominio cada seccion deberia tener por 
        buena practica tener un encabezado
    NAV
        Es una etiqueta para agragar navegacion (indice de un libro) pueden ser distintas paginas
        linkeadas en el nav. 
    ASIDE
        Es una etiqueta de agrupacion pero se usa para contenido secundario, puede servir para publicidad
        puede para algun detalle que tiene relacion con el contenido pero que no es parte, seria como
        cuando uno usa el entre parentesis en un texto.

***ELEMENTOS DE BLOQUE
    
    Los elementos de bloques reservan un gran bloque donde todo lo que se ingresa queda una la lado del otro
        
    ENCABEZADOS: H1....H6
    Párrafos: P
    Elementos de Seccion:
    Blockquope 
    Pre
    Div No es una etique senantica, se usa mas que nada para ayuda de diseños en CSS.

*** ELEMENTOS DE LINEA
    EM:         Para dar enfacis a un titulo o texto lo pone en cursiva
    STRONG:     Pone el texto en negrita
    TIME:       Para agrega una fecha
    KBD:        teclas del teclado (ejemplo abajo)
    SUB y SUP   sub indice o supindice
    DEL         lo que se escribe queda tachado

    Etiqueta de linea No semanticas
    SPAN        Se usan para CSS
    B           negritas
    U           subrayado
    I           Cursiva

***Enlaces

Se crean con la etiqueta ancla

    <a href="destino del enlace">contenido del enlace </a>

alguno de sus atributos son

        El atributo targer="_blank"  para que un enlace se abra en una nueva pestaña
        <a href="sucursales" target="_blank"> sucursales</a>
        El atributo rel="nofollow"
        rel="nofollow" evita que google siga el enlace
        El atributo download  se usa para que un enlace <a> descargue un archivo directamente, en lugar de abrirlo en el navegador. Es especialmente útil cuando querés ofrecer archivos como PDFs, imágenes o documentos para que el usuario los guarde en su dispositivo
 
        <a href="archivo.pdf" download>Descargar PDF</a>


ejemplo de navegar un doc extenso en html utilizando anclas con el atributo "id=xxxxx"

<section id="indice"><!-- recordar lo de la i mayuscula -->
    <h2> Indice </h2>
    <a href="#Cap1">Capitulo 1</a>
    <br> <!-- Salta de linea -->
    <a href="#Cap2">Capitulo 2</a>
    <br>
    <a href="#Cap3">Capitulo 3</a>
    <br>
    <a href="#Cap4">Capitulo 4</a>
</section>

<section id="Cap1">
    <h2> Capitulo 1 </h2>
    <a href="#indice"><p>Ir al indice</p></a>
<p>
    El North American P-51 Mustang fue un caza y caza de escolta monomotor estadounidense de largo alcance, utilizado por....
</p>
</section>


***Crear listas en html

        Las listas son distintos tipos de listas como los dias de la semana, las tareas pendientes, la lista de compras
        Hay dos tipos de listas
        1* listas Ordenadas con etiquetas <ol></ol> usan numeros o letras
        2* listas no Ordenadas o de viñetas <ul></ul> usan Viñetas

        cada item en cada una de las listas se identifican por la etiqueta <li></li>

        ol-> Ordered List
        ul-> Unordered List
        li-> List item

otro tipo de listas poco frecuentes

    Las listas de definicion son poco usadas, su funcion principal es definir un termino, 
    seria una palabra y su explicacion y utilizan las siguientes etiquetas

            dl -> definition list
            dt -> definition term
            dd -> definition description
    Ejemplo 
    
    <dl>
        <dt>HTML</dt>
        <dd>Hypertext Markup Language</dd>
        <dt>Etiqueta</dt>
        <dd>Son los nombres de los elementos de HTML</dd>
    </dl>

***Imagenes

    las imagenes en html se incorporan con la etiqueta img
    
    <img src="ruta de la imagen" alt="descripcion de la imagen">
    
    <img src="https://images-na.ssl-images-amazon.com/images/I/71W80exqmNL._AC_SL1500_.jpg" 
    alt="Es una guitarra fender stratocaste de color negro con pickguard color blanco" width="100" >

    La etiqueta picture nos permite agragar varias imagenes, que por ejemplo pueden ser iguales, pero con distinto
        tipo de archivo, esto permite que el navegador cargue la que tiene un formato compatible.
    
        <picture>
            <source srcset="guitarra.jpg">
            <source srcset="guitarra.png">
            <img src="guitarra.svg" alt="">
        </picture>

    la etiqueta figure permite colocar una descripcion bajo  una imagen y su sintaxis es 
    
    <figure>
        <figcaption>
            
        </figcaption>
    </figure>
    Donde figcaption es el texto que quiero agregar a la imagen
  

    <figure>
        <img src="guitarra.jpg" alt="" width="100"> 
        <figcaption style="font-size: 8px;">
         Fender Stratocaste Mod 63 Standar 
        </figcaption>
    </figure>

***Insertar Video en html

    Para insertar un Video en nuestra pagina web utilizamos la etiqueta video. ejemplo
    <video src="Ruta al Video"></video>
    al video se le puede agragar el atributo control para que nos muestre los controles
    tambien se puede usar el atributo "poster" que le agrega una caratula a nuestro video
    Con Audio es igual que en video
    Es mejor usar enlace a youtube o plataforma similar
    con source permite incluir varios formatos para mayor compatibilidad.

    ejemplo 

        <video width="640" height="360" controls poster="imagen-previa.jpg">
        <source src="video.mp4" type="video/mp4">
        <source src="video.webm" type="video/webm">
        
    </video>

***Tablas

    las tablas se crean con la etiqueta table <table></table> 

    - <table>: define la tabla.
    - border="1": agrega un borde visible.
    - <caption>: título de la tabla.
    - <tr>: define cada fila.
    - <th>: celda de encabezado (negrita y centrada por defecto).
    - <td>: celda de datos.
    -los atributos colspan=n unifica celdas de una columna, "n" es la cantidad de celdas que voy a unificar
    -rowspan=n   unifica celdas de una fila
    
    ejemplo:
        <td colspan="3"></td>
        <td> un valor</td>
    
    -con la etiqueta colgroup se puede crear las columnas para poder aplicarle por ejemplo estilos, la etiqueta se usa junto a la etiqueta col, que se coloca en coincidencia con la cantidad de columnas. 
    
    ejemplo

    <colgroup>
        <col> <!-- tambien es puede  usar span="n" para evitar poner varias veces col-->
        <col>
    </colgroup>


<table border="1">
  <caption>Horario de clases</caption>
  <tr>
    <th>Día</th>
    <th>Materia</th>
    <th>Hora</th>
  </tr>
  <tr>
    <td>Lunes</td>
    <td>Matemática</td>
    <td>08:00 - 09:30</td>
  </tr>
  <tr>
    <td>Martes</td>
    <td>Historia</td>
    <td>10:00 - 11:30</td>
  </tr>
  <tr>
    <td>Miércoles</td>
    <td>Biología</td>
    <td>13:00 - 14:30</td>
  </tr>
</table>

***Formularios 

    La etiqueta Form es la que enmarca los formularios, los formularios son fundamentales para poder capturar
    datos de los usuarios. Form tiene un atributo "ACTION" el cual recibe la ruta
    donde se va a guardar los datos del formulario.
    La etiqueta input sirve para agregar un campo donde el usuario  deja algun dato, el atributo type:="text" 
    se puede quitar, sirve para indicar el tipo de dato que se espera
    La etiqueta button sirve para crear un boton
    el atributo place holder sirve para indicar que dato se debe escribir
    -->
    <form action="resultado.html">
        <input placeholder="Nombre">
        <br>
        <input type="number" placeholder="Edad" >
        <button>Enviar</button>

    </form>

    el atributo placeholder no es bueno para trabajar las indicaciones en un campo de datos
        Para eso es mejor usar la etiqueta LABEL el atributo for:= del label permite conetar con el ID de campo
        al cual esta conectado, recordar ids. en ingles 
        El atributo value:= se usa para ingresar un valor predeterminado
        Los datos de pueden enviar de dos formas
        1 con la etiquete BUTTON
        2 con la etiqueta INPUT y en el atributo type:= se coloca el tipo submit, tambien se usa value para indicar el nombre del boton
        La etiqueta FIELDSET sirve para agrupar campos, dentro de fieldset se coloca la etiqueta LEGEND que sirve
        para poner un titulo al campo los imput necesitan  un atributo "name" para identificar el campo

    Ejemplo:
    
    <form action="recibirform.html">
        <fieldset>
            <legend>Datos De Usuario</legend>
            <label for="name">Nombre</label>
            <input placeholder="Nombre" id="name" value="Marcelo" name="nombres">
            <br>
            <label > Edad <input type="number" placeholder="Edad" id="age">  </label>
            <br>
            <button>Enviar</button>
            <br>
            <input type="submit" value="Ingresar">
        </fieldset>
        

    </form>

    Los tipos de Input
    
    El tipo mas usado dentro del type:= es Type que sirve para datos de tipo texto pero tambien sirve para numeros
    el type "number" sirve para numero
    el type tipo "date" sirve para fechas
    el type "email" sirve para ingresar mail 
    el type "tel"   sirve para telefono
    el type "color" sirve para seleccionar color
    el type "password" sirve para contrase├▒as y quedan ocultas pero sin sifrado
    el type "range" coloca un deslizador puede usar atributos min="" max:="" step=""
    
        <form  action="recibirform.php" method="post">
            <fieldset>
                <legend>Datos De Usuario</legend>
                <label for="name">Nombre</label>
                <input placeholder="Nombre" id="name" value="Marcelo">
                <br>
                <label > Edad <input type="number" >  </label>
                <br>
                <label > Fecha <input type="date" >  </label>
                <br>
                <label > Pass <input type="password" >  </label>
                <br>
                <button>Enviar</button>
                <br>
                <input type="submit" value="Ingresar">
            </fieldset>

    Checkbox es un tipo de campo que permite al ususario seleccionar alguna o todas las opciones disponibles de una lista 
        
        Ejemplo

            <fieldset>
                <legend> Que musica te gusta</legend>
                <label>
                    Metal
                <input type="checkbox">
                </label>
                <br>
                <label>
                    Rock
                <input type="checkbox">
                </label>
                <br>
                <label>
                    Pop
                <input type="checkbox">
                </label>
            </fieldset>

        
    el atributo radio solo permite seleccionar solo un valor pero para eso el identificador name de los campos deben
    ser el mismo
        
        ejemplo 
            
            <form action="recibirform.html">
                <fieldset>
                    <legend> Que musica te gusta</legend>
                    <label>
                        Metal
                    <input type="radio" name="musica">
                    </label>
                    <br>
                    <label>
                        Rock
                    <input type="radio" name="musica">
                    </label>
                    <br>
                    <label>
                        Pop
                    <input type="radio" name="musica">
                    </label>
                </fieldset>
        
        
        
        <select name="paises" id="">
            <optgroup label="Sud America">
            <option value="pe">Peru</option>
            <option value="br">Brasil</option>
            <option value="ch">Chile</option>
            </optgroup>
        </select>
        <br>
        <textarea name="" id="comment" cols="30" rows="10"></textarea>


    </form>
        
        otros atributos de input si quiero que una opcion este seleccionada por defecto puede usar el atributo checked 
        con el atributo required se fuerza al usuario a ingresar un dato para el envio Selec se utiliza para la etiqueta option de optgrup
        readonly para solo lectura autocomplete para la etiqueta form
        
    </body>
    </html>