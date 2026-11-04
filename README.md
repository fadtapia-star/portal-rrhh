https://github.com/user-attachments/assets/660ab078-c79f-4d0d-8ec7-1f15f810edda

[Prompts.txt](https://github.com/user-attachments/files/34384729/Prompts.txt)
Registro de Prompts Utilizados en el Proceso
A continuación se documenta la secuencia cronológica de prompts utilizados durante las sesiones de trabajo para guiar la construcción, configuración y refactorización incremental del Portal RR.HH.:
Prompt de inicio
"Soy estudiante de un curso inicial de desarrollo web. Voy a construir 'Portal RR.HH.', una página con HTML, CSS y JavaScript que muestra datos de la base Oracle XE (esquema HR) a través de un servidor Node.js con Express y oracledb que ya tengo funcionando. Ayúdame paso a paso, con código simple, comentarios en español y una explicación corta de cada parte. No avances al siguiente paso hasta que yo te confirme que funcionó."
Navegación y estructura base (index.html)
"Crea un index.html con un menú de 5 enlaces que usen data-seccion y 5 secciones con class='seccion': Inicio, Departamentos, Equipo, Evaluador y Agenda. Usa esta función de navegación que ya tengo:
<nav id='menuPrincipal' class='navegacion'>
    <a href='#inicio' data-seccion='inicio'>Inicio</a>
    <a href='#noticias' data-seccion='noticias'>Noticias</a>
    <a href='#galeria' data-seccion='galeria'>Galería</a>
    <a href='#calendario' data-seccion='calendario'>Calendario</a>
    <a href='#actividades' data-seccion='actividades'>Actividades</a>
    <a href='#basedatos' data-seccion='basedatos'>Base de datos HR</a>
</nav>"
Estilos responsivos y menú móvil
"Dame estilos para una grilla de tarjetas de 3 columnas que pase a 1 columna en celular, y un menú que se abra con un botón ☰"
Lógica inicial del frontend (app.js)
"Crea el app.js, tiene que incluir:
1. Inicio: nombre del portal, un texto de bienvenida y un botón que lleva a Departamentos.
2. Departamentos: una tarjeta por departamento, creada con JavaScript desde /api/hr/departamentos, con su nombre y su cantidad de empleados.
3. Equipo: tabla de empleados desde /api/hr/empleados, con un buscador por nombre.
4. Evaluador de salario: el usuario elige un cargo y escribe un salario. La página responde con if / else si está bajo el rango, dentro del rango o sobre el rango del cargo. Necesita una ruta nueva en el servidor: /api/hr/cargos, que consulta la tabla JOBS (job_id, job_title, min_salary, max_salary).
5. Agenda RR.HH.: agregar actividades con fecha, guardarlas en localStorage y mostrarlas ordenadas por fecha."
Evaluador de salario y backend
"Evaluador de salario: el usuario elige un cargo y escribe un salario. La página responde con if / else si está bajo el rango, dentro del rango o sobre el rango del cargo.
Este es mi server.js: [pega el archivo]. Agrega una ruta /api/hr/cargos que consulte job_id, job_title, min_salary y max_salary de la tabla JOBS usando la función consulta."
Consumo de API con fetch
"Datos con fetch:
'La ruta /api/hr/departamentos devuelve esto: ... Escribe una función con fetch que cree una tarjeta por departamento y explica cada línea'"
Agenda RR.HH. con persistencia
"Agenda RR.HH.: agregar actividades con fecha, guardarlas en localStorage y mostrarlas ordenadas por fecha. Funciona y guarda o muestra los datos."
Enriquecimiento con JOIN (Departamentos y Ciudades)
"Mostrar en cada tarjeta de departamento la ciudad donde está (JOIN con LOCATIONS)."
Filtro combinado en Equipo
"Agregar un filtro por departamento en la tabla de Equipo."
Módulo interactivo Empleado del Mes
"Hacer seccion empleado del mes:
Empleado del mes: elegir una foto con FileReader, mostrarla con el nombre de un empleado y aplicar al menos un filtro (escala de grises o brillo)."
Ordenamiento interactivo de tablas
"Ordenar la tabla de Equipo al hacer clic en un encabezado."
