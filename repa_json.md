***Objetos en JS
    Que es un objeto en POO
    🧠 En PPO, un objeto es una unidad que combina datos y funciones en un solo conjunto el cual nos permite representar de forma abastractas cosas (entes) de la vida real.

    como es su sintaxis en JS

    {
    nombre: "Lucía",
    edad: 30
    };

    Esto es un objeto literal solo con 2 atributos y sin metodos, lo importante es que es basicamente un valor!!! un valor de tipo objeto y que lo puedo asignar a una variable o una constante

    const persona = {
    nombre: "Lucía",
    edad: 30
    };

    En los array podia acceder a los valores contenidos mediante el indice (entre otros metodos) en Objetos puedo acceder a los atributos mediante el nombre de la variable que lo contiene el caracter "." y el nombre de la propiedad que quiero acceder por ejemplo persona.edad me devolvera 30 en el ejemplo anterior.

    pero los objetos pueden ademas de almacenar valores, hacer cosas mediante funciones internas, las cuales llamaremos en adelante METODOS.

    ***Metodos

    Como es la sintaxis de un metodo?

    const persona = {
    nombre: "Lucía",
    edad: 30,
    
    // METODO
    
    presentarce: function() {
        console.log(`Hola, soy ${this.nombre}, tengo ${this.edad} años `);
        }
    };

    Veamos el ejemplo anterior
    "presentarce" parece por sintaxis una propiedad como cualquier otra, pero despues de los ":" en vez de tener algun valor, recibe una funcion, esta es el metodo.
    Y como accedo a ella? 
    mediante la misma sintaxis que las propiedades, es decir  "persona.presentarce"
    es de notar en este ejemplo la palabra clave "This"  se usa para referenciar el valor de un atributo interno del objeto, por ejemplo this.edad me devuelve el valor 30.

    JS tiene Metos integrados de los cuales vimos algunos en la reunion anterior, cuando hablamos de arrays, estos eran
    push (), pop(), toUpperCase() entre otros. 
    Pero ahora veremos 3 que son importanticimos en POO

    METODO CONSTRUCTOR

    Este metodo permite crear multiples objeto, a partir de una estructura llamada clase esta es su sintaxis

    // Se crea la clase persona
    class Persona {
    constructor(nombre, edad) {
        this.nombre = nombre;
        this.edad = edad;
    }

    presentarse() {
        console.log(`Hola, soy ${this.nombre} y tengo ${this.edad}años.`);
        }
    }

    Veamos este codigo
    
    inicia con la palabra reservada class, para indicar que se trata de una clase, luego viene el nombre el cual debe estar en mayuscula y en singular. Luego vendra un cuerpo { } el cual contendra el metodo constructor, este recibe como parametros los valores a asignar a las propiedades, perooo..... observar que la asignacion en este caso no es como en los objetos literales
    donde edad:30 en este caso la asignacion se hace usando el operador "=" en las clases de JS no se puede usar la misma sintaxis que en los objetos literales para los atributos.

    para crear un nuevo objeto literal (instanciar) desde una clase se usa la siguiente sintaxis

    const paola = new Persona ("Paola", 30);

    y si quiero ahora que paola se presente hago lo siguiente 

    paola.presentarse(); 

    igual que haciamos en los metodos y atributos anteriores 

    ***Getter and Setter

    metodos:
    GET -> Obtener Info
    SET -> Dar Info

    son junto a constructor los metodos mas importantes en JS para la POO, se usan para acceder a las propiedades de un objeto, obteniendo o modificando su valor y se usan en JavaScript (y otros lenguajes orientados a objetos) para darle mayor control y flexibilidad al acceso de las propiedades de un objeto, evitando acceder directamente a las propiedades.
    Por que no querer acceder directamente a las propiedades?

    - proteger datos internos que no deberían modificarse sin control.
    - separar cómo se accede de cómo se almacena.
    - Se puede cambiar la lógica interna más adelante sin modificar la interfaz de uso.

    veamos un ejemplo de la sintaxis usando la clase persona



    class Persona {
    
    constructor(nombre, edad) {
        this.nombre = nombre;
        this.edad = edad;
        }

    getNombre() {
        return this.nombre
        }

    getEdad() {
        return this.edad
        }

    setNombre(nuevoNombre) {
        this.nombre = nuevoNombre
        }

    setEdad(nuevaEdad) {
        this.edad = nuevaEdad
        }

    presentarse() {
        console.log(`Hola, soy ${this.nombre} y tengo ${this.edad}años.`);
        }
    
    }

creamo el objeto paola de 30 años

const paola = new Persona("Paola", 30);

ahora le cambiamos la edad a paola por 25

paola.setEdad() = 25

ahora pidamos la edad de paola

console.log ('${paola.getEdad}')

***Herencia

si ahora me interesa crea una nueva clase que sea Cliente o Vendedor podria usar la estructura creada en la clase Persona y extenderla con las propiedades que sea necesario para eso procedo de la siguiente forma.



creo la clase cliente y lo extiendo desde la clase usuario

    class Cliente extends Persona {
            
        constructor(nombre, edad, tarjeta) {
            
        }
    }

    en este caso se agrego el parametro tarjeta
    pero los atributos nombre y edad no son de Cliente, son de Persona, para poder usarlos lo hago de la siguiente forma

    class Cliente extends Persona {
            
        constructor(nombre, edad, tarjeta) {
            super (nombre,edad)
            // y uso el this para la prop nueva
            this.tarjeta= tarjeta    
        }
    }

    ahora creemos un Vendedor extendiendo persona

    class Vendedor extends Persona {
            
        constructor(nombre, edad, legajo) {
            super (nombre,edad)
            // y uso el this para la prop nueva
            this.legajo= legajo    
        }
    }