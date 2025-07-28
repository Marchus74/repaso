***CLI

    Una herramienta CLI (Command Line Interface o Interfaz de Línea de Comandos) es un programa que permite interactuar con un sistema operativo o software escribiendo comandos en texto plano, en lugar de usar botones o menús gráficos como en una GUI (interfaz gráfica de usuario). Cuando ejecutamos powershell entramos en la terminal de windows que es una interface CLI

***NPM
    
    Node Package Manager  es el gestor de paquetes oficial para Node.js. Un package manager o gestor de paquetes es una herramienta que automatiza la instalación, actualización, configuración y eliminación de software en un sistema operativo o entorno de desarrollo.

        npm permite:

        - Instalar paquetes (librerías, herramientas, frameworks) para proyectos JavaScript.
        - Gestionar dependencias de manera eficiente mediante el archivo package.json.
        - Ejecutar scripts definidos en el proyecto (como pruebas, compilaciones, etc.)
 
***YARN

    Nosotros vamos a usar tambien yarn. Yarn es un gestor de paquetes para JavaScript, creado como una alternativa a npm, con el objetivo de mejorar la velocidad, seguridad y confiabilidad en la gestión de dependencias de proyectos.

        Características principales de Yarn
        
        - Rápido y eficiente: Usa instalación paralela y almacenamiento en caché para acelerar el proceso.
        - Seguro: Verifica la integridad de los paquetes mediante checksums.
        - Determinista: Siempre instala las mismas versiones gracias al archivo yarn.lock.
        - Compatible con npm: Usa el mismo registro de paquetes, por lo que puedes instalar paquetes de npm sin problemas.
        - Soporte offline: Puedes instalar paquetes sin conexión si ya fueron descargados antes.

***NPX

    npx es una herramienta incluida con npm (desde la versión 5.2.0) cuyo propósito principal es ejecutar paquetes de Node.js sin necesidad de instalarlos previamente.

    ¿Qué significa "npx"?
    Es el acrónimo de Node Package eXecute.

    🧩 ¿Para qué sirve?
    - 🏃‍♂️ Ejecutar paquetes directamente desde el registro de npm.
    - 🧪 Probar herramientas sin instalarlas globalmente.
    - 🧼 Evitar contaminar tu sistema con instalaciones innecesarias.
    - 📦 Ejecutar versiones específicas de paquetes.

    📋 Ejemplos de uso
    
        npx create-react-app mi-app

    Esto crea una app de React sin instalar create-react-app globalmente.

***Vite

    Vite es un build tool y servidor de desarrollo que permite crear aplicaciones web modernas con frameworks como React, Vue, Svelte, Preact, o incluso con JavaScript puro (vanilla). Está diseñado para ser rápido, modular y fácil de configurar.

        Características principales
    - 🚀 Inicio instantáneo: usa módulos ES nativos para evitar la compilación inicial completa.
    - 🔄 Hot Module Replacement (HMR): actualiza los cambios en tiempo real sin recargar la página.
    - 🧼 Build optimizado: usa Rollup para producción, con técnicas como code splitting y tree shaking.
    - 🧪 Soporte para TypeScript, JSX, CSS, Sass, etc. sin configuración adicional.
    - 🔌 Sistema de plugins: permite extender funcionalidades fácilmente.

    comandos para usar vite con yarn

        Crear el proyecto  " yarn create vite "
        Intalar las dependencias Yarn
        Inicializar el Servidor " yarn dev --host"

***Creando un proyecto con React + Vite , Tailwind CSS, ESLint y Prettier, usando Yarn

        yarn create vite mi-proyecto --template react
        cd mi-proyecto
        yarn install o yarn
        yarn add -D tailwindcss postcss autoprefixer
        
        Esto se usa solo para versiones anteriores a la 4 

                npx tailwindcss init -p

                Edita tailwind.config.js:
                    
                    export default {
                        content: ["./index.html", "./src/**/*.{js,jsx}"],
                        theme: {
                            extend: {},
                        },
                        plugins: [],
                    };
        
        En src/index.css, reemplaza todo con:

        @tailwind base;
        @tailwind components;
        @tailwind utilities;
        
        
        En la version actual (4) no es necesario el archivo tailwind.config.js

            solo en la version actual

                Crear el archivo postcss.config.js

                    export default {
                        plugins: {
                            '@tailwindcss/postcss': {},
                            autoprefixer: {},
                        },
                    };

        En src/index.css, reemplaza todo con:

        @import "tailwindcss";

        yarn add -D eslint prettier eslint-config-prettier eslint-plugin-react eslint-plugin-react-hooks


        Crea .eslintrc.js:

            module.exports = {
                env: {
                    browser: true,
                    es2021: true,
                },
                extends: [
                    "eslint:recommended",
                    "plugin:react/recommended",
                    "plugin:react-hooks/recommended",
                    "prettier",
                ],
                parserOptions: {
                    ecmaFeatures: {
                    jsx: true,
                    },
                    ecmaVersion: "latest",
                    sourceType: "module",
                },
                plugins: ["react"],
                rules: {
                    "react/react-in-jsx-scope": "off",
                },
                settings: {
                    react: {
                    version: "detect",
                    },
                },
            };

        Crea .prettierrc:
            {
                "semi": true,
                "singleQuote": true,
                "tabWidth": 2,
                "trailingComma": "all"
            }

 





