***Tipos de Datos

    Tipos de Datos
        Numericos (number): no distingue decimal 
        String: con comillas "texto" o  'texto', un solo caracter es string
        Booleaos (Boolean): puede ser false o true
        Array (tambien es Objeto): ["dato1","dato2","dato3","dato4"] cada dato puede ser de distinto tipo
            Los array tienen un valor y un identificador el valor es el datoX 
            y el identificador es su posicion en la lista. 
            (4) ['dato1', 'dato2', 'dato3', 'dato4']
            0:"dato1"
            1:"dato2"
            2:"dato3"
            3:"dato4"
            length:4
        Objetos: Tienen un identificador y un valor y su estructura es la siguiente
        {
            nombre: "Juan", 
            apellido: "Lopez"
        Tipo Nulo (NULL): un tipo de dato nulo
        No definido (undefined): inicializa una variable pero sin un dato
        }

    Datos Array y Objet son los dos de tipo objeto ¿cual es la diferencias?
        Depende del lenguaje en JS no se distingue la diferencia de tipo pero ambos
        cumplen roles distintos en la estructura y organización de los datos

    Datos curiosos, sabias que en algunos lenguajes los estring son arrays?
        ¿Que se necesita para ser un array?
            *acceder al elemento mediente su indice
            *poder modificarlos
        en JS no son array ya que no permite modificar sus datos, pero aun asi los string se pueden recorrer letra a letra mediante indice como un array
    
*** Operadores

    /**
    *  let numero = 25 (operador) 23
    * console.log(a)
    * let a=10
    * let b= 3
    * asignacion directa a+= b
    * a**b eleva al cubo
    */

    /**
    * El operador + esta sobrecargado y sirve como concatenacio (para unir dos variables)
    * let Nombre   = "Juan"
    * let Apellido = 'Lopez'
    * let ombreCompleto = nombre + "(espacio)" + apellido
    * otra forma de concatenar texto 
    *      let alias = `Mi nombre es ${nombre} y mi apellido es ${apellido}` (alt+96)
    *  
    */

    /**
    * operadores de comparacion 
    * hacer la comparacion por tipo numero y string
    *  a == b
    *  si eb vez de == pongo === ahora si compara valor y tipo
    * a === b
    * Para es diferente es !=
    * a != b
    * Para extrictamente igual es !==
    * a !== b
    * 
    */

    /**
    * Operadores Logicos
    * a >= b
    * 
    */

    /**
    * Operadores Logicos
    * AND (&&)
    * OR  (||)
    * 
    * let a = 10
    * let b = 20
    * let c = 30
    * 
    * let resp = (b > a ) && (b > c)
    * console.log (resp)
    */

    /**
    * Unarios y Ternarios
    * son los que se usan por ejemplo para incremento, decremento
    * 
    * a++ o a-- incremeta en 1 o decremeta en 1
    * 
    * Termario
    * let c = b > a ? "Es Verdadero!!!" : " Esto es Falso!!"
    */

    /**
    * Type coercion
    * es la capacidad que tiene el lenguaje para cambiar el tipo de dato
    * 
    * let a = 20
    * let b = 60 probar con string o como numero y usar (typeof)
    * 
    * let resp = a + b 
    * 
    * que pasa con true + true

    */

*** Estructuras de Control

    El condicional IF

    
    let nombre = "Carlos"
    let edad = "81"

    if (edad > 18 && edad < 80){
    console.log ( `El señor ${nombre} cumple las condiciones para sacar nuesta tarjeta de credito`)
    } else {
    console.log ( `El señor ${nombre} No cumple las condiciones para sacar nuesta tarjeta de credito`) //"`" no olvidar se llaman template
    }


    /**
    * Multialternativa
    * se pueden con if por ejemplo
    * si la persona tiene 18 años ofrecer trabajo
    * si tiene 25 ofrecer planes de invercion
    * si tiene 40 ofrecer planes medicos
    * cualquier otro caso no ofrecer nada  
    */

    if ( edad == 18) {
    console.log ( `El señor ${nombre} puede trabajar con nosotros`)
    } 
    else if ( edad == 25) {
    console.log ( `El señor ${nombre} puede invertir en nuestros activos`)
    }
    else if ( edad == 40) {
        console.log ( `El señor ${nombre} puede entrar en nuestro plan de salud`)
    } 
    else {
        console.log ( `El señor ${nombre} puede irse a tomar por culo` )
    }

    
    switch (edad) {
    case 18:
        console.log ( `El señor ${nombre} puede trabajar con nosotros`)
        break
    case 25:
        console.log ( `El señor ${nombre} puede invertir en nuestros activos`)
        break
    case 40: 
        console.log ( `El señor ${nombre} puede entrar en nuestro plan de salud`)
        break
    default:
    console.log ( `El señor ${nombre} puede irse a tomar por culo` )
    }
    console.log ( "******Fin del switch *******" )
    
    Recorridos 
   
    Recorridos usando For
    

        for (valor de inicio; condicion ; incremento) {

        }
    */

    for (let i= 0 ; i < 10 ; i ++) {
    console.log(i)
    }

    let clientes = ["Martin" , "Carlos", "Pedro"]

    for (let i = 0; i < clientes.length; i++) {
    console.log(clientes[i]);
    }
    
    
    Ciclo While
    

    let numerodeclientes = 10

    while (numerodeclientes > 0) {

    console.log (`Completar datos de cliente numero ${numerodeclientes-1}`)
    numerodeclientes--
    }


