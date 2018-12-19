# Preprocesamiento de imágenes de RADAR
Si bien las imágenes SAR han demostrado su utilidad en aplicaciones hidrológicas, cuando se trata de estudiar vegetación con diferentes niveles de inundabilidad, la literatura presenta resultados que, en algunos casos, son contradictorios debido a las diferencias en la estructura de la vegetación y en el grado de inundabilidad de la misma y al sistema utilizado (banda, polarización, ángulo de incidencia) (Pereira de Farias Costa et al. 1997). Por consiguiente, para facilitar la interpretación de las imágenes SAR del Bajo Delta del Río Paraná se planteó un enfoque metodológico a fin de comprender, en la señal de radar retrodispersada, los efectos debido a las características del sistema y de su tratamiento (distorsiones radiométricas y geométricas), y los de la información propia del objeto de estudio.

La figura XXXX resume la metodología de pre-procesamiento en el software GAMMA  este se utilizó ya que tiene una alta capacidad de procesamiento avanzado de datos SAR. Pasos como procesamiento SAR, registro de imágenes de precisión, procesamiento interferométrico, calibración radiométrica y geocodificación están plenamente operativos y se ofrecen a los clientes con condiciones atractivas. También se puede ofrecer un procesamiento de datos avanzado, como el mosaico de áreas grandes, así como el soporte para la selección de datos, la determinación de la estrategia de procesamiento y la interpretación de los resultados. Los productos de datos se almacenan en archivos ráster que pueden importarse fácilmente en otros sistemas de software o GIS. La mayoría de los productos también están disponibles como GeoTIFF o DIMAP.

* **Conjuntos de datos de entrada:** 
La imagen SAR de entrada debe estar orientada a la trayectoria (nivel 1.1 / SLC por preferencia), no debe estar corregida a terreno,  Los metadatos de imagen SAR de entrada deben contener vectores de estado en órbita (ubicaciones y velocidades), información de actitud y alcance del sensor adicionalmente se debe disponer del modelo de elevación digital para determinar las alturas y pendientes del terreno.

* **Preparación de datos:**
GAMMA requiere datos enteros de 16 bits o  datos flotantes de 32 bits para el DEM, El archivo de anotación ASCII (extensión .par) define la geometría de la imagen DEM, la ubicación y el tamaño de la celda.  GAMMA trata el valor 0 como valor de fondo, no como una altura válida.

* **Calibración radiométrica:**
Determina el efecto de iluminación local  del radar usando la pendiente y la orientación con respecto al sensor SAR y utiliza el factor de corrección para suprimir los efectos de iluminación debido a pendientes, La resolución DEM determina el nivel de detalle que se debe corregir.
Los niveles de datos SAR pueden calibrarse totalmente a valores normalizados de retrodispersión, Se aplicará una constante de calibración para convertir números digitales de archivos a un valor de retrodispersión. En algunos casos (por ejemplo, los productos Envisat SLC), la corrección del patrón de antena y la pérdida de propagación de rango deben corregirse también. La salida es un valor de intensidad Gamma (o Sigma naught). Posteriormente se corrigen los efectos de iluminación del terreno, se realizará después de la corrección geométrica del terreno.

* **Preparación del DEM:**
Se descargar el área de interés del SRTM (Shuttle Radar Topography Mission), se debe hacer un mosaico virtual y se reemplaza los valores del background por cero, la imagen de salida toma la proyección del DEM, desde el comienzo del trabajo se debe definir el sistema de proyección.

* **Corrección geométrica:**
La corrección geométrica comprende el Multi-looking, la orto-rectificación (remoción de distorsiones inducidas por el terreno), la georreferenciación (deformación a la proyección de mapas (por ejemplo, UTM) o de latitud / longitud). La altura del terreno y la información de la pendiente se extraen de un modelo digital de elevación.
El multi-looking combina píxeles vecinos haciendo un promedio las ventajas son mejorar la radiometría de imagen, disminuir el ruido. Los píxeles se ajustan de acuerdo a la resolución en rango y azimut. El tamaño del archivo de la imagen procesada se reducirá, asi mismo la desventaja se asocia a la resolución espacial por la disminución del número de looks.

* **Orto-rectificación y geocodificación:**
Define una tabla de búsqueda geográfica que especifica la transformación de píxeles SAR a coordenadas de acurdo a la proyección establecida. Se determinar LUT utilizando la geometría SAR y el DEM, posteriormente se simula la imagen SAR utilizando estos parámetros geométricos y se co-registra el SAR real con SAR simulado para refinar el LUT.

* **Corrección radiométrica del terreno:**
Utilizar parámetros de geometría a partir de la salida de procesamiento geométrico y calcular el ángulo plano de incidencia a la tierra, así mismo determina los ángulos locales de altitud de la imagen SAR en relación con la pendiente local. Se calcular el factor de corrección radiométrico local y se corrige la imagen de retro-dispersión finalmente se convertir a decibelios (dB) escala = 10 * LOG10 (intensidad).
