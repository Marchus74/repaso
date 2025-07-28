En la reunion pasada vimos como modificar el DOM usando JS vainilla, el uso de este metodo es bastante pesado, se imaginan por ejemplo hacer el codigo de un header sencillo mediante este metodo? pongamos por caso el header de la pizza del comisario

En HTML seria 

<header class="header">
        <div class="content-logo"><img  src="/Img/logo iso.jpg" alt="" class="content-logo"><a href="/" class="home"></a></div>
        <nav class="main-menu">
            <ul class="main-menu_ul">
                <li class="ul_li">
                    <a href="/" class="li_a">Inicio</a></li>
                <li class="ul_li">
                    <a href="menu.html" class="li_a">Menú</a></li>
                <li class="ul_li">
                    <a href="menuReact.html" class="li_a">MenúR</a></li>    
                <li class="ul_li">
                    <a href="/sucursale.html" class="li_a">Sucursales</a></li>
                <li class="ul_li"><a href="/pedidos.html" class="li_a-red">PEDIDOS</a></li>
            </ul>
        </nav>
</header>

Si lo pasamos a JS quedaria asi

// Crear elementos
const header = document.createElement('header');
header.className = 'header';

const contentLogo = document.createElement('div');
contentLogo.className = 'content-logo';

const logoImg = document.createElement('img');
logoImg.src = '/Img/logo iso.jpg';
logoImg.alt = '';
logoImg.className = 'content-logo';

const homeLink = document.createElement('a');
homeLink.href = '/';
homeLink.className = 'home';

contentLogo.appendChild(logoImg);
contentLogo.appendChild(homeLink);

// Menú
const nav = document.createElement('nav');
nav.className = 'main-menu';

const ul = document.createElement('ul');
ul.className = 'main-menu_ul';

const menuItems = [
  { href: '/', text: 'Inicio', class: 'li_a' },
  { href: 'menu.html', text: 'Menú', class: 'li_a' },
  { href: 'menuReact.html', text: 'MenúR', class: 'li_a' },
  { href: '/sucursale.html', text: 'Sucursales', class: 'li_a' },
  { href: '/pedidos.html', text: 'PEDIDOS', class: 'li_a-red' },
];

menuItems.forEach(item => {
  const li = document.createElement('li');
  li.className = 'ul_li';

  const a = document.createElement('a');
  a.href = item.href;
  a.textContent = item.text;
  a.className = item.class;

  li.appendChild(a);
  ul.appendChild(li);
});

nav.appendChild(ul);

// Ensamblar el header
header.appendChild(contentLogo);
header.appendChild(nav);

// Insertar en el documento
document.body.prepend(header); // o document.querySelector('main').prepend(header);

ademas de eso hay que tener en cuenta que cada etiqueta puede presentar varios atributos lo cuales tambien hay que pasar a JS por ejemplo la etiqueta IMG tiene todos estos atributos

- src: Ruta o URL de la imagen.
- alt: Texto alternativo cuando no se carga la imagen.
- width: Ancho (px o %).
- height: Alto (px o %).
- loading: Estrategia de carga (ej. "lazy").
- decoding: Método de decodificación ("async", "sync" o "auto").
- crossorigin: Política CORS ("anonymous" o "use-credentials").
- referrerpolicy: Controla qué info se envía como referencia ("no-referrer", "origin"...).
- usemap: Enlaza la imagen a un <map> interactivo.
- ismap: Indica que la imagen es parte de un mapa de imagen dentro de un <a>.
- title: Texto tipo "tooltip" al pasar el cursor.
- class: Para estilizar con CSS.
- id: Identificador único del elemento.
- style: Estilos en línea.
- name (obsoleto): Ya no se usa.

y eso en una sola etiqueta!!!!!

y si creamos una funcion que permita crear una etiqueta de forma dinamica ??
Vamos a crear un HEADER

function createElement (elemento, atributos = {} , hijos [] ) {
    const elem = documente.createElement (elemento);
    let keys = Object.keys (atributos); // si no entienden que paso aca pregunten!!
    keys.map (k => elem. serAtribute (k, atributos (k))); 

    retun elem   
}

ahora paso el elemento al dom mediante una nueva funcion

function render (contenido, elementoRaiz) {
    let elemRaiz = documente.getElementById (elementoRaiz); // aca  root sera el body
    elemRaiz.appendChild (contenido)
}

//Utilizo la funcion

//lo guardo
const Header = createElement ("header", {"id": "mainHeader", "class": "main-header header"})

//lo utilizo

render (Header, "root") //recoradar agregar el id a body

Esto sin mas es una libreria JS, eso si para que sea una libreria le falta algunas cositas, primero pasarlo a un archivo distinto que podria llamarse  libreria_JS.js
luedo hay que agregar algunas lineas ya que tengo que exportarla y luego importarla



export function createElement (elemento, atributos = {} , hijos = [] ) {
    const elem = documente.createElement (elemento);
    let keys = Object.keys (atributos); // si no entienden que paso aca pregunten!!
    keys.map (k => elem. serAtribute (k, atributos (k))); 

    hijos.map ( h => {
        if (typeof h === "string") {
            elem.innerHTML += h;
            return;
        }
        elem.appendChild (h);
    })

    retun elem   
}

export function render (contenido, elementoRaiz) {
    let elemRaiz = documente.getElementById (elementoRaiz); // aca  root sera el body
    elemRaiz.appendChild (contenido)
}

y en el archivo scrit.js que es donde la voy a utilizar la importo

    import {createElement, render} from "./libreria_JS.js"

    // ahora si la puedo usar

    const Header = createElement ("header", {"id": "mainHeader", "class": "main-header header"});

    render (Header, "root");

Prueben el codigo!!!!!

Asi Fue como comenzo en facebook, REACT!!!

EL Fundamento de lo .JSX

la idea de react fue crear un elemento JS pero con la sintaxis de HTML, eso si con algunas sutiles diferencias entre HTML y JSX

la sintaxis basica de un elemento JSX es la siguiente 


        const MiComponente = ({ nombre }) => {
            return (
                <>
                <h1>Hola, {nombre} 👋</h1>
                </>
            );
        };

Notar que ya no hablamos de elementos, ahora un elemento, por ejemplo Header se llama "COMPONENTE"  

REACORDAR que en JSX no admite mas de un Padre asi que debemos usar fragment 

Bueno, ya terminamos aca, ahora nos vamos a otra carpeta donde crearemos un proyecto React, Bye!!!!

