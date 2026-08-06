# Constancia — demo comercial (mudanzas)

Maqueta de venta. Un solo archivo, `index.html`, sin build, sin backend, sin
dependencias externas. Se abre desde un link en el celular y carga al instante.

## Qué es

Dos flujos sobre los dos sangrados del cliente:

- **Acta de carga** — deja constancia del estado de cada bulto antes de subirlo
  al camión, con nota y sello de hora. Es el flujo principal.
- **Cotización** — levanta el inventario con foto, volumen y notas de acceso.
  No calcula ni muestra precio: el campo "Su cotización" va en blanco a
  propósito.

Cada flujo tiene un ejemplo terminado (se ve completo) y un flujo de armado
(se detiene en el corte). La diferencia entre los dos es el argumento de venta.

## Reglas que el archivo respeta

- Marca neutra. No aparece el nombre ni el logo de ningún cliente real.
- Ningún precio en pesos, en ningún lado.
- El corte cierra con mensaje y firma. Sin botón, sin link, sin CTA.
- Recargar deja todo limpio: no hay persistencia.
- Cero llamadas de red. Funciona sin internet una vez cargado.

## Cosas que se tocan al mantenerlo

- `DEMO_NOW` — fecha y hora congeladas. Todo lo que se sella se calcula a
  partir de esta constante, nunca del reloj real, para que la demo se vea
  idéntica cada vez que se abre.
- `ITEMS` — catálogo de 15 piezas: nombre, volumen, dibujo y `mark` (dónde cae
  la marca de daño en esa captura).
- `ACTA` y `COT` — datos semilla de los dos ejemplos terminados, escritos a
  mano.
- `CUT` — pasos de la transición del corte. El texto del mensaje y la firma
  están en el HTML, en `#cut-msg`, y son literales.

## Sobre las capturas

Las 15 piezas del catálogo son ilustraciones vectoriales dibujadas en el mismo
encuadre y con la misma luz, embebidas en el archivo. Sustituirlas por
fotografías reales es un cambio local: cada entrada de `ITEMS` toma su dibujo
de `G`, y el envoltorio `shot()` ya aplica el encuadre y el recorte cerrado de
miniatura.

## Publicar

GitHub Pages, sirviendo la raíz de la rama. `index.html` está en la raíz, así
que no hace falta configuración adicional.
