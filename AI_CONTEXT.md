# AI_CONTEXT — Proyecto RECYCLING_PROJECT

> Documento de traspaso. Cualquier modelo o persona que retome este proyecto debe leer este archivo primero.
> Última actualización: **2026-10-23** · Estado: **diseño cerrado, pre-operación** · Idioma de trabajo: español (Colombia).

---

## 1. Qué es el proyecto

Micro-negocio de **recolección y comercialización de material reciclable en Bogotá**, operado con un **triciclo de carga con cajón metálico tipo publicitario**. El triciclo cumple doble función: transporte del material y soporte publicitario del negocio del cliente.

- **Meta económica declarada:** ~**$300.000 COP por día**.
- **Alcance actual:** definición del vehículo, catálogo de materiales, precios de referencia y plan de rutas.
- **Fuera de alcance por ahora:** permisos, formalización, clientes ancla, motorización.

---

## 2. Vehículo — especificación cerrada

| Componente | Especificación |
|---|---|
| Estructura | Tubería redonda y cuadrada estructural en **Cold Rolled** |
| Unidad real (foto 2026-10-23) | Bastidor y cajón en tubo y lámina **pintados de verde**; cajón **abierto y bajo**, con forro interior claro y atornillado al bastidor; **parrilla tubular** del lado opuesto al cajón; tres ruedas con **llanta de tacos**. No se ven luces, espejos, cinta reflectiva ni el freno. Foto en `assets/triciclo_real.jpg`. |
| Piso | Lámina **calibre 20**, resistente y liviana |
| Rodamientos | Industriales de balineras |
| Llantas | **17 x 250** de moto, con radios para carga |
| Freno | De coster (contra pedal) marca **Velosteer**, más freno de parqueo |
| Guardabarros | Metálicos |
| Cajón | Metálico, **independiente del triciclo** (desmontable) |
| Medidas del cajón | **65 cm ancho × 85 cm largo × 70 cm alto** |
| Volumen útil del cajón | **≈ 0,387 m³ ≈ 387 litros** (cálculo: 0,65 × 0,85 × 0,70) |
| Medida total | **1,90 m de largo** aprox. |
| Parrilla | Trasera, con cajón de **30 × 30 × 30 cm** |
| Silla | Abullonada |
| Pintura | Electrostática, gofrada o lisa |
| Capacidad de carga | **250 kg** |
| Peso del vehículo | ≈ **90 kg** |

**Usos previstos:** venta de accesorios, café, jugos, huevos, negocios en general.

**Opciones adicionales (no incluidas aún):** cajón trasero, carpa rectangular, parasol, luces, motor eléctrico.

> **Política de carga (decidida el 2026-10-23):** la capacidad de **250 kg es el techo estructural**, no un peso de trabajo. Con un triciclo reforzado la carga operativa serían **150 kg**; con **la unidad real de la foto el tope es 80 kg por viaje**, porque sus ruedas de 36 radios reciben ~72 kg cada una. Ver secciones 2.1 y 2.2.

### 2.1 Límite real de pedaleo

El usuario planteó la duda: pedalear con 250 kg puede ser extenuante. La respuesta técnica es que **sí lo es**, y que el límite práctico está bastante por debajo del límite del equipo.

Cálculo con vehículo de 90 kg + conductor de ~75 kg + carga, resistencia a la rodadura 0,012, rendimiento de transmisión 0,95 y **90 W de pedal sostenidos** (esfuerzo realista para una jornada de 5 h a 2.640 m de altura, donde la capacidad aeróbica cae 12–15% frente al nivel del mar):

| Carga | Peso rodando | Plano (0%) | Subida 3% | Subida 5% |
|---|---|---|---|---|
| 100 kg | 265 kg | 9,9 km/h | 2,8 km/h | 1,9 km/h |
| **150 kg** | 315 kg | **8,3 km/h** | 2,4 km/h | 1,6 km/h |
| 200 kg | 365 kg | 7,2 km/h | 2,0 km/h | 1,4 km/h |
| 250 kg | 415 kg | 6,3 km/h | 1,8 km/h | 1,2 km/h |

Lectura:

1. **En plano, 250 kg se pedalea** — requiere ~115 W a 8 km/h frente a ~87 W con 150 kg. Es la diferencia entre una jornada llevadera y una que agota antes de mediodía.
2. **En pendiente, no.** Con 250 kg al 5% el avance cae a 1,2 km/h: por debajo de caminar. En el centro de Bogotá hay subidas de ese orden entre La Favorita, Candelaria y la Séptima.
3. **El primer fallo no es muscular.** Con 415 kg rodando, el freno de contra pedal disipa en cada bajada la energía de un vehículo cuatro veces más pesado que una bicicleta (calienta y pierde mordida), y la carga dinámica de un hueco multiplica el peso sobre ejes y radios entre 1,5 y 2,5 veces. A 250 kg constantes no hay margen.
4. **Regla operativa:** hasta 150 kg en cualquier corredor; 150–180 kg solo en el occidente plano (Fontibón, Kennedy, Puente Aranda, Bosa); nunca más de 180 kg en recorridos con subida del 4–5%.

### 2.2 Tope real de la unidad fotografiada

La unidad verde de las fotos no soporta la carga que asumía la ficha: ruedas de bicicleta de **36 radios** con buje de eje simple (sin tambor ni piñón), **eje rígido sin diferencial**, cajón de paneles claros atornillados a un marco de ángulo y **una sola marcha**.

Estimación con 65 kg de vacío y reparto 65/35:

| Carga | Peso por rueda trasera | Veredicto |
|---|---|---|
| 150 kg | ~100 kg | Se dobla el rin en curva |
| 100 kg | ~78 kg | Marginal, solo plano |
| **80 kg** | **~72 kg** | **Techo operativo** |
| 50 kg | ~60 kg | Cómodo |