*** Funciones

    // Declaro la Funcion

        function nombreDeLaFuncion() {
            console.log ("Esto es una Funcion")
        }


    // invocar la funcion

        nombreDeLaFuncion()
    

    ¿ No nos falta algo en las funciones ?

        Nos falta el return, el return hace que la funcion retorne un valor y ese valor lo puedo usar en cualquier lado que necesite.  en el ejemplo anterior console.log se ejecuta dentro de la funcion, pero si en vez de eso uso return la sintaxis quedaria asi

    // Declaro la Funcion

        function nombreDeLaFuncion() {
            return ("Esto es una Funcion")
        }


    // invocar la funcion

        console.log (nombreDeLaFuncion())



    /**
    * FUNCIONES con CONSTANTES
    * como buena practica si voy a almacenar una funcion en una variable es mejor hacerlo en una
    * constante ya que mi funcion nunca debe cambiar y por eso JS permite usar las arrow function
    *   const nombreDeLaFunsion = (parametro) => `hola ${parametro}`
    */

    ejemplo:

        const salu2 = (nombre) => `hola ${nombre}, buenos dias`

        console.log (salu2 ("Juan Perez"))
    
    
    *** Arrays
        
        * Tambien llamadas listas (en GOBSTONE) o arreglos son colecciones de datos, 
        * en JS pueden tener distintos tipos
        * Se pueden crear vacias o con datos
        * los array son de tipo objetos en JS
        

        let arrayVacio= []
        let arrayConDatos= ["dato string", 325 , true, arrayVacio, {objeto}]

        Cosas que se puede hacer con los array

        🧰 Agregar y eliminar elementos
        - push() → agrega al final
        - pop() → elimina del final
        - unshift() → agrega al inicio
        - shift() → elimina del inicio
        - splice() → agrega, elimina o reemplaza en cualquier posición

        🔁 Recorrer y transformar
        - forEach() → ejecuta una función por cada elemento
        - map() → transforma cada elemento y devuelve un nuevo array
        - filter() → devuelve solo los elementos que cumplen una condición
        - reduce() → acumula valores en un solo resultado
        - flatMap() → combina map() + flat() en una sola pasada

        🔍 Buscar elementos
        - find() → devuelve el primer elemento que cumple una condición
        - findIndex() → devuelve el índice del primero que cumple
        - findLast() / findLastIndex() → versiones que buscan desde el final
        - indexOf() / lastIndexOf() → busca por valor
        - includes() → verifica si existe un valor

        📐 Ordenar y reorganizar
        - sort() → ordena los elementos
        - reverse() → invierte el orden
        - toSorted() / toReversed() → versiones que devuelven copias ordenadas/invertidas
        - toSpliced() → copia con elementos eliminados o reemplazados

        🧪 Transformar a otros formatos
        - join() → convierte el array en string
        - concat() → une arrays
        - slice() → copia una parte del array
        - flat() → aplana arrays anidados
        - fill() → rellena con un valor
        - from() → crea un array desde un iterable

        🧠 Validaciones y utilidades
        - some() → ¿al menos uno cumple la condición?
        - every() → ¿todos cumplen la condición?
        - isArray() → ¿es un array?
        - at() → accede por índice (incluye negativos)
        - length → cantidad de elementos

        🧬 Extras modernos
        - Desestructuración: const [a, b] = arr;
        - Spread operator: const copia = [...arr];
        - Comparación profunda: JSON.stringify(arr1) === JSON.stringify(arr2)




        agregar un dato a un array 

        // push "agraga un dato al final"
        
        //inicio array nombres Vacio

        let nombres = []
        
        // abrego elementos a mi array usando push
        
        nombres.push("Juan", "Pedro","Miguel","Carlos")
        
        //visualizo el array

        console.log(nombres)

        Lo mismo pero para quitar el ultimo

        //.pop "quita el ultimo dato"

        nombres.pop()
        console.log(nombres) 

        ¿y si quiero partir la lista en 2 sin modificar el array original?

        uso el metodo slice, su sintexis es la siguiente

            nombreDelArray.slice(0 (posicion de inicio), numero_del_elemento_anterior_que_quiero_cortar)

         ejemplo:

         const postres = ["tarta", "helado", "flan", "brownie", "gelatina"];

        const favoritos = postres.slice(1, 4);

        console.log(favoritos);     // ["helado", "flan", "brownie"]
          

        "Importante, este metodo no modifica el array original!!!!!"

        console.log(postres);       // ["tarta", "helado", "flan", "brownie", "gelatina"] 

        
        Recorriendo los Array

        Para recorrer se usa por ejemplo foreach su sintaxis es

            nombreDeLArray.forEach((elemento, indice) => {
            // Código a ejecutar
            // sumar 1 al indice
            });


        Con ForEach:

            const postres = ["tarta", "helado", "flan", "brownie", "gelatina"];

            postres.forEach((postre, indice) => {
                console.log(`Postre #${indice + 1}: ${postre}`);
            });
        
        con Map:

            sintaxis basica
            array.map((elemento, indice, array) => {
            // Código que transforma el elemento
            return nuevoValor;
            });


            const postres = ["tarta", "helado", "flan", "brownie", "gelatina"];

            const postresEnMayusculas = postres.map((postre, i) => {
            return `Postre #${i + 1}: ${postre.toUpperCase()}`;
            });

            console.log(postresEnMayusculas);

            Diferencias clave entre forEach() y map()
             
            | Retorno         |forEach() No devuelve nada (undefined)           | map() Devuelve un nuevo array transformado | 
            | Propósito       | forEach() Ejecutar una acción por cada elemento | map() Transformar cada elemento y crear otro array | 
            | Encadenamiento | forEach() No se puede encadenar | map() Sí, se puede  encadenar con filter(), reduce()... | 
            | Uso típico     | forEach() Logs, efectos secundarios, DOM updates | map() Formatear datos, cálculos, render dinámico | 
            | Modifica el original | No | No | 

             ¿Cuál usar?
            - Usá forEach() si solo querés hacer algo con cada elemento (como imprimir, actualizar el DOM, etc.).
            - Usá map() si querés transformar los datos y guardar el resultado.






            

        








************************************************************************************************


    comenzar por los datos, tipos y las variables y constante

    condicionales

    el if y  else if 
    el switch para multiples casos contra una variable
    el for para recorrer estructura vemos como recorrer un string

    let texto= "una Simple Frase"

    for (let i= 0; i < texto.length ; i++ ) {
        console.log (texto[i])

    }

    el ciclo while
    cuando usarlo?

Funciones


Cosas que se puede hacer con los array

🧰 Agregar y eliminar elementos
- push() → agrega al final
- pop() → elimina del final
- unshift() → agrega al inicio
- shift() → elimina del inicio
- splice() → agrega, elimina o reemplaza en cualquier posición

🔁 Recorrer y transformar
- forEach() → ejecuta una función por cada elemento
- map() → transforma cada elemento y devuelve un nuevo array
- filter() → devuelve solo los elementos que cumplen una condición
- reduce() → acumula valores en un solo resultado
- flatMap() → combina map() + flat() en una sola pasada

🔍 Buscar elementos
- find() → devuelve el primer elemento que cumple una condición
- findIndex() → devuelve el índice del primero que cumple
- findLast() / findLastIndex() → versiones que buscan desde el final
- indexOf() / lastIndexOf() → busca por valor
- includes() → verifica si existe un valor

📐 Ordenar y reorganizar
- sort() → ordena los elementos
- reverse() → invierte el orden
- toSorted() / toReversed() → versiones que devuelven copias ordenadas/invertidas
- toSpliced() → copia con elementos eliminados o reemplazados

🧪 Transformar a otros formatos
- join() → convierte el array en string
- concat() → une arrays
- slice() → copia una parte del array
- flat() → aplana arrays anidados
- fill() → rellena con un valor
- from() → crea un array desde un iterable

🧠 Validaciones y utilidades
- some() → ¿al menos uno cumple la condición?
- every() → ¿todos cumplen la condición?
- isArray() → ¿es un array?
- at() → accede por índice (incluye negativos)
- length → cantidad de elementos

🧬 Extras modernos
- Desestructuración: const [a, b] = arr;
- Spread operator: const copia = [...arr];
- Comparación profunda: JSON.stringify(arr1) === JSON.stringify(arr2)






