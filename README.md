# Cardify


El reto consiste en la creación de un plugin de jQuery que dado un conjunto de imágenes con una descripción al pasar se visualizará con el efecto hover.

![image](https://user-images.githubusercontent.com/19315632/38486092-9d742228-3ba1-11e8-8aef-fa1fcfb46b5f.png)

## Desarrollado para 
[Laboratoria](http://laboratoria.la)

## Flujo de trabajo

+ Planeación de trabajo con [Trello](https://trello.com/b/bYxjDYth)

## Instalación

1. Se descargará un raw con los archivos del plugin.
2. Se agregarán los archivos en la carpeta _vendors_
3. Se llamarán a la librería mediante un `<script>`
4. Por último se llamará a la librería mediante la función `$('.container').cardify({});`


### Global (navegador)

```html
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.2.1/jquery.min.js"></script>
<script src="index.js"></script>
```

## Uso

```js
// `container` es el selector del contenedor donde se buscarán todas las
// imágenes a ser procesadas.
$('.container').cardify({});
```

### Ejemplos

![demo](https://user-images.githubusercontent.com/19315632/38486368-6cb795ec-3ba2-11e8-85b4-46d0e4dd8fa4.png)

```html
  <div class="container">
      <img src="assets/images/perro1.jpg" alt="Cachorro1">
      <img src="assets/images/perro2.jpg" alt="Cachorro2">
      <img src="assets/images/perro3.jpg" alt="Cachorro3">
      <img src="assets/images/perro4.jpg" alt="Cachorro4">
      <img src="assets/images/perro5.jpg" alt="Cachorro5">
      <img src="assets/images/perro6.jpg" alt="Cachorro6">
  </div>
```

```js
$('.container').cardify({});
```

### Snippets

+ html
```html
 <div class="container">
    <img src="" alt="">
  </div>
```

+ js
```js
(function($) {
  $.fn.cardify = function() {
    $('img').hover(
       function() {
         var image = $(this)
       $(this).each(function() {
         if ( image.parent().is("figure")) {
           $( "figcaption" ).remove()
           image.unwrap();
           image.removeClass('hover')

         } else {
           image.wrap( "<figure class=inline></figure>" );
           $("figure").append('<figcaption class=letter>' + $(this).attr('alt') + '</figcaption>')
           image.addClass('hover')

         }
       })
     });

  };
}(jQuery));

```

## Bibliografía
+ [Babel](https://platzi.com/blog/que-es-babel/)
+ [Gitignore](https://desarrolloweb.com/articulos/archivo-gitignore.html)
+ [Creación de plugin-1](https://www.youtube.com/watch?v=Ghh0u1uBWAw)
+ [Creación de plugin-2](https://www.youtube.com/watch?v=ATDlkSKZiH0&index=2&list=PL0jno8rTZiDG_x2wkZdGDL6b9ccZ0BjdN)
+ [Creación de Snippets](https://www.youtube.com/watch?v=GMtRCoW9LME)
