# Panel de Ampliaciones de Trabajo

Página única (`index.html`) con el mismo diseño del panel de posventa, que lee **en vivo** la hoja de Google Sheets de ampliaciones (también acepta cargar un .xlsx/.csv a mano).

## Qué muestra
- Filtros por sucursal, mes, categoría de repuesto y búsqueda libre
- KPIs: emitidos, aprobados, efectividad, monto ofrecido, MO aprobada, repuestos aprobados, total aprobado, ticket promedio
- Evolución de aprobaciones (por día o por semana)
- Top repuestos aceptados
- Rendimiento por unidad de negocio (clic en una tarjeta para filtrar)
- Aceptación por categoría y repuestos más ofrecidos (conversión)
- Detalle de presupuestos con sus ítems y descarga a CSV

## Reglas de cálculo
- Presupuesto = N° de Orden (igual que el panel original).
- Ofrecido = Precio × Cant + Mano O. · Aprobado = lo mismo en filas con "SI".
- **"Aceptado" vacío = no aprobado.** Solo se heredan de la fila anterior N° Orden, N° Presup, Fecha y Cliente (por celdas combinadas).

## Sucursales
Se asignan por rango de N° de Orden (y, si no entra, por N° de Presupuesto). Se editan en `SUCURSALES` dentro de `index.html`:

| Sucursal | N° Orden | N° Presup |
|---|---|---|
| Santa Fe | > 5.000.000 | 70.000 – 99.999 |
| Jujuy | 250.001 – 5.000.000 | 130.000 – 199.999 |
| VW Express | 110.000 – 250.000 | 5.000 – 9.999 |
| Tartagal | 2.000 – 11.000 | 1 – 999 |

## Requisito de la hoja
Compartida como **"Cualquier persona con el enlace → Lector"**. Si no se puede leer, se muestra la copia de respaldo incluida.

## Publicar en GitHub Pages
1. Crear repositorio (ej. `panel-ampliaciones`) y subir `index.html` y `README.md`.
2. Settings → Pages → *Deploy from a branch* → `main` / `(root)` → Save.
3. Queda en `https://<usuario>.github.io/panel-ampliaciones/`.
