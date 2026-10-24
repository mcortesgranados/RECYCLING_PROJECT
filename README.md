# RECYCLING_PROJECT

Paquete documental del proyecto de **recolección y venta de material reciclable con triciclo de carga en Bogotá**.

Todo está en español, en formatos abribles sin instalar nada (HTML + PDF) y en datos editables (CSV, Markdown).

---

## Por dónde empezar

1. **`index.html`** — portal de entrada. Resume el proyecto y enlaza a todo lo demás.
2. **`AI_CONTEXT.md`** — el documento de contexto: qué se decidió, qué falta, de dónde salen los datos. Si retomas el proyecto en un mes, lee esto primero.
3. **`02_materiales/guia_materiales.html`** — la guía de campo: 18 materiales con foto del envase, cómo reconocerlos y cuánto valen.

---

## Estructura

```
RECYCLING_PROJECT/
├── AI_CONTEXT.md                 Contexto maestro y bitácora de decisiones
├── README.md                     Este archivo
├── index.html                    Portal de entrada
├── index.pdf                     Portal en PDF
├── assets/
│   └── styles.css                Estilos compartidos por las páginas HTML
├── 01_producto/
│   ├── ficha_triciclo.html       Especificación del vehículo
│   └── ficha_triciclo.pdf
├── 02_materiales/
│   ├── guia_materiales.html      Guía visual de 18 materiales
│   ├── guia_materiales.pdf
│   └── materiales.csv            Los 18 materiales en tabla editable
├── 03_rutas/
│   ├── mapa_rutas.html           Mapa + tabla de rutas + semana
│   ├── mapa_rutas.pdf
│   ├── mapa_bogota.png           Solo el mapa (alta resolución)
│   ├── mapa_rutas_bogota.png     Póster con título y leyenda
│   └── rutas.csv                 Paradas, orden y horarios
└── 04_operacion/
    ├── precios_referencia.csv    Precios con fuente y estado de verificación
    └── registro_recoleccion.csv  Plantilla para llenar en la calle
```

---

## Los CSV

Todos van separados por **punto y coma** y con **UTF-8 con BOM**, para que Excel en español los abra sin romper tildes ni columnas.

| Archivo | Qué contiene |
|---|---|
| `materiales.csv` | 18 filas: material, código de reciclaje, decisión (recoger/preguntar/evitar), precio, envase de ejemplo, cómo reconocerlo, cómo empacarlo, advertencia |
| `rutas.csv` | 12 filas: una por parada, con ruta, color, orden de visita, localidad, franja horaria y materiales |
| `precios_referencia.csv` | 19 materiales con precio mínimo, máximo, fuente y estado (`Referencia`, `Confirmar`, `Evitar`) |
| `registro_recoleccion.csv` | Plantilla vacía con una fila de ejemplo. Columnas: fecha, día, ruta, negocio, zona, material, kilos, precio, valor, observaciones |

**Cómo usar la plantilla de campo:** bórrale la fila de ejemplo, llénala en el celular o en papel, y al final de la semana suma la columna `valor_cop`. En dos semanas sabrás qué ruta y qué material te están pagando de verdad.

---

## Avisos sobre los datos

- Los **precios** son referencias de mercado, no tarifas fijas. Cambian a diario y dependen de la bodega, la limpieza del material y el volumen.
- Las cifras de **cobre, latón y bronce** provienen de una lista pública de un comprador de chatarra de Bogotá (2026). Las de **cartón, PET, vidrio, aluminio y chatarra** vienen de la tabla aportada por el dueño del proyecto.
- Los materiales sin precio confirmado aparecen como **"Confirmar en bodega"**. No se inventaron cifras.
- Las **estimaciones de ingresos** ($230.000–$270.000 por viaje lleno) son cálculos con esos precios; no incluyen tiempo, combustible ni mermas.
- El **mapa** usa los límites reales de las 20 localidades de Bogotá. Las líneas marcan corredores, no calles. La base de operación es fija: **barrio La Favorita**, localidad de Los Mártires (Calle 17 con Carrera 17).

---

## Cómo regenerar los PDF

Los PDF se generan desde los HTML con un navegador headless (Edge o Chrome). Ejemplo en PowerShell:

```powershell
$edge = "C:\Program Files (x86)\Microsoft\Edge\Application\msedge.exe"
& $edge --headless=new --disable-gpu --allow-file-access-from-files `
  --no-pdf-header-footer --virtual-time-budget=12000 `
  --print-to-pdf="03_rutas\mapa_rutas.pdf" "file:///E:/RECYCLING_PROJECT/03_rutas/mapa_rutas.html"
```

Si editas un HTML, vuelve a correr ese comando para actualizar su PDF.

---

## Estado del repositorio

- Repositorio git inicializado en `main`, con remoto `origin` → `github.com/mcortesgranados/RECYCLING_PROJECT`.
- **Los archivos están creados pero sin commit ni push.** Revisa el contenido y decide qué versión subir.

---

## Siguientes pasos sugeridos

1. Confirmar la ubicación real de la bodega y recalcular las cuatro rutas.
2. Conseguir precios de PEAD, PP, papel blanco, periódico, tetra y vidrio con una bodega concreta.
3. Decidir si se instala motor eléctrico.
4. Revisar permisos de operación y uso del espacio público.
5. Definir si el cajón se monetiza como espacio publicitario.
