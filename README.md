# Participación en elecciones presidenciales — Tablero global

Tablero interactivo para explorar la participación electoral en elecciones presidenciales de países del mundo, a partir de una base histórica de resultados electorales y una tabla de referencia que asigna países a continentes o regiones.

El tablero está desarrollado como un **archivo HTML autocontenido**: los datos están incorporados en el documento y las visualizaciones se generan en el navegador, sin instalar dependencias ni conectarse a servicios externos.

## Contenido del proyecto

- `tablero_participacion_electoral.html`: tablero interactivo listo para abrir en un navegador o publicar mediante GitHub Pages.
- `0_idea_export_voter_turnout_database_world.xlsx`: base de datos de participación electoral.
- `4_isocodes3_continents.xlsx`: tabla de países, códigos ISO3 y continente/región.

> Incluye los archivos Excel en el repositorio solo si tienes autorización para redistribuirlos. El HTML generado ya incorpora los registros usados para construir el tablero.

## Funcionalidades

### Filtros globales
- **Continente / región:** permite consultar una región específica o todos los registros.
- **Año:** permite elegir un año de elección, el último año disponible o todos los años.

### Pestañas del tablero

1. **Resumen global**
   - Promedio de participación del año seleccionado o del último año disponible.
   - Evolución anual del promedio, con promedio móvil de cinco años.
   - Promedio de participación por continente o región.
   - Ranking de los diez países con mayor participación.

2. **Países y ranking**
   - Tabla de resultados por país.
   - País, código ISO3, continente/región, año y porcentaje de participación.
   - Búsqueda por nombre de país o código ISO3.

3. **Serie histórica**
   - Evolución anual del promedio de participación.
   - Cantidad de registros electorales por año.
   - Distribución de registros por rangos de participación.

4. **Datos y metodología**
   - Descripción de la integración de las bases y de los indicadores.
   - Consideraciones sobre cobertura y comparabilidad.

## Fuentes de datos

El tablero se construyó con dos archivos Excel:

- `0_idea_export_voter_turnout_database_world.xlsx`
  - Variables utilizadas: `Country`, `ISO2`, `ISO3`, `year` y `Voter Turnout`.
- `4_isocodes3_continents.xlsx`
  - Variables utilizadas: `Country`, `ISO3` y `Continent`.

### Integración
Las bases se relacionan mediante el código de país **ISO3**. La fecha de elección de la base de resultados se convierte a año calendario para construir los filtros y las agregaciones.

## Metodología e interpretación

- **Promedio de participación:** media aritmética simple de los valores de `Voter Turnout` incluidos en cada grupo. No se pondera por población ni por número de electores.
- **Evolución anual:** promedio de todos los registros disponibles para cada año. La cantidad y composición de países puede cambiar entre años.
- **Ranking con un año específico:** ordena los registros de ese año por participación, de mayor a menor.
- **Ranking con “Todos los años”:** toma la elección más reciente registrada para cada país y ordena esos registros por participación.
- **Continentes y regiones:** se conserva la clasificación del archivo de referencia. Por ello, las categorías pueden incluir regiones subcontinentales y no solo continentes en sentido estricto.
- **Periodo:** aunque el alcance planteado es 1940–2026, la base recibida contiene registros desde 1945 hasta 2026. La disponibilidad real depende de los datos fuente.

### Precauciones de lectura
- Un promedio anual no necesariamente compara el mismo conjunto de países a lo largo del tiempo.
- Los años con pocos registros pueden ser menos representativos.
- Los porcentajes deben interpretarse conforme a la definición y calidad de la variable de participación en la fuente original.
- El tablero presenta los datos suministrados y no constituye una validación independiente de los resultados electorales.

## Cómo usarlo localmente

1. Descarga o clona este repositorio.
2. Abre `tablero_participacion_electoral.html` con un navegador moderno (por ejemplo, Chrome, Edge o Firefox).
3. Selecciona continente/región y año en los filtros.
4. Navega por las pestañas para explorar los gráficos, la tabla y la metodología.

No se requiere Python, Node.js, servidor local ni conexión a internet para utilizar el archivo HTML.

## Publicar con GitHub Pages

1. Sube `tablero_participacion_electoral.html` al repositorio.
2. En GitHub, abre **Settings → Pages**.
3. En **Build and deployment**, selecciona la fuente de publicación correspondiente a tu repositorio (por ejemplo, la rama `main` y la carpeta `/root`, si el archivo está en la raíz).
4. Guarda la configuración y espera a que GitHub Pages publique el sitio.

**Sugerencia:** para que el tablero sea la página principal del repositorio en GitHub Pages, puedes renombrar el archivo a `index.html`. Si lo mantienes con su nombre actual, normalmente podrás abrirlo usando la ruta directa al archivo publicado.

## Tecnologías

- HTML5
- CSS
- JavaScript
- SVG para las visualizaciones

No utiliza frameworks ni librerías externas en tiempo de ejecución.

## Licencia y atribución

Antes de añadir una licencia, verifica los términos de uso y redistribución de las bases de datos originales. Si los datos proceden de una fuente externa, añade aquí la referencia bibliográfica, URL y condiciones de uso correspondientes.

---

**Estado:** tablero interactivo generado a partir de los archivos Excel suministrados.  
**Idioma de la interfaz:** español.
