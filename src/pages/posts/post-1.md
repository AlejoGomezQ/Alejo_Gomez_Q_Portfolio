---
layout: ../../layouts/BlogPostLayout.astro
title: "¡Angular explota con su nueva versión! La versión 18 del framework ya está disponible."
pubDate: 2024-06-28
description: "¡Angular v18 ha llegado para revolucionar el desarrollo web! Este robusto framework de Google optimiza el rendimiento y simplifica el trabajo del desarrollador con nuevas características como la detección de cambios sin ZoneJS, signals más estables, y mejoras en el renderizado del lado del servidor. Descubre todas las novedades y mejora tu experiencia con Angular."
author: "Alejo Gómez Q"
image:
  url: "/images/blog/logo-angular18.webp"
  alt: "Nueva version Angular."
tags: ["Angular", "Angular v18", "Google", "Angular Material", "Wiz"]
---

La espera ha terminado. Angular v18, unos de los frameworks de Google mas robustos para el desarrollo web ha llegado con toda. Su enfoque es claro en cuanto a optimización del rendimiento y su nueva versión llega con características que simplifican el trabajo del desarrollador.

## Zoneless – Change Detection

Como bien se sabe, **ZoneJS** ha sido el encargado de activar la detección de cambios en Angular. Cabe resaltar que siempre ha sido un dolor de cabeza para los desarrolladores trabajar con ello debido a la reducción del rendimiento y la experiencia de desarrollo. Esto se ve reflejado en que cada vez que realizas un cambio, la aplicación hace una especie de burbujeo sobre todo el árbol de componentes para ver si hubo cambios sobre toda la aplicación.

Ahora, Angular v18 introduce una nueva forma de activar la detección de cambios aunque aún se encuentra en una etapa experimental. Como ya no dependerá de ZoneJS para detectar los cambios en el árbol de componentes, Angular ahora tiene su propia detección de cambios. Es importante resaltar que esta nueva funcionalidad es opcional y el soporte para aplicaciones que aun sigan trabajando con ZoneJS se seguirá manteniendo.

Para habilitar esta nueva funcionalidad y trabajar tu proyecto de Angular con zoneless es:

## Estandarización de Signals

Como se ha venido trabajando desde Angular v17, pero ahora con una versión mas estable, los nuevos signals inputs, signals queries y la nueva sintaxis de input y output esta disponible.