**Decisión del 2026-10-23: operar a 80 kg por viaje** y no reforzar la unidad todavía. El refuerzo (eje con tambor, ruedas 20" de radios gruesos, plato pequeño) cuesta ≈ $860.000–$1.350.000 en versión mínima y ≈ $1.300.000–$2.470.000 con eje nuevo, contra un valor de unidad usada de ~$500.000: no se paga. Antes de invertir hay que confirmar el freno.

**Consecuencia aplicada al plan (2026-10-23, sesiones 5, 6 y 9):** el plan se reescribió en **dos tandas diarias**, y ningún viaje pasa de **80 kg**. La tanda A repite el corredor principal en su mejor hora; la tanda B es la segunda capa de la misma zona (o la de al lado) a la hora en que ese material se repone: comercio a media mañana, oficinas a media tarde, talleres temprano. Pasar de 6 a 12 tandas lleva el plan de 69% a **108% de la meta**, a cambio de jornadas de 6–8 horas. Con el tope de 80 kg son **25 viajes** y ≈**185 km por semana**: bajar de 150 a 80 kg no cuesta plata, cuesta ≈3 h 15 de jornada repartidas entre los seis días.

> **Regla de oro:** si un día no hay material para la tanda B, se cierra el día. No se rellena con kilómetros ni con peso.

---

## 3. Catálogo de materiales (20 fichas)

Documento completo con foto del envase típico, cómo reconocerlo, cómo empacarlo y advertencias:
**`02_materiales/guia_materiales.html`** (también en PDF y CSV).

### Semáforo de decisión

| Color | Significado |
|---|---|
| Verde | **Recoger** — hay comprador casi seguro |
| Ámbar | **Preguntar** — solo si la bodega confirma precio y recepción |
| Rojo | **Evitar** — ocupa espacio y casi nadie lo compra |

### Resumen

| # | Material | Envase de ejemplo | Decisión |
|---|---|---|---|
| 01 | Cartón corrugado | Caja de mercado, de electrodoméstico | Recoger |
| 02 | PET transparente (código 1) | Botella de agua, garrafa de aceite | Recoger |
| 03 | PET de color | Botella verde de gaseosa | Preguntar |
| 04 | PEAD / HDPE (código 2) | Garrafa de detergente, champú | Recoger |
| 05 | PP — polipropileno (código 5) | Balde, canastilla, tapa de botella | Recoger |
| 06 | Aluminio | Lata de cerveza o gaseosa | Recoger |
| 07 | Hojalata | Lata de atún, tarro de café | Preguntar |
| 08 | Cobre | Cable, tubo de refrigeración | Recoger |
| 09 | Bronce y latón | Llaves, grifería, válvulas | Recoger |
| 10 | Chatarra / hierro y acero | Varilla, reja, bicicleta vieja | Preguntar |
| 11 | Vidrio | Botella de cerveza, frasco de café | Preguntar |
| 12 | Papel blanco y archivo | Hojas de oficina, fotocopias | Recoger |
| 13 | Periódico y revista | Periódico, volantes | Preguntar |
| 14 | Tetra Pak | Caja de leche o jugo | Preguntar |
| 15 | Bolsas y film plástico | Bolsa de mercado, vinipel | Preguntar |
| 16 | Envolturas de papas y mecato | Paquete de papas, galletas | Evitar |
| 17 | Icopor / poliestireno (código 6) | Bandeja de comida, vaso desechable | Evitar |
| 18 | Cartón plegadizo | Cajetilla vacía, caja de cereal | Preguntar |

### Orden de prioridad por kilo y por espacio

1. Cobre · 2. Bronce y latón · 3. Aluminio · 4. PET y PEAD/PP · 5. Papel blanco/archivo · 6. Cartón · 7. Vidrio y chatarra · 8. Snacks, icopor, tetra.

**Regla práctica:** si un material pesa poco, ocupa mucho espacio y nadie confirma que lo compra, no vale la pena transportarlo.

---

## 4. Precios de referencia (COP por kilo)

### 4.1 Tabla aportada por el usuario (base del negocio)

| Material | Precio aprox./kg | Con 30 kg/día |
|---|---|---|
| Cartón | $300 – $700 | $9.000 – $21.000 |
| Plástico PET | $800 – $1.500 | $24.000 – $45.000 |
| Vidrio | $100 – $300 | $3.000 – $9.000 |
| Aluminio | $4.000 – $7.000 | $120.000 – $210.000 |
| Chatarra / metal | $800 – $2.000 | $24.000 – $60.000 |

### 4.2 Referencia de metales no ferrosos — Bogotá, 2026

Lista pública de un comprador de chatarra de la ciudad (varía a diario; confirmar siempre):

| Tipo | Precio/kg | Cómo se reconoce |
|---|---|---|
| Cobre rojo limpio | **$35.000** | Cable pelado, sin estañar ni oxidar |
| Cobre rojo #2 | $35.000 | Con oxidación, soldadura o pintura |
| Cable con forro | $11.000 | Se paga por cobre neto, descontando forro |
| Cobre de radiador | $22.000 | Mezclado con latón y soldadura |
| Bronce y latón | $22.000 | Llaves, válvulas, accesorios |

> **Hallazgo central:** el cobre y el latón valen entre **10 y 40 veces** más que el cartón o el vidrio. La tabla original del proyecto no incluía metales no ferrosos y eso cambiaba por completo la estrategia de recolección.

### 4.3 Materiales sin precio confirmado

PEAD/PP, papel blanco, periódico, tetra, film y vidrio no tienen aún precio verificado con una bodega concreta. En los documentos aparecen como **"confirmar en bodega"**; no se inventaron cifras.

---

## 5. Plan de rutas — 4 rutas, una por día

Documento completo: **`03_rutas/mapa_rutas.html`** (mapa + tabla + CSV).

- **Base de acopio:** **barrio La Favorita**, localidad de Los Mártires (Calle 17 con Carrera 17). Punto de partida y de llegada fijo de las seis jornadas.
- **Lógica:** una ruta = un día completo. Se sale vacío al punto más lejano y se vuelve cargando.
- **Números en el mapa:** 1 = parada más lejana, 3 = más cercana a la bodega.

| Ruta | Color | Paradas (1→3) | Materiales | Horario |
|---|---|---|---|---|
| 1 · Centro | Azul | Santa Fe → Candelaria | Cartón, plegadizo, PET | 5:00 – 9:00 |
| 2 · Norte | Terracota | Usaquén → Chapinero → Teusaquillo | Vidrio, PET, papel, aluminio | 9:30 – 13:00 |
| 3 · Occidente | Ámbar | Bosa → Kennedy → Fontibón | Chatarra, cobre, latón, aluminio | 13:30 – 16:30 |
| 4 · Sur | Morado | Rafael Uribe Uribe → Tunjuelito → Antonio Nariño | PET, latas, cartón | 16:00 – 18:30 |

**Semana:** Lun R1 · Mar R2 · Mié R3 · Jue R4 · Vie R1 (repaso comercio) · Sáb mixta (clientes fijos) · Dom descanso.

**Por qué así:**
- **Miércoles es el día de la plata:** la ruta 3 pesa poco (130–150 kg) pero es la de mayor valor por kilo. Como no llena el cajón, admite dos vueltas.
- **Lunes y viernes se repite comercio** porque el cartón y el plegadizo se acumulan rápido y ocupan mucho volumen.
- **Sábado no es ruta nueva:** es repaso de clientes que ya dijeron sí.

### 5.1 Plan diario, calle por calle

Documento: **`03_rutas/plan_semanal.html`** (y `.pdf`).

| Día | Ruta | Corredor principal | Viajes | Descarga sugerida |
|---|---|---|---|---|
| Lunes | Ruta 1 · Centro | Calle 17 → Cra 17 → Calle 19 → Cra 7 → Calle 26 → Cra 10 | A: 3 viajes (80+50+40) · B: 2 (50+45) | ECA Mártires |
| Martes | Ruta 2 · Norte | Calle 19 → Cra 7 → Calle 63 → Cra 11 → Calle 116 → Cra 15 | A: 3 viajes (80+60+60) · B: 2 (60+60) | Toberín (A1) · Mártires (resto) · Puente Aranda 1 (B) |
| Miércoles | Ruta 3 · Occidente | Calle 13 → Cra 50 → Av. 68 → Av. Boyacá → Autopista Sur → Av. Bosa → Av. 1° de Mayo → Calle 17 | B: 1 viaje de 80 · A: 2 de 66 | Puente Aranda 1 (B) · Fontibón (A) |
| Jueves | Ruta 4 · Sur | Calle 13 → Cra 24 → Calle 17 Sur → Cra 50 → Calle 32 Sur → Cra 10 | B: 2 (50+50) · A: 3 (80+60+45) | ECA Mártires |
| Viernes | Ruta 1 · repaso | Mismo corredor del lunes, solo clientes fijos | A: 3 (80+45+45) · B: 2 (50+45) | ECA Mártires |
| Sábado | Mixta | Recolección puntual confirmada por WhatsApp | A: 1 (75) · B: 1 (45) | ECA Kennedy / Depósito Gaitán |

> **Total: 12 tandas y 25 viajes.** El jueves cierra a las 19:50; sin luces se queda en 4 viajes y los 45 kg restantes pasan al sábado.

> **Regla de seguridad del plan:** el triciclo **no** circula por Autopista Norte, Autopista Sur ni carriles rápidos de la NQS con carga. Vías locales, calzada lenta y ciclorruta donde exista.

### 5.2 Directorio de centros de acopio

17 puntos con dirección y enlace a Google Maps:

- **14 ECAs** del Distrito (Estaciones de Clasificación y Aprovechamiento): Mártires, Puente Aranda 1 y 2, Fontibón (Montevideo), Kennedy, Coroteros, Alquería, Bodegas 5 y 6 María Paz, Toberín 1 y 2, Engativá, Engativá 2 (Las Ferias), Usme. Direcciones tomadas de la planilla oficial de la **UAESP**.
- **3 compradores privados**: METALREC (Calle 21C N° 42-169, Autopista Medellín), Depósito Gaitán (Carrera 128 N° 14B-90) y Comercializadora Gamboa JJ (Carrera 32 N° 11A-81). Direcciones publicadas en sus propios sitios.

**Distinción operativa:** la ECA pesa y clasifica y suele operar con organizaciones de recicladores; la bodega privada compra directo y paga en el momento. Conviene usar la ECA cercana como precio de referencia para negociar con la privada.

**Horarios:** solo METALREC publica horario (lun–sáb, 7:00–13:00). El resto aparece como «Confirmar» y no se inventó.

> **Advertencia de alcance:** las líneas del mapa son **corredores entre localidades**, no el trazado calle por calle. Marcan por dónde y en qué orden, no la ruta exacta.

> **Convención de lectura (2026-10-23):** en el plan diario, cada vía del tramo va en un **recuadro rojo con flecha de sentido** (↑ norte, ↓ sur, → oriente, ← occidente) y debajo la instrucción «Coger X sentido Y hasta Z». El recuadro gris es el punto de salida, no una vía. Los sentidos se derivan de la numeración de Bogotá —calles suben al norte, carreras al occidente—, **no están verificados contra señalización ni cierres**. Las filas de descarga llevan etiqueta roja con ⚠.

> **Columna de gestión comercial (2026-10-23):** cada fila cierra con un **recuadro rojo** que trae el guion textual para pedir el material en el establecimiento y, debajo, **por quién preguntar** (dueño, administrador, jefe de cocina, maestro de taller, recepcionista, pesador de la ECA). Los tramos de traslado, salida y regreso dicen «Sin gestión en este tramo». **Los guiones no ofrecen comprar**: preguntan por el comprador actual («¿quién le compra la chatarra hoy?») y ofrecen el servicio de sacarlo sin costo. Antes de las 7:00 no se pregunta: se recoge lo que quedó en el andén.

---

## 6. Economía estimada por día

Cifras del plan vigente. Composición, kilos y precios están detallados en `03_rutas/plan_semanal.html`.

| Día | Mezcla supuesta | Tanda A | Tanda B | Kilos | **Día** | vs. meta |
|---|---|---|---|---|---|---|
| Lunes | 45% cartón · 30% PET · 20% papel · 5% aluminio | $160.650 | $84.000 | 265 | **$244.650** | 82% |
| Martes | 40% vidrio · 30% PET · 25% papel · 5% aluminio | $165.000 | $94.000 | 320 | **$259.000** | 86% |
| Miércoles | 81% chatarra · 11% aluminio · 4% cable · 2% latón · 1% cobre | $392.000 | $237.500 | 212 | **$629.500** | 210% |
| Jueves | 46% cartón · 35% PET · 15% vidrio · 4% aluminio | $166.650 | $79.000 | 285 | **$245.650** | 82% |
| Viernes | Igual que el lunes, solo clientes fijos | $160.650 | $84.000 | 265 | **$244.650** | 82% |
| Sábado | 85% chatarra · 13% aluminio · 2% cobre | $196.500 | $117.200 | 120 | **$313.700** | 105% |
| **Semana** | Seis jornadas, **12 tandas / 25 viajes** | $1.241.450 | $695.700 | 1.467 | **$1.937.150** | **108%** |

> **La segunda tanda cuesta trabajo, no plata.** Los kilos de la tanda A son los mismos del plan anterior; la tanda B agrega material que antes quedaba en la calle. El costo es tiempo y kilómetros: 25 viajes, ≈ 185 km por semana y jornadas de 6 a 8 horas.

### La brecha contra la meta

- Meta: 6 días × $300.000 = **$1.800.000/semana**.
- Con una tanda por día: **$1.241.450** = 69% (brecha de $558.550).
- Con dos tandas por día: **$1.937.150** = **108%**, con **$137.150 de superávit**.
- Promedio diario: **$322.900**, no $207.000.

**Dónde se cierra:** la tanda B aporta $695.700. El miércoles solo pesa $629.500 (más que su propia meta) y junto al sábado —los dos días de metal— suma el 49% del ingreso semanal.

**El supuesto frágil:** la tanda B rinde 55% de los kilos de la A (60% en metales) y se paga 5% menos por kilo. Probado en rango: al 35% la semana queda en ≈$1.660.000 (92%); al 70% en ≈$2.090.000 (116%). En los dos extremos supera la meta, pero por márgenes distintos.

### Supuestos detrás de las cifras

1. **Papel blanco valuado al precio del cartón** ($300–$700/kg). No hay precio confirmado y no se quiso inventar uno alto.
2. **PEAD, PP, tetra y film no suman ingresos**: sin comprador confirmado no se les asigna valor.
3. **Kilos por día** = estimación de capacidad del cajón (387 L) y densidad de cada material, no medición.
4. **Escenario medio** = punto medio de cada rango de precio; **alto** = máximo.
5. **No incluye** tiempo, combustible ni mermas por material sucio o húmedo.

## 7. Decisiones tomadas en esta fase

1. **Cuatro rutas geográficas**, no una ruta única: el recorrido se organiza por tipo de zona, no por tipo de material.
2. **Salir vacío al punto más lejano** y volver cargando, para no empujar peso muerto lejos de la base.
3. **Metales primero**: cobre, latón y aluminio son la prioridad de identificación y de espacio.
4. **No acumular snacks, icopor ni tetra** sin comprador confirmado.
5. **Vender por separado**: PET transparente ≠ PET color; cable con forro ≠ cobre pelado; aluminio ≠ hierro.
6. **Preguntar antes de llenar el cajón**: precio del día y condiciones (tapas, etiquetas, tetra, bolsas).
7. **Tope de 150 kg de carga útil** (2026-10-23): los 250 kg son techo estructural, no peso de trabajo. Se pedalea hasta 150; de 150 a 180 solo en el occidente plano.
8. **El plan se ejecuta por viajes, no por jornadas** (2026-10-23): si el día rinde más de 150 kg, se hacen dos vueltas. Se prefiere un viaje extra a un cajón recargado: protege frenos, radios y piso, y cada tramo cargado se hace a 8,3 km/h en vez de 6,3. Cuando el material no cabe, se recorta y se deja para el sábado; nunca se completa el cajón.
9. **Descargar cerca de la zona, no siempre en Mártires**: el martes el viaje 1 se cierra en la ECA Toberín para no bajar 13 km con 105 kg de vidrio.
10. **Dos tandas diarias** (2026-10-23): la segunda tanda no repite cuadras, cubre la capa que la primera no alcanzó y en la hora en que el material se repone. Es lo que lleva el plan a 108% de la meta sin subir el peso por viaje.
11. **Si no hay material para la tanda B, se cierra el día.** No se rellena con kilómetros ni con carga.
12. **Las primeras semanas no se compra: se recoge** (2026-10-23). No se dice un precio hasta tener el precio del día en la ECA. El argumento en la calle es el servicio —«yo se lo saco, usted no hace nada»— y el material se vende a precio de lista. Las cuentas del plan son de venta, no de compra: pagar por el material es un costo que el modelo no tiene.
13. **Tope de 80 kg por viaje con la unidad real** (2026-10-23): no es negociable mientras las ruedas sean de 36 radios y el eje rígido. El corte se hace por peso, no por reloj. Subir a 150 kg exige el refuerzo de la sección 2.2.

---

## 8. Reglas de seguridad y legalidad

**Nunca subir al triciclo:**

| Material | Riesgo |
|---|---|
| Baterías de carro o celular | Ácido y riesgo de incendio |
| Aerosoles y pipetas de gas | Explotan al compactar o con el calor del cajón metálico |
| Cables de red eléctrica o semáforos | Delito; solo cobre de procedencia legítima |
| Envases con químicos desconocidos | Sin etiqueta no se sabe qué contienen |
| Vidrio roto suelto y bombillas | Cortan y contaminan el resto de la carga |
| Residuos hospitalarios | Riesgo biológico; requieren ruta y permiso especial |

**En el recorrido:** guantes, calzado cerrado, carga asegurada y **tope de 150 kg** de carga útil (ver 2.1). Sobre 315 kg rodando la frenada se alarga y el freno de contra pedal pierde mordida en bajada.

---

## 9. Preguntas abiertas

1. **Medidas interiores del cajón real** (largo × ancho × alto). La foto muestra un cajón más bajo que los 70 cm de la ficha; sin la medida no se sabe a qué peso se llena de cartón, y ese dato ajusta el tope de 150 kg.
2. **Freno de la unidad real**: tipo, si actúa sobre la rueda trasera y si tiene freno de parqueo. No se ve en la foto y es el límite de seguridad con carga en bajada.
3. **Peso en vacío de la unidad real.** Los cálculos usan 90 kg; si la unidad pesa más, la velocidad sostenible baja y los tiempos del plan se alargan.
4. **¿Dónde se guarda el triciclo en La Favorita?** Hay base definida (barrio La Favorita, Los Mártires), pero falta el punto exacto de parqueo, que define la hora real de salida.
5. **¿Hay precios confirmados** de PEAD/PP, papel blanco, periódico, tetra, film y vidrio con una bodega concreta?
6. **¿Se instala motor eléctrico?** Cambia autonomía, costo por día y capacidad real de carga.
7. **¿Permisos y espacio público?** Estacionar y operar en vía pública tiene restricciones en Bogotá.
8. **¿Cliente ancla de publicidad?** El cajón es espacio publicitario; hay que definir si se monetiza.
9. **¿Se formaliza como reciclador de oficio** (registro, ARL, ruta selectiva)?

---

## 10. Mapa de archivos

```
RECYCLING_PROJECT/
├── AI_CONTEXT.md                 ← este documento
├── README.md                     ← cómo usar el paquete
├── index.html                    ← portal de entrada
├── assets/
│   └── styles.css                ← hoja de estilos compartida
├── 01_producto/
│   ├── ficha_triciclo.html
│   └── ficha_triciclo.pdf
├── 02_materiales/
│   ├── guia_materiales.html      ← 20 fichas con foto
│   ├── guia_materiales.pdf
│   └── materiales.csv
├── 03_rutas/
│   ├── mapa_rutas.html           ← mapa + tabla de rutas
│   ├── mapa_rutas.pdf
│   ├── plan_semanal.html         ← plan día por día + directorio de acopio
│   ├── plan_semanal.pdf
│   ├── mapa_bogota.png           ← solo el mapa
│   ├── mapa_rutas_bogota.png     ← póster con leyenda
│   └── rutas.csv
└── 04_operacion/
    ├── precios_referencia.csv
    └── registro_recoleccion.csv  ← plantilla de campo
```

---

## 11. Fuentes

| Dato | Fuente |
|---|---|
| Límites de las 20 localidades de Bogotá | GeoJSON público `decolector/bta-geodata` (`local.geojson`), cartografía distrital |
| Precios de cobre, latón y bronce (Bogotá, 2026) | Lista pública de comprador de chatarra — depositogaitan.com |
| Precios de cartón, PET, vidrio, aluminio, chatarra | Tabla aportada por el usuario en la sesión del 2026-10-23 |
| Especificación del triciclo | Ficha aportada por el usuario |
| Fotos de envases | Referencias visuales de bancos de imágenes; son orientativas, varían por marca |
| Direcciones de las 14 ECAs | Planilla oficial de la UAESP, Alcaldía Mayor de Bogotá (`ecas actuales.xlsx`) |
| METALREC | Dirección y horario publicados en metalrec.com.co |
| Depósito Gaitán | Dirección y lista de precios publicadas en depositogaitan.com |
| Comercializadora Gamboa JJ | Dirección publicada en comercializadoragamboa.com |

---

## 12. Historial de sesiones

| Fecha | Qué se hizo |
|---|---|
| 2026-10-24 (13) | Se sumaron **cable de red (UTP)** y **cable coaxial** como fichas 09 y 10 del catálogo, con precio estimado por contenido de cobre ($5.000–$8.000 y $3.000–$5.000/kg), la **prueba del imán** y la regla de no pelar. Entraron también en el CSV de materiales (20 filas) y en el ranking de prioridad por kilo como puesto 4. Referencia verificada: cable con forro $11.000/kg y cobre limpio $35.000/kg en Depósito Gaitán, 2026. |
| 2026-10-23 (12) | Dos correcciones de realidad en el plan: **los horarios de apertura** (antes de las 7:00 no hay comercio ni oficina abiertos; esas filas pasaron a «se recoge lo del andén» y la regla entró al protocolo) y **los guiones comerciales** (nueve reescritos para preguntar por el comprador actual en vez de ofrecer compra, más el bloque «las primeras semanas no se compra» y la prueba de los diez locales). PDF en 12 páginas. |
| 2026-10-23 (11) | Se agregó al plan la sección **«Protocolo de parqueo y voz»**: tabla de qué material se recoge del andén y cuál hay que pedir, seis reglas de seguridad del triciclo (10 metros, umbral, mismo lado del andén, candado, nunca lleno, pedir que lo saquen) y la regla de las dos primeras semanas (preguntar sin cargar). PDF en 12 páginas. |
| 2026-10-23 (10) | Se añadió la **quinta columna «Qué decir y por quién preguntar»** en las 61 filas del plan diario: guion textual entre comillas para pedir el material y el rol a buscar en cada tipo de establecimiento. Los traslados dicen «Sin gestión». Encabezados de tabla repetidos en cada página del PDF (11 páginas). |
| 2026-10-23 (9) | **Plan ajustado a 80 kg por viaje** con la unidad real: de 17 a **25 viajes** (lunes 5, martes 5, miércoles 3, jueves 5, viernes 5, sábado 2), ≈185 km y **+3 h 15** de jornada. El ingreso **no cambia** ($1.937.150) porque el material es el mismo. El miércoles pasa a 2 viajes de 66 kg (cierra 18:40) y el jueves a las 19:50. Se descartó por ahora el refuerzo de la unidad: cuesta más que el valor de la unidad usada. |
| 2026-10-23 (8) | Se incorporó la **foto de la unidad real** (`assets/triciclo_real.jpg`) y su lectura operativa: cajón bajo y abierto → red o cabuya obligatoria; parrilla delantera solo para volumen liviano; llanta de tacos → 5% de margen en los tiempos; sin luces visibles → el jueves en dos tandas depende de instalarlas. Nueva sección en la ficha y nota en el plan. Quedan tres mediciones pendientes: medidas del cajón, tipo de freno y peso en vacío. |
| 2026-10-23 (7) | Se reescribió la columna «Por dónde» del plan diario: **una caja roja por vía con su flecha de sentido** y, debajo, la instrucción «Coger X sentido Y hasta Z» en las 61 filas. Las 16 filas de descarga llevan etiqueta roja con ⚠. Añadida la leyenda de flechas y la advertencia de que los sentidos salen de la numeración, no de señalización verificada. PDF reajustado a 10 páginas. |
| 2026-10-23 (6) | Se pasó el plan a **dos tandas diarias** (12 tandas, 17 viajes, 1.467 kg/semana). Ingreso estimado **$1.937.150 = 108% de la meta**, con la tanda B aportando $695.700. Se documentó el supuesto del 55% de rendimiento de la B con su rango (35%–70% → $1.660.000–$2.090.000), el costo en horas y mantenimiento (revisión cada dos semanas) y la regla de cerrar el día si no hay material. Actualizados plan, portal y este documento. |
| 2026-10-23 (5) | Se reescribió el **plan diario por viajes de ≤150 kg**: lunes y viernes 2 viajes (95+75 y 90+80), martes 2 viajes (105+95, el primero cierra en ECA Toberín), jueves 2 viajes (100+85, termina 19:10 y exige luces), miércoles 1 viaje de 130–150, sábado 1–2. El ingreso estimado no cambió ($1.241.450/semana); el costo es ≈ +1 h 20 y +14 km. Se actualizaron la tabla de rutas, el mapa de rutas y el portal. |
| 2026-10-23 (4) | Se fijó el **tope operativo de 150 kg** de carga útil (frente a los 250 kg de capacidad estructural), con la tabla de velocidad sostenible según carga y pendiente. Se documentó en la ficha del triciclo, en el portal y en la sección 2.1. Queda pendiente decidir el recorte de martes y jueves, que hoy superan ese tope. |
| 2026-10-23 (3) | Se fijó el **barrio La Favorita (Los Mártires)** como punto de partida y llegada de todas las jornadas. Se rehízo el mapa con la base nueva y se reescribió el plan diario con las calles de salida desde Calle 17 con Carrera 17. Ruta 1 pasa a dos paradas porque la base ya está dentro del centro. |
| 2026-10-23 (2) | Se agregó el plan diario calle por calle con franjas horarias y el directorio de 17 centros de acopio con dirección y enlace a Google Maps. Se enlazaron desde el portal los archivos que estaban huérfanos. |
| 2026-10-23 | Sesión inicial. Se definió el vehículo, se armó el catálogo de 18 materiales con precios y criterios, se respondieron dudas sobre snacks/cajetillas/PET aplastado, se generó la guía visual, se diseñó el plan de 4 rutas y se dibujó sobre el mapa real de Bogotá. Se empaquetó todo en este repositorio. |
