# VIGAS.CALC · Maderas Paco Cacharolo

Calculadora del **diámetro mínimo de tronco** necesario para aserrar una viga de
madera de sección dada. Pensada para usarla a pie de parque de maderas: se mide
con el calibre la testa de los postes y se elige el más pequeño que dé la viga,
desperdiciando el mínimo de madera.

**En producción: [vigas.cacharolo.es](https://vigas.cacharolo.es)**

## Cómo funciona

El diámetro mínimo es la diagonal de la sección de la viga — teorema de
Pitágoras:

```
Ø = √(ancho² + alto²)
```

Ejemplo: una viga de 20 × 10 cm necesita un tronco de Ø ≥ √(20² + 10²) = **22,36 cm**.

Se introducen **ancho** y **alto** en cm (y opcionalmente el **largo** en m) y
la aplicación devuelve:

- **Ø mínimo del tronco**, con el valor redondeado al medio centímetro para
  buscar con el calibre
- **Volumen de la viga** en m³ (si se indica el largo)
- **Volumen del tronco** equivalente y **% de madera desperdiciada**
- Dos dibujos a escala real de la sección: el tronco con la viga inscrita y su
  diagonal, y una perspectiva de la viga saliendo del tronco

Detalles de uso: acepta coma o punto decimal, Enter calcula, y una vez hecho el
primer cálculo los resultados se actualizan en vivo al cambiar cualquier campo.
El botón de la esquina superior derecha pone la página a pantalla completa.

## Tecnología

Un único [`index.html`](index.html) estático: HTML, CSS y JavaScript vanilla,
sin dependencias ni proceso de build. Los dibujos son SVG generados en el
propio navegador. Tipografías Space Grotesk e IBM Plex Mono vía Google Fonts.

Para probarlo en local basta con abrir `index.html` en el navegador, o servirlo
con cualquier servidor estático:

```sh
python3 -m http.server 4173
# → http://localhost:4173
```

## Despliegue

GitHub Pages, rama `main`, carpeta raíz. Cada push a `main` publica
automáticamente. El dominio personalizado `vigas.cacharolo.es` se configura con
el archivo [`CNAME`](CNAME) y un registro DNS `CNAME` de `vigas` →
`edgarfigueirasmpc.github.io`.
