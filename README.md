# Estancias Jesuíticas de Córdoba: Extensión territorial aproximada

Georreferenciación y adaptación del mapa "Las Estancias Jesuíticas: Extensión Territorial (circa 1750)" de Luis Córsico. Publicado en: Piana (2004) "La Estancia Jesuítica de Caroya. Historia de la propiedad (siglos XVI-XIX)". Según reproducción en: [https://sfera.unife.it/handle/11392/2389003 Cufré, Pedro David (2015) "Aproximaciones a los problemas de interpretación y conservación arqueológica arquitectónica en la Estancia Jesuítica de Jesús María, Córdoba, Argentina."].

# Procedimiento

1. A partir de la ilustración 15 en https://sfera.unife.it/handle/11392/2389003 creo el archivo `estancias.png` (no se incluye por posibles restricciones de derecho de autor).

2. En QGIS 3.28, uso el plugin QuickMapServices para usar OpenStreetMap Standard como mapa base.

3. Uso el Georeferencer de QGIS para alinear puntos del archivo `estancias.png` con puntos del mapa base. En general uso límites entre departamentos y con otras provincias. Los puntos usados están en `estancias.points`.

4. Georeferencio la imagen usando transformación "Thin Plate Spline". La imagen así georreferenciada es `estancias_geo_tps.tiff` (nuevamente, no se incluye por posibles restricciones de derechos de autor).

5. Superpongo la imagen georreferenciada en el mapa base, y agrego una nueva capa Shapefile: `estancias_extension`, con tipo de geometría "Polygon".

6. En esta nueva capa, dibujo la extensión de las estancias jesuíticas, según la imagen georreferenciada. Cabe aclarar aquí que es posible ver discrepancias entre el recorrido de los ríos en el mapa base y la imagen georreferenciada. Esto es un problema, ya que los límites de las estancias a veces se trazan en función del recorrido de estos ríos.

7. Creo otra capa Shapefile: `estancias_cascos`, con tipo de geometría "Point".

8. Aquí uso el plugin Lat Lon Tools para crear los puntos correspondientes a los cinco cascos de estancias según las coordenadas que figuran aquí: https://es.wikipedia.org/wiki/Estancias_jesu%C3%ADticas. Faltaría la coordenada correspondiente al yacimiento arqueológico de la estancia San Ignacio, declarado Monumento Histórico Provincial en 2017.

9. Finalmente, exporto las capas en formato GeoJSON para guardar en Wikimedia Commons: https://www.mediawiki.org/wiki/Help:Map_Data
