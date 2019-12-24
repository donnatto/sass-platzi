# Curso de Sass

## Preprocesadores

Los mas comunes son Sass, Less y Stylus.

- Less es muy simple para proyectos pequeños. Compactos y rapido
- Sass tiene gran soporte por la comunidad
- Stylus es muy completo

Sass es para desarrollo. No se va a subir. Se utiliza un compilador para convertirlo a css

## Variables

Elementos que podemos definir y asignarle un valor especifico.

- Hacer comentarios a los segmentos

## BEM

Block element modifier

& hace referencia al padre

## Mixins

Nos permiten reusar declaraciones e incluso modificar el valor cuando la reutilizamos

## Content

Directiva @content permiten incluir un bloque dentro de un mixin

## Extend

@extend hace que las clases extiendan todas las propiedades de la clase padre. Utilizar el placeholder % para evitar el duplicado del codigo

## Funciones

Podemos añadir una funcion a una propiedad, podemos añadir una funcion a un valor.

```scss
@function suma($numero-uno, $numero-dos) {
  @return $numero-uno + $numero-dos;
}

.div {
  padding: suma(10px, 5px);
}
```

### Ejemplos de Funciones

Funciones tambien pueden extraer valores de un array.

```scss
$fs : (
  big: 24px,
  notmal: 16px,
  small: 14px,
  xsmall: 12px,
);

p {
  font-size: map-get($fs, normal);
}

small {
  color: grey;
  font-size: map-get($fs, xsmall);
}
```

## Directivas de control de flujo

```scss
$font-weigths: normal, bold, italic

@each $font in ($font-weigths) {
  .#{$font} {font-weigth: $font;}
}

// Se traduce a
.normal {
  font-weigth: normal;
}
.bold {
  font-weigth: bold;
}
.italic {
  font-weigth: italic;
}
```

## For

```scss
@for i from 1 to 5 {
  .class-#{$i} {
    &:before {
      content: "#{$1}";
    }
  }
}

$columns: 100% / 12;

@for $i from 1 through 12 {
  .col-#{$i} {
    width: $i * $columns;
  }
}
```

## Condicionales

```scss
p {
  text-color: black;
}

$background-color: black;

@if $background-color == black {
  p {
    text-color: white;
  }
}

// Puedo condicionar si incluir partials
```
