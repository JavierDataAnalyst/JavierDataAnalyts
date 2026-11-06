**ES** · Dashboard de riesgo de crédito sobre la fintech ficticia de este repo. 
## 1. Cargar los datos
*Inicio → Obtener datos → Texto/CSV* y carga los 5 archivos de `data/csv/`: `clientes`, `solicitudes`, `prestamos`, `pagos`, `cartera_cierre`. Usa **Transformar datos**, no *Cargar*.

## 2. Limpiar en Power Query (los datos traen errores a propósito)
| Tabla | Paso | Cómo comprobarlo |
|---|---|---|
| Todas | Tipos: columnas `fecha_*` → Fecha; `monto`, `saldo`, `valor` → Número entero; `tasa_ea` → Decimal | Sin errores en la vista previa |
| `clientes` | `ciudad` → *Reemplazar valores* `Bogotá D.C.` → `Bogotá` | |
| `clientes` | `ciudad` → *Transformar → Formato → Recortar* y luego *Poner en mayúsculas cada palabra* | |
| `clientes` | *Reemplazar valores* (opciones avanzadas: *Coincidir con el contenido de toda la celda*): `Bogota` → `Bogotá`; `Medellin` → `Medellín`; `Barranquila` → `Barranquilla` | Filtro de la columna: solo 6 valores |
| `pagos` | Selecciona todas las columnas → *Quitar filas → Quitar duplicados* | 2,129 → **2,099** filas |
| `prestamos` | *Combinar consultas* con `solicitudes` por `solicitud_id` (externa izquierda) y expande solo `canal` | Columna `canal` sin vacíos |

Cierra y aplica.

## 3. Modelo
1. *Modelado → Nueva tabla*: crea `Calendario` y `Canal` con el DAX de `medidas.dax`. Marca `Calendario` como tabla de fechas.
2. En `prestamos`, *Nueva columna*: `Tipo de credito`.
3. Relaciones (vista de modelo), todas de uno a varios y en una sola dirección:
   - `Calendario[Date]` → `prestamos[fecha_desembolso]` y → `solicitudes[fecha_solicitud]`
   - `Canal[canal]` → `prestamos[canal]` y → `solicitudes[canal]`
   - `clientes[cliente_id]` → `prestamos[cliente_id]` y → `solicitudes[cliente_id]`
   - `prestamos[prestamo_id]` → `cartera_cierre[prestamo_id]` y → `pagos[prestamo_id]`
   - **No** relaciones `solicitudes` con `prestamos`: el canal ya está en `prestamos`.

## 4. Medidas
Crea cada medida de `medidas.dax` con *Inicio → Nueva medida*, una por una. Formato: montos sin decimales; tasas y `% Mora 30+` como porcentaje con 1 decimal.

## 5. Página "Riesgo de crédito"
- **Título con la conclusión:** "WhatsApp trae volumen, pero su cosecha de abril tiene 1.6× más mora".
- **4 tarjetas:** Monto desembolsado · Número de préstamos · Tasa de aprobación · % Mora 30+.
- **Líneas:** Tasa de aprobación por `Calendario[Mes]`, leyenda `Canal[canal]`.
- **Columnas:** Monto desembolsado por `Calendario[Mes]`, leyenda `Canal[canal]`.
- **Matriz:** filas `Calendario[Mes]` (cosecha), columnas `Canal[canal]`, valor `% Mora 30+` con escala de color de fondo; agrega `Cosecha madura` como valor o en la información sobre herramientas.
- **Segmentadores:** `clientes[ciudad]`, `Canal[canal]`, `prestamos[Tipo de credito]`.
- **Colores:** Web `#0B8A7E`, App `#4F46E5`, WhatsApp `#D97706`.

## 6. Cifras de control (si no te dan, algo del modelo está mal)
| Medida | Valor esperado |
|---|---|
| Monto desembolsado | 688,900,000 |
| Número de préstamos | 2,219 |
| Tasa de aprobación (total) | 54.6 % |
| Tasa de aprobación, abril | 50.7 % |
| % Mora 30+ (total) | 5.5 % |
| % Mora 30+ cosecha abril: Web / App / WhatsApp | 7.6 % / 7.3 % / 12.3 % |
| Variación mensual, junio | 12.7 % |
| Filas de `pagos` tras quitar duplicados | 2,099 |

## 7. Capturas
Guarda en esta carpeta, en PNG de unos 1600 px de ancho:
- `01_dashboard.png`: la página completa.
- `02_modelo.png`: la vista de modelo con las relaciones.
- `03_mora_cosecha.png`: la matriz de mora 30+ por cosecha y canal.

---

**EN** · Credit-risk dashboard on this repo's fictional fintech. Load the five CSVs from `data/csv/`, clean them in Power Query (types, 6 normalized cities, remove duplicate payments, merge `canal` into `prestamos`), build the star schema above, paste the measures from `medidas.dax` one by one, and check the control figures in section 6.
