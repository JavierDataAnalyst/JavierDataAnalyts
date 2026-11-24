# Javier Daza · Analytics Engineer & BI

### Ingeniería de producción en la teoría, datos en la práctica.

📍 Bogotá, Colombia · 💼 Presencial, híbrido o remoto · 🗣️ Español nativo, inglés profesional (trabajo diario con equipos en EE. UU.) ·
📫 [LinkedIn](https://www.linkedin.com/in/javier-daza-5201b1176/) · [Correo](mailto:javier.m.daza.p@gmail.com) · [Portafolio](https://javierdataanalyst.github.io/Issues-and-solutions/)

**Ingeniero de Producción** (Universidad Distrital) que construye **pipelines de datos confiables, modelos dimensionales y
tableros para decidir**. Hoy trabajo en datos para financieras de Puerto Rico y Colombia; quiero llevar esa disciplina a
las **industrias físicas**: energía, manufactura, logística, agroindustria y construcción (**Industria 4.0**).

> **EN** · Production engineer turned analytics engineer. I build tested data pipelines, dimensional models and
> decision-ready dashboards (SQL, Python, dbt, Power BI), and I want to apply them to energy, manufacturing and logistics.

---

## 🎯 Qué busco

| Roles | Sectores | Modalidad |
|---|---|---|
| Analytics Engineer · Data Engineer · BI Analyst / Developer | Energía · Manufactura · Logística y supply chain · Agroindustria · Construcción | Presencial, híbrido o remoto (Bogotá) |

---

## ⚡ Proyecto destacado: qué mueve el precio de la energía en Colombia

[![El precio de bolsa sigue a las lluvias](https://raw.githubusercontent.com/JavierDataAnalyst/Colombia-energy-analytics/main/docs/img/hydro_vs_price.png)](https://javierdataanalyst.github.io/Colombia-energy-analytics/)

**[Ver la página interactiva](https://javierdataanalyst.github.io/Colombia-energy-analytics/)** · **[Ver el código](https://github.com/JavierDataAnalyst/Colombia-energy-analytics)**

- **Problema:** una empresa que compra energía en bolsa necesita saber cuándo subirá el precio para decidir si fija un contrato.
- **Hallazgo:** el precio sigue a los **aportes hídricos** (correlación −0,68), no al nivel de los embalses (−0,18). En meses secos la mediana del precio fue **unas 3 veces** la de los meses húmedos.
- **Ingeniería:** ingesta desde la API pública de XM (**11 millones de registros horarios**), modelo estrella en **dbt + DuckDB**, **16 pruebas de datos** (incluida la conciliación diaria de la generación por planta contra el total del sistema) y actualización semanal automática con **GitHub Actions**.

---

## 📊 Experiencia

**Analista de Datos Biz Ops · BI y Riesgo de Cartera** — financieras de Puerto Rico y Colombia · 2024 – hoy · remoto

- **Fuente única de verdad:** uní dos sistemas de préstamos (originación y administración) en un solo modelo, sin duplicados.
- **Reportes auditables:** el informe mensual al banco se recalcula desde la fuente y cada cifra se puede comprobar.
- **Automatización:** procesos diarios con Python, Supabase y GitHub Actions que antes se hacían a mano.
- **Más de 30 tableros** para finanzas, operaciones, ventas y marketing.
- **Más de 500.000 registros** conciliados en una base de contacto único para campañas multicanal.

**Analista de Marketing Comercial** — Kimberly-Clark · 2021 · práctica

---

## 🧰 Stack

| Área | Lo uso hoy (trabajo y proyectos) | Aprendiendo |
|---|---|---|
| **Datos y SQL** | SQL avanzado (PostgreSQL, SQL Server, MySQL): funciones de ventana, CTEs · modelado dimensional (Kimball) · calidad de datos | — |
| **Ingeniería** | Python (pandas, APIs REST) · dbt · DuckDB · Git y GitHub Actions · Supabase · n8n | AWS (S3, Glue, Athena, Lambda) |
| **BI** | Power BI (DAX, Power Query) · Excel avanzado · tableros web | — |
| **IA** | Asistentes de código con controles: cada resultado se valida contra la fuente | Agentes y automatizaciones con IA |

---

## 🧠 Lo que la IA no reemplaza: criterio

La IA ya escribe SQL y arma tableros. Lo que aporto es lo que pasa **antes y después** del tablero:

| Lo que hago | Un ejemplo real |
|---|---|
| **Entender el proceso que genera el dato** | Al construir el motor de mora detecté que las fotos diarias repetidas de la cartera inflaban las tasas, y lo corregí desde el origen. |
| **Decidir si una cifra es confiable** | En un reporte para el banco encontré una prueba que nunca podía fallar: solo promediaba los préstamos que ya cumplían. La llevé a gerencia antes de corregirla. |
| **Traducir entre negocio y datos** | Respondo a bancos e inversionistas con cifras que ellos mismos pueden recalcular desde la fuente. |
| **Diseñar sistemas con controles** | Mis flujos se detienen solos si una cifra no cuadra contra la fuente o si aparece un dato personal donde no debe. |

**Cómo presento un análisis:** como un memo de decisión. **Problema** → **Opciones** → **Recomendación** → **Evidencia**.

---

## 🏭 De la ingeniería de producción a los datos

| Lo que estudié | Cómo lo aplico en datos |
|---|---|
| Control estadístico de calidad y control de procesos | Validaciones que detienen un flujo cuando una cifra no cuadra |
| Planeación de la producción y diseño de procesos | Pipelines automatizados que eliminan pasos manuales y cuellos de botella |
| Gestión de calidad | Una sola fuente de verdad, sin duplicados ni definiciones distintas |
| Diseño de experimentos y modelos estocásticos | Comparar antes y después con método, no con intuición |
| Programación lineal y simulación | Modelos para decidir con recursos limitados |

**Temas que quiero llevar a planta:** eficiencia de equipos (OEE), mantenimiento predictivo, planeación de demanda e
inventarios, trazabilidad de la cadena de suministro y consumo de energía.

---

## 📁 Más proyectos

| Proyecto | Qué es |
|---|---|
| [Portafolio y hoja de vida](https://javierdataanalyst.github.io/Issues-and-solutions/) | Proyectos de datos financieros descritos sin datos sensibles, demos con datos ficticios, SQL y Power BI. |
| [Guía de agentes de IA](https://javierdataanalyst.github.io/Agentes-de-IA/) | Guía educativa en español, paso a paso, con ejercicios y tarjetas de repaso. |

---

## 🎓 Formación

**Ingeniero de Producción** · Universidad Distrital Francisco José de Caldas (ciclo propedéutico: Tecnología en
Gestión de la Producción Industrial → Ingeniería de Producción).

<details>
<summary>Asignaturas relevantes para Industria 4.0</summary>

| Área | Asignaturas |
|---|---|
| Calidad y procesos | Control estadístico de calidad · Gestión de calidad · Control de procesos · Diseño de experimentos · Procesos industriales |
| Operaciones | Planeación de la producción · Logística integral · Mantenimiento industrial · Automatización · Sistemas flexibles de manufactura · Dirección de producción |
| Modelos y decisión | Programación lineal · Modelos determinísticos y estocásticos de producción · Simulación · Estadística y probabilidades |
| Costos y proyectos | Costos de producción · Ingeniería económica · Formulación y evaluación de proyectos |

</details>