Cada vez los signals se están volviendo mas populares en los diferentes frameworks y están facilitando el manejo de información . Un signal, es un tipo de dato que permite el flujo de datos de manera unidireccional mediante el modelado de celdas de estado y cálculos derivados de otros estados. Puedes profundizar más sobre signals y su estandarización en este interesante [blog post](https://eisenbergeffect.medium.com/a-tc39-proposal-for-signals-f0bedd37a335).

**new Signal.State()** sería el equivalente de **signal()** en Angular. **new Signal.Computed()** sería el equivalente de **computed()**. En cuando a **effect()**, no se tiene un equivalente en Angular como en todos los otros frameworks, de esta forma, este queda por fuera del alcance de la propuesta.

## @defer – Estable

Ahora la sintaxis y el uso de **@defer** es estable. Esta directiva permite definir un bloque de plantilla que se cargara de forma diferida cuando se cumpla cierto condicional. Al utilizar este bloque con carga diferida, mejorara altamente la carga inicial y mejorara el resultado de Core Web Vitals. En el siguiente enlace oficial de [**@defer**](https://angular.dev/guide/defer) puedes ampliar información acerca de esta poderosa directiva.

## Built-In control flow – Estable

Ahora en Angular v18 la sintaxis de Built-in control flow se puede usar de forma estable. Como recomendación del equipo de Angular, se debería considerar dentro del desarrollo de nuevas aplicaciones o puede migrar fácilmente utilizando los esquemas proporcionados de la siguiente forma:

## Angular Material v3 – Estable

Con la llegada de Angular v18 se tiene soporte estable para Angular Material, por lo que es seguro utilizar los nuevos features agregados en v3 en nuestros proyectos.

## Server-side rendering

Con la llegada de Angular v18, llegaron nuevas mejoras a las características de Server Side Rendering (SSR), vamos a nombrar algunas de ellas a continuación:
Repetición de eventos

Un par de meses atrás el Equipo de Angular anuncio la fusión que venía trabajando con el equipo de Google Wiz. Angular siempre se ha centrado en la productividad y la experiencia del desarrollador y Wiz se ha centrado en el rendimiento para el consumidor.

El resultado de esta fusión, Wiz integro signal en su modelo de renderizado. Ahora, el equipo de Angular, anuncio que YouTube usara signals para mejorar el rendimiento, además de incluir la hidratación parcial.

Con las mejoras en hidratación ahora es posible registrar las interacciones del usuario durante esta fase y ejecutarlas cuando la aplicación haya cargado por completo. Recordemos que este proceso es cuando el HTML renderizado por el servidor se transforma en una aplicación de angular completamente funcional.

### Depuración mejorada

Angular DevTools, las herramientas para el desarrollador propias de Angular, se ha actualizado para brindar una mejor visión durante el proceso de hidratación. Este proceso se puede observar junto al nuevo icono colocado al lado del nombre. Lo mejor de todo, es que, si tienes errores de hidratación, Angular DevTools te las mostrará en el explorador de componentes.

### Hidratación en CDK y Material

En esta nueva versión de Angular v18, todos los componentes y primitivas son compatibles con la hidratación.

### Hidratación parcial

El equipo de Angular hablo sobre esta técnica que es realizar el proceso de hidratación de forma incremental luego de haber terminado el renderizado del lado del servidor. Con esta nueva técnica, la carga inicial de JavaScript es menor y mejora el rendimiento de la aplicación.

### Firebase App Hosting

Este nuevo servicio busca simplificar al máximo la creación y publicación de aplicaciones web dinámicas, ofreciendo:

- Soporte nativo para aplicaciones Angular.
- CI / CD con GitHub.
- Conexión directa con otros servicios de Firebase.

## Nuevo paquete de construcción

Angular ha creado un nuevo paquete para hacer el **build** de la aplicación, el cual se conoce como **@angular/build**, centrado en herramientas modernas como esbuild y Vite, logrando un paquete más ligero y eficiente.

Anteriormente, todas las herramientas de construcción, incluyendo Webpack, estaban juntas en el mismo paquete **@angular-devkit/build-angular**. Ahora en Angular v18, tendrás la opción de migrar a este nuevo sistema, ajustando las dependencias en tu package.json.

## Redirección de rutas como funciones

Con Angular v18, la propiedad redirectTo de una ruta ahora es posible usarla con funciones, llamada **RedirectFunction**, la cual permite crear redirecciones dinámicas.
**RedirectFunction**, recibe información sobre la ruta actual, como parámetros o consultas, y en base a esto, decide a donde debe ser redirigido el usuario. Esta nueva funcionalidad trabaja de manera similar a las guardias y se ejecuta en el inyector de entorno.

## HttpClientModule – Obsoletos

Con la estandarización de los **Standalone Components**, en Angular v18, los módulos **HttpClientModule** (junto con HttpClientTestingModule, HttpClientXsrfModule, y HttpClientJsonpModule) han sido marcados como obsoletos. Esto no significa que ya no funcionen, pero sí que es hora de empezar a usar alternativas más modernas.

Ahora en la nueva versión se pueden utilizar las funciones **provideHttpClient()** y **provideHttpClientTesting()**. La incorporación de estas funciones ofrece una forma más directa y eficiente de configurar el cliente HTTP.

## Contenido alternativo para ng-content

Con la llegada de Angular v18, ahora se puede agregar contenido alternativo dentro de la etiqueta <ng-content>, el cual se mostrara si no se proyecta ningún contenido en el componente.

Con esta nueva actualización, sino se tiene un header en la aplicación, el que este señalado como por defecto será el que se mostrará.

## Nueva documentación oficial – angular.dev

El equipo de Angular ha anunciado que la nueva documentación oficial se encuentra en angular.dev. Puedes revisarla y ampliar tus conocimientos [aquí](https://angular.dev/)
Esta nueva versión de **Angular (v18)** ha llegado con muchas mejoras para hacer de el desarrollo web una experiencia mas eficiente y satisfactoria. Optimización en rendimiento y nuevas funcionalidades son los pilares de esta nueva llegada. ¡Atrévete a sumergirte en el mundo de Angular con su nueva versión mejorada, **Angular v18!**

Un gusto para mi que me hayas leído y espero que hayas disfrutado de este recorrido sobre **Angular v18**.
