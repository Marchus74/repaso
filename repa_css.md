***Variables

        selector {
            --propiedad: valor          se usa para declarar la variable
        }

    h2 {
        color: var(--colorAzul);
        font-size: calc( var(--tamañoLetra) * 6);
    }

    Los selectores se dividen en los siguientes tipos:
            selectores simples          (una sola palabra)
            selectores compuesto        (mas de una palabra)
            Selectores con operadores   (+ > * )
            Selectores de atributos
            Selectores pseudoclases y pseudoelementos

    La cascada se puede romper con !important "pero no es buena practica"

***Layer

    Layer está diseñado para dar mayor control sobre cómo se combinan distintos estilos que vienen de múltiples fuentes: por ejemplo, estilos base, frameworks como Tailwind, o tus propios componentes personalizados. 

    Un layer te permite agrupar reglas CSS bajo un nombre, y luego controlar el orden de prioridad entre esas capas. Esto mejora la organización y facilita el manejo del cascade cuando estás usando muchas fuentes de estilos.

    @layer nombre {
    /* Tus reglas CSS */
    h1 {
        color: red;
    }
    }

    Se puede tener varias capas y definir el orden con:

    @import url('reset.css') layer(base);
    @import url('framework.css') layer(framework);
    @import url('custom.css') layer(custom);

    @layer base, framework, custom;

    Esto significa que:
    Las reglas en base tienen menor prioridad que las de framework,
    Y framework tiene menor prioridad que custom.

    Ejemplo:

    @layer tailwind {
    h1 {
        font-size: 2rem;
        color: blue;
    }
    }

    @layer personal {
    h1 {
        color: green;
    }
    }

    @layer tailwind, personal;

    Si se importa archivos CSS separados, se puede asignar una capa:

    css
    @import url('reset.css') layer(reset);
    @import url('tailwind.css') layer(tailwind);
    @import url('custom.css') layer(personal);

    Luego definís el orden de las capas con:
    css
    @layer reset, tailwind, personal;

***skeleton

    Estilos que se aplican durante la pantalla de carga, son implementadas para mejorar la experiencia de usuario

    Skeleton UI o Skeleton Loading
    Es una técnica que se utiliza para mostrar una representación “fantasma” o vacía del contenido mientras se carga, especialmente útil en SPA como React. En lugar de ver un spinner o una pantalla vacía, el usuario ve formas que imitan el layout final: por ejemplo, rectángulos grises donde irán textos o imágenes.

    Con Tailwind pse puede usar utilidades para crear el efecto:

    jsx
    <div className="bg-gray-300 animate-pulse rounded h-6 w-full" />
    Este animate-pulse genera un parpadeo suave que simula carga.

***Pseudoclases

    Una pseudoclase es una palabra clave que se agrega al selector precedida por dos puntos :. Indica que se debe aplicar un estilo solo cuando el elemento cumple cierta condición.

   
        -hover:     cuando paso el mouse por el elemento se aplica la propiedad declarada en la regla
        -targuet:       se aplica sobre el destion "href" del elemento 
        -not():         se aplica a los elementos que no cumplan con la condicion, not() recibe parametros
        -empty:         Se aplica solo en los elementos que estan vacios
    
    pseudoclases de formularios
    son las que se aplican en los formularios
        -required:      se aplica en los campos que son obligatorios
        -chequed:       se aplica cuando se da click en un check
        -focus:         se aplica cuando estoy sobre el campo
    
    pseudoclases respecto de posicion respecto de los hermanos
        -first-child    se aplica en el primero de los hermanos
        -last-child     se aplica en el ultimo
        first-of-type   se aplica al primero de su tipo
        last-of-type    se aplica al ultimo de su tipo  

    
    | :hover | Aplica estilo cuando el usuario pasa el cursor sobre el elemento. | 
    | :active | Aplica estilo cuando el elemento está activo (por ejemplo, mientras se hace clic). | 
    | :focus | Aplica estilo cuando el elemento está enfocado (por ejemplo, un campo de texto seleccionado). | 
    | :first-child | Selecciona el primer hijo dentro de su contenedor. | 
    | :last-child | Selecciona el último hijo. | 
    | :nth-child(n) | Selecciona el hijo número n. | 
    | :checked | Estiliza inputs tipo radio o checkbox que están seleccionados. | 
    | :disabled | Aplica estilos a elementos de formulario deshabilitados. | 


    button:hover {
    background-color: #607D8B; /* azul grisáceo */
    color: white;
    cursor: pointer;
    }


***Color

    Notación RGB (aditiva)
    Red 0-255
    Green 0-255
    Blue 0-255
    RGBA : (shorthand) 120, 50, 30, .5 (Canal Alfa, transparencia)
    Cuanto mas grande el numero mas se adiciona
*/

/* Notación hexadecimal 
    0 1 2 3 4 5 6 7 8 9 A B C D E F (256)
    0 1 2 3 4 5 6 7 8 9 A B C D E F (256)
    la notacion es: 
    #red green blue y si por ejemplo quiero un rojo puro #ff0000  si quiero un azul puro #00ff00
*/


/* Notación HSL 
    Hue (tono, de 0 a 360)
    Saturation (intensidad del color, de 0, gris a 100%, el color puro).
    Light (luz, de 0%, negro, a 100% que es blanco).
    de 0 a 120 rojos de 121 a 270 azules de 271 a 360 verdes
    Ojo aca el rojo puro es el valor mas chico
*/

body {
    background: hsl(0, 100%, 40%);
}

/* Degradados 

    background-image: linear-gradient(color1, color2, color3)
    background-image: radial-gradient(color1,color2,color3)
*/

***Flexbox

    | Propiedad | Descripción | 
    | flex-direction | Define la dirección del layout: row (horizontal), column (vertical). | 
    | justify-content | Controla la alineación horizontal: center, space-between, etc. | 
    | align-items | Alinea los elementos verticalmente: center, stretch, flex-start... | 
    | flex-wrap | Permite que los elementos se ajusten en múltiples líneas. | 
    | gap | Agrega espacio entre elementos. | 



        Propiedades clave de los ítems
    | Propiedad | Descripción | 
    | flex-grow | Indica cuánto puede crecer un elemento en relación a los demás. | 
    | flex-shrink | Indica cuánto puede reducirse. | 
    | flex-basis | Define el tamaño inicial antes de ajustarse. | 
    | align-self | Permite sobrescribir la alineación vertical solo para ese elemento. | 


    Ejemplo
    .container {
        display: flex;
        flex-direction: row;
        justify-content: space-between;
        align-items: center;
        gap: 1rem;
    }

    en tailwind

    <div class="flex flex-row justify-between items-center gap-4">
        <div>Elemento 1</div>
        <div>Elemento 2</div>
        <div>Elemento 3</div>
    </div>

***Grid

    | Propiedad | Función | 
    | display: grid | Activa el sistema de cuadrícula | 
    | grid-template-columns | Define cuántas columnas y su ancho | 
    | grid-template-rows | Define las filas y su alto | 
    | gap | Espacio entre filas y columnas | 
    | grid-template-areas | Asigna nombres a zonas del grid | 


    Ejemplo clásico de Grid
    .container {
        display: grid;
        grid-template-columns: 1fr 2fr;
        grid-template-rows: auto auto;
        gap: 1rem;
    }


    <div class="container">
        <div>Columna 1</div>
        <div>Columna 2</div>
        <div>Fila 2, Col 1</div>
        <div>Fila 2, Col 2</div>
    </div>


    Esto crea un layout con 2 columnas: la primera ocupa 1fr (una fracción) y la segunda 2fr, lo que significa que es el doble de ancha. Las filas se ajustan automáticamente (auto).
   
    EN Tailwind

    <div class="grid grid-cols-2 gap-4">
        <div class="bg-blue-200 p-4">Columna 1</div>
        <div class="bg-blue-300 p-4">Columna 2</div>
        <div class="bg-blue-200 p-4">Fila 2, Col 1</div>
        <div class="bg-blue-300 p-4">Fila 2, Col 2</div>
    </div>