# CI/CD DevOps

## Antes de CI/CD

1. Equipo de desarrollo de software
2. Git
3. Compilacion
4. Empaquetado
5. Equipo de operaciones
6. Entorno de prueba
7. Equipo de garantia de calidad
8. Sitio web publico

### Iteracion

Repeticion del ciclo desde la fase de desarrollo de software hasta la fase de lanzamiento al produccion (Sitio web publico).

### Puntos debiles antes de CI/CD DevOps

- La integracion es un proceso manual que requiere mucho tiempo y esfuerzo.
- Solucion de problemas al final de cada iteracion.
- Problemas de fusion intermedia puede detener los equipos de desarrollo involucrados.
- Largo ciclo de feedback para los defectos funcionales.
- Iteraciones largas por efecto acumulativo de todos los problemas anteriores.

### Integracion continua

Sucede de forma automatizada. Cuando alguien hace un commit en la rama principal, el paquete de lanzamiento se prepara en minutos.

1. Requiere que los desarrolladores integren el codigo a un repositorio central compartido varias veces al dia.
2. Los desarrolladores realizaran commits de forma regular. Se utiliza un servidor de compilacion.
3. La compilacion debe activarse cada vez que un desarrollador realice un commit.
4. La construccion (codigo + pruebas) debe compilar el codigo y ejecutar de forma automatica las pruebas.
5. En el caso de una contruccion fallida, el desarrollador sera notificado y tendra la posibilidad de conocer el error en la compilacion antes de la realizacion de un merge.
6. La construccion debe incluir pruebas automaticas que aseguren la calidad del codigo.

### Integracion continua vs integracion tradicional

1. Integracion automatizada y rapida.
2. Problemas reportados a tiempo por iteracion frecuente (Anteriormente los problemas solo eran reportados al final de cada iteracion).
3. Problemas con prioridad de arreglo para desarrolladores (Anteriormente los problemas de fusion intermedia detenian a los equipos de trabajo).
4. Ciclos de feedback mas cortos, notificaciones inmediatas.
5. Iteracion mas corta, tiempo de comercializacion mas rapido.

## Pipelines

### Build pipeline

Permite optimizar el proceso cuando multiples builds estan en fila.

> Git(branch) -> Compilacion -> Empaquetado -> Pruebas unitarias automatizadas -> Pruebas de interfaz de usuario automatizadas

Durante el proceso de integracion continua, cuando un desarrollador realiza un commit y push a la rama del repositorio, se activa el proceso de compilacion; un segundo desarrollador puede realizar el mismo proceso y no necesita esperar a que el commit del primer desarrollador complete todas las intstancias, de una vez ingresara al proceso del `build pipeline`.

## Antes de DevOps

1. Equipo de operaciones
    - Recibia el empaquetado de instrucciones
    - Se prepara el entorno de prueba de acuerdo a las instrucciones

## Llegada de la entrega continua

La entrega continua es una practica de desarrollo de software, en donde el software PUEDE  lanzarse a produccion en cualquier momento (Se mantiene un estado desde el cual se puede hacer un deploy a produccion siempre, este lanzamiento no se realiza automaticamente).

### Objetivo

El software siempre debe estar listo para su paso a produccion.

### Requisitos

El codigo debe estar almacenado en un mismo repositorio en donde se compila y construye de forma automatica al menos una vez al dia.

#### Release pipeline o pipeline de lanzamiento

Las instrucciones de instalacion son proporcionadas mediante scripts en un archivo ya sea shell (unix), powershell (windows). Dicho archivo podra ser llamado durante la preparacion del entorno, de esta manera las instrucciones son ejecutadas de forma automatica sin ningun tipo de intervencion manual.

## Puntos debiles (operaciones tradicionales vs entrega continua)

### Operaciones tradicionales

- No se garantiza la exactitud de las instruccion
- Diferencias de instalacion para diferentes entornos
- Naturales propensa a errores por tareas manuales

### Entrega continua

- Las instrucciones se convierten en scripts automatizados
- El proceso de lanzamiento se hace mas corto