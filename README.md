# Portugal and Spain Travel Map for display of our private tours
Portugal and Spain interactive travel map built on a SVG layer and RaphaelJS Library.

## Demo

[Demo](https://terratraditionsconsulting.com)

## Usage

The map is ready to be integrated into any Web page because it is contained in a single minified JavaScript file: spain-travel-map.min.js
The map depends on the library [RaphaëlJs](http://raphaeljs.com)

1. Loads raphaeljs and the script spain-travel-map.js

  ```
  <script type="text/javascript" src="some/path/raphael-min.js"></script>
  <script type="text/javascript" src="some/path/spain-travel-map.min.js"></script>
  ```

2. Loads a map instance. The map accepts the following configuration parameters:

  ```
  <script type="text/javascript">
      new SpainMap({
        id: 'map', //(Required) HTML element in which the map will be rendered
        width: 700, //(Required) map width
        height: 400, //(Required) map height
        fillColor: "#eeeeee", // map fill color
        strokeColor: "#bbbbbb", // frontier lines color
        strokeWidth: 0.7, // frontier lines width
        selectedColor: "#99eeee", // fill color of the province as you hover the mouse over
        animationDuration: 200, // Duration of output animation
        onClick: function(province, mouseevent) {
          // method to be executed when you click on a province
        },
        onMouseOver: function(province, mouseevent) {
          // Method that will run when hovering over a province
        },
        onMouseOut: function(province, mouseevent) {
          // Method to run when you leave a province
        }
      });
  </script>
  ```

  ...

  ```
  <div id="map"></div>
  ```

## Fuentes
- [Mapa SVG de España](http://commons.wikimedia.org/wiki/File:Andaluc%C3%ADa_Oriental_con_M%C3%A1laga.svg)

- [RaphaëlJs](http://raphaeljs.com)

- Obtuve tips muy útiles de las siguientes fuentes:

  - [us-map-raphael](https://github.com/robflaherty/us-map-raphael)
  - [Marcin Dziewulski's Blog Post](http://playground.mobily.pl/tutorials/building-an-interactive-map-with-raphael.html)

## Generación de Paths a partir del fichero SVG
He creado un pequeño script ruby que procesa el mapa SVG para generar los paths de entrada de Raphaël. Es posible que funcione también con otros mapas que no estén agrupados, así que podría ser una buena base para desarrollar mapas de otras regiones.

El script se encuentra en `/utils/jsonify.rb` y su uso sería el siguiente presuponiendo que exista un fichero con nombre `input.svg` en el mismo directorio:

```
cd utils
ruby jsonize.rb > spain-map.coffee
```
Existen también servicios web que realizan conversiones a partir de SVGs más complejos como:
[Ready Set Raphael](http://readysetraphael.com)
[SVG2RaphaelJs](http://toki-woki.net/p/SVG2RaphaelJS/)
