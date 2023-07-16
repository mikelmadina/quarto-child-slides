# quarto-child-slides: Reutilizar diapositivas con Quarto / Reveal.js

Ejemplo simple sobre cómo reutilizar contenido de diapositivas en diversas presentaciones de Quarto. Se ha usado RStudio como IDE.

-   Archivos de **diapositivas**: archivos QMD con contenido reutilizable en presentaciones.
-   Archivos de **presentación**: archivos QMD que incluyen contenido propio y/o de archivos de diapositivas.

A tener en cuenta:

-   Quarto/Reveal.js
    -   Los archivos (imágenes, datos...) referenciados en una diapositiva/presentación no pueden estar fuera de la carpeta en la que está el archivo de presentación. Aunque las rutas relativas funcionan correctamente en la previsualización de RStudio, al compilar las presentaciones dejan de funcionar.
-   En las diapositivas:
    -   Los archivos de diapositiva no deben tener el atributo `title` (interfiere con el título del archivo de la presentación; de hecho, mejor si no contienen metadatos que se usen en la plantilla de Reveal.js, aunque podemos usar metadatos para controlas nuestros contenidos).
    -   Para evitar problemas con la opción de configuración `navigation-mode: grid` , las diapositivas deberían crearse con el triple *hash* (`###`) en lugar del doble o simple, que podemos usar en el archivo de presentación.
    -   En el caso de usar subcarpetas, las rutas de los archivos referenciados deben crearse tomando como partida el archivo de presentación, no el de diapositiva.

![](http://mikelmadina.com/images/xaringan_child_slides.png#center)

```         
Proyecto
| presentacion_larga.qmd
└─ Diapositivas
| | canales-graficos.qmd
| | marcas-graficas.qmd
| └─ images
| | | canales.png
| | | marcas.png
```
