# BlockStore Monterrey

Asistente de compra y cotizador de block de concreto (#5, #6 y #8).

Sitio estático de un solo archivo (`index.html`) con:

- Catálogo de productos con especificaciones y fotos.
- Cotizador: precios por zona de entrega (Ocurre / Zonas 1-4 hasta 70 km),
  cálculo de distancia por carretera desde la planta (Nominatim + OSRM,
  mapa Leaflet con pin ajustable), remisionado o facturado (+IVA 16%),
  pedido mínimo a domicilio (1,500 pzs #5/#6 · 1,050 pzs #8), fecha de
  entrega con 2 días de anticipación y pedido urgente con cargo extra.
- Resumen con envío de la petición por WhatsApp y descarga de la
  cotización en PDF de una sola hoja (html2pdf.js).
- Cada cotización generada se guarda en Supabase
  (tabla `cotizaciones_block`, política RLS de solo inserción para `anon`).

Las fotos de producto se sirven desde `img/` vía jsDelivr.

## Editar precios y configuración

Todo está al inicio del `<script>` de `index.html`: `PRECIOS_5_6`,
`PRECIOS_B8`, `ZONAS`, `TARIFA_URGENTE`, `WHATSAPP_NEGOCIO`, `BASE`
(coordenadas de la planta) y `SUPABASE_URL`/`SUPABASE_KEY`.
