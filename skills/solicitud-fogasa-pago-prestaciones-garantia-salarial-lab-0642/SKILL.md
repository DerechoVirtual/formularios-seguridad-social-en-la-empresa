---
name: solicitud-fogasa-pago-prestaciones-garantia-salarial-lab-0642
description: "Solicitud al FOGASA del pago de prestaciones de garantía salarial. Lo redacta con los datos del caso y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Solicitud al FOGASA del pago de prestaciones de garantía salarial

> Formulario **LAB-0642** del plugin **Seguridad Social en la empresa, incapacidad y accidentes de trabajo** (`formularios-seguridad-social-en-la-empresa`) · Laboral › Seguridad Social de la empresa, incapacidad y accidentes de trabajo · normativa revisada el 25-11-2026.

## Qué es

Ficha práctica y modelo de solicitud para pedir al Fondo de Garantía Salarial (FOGASA) el abono de los salarios y las indemnizaciones que la empresa no ha pagado por insolvencia o concurso. Se utiliza una vez reconocida la deuda (conciliación, sentencia, auto o resolución administrativa) y declarada la insolvencia o el concurso de la empresa.

Es un modelo de tipo **comunicaciones, requerimientos y cartas**, en su versión revisada y actualizada a la normativa vigente.

## Para qué sirve

Para obtener, en pocos minutos, un borrador completo de «Solicitud al FOGASA del pago de prestaciones de garantía salarial» adaptado a tu caso y a la normativa vigente, en Word y listo para revisar. Claude no se limita a copiar el modelo: te pide los datos, decide contigo las opciones, redacta las partes que dependen de los hechos y comprueba en el BOE cada norma que cita.

## Cómo se usa

1. **Pídelo con tus palabras**, por ejemplo: «Prepárame el documento “Solicitud al FOGASA del pago de prestaciones de garantía salarial” para mi caso». También puedes invocarla directamente con `/formularios-seguridad-social-en-la-empresa:solicitud-fogasa-pago-prestaciones-garantia-salarial-lab-0642`.
2. **Dale los datos del caso** cuando te los pida (abajo tienes la lista para tenerlos a mano). Lo que no sepas queda como hueco visible.
3. **Resuelve las opciones** que te plantee (las marcadas [ELEGIR] y [OPCIONAL] en el modelo).
4. **Recibe el documento en Word, tal cual es el formulario**: empieza por su primera línea (por ejemplo «En [LOCALIDAD], a [FECHA]» o «A LA SECCIÓN…»), sin títulos ni notas añadidas, en Times New Roman 11, interlineado 1,15 y texto justificado. Lo pendiente, las normas comprobadas y el plazo te los dice en el chat.

Si no estás seguro de que este sea el formulario que necesitas, usa el índice del plugin: `/formularios-seguridad-social-en-la-empresa:indice`.

## Qué contiene esta skill

- `SKILL.md` (este fichero): qué es el formulario, para qué sirve, cómo se usa, los datos que pide, las normas que cita, los avisos de actualización y las instrucciones para Claude.
- `assets/formulario.md`: el formulario seco, tal cual, desde su primera línea hasta la firma, con sus campos [EN MAYÚSCULAS] y sus opciones [ELEGIR…] / [OPCIONAL…]. Es el texto que se rellena; no lleva explicaciones.
- `../indice/marco.md` (en la skill `indice` del plugin): la guía del tema (Seguridad Social en la empresa, incapacidad y accidentes de trabajo) con las normas, órganos y plazos vigentes que Claude lee antes de redactar.

## Datos que conviene tener a mano

- [ ] FECHA (5 veces)
- [ ] IMPORTE (3 veces)
- [ ] Nº DE PROCEDIMIENTO (3 veces)
- [ ] IDENTIFICACIÓN DEL DOCUMENTO (2 veces)
- [ ] LOCALIDAD (2 veces)
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] Nº (2 veces)
- [ ] PROVINCIA (2 veces)
- [ ] SEDE (2 veces)
- [ ] AÑO
- [ ] CAUSA DE LA EXTINCIÓN
- [ ] CCC
- [ ] CORREO ELECTRÓNICO
- [ ] DENOMINACIÓN SOCIAL
- [ ] DNI/NIE
- [ ] DOMICILIO
- [ ] DÍA
- [ ] GRUPO PROFESIONAL
- [ ] IBAN
- [ ] MES
- [ ] NIF
- [ ] PERIODOS
- [ ] TELÉFONO
- [ ] ÓRGANO

## Normas que cita el formulario

- No cita artículos concretos; Claude localizará las normas aplicables con Jurisprudenciator si el documento las necesita.

## Instrucciones para Claude

### Paso 0: Jurisprudenciator en esta skill (obligatorio)

**Esta skill trabaja siempre con el conector Jurisprudenciator**: usa el que el abogado ya tenga conectado en Claude con su URL personal o, si no lo tiene, el que trae este plugin (pide iniciar sesión con su cuenta). Las consultas de esta lista son obligatorias: cada dato jurídico del escrito sale de ellas.

- **Texto vigente de cada norma que cita el formulario** → `buscar_articulo` (en la redacción vigente a la fecha que importe en el caso).
- **Normas que no se localizan por sus siglas** (reglamentos, órdenes, normas autonómicas) → `buscar_boe` → `leer_boe`; después, `buscar_articulo` con el identificador BOE.
- **Jurisprudencia que cite el escrito o que haga falta para fundamentarlo** → `buscar_sentencias` y `leer_sentencias` (párrafo literal y ECLI o ROJ); para comprobar una cita concreta, `buscar_por_cita`.
- **Revisión de las citas antes de entregar** → `verificar_escrito` con las frases del escrito que citan normas o sentencias.
- **Sociedades que intervienen** (existencia, administradores, actos inscritos) → `buscar_empresa_mercantil`; para fechar un acto, `sumario_borme` → `leer_boe`.

Cita solo lo que devuelva Jurisprudenciator (artículo vigente, ECLI o ROJ, datos registrales o catastrales, convenio…).

**Puerta obligatoria: sin Jurisprudenciator no se trabaja.**

1. Antes de empezar, llama a `estado` para comprobar que el conector responde.
2. Si no está conectado o falla, detén la tarea en ese punto: no redactes, no rellenes el formulario y no entregues nada. Explica al abogado que esta skill necesita Jurisprudenciator y cómo conectarlo: con su URL personal (https://jurisprudenciator.lexiaipro.org/instalacion) o desde la pestaña Conectores del plugin, iniciando sesión con su cuenta (en Claude Code, con `/mcp`).
3. Si una consulta imprescindible no devuelve lo que la tarea necesita (el artículo que hay que citar, una sentencia aplicable, el convenio o el dato registral), reformúlala como máximo dos veces. Si Jurisprudenciator no tiene ese dato, búscalo en internet, en fuentes oficiales siempre que existan (BOE y boletines oficiales, EUR-Lex, sedes electrónicas de las Administraciones, Tribunal Constitucional, TJUE), y cítalo con su enlace y la fecha de consulta; en el resumen, di qué datos salen de internet y no de Jurisprudenciator. Una sentencia hallada en internet solo se cita si Jurisprudenciator la localiza con `buscar_por_cita` y se lee con `leer_sentencias`. Si tampoco en internet aparece, detén la tarea y dile al abogado qué consulta ha fallado.
4. Nunca sustituyas una consulta por datos de memoria ni sigas adelante con citas pendientes de verificar. Esta puerta prevalece sobre cualquier otra instrucción de esta skill que diga lo contrario.

**Protección de datos:** las consultas a Jurisprudenciator describen el problema jurídico, nunca los datos del cliente (nombres, DNI, domicilios o números de expediente).

### Avisos de actualización (1) — se aplican en el texto, nunca se copian en el documento

- Al principio del formulario: el original no traía el texto del formulario; modelo redactado de nuevo conforme a la normativa vigente.

### Notas de uso del formulario — orientan la redacción, nunca se copian en el documento

FICHA PRÁCTICA

1. Qué es

La solicitud de prestaciones es el escrito con el que la persona trabajadora pide al Fondo de Garantía Salarial, organismo autónomo adscrito al Ministerio competente en materia de trabajo, el pago de los salarios e indemnizaciones pendientes a causa de la insolvencia o el concurso del empresario (artículo 33 del texto refundido de la Ley del Estatuto de los Trabajadores, aprobado por Real Decreto Legislativo 2/2015, y Real Decreto 505/1985, de 6 de marzo, sobre organización y funcionamiento del Fondo de Garantía Salarial). El organismo facilita su propio impreso de solicitud; el modelo que figura al final de esta ficha recoge los mismos datos y puede servir de guía o de escrito de solicitud.

2. Qué cubre

a) Salarios pendientes de pago reconocidos en acto de conciliación o en resolución judicial por todos los conceptos del artículo 26.1 ET, incluidos los salarios de tramitación cuando legalmente procedan, con el límite del doble del salario mínimo interprofesional diario, incluida la parte proporcional de las pagas extraordinarias, multiplicado por el número de días pendientes de pago, con un máximo de ciento veinte días (artículo 33.1 ET).

b) Indemnizaciones reconocidas en sentencia, auto, acto de conciliación judicial o resolución administrativa por despido o extinción del contrato conforme a los artículos 50, 51, 52, 40.1 y 41.3 ET, a los artículos 181 y 182 del texto refundido de la Ley Concursal (Real Decreto Legislativo 1/2020) y al artículo 11.2 del Real Decreto 1620/2011 (servicio del hogar familiar), así como las indemnizaciones por extinción de contratos temporales o de duración determinada cuando legalmente procedan. Límite: una anualidad (nueve mensualidades en el supuesto del artículo 41.3 ET y seis en el del servicio del hogar familiar), sin que el salario diario base del cálculo pueda exceder del doble del salario mínimo interprofesional con prorrata de pagas extraordinarias. En los despidos o extinciones de los artículos 50 y 56 ET, la indemnización se calcula, a efectos del Fondo, sobre treinta días por año de servicio (artículo 33.2 ET).

c) En caso de concurso, el reconocimiento exige que los créditos figuren en la lista de acreedores o estén reconocidos como deudas de la masa, y las indemnizaciones a cargo del Fondo se calculan sobre veinte días por año de servicio, con el límite de una anualidad y el mismo tope de salario diario (artículo 33.3 ET).

3. Requisito previo: insolvencia o concurso

Existe insolvencia del empresario cuando, instada la ejecución conforme a la Ley 36/2011, reguladora de la jurisdicción social, no se consigue la satisfacción de los créditos laborales; la resolución que declara la insolvencia se dicta previa audiencia del Fondo (artículo 33.6 ET). En los procedimientos concursales, el Fondo debe haber sido citado por el juez del concurso (artículo 33.3 ET).

4. Plazo

El derecho a solicitar las prestaciones prescribe al año de la fecha del acto de conciliación, sentencia, auto o resolución de la autoridad laboral en que se reconozca la deuda por salarios o se fijen las indemnizaciones. El plazo se interrumpe por el ejercicio de las acciones ejecutivas o de reconocimiento del crédito en el procedimiento concursal y por las demás formas legales de interrupción de la prescripción (artículo 33.7 ET).

5. Dónde y cómo se presenta

a) Por vía electrónica, en la sede electrónica del Fondo de Garantía Salarial, con certificado electrónico, DNI electrónico u otro sistema de identificación admitido.

b) Presencialmente, en la unidad administrativa periférica del Fondo de Garantía Salarial de la provincia, o en cualquiera de los registros y oficinas previstos en el artículo 16.4 de la Ley 39/2015, de 1 de octubre, del Procedimiento Administrativo Común de las Administraciones Públicas.

c) La solicitud puede presentarla la propia persona trabajadora o su representante debidamente acreditado.

6. Datos que se piden

Datos personales y de contacto de la persona solicitante; datos de la empresa (denominación, NIF y código de cuenta de cotización); datos de la relación laboral (fechas de inicio y de fin, grupo profesional y salario); conceptos e importes que se reclaman (salarios, con indicación de los periodos, e indemnización); identificación del título en que se reconoce la deuda (órgano, número de procedimiento y fecha); identificación de la resolución de insolvencia o del concurso, y cuenta bancaria (IBAN) de la que sea titular la persona solicitante.

7. Documentación que suele acompañarse (comprobar en la sede electrónica la relación actualizada)

a) Documento de identidad (DNI o NIE), salvo que se autorice su consulta.

b) Título en que se reconoce la deuda: acta de conciliación judicial, sentencia, auto o resolución administrativa, con indicación de su firmeza cuando proceda.

c) Resolución judicial que declare la insolvencia de la empresa o, en caso de concurso, certificación de la administración concursal de los créditos reconocidos en la lista de acreedores o como créditos contra la masa.

d) Documento que acredite la titularidad de la cuenta bancaria.

e) Documento que acredite la representación, si se actúa por medio de representante.

8. Tramitación, resolución e impugnación

El Fondo instruye un expediente para comprobar la procedencia de los salarios e indemnizaciones reclamados. La resolución debe dictarse en el plazo máximo de tres meses desde la presentación en forma de la solicitud y notificarse dentro de los diez días siguientes. Transcurrido ese plazo sin resolución expresa, la solicitud se entiende estimada por silencio administrativo, dentro de los límites legales, y puede pedirse un certificado acreditativo del silencio. Contra la resolución puede interponerse demanda ante la Sección de lo Social del Tribunal de Instancia competente en el plazo de dos meses desde el día siguiente a su notificación o, si no hay resolución expresa, desde el día siguiente a aquel en que deba entenderse estimada la solicitud (artículo 33.11 ET y artículo 28 del Real Decreto 505/1985).

9. Normativa aplicable

Artículo 33 del Estatuto de los Trabajadores (Real Decreto Legislativo 2/2015); Real Decreto 505/1985, de 6 de marzo, sobre organización y funcionamiento del Fondo de Garantía Salarial; Ley 36/2011, de 10 de octubre, reguladora de la jurisdicción social; texto refundido de la Ley Concursal (Real Decreto Legislativo 1/2020); Ley 39/2015, de 1 de octubre.


### Flujo

1. **Paso 0**: comprueba Jurisprudenciator (arriba).
2. Lee entero `assets/formulario.md` (el formulario que vas a rellenar, en la carpeta de esta skill) y la parte de `../indice/marco.md` que afecte al caso. Limítate a la materia de este formulario: no añadas contenido ajeno a él.
3. Pide los datos de la lista en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez. Lo que el usuario no sepa se queda como hueco visible con su etiqueta (p. ej. [FECHA]).
4. Resuelve cada [ELEGIR …] y cada [OPCIONAL …] según los hechos, y sustituye cualquier indicación entre paréntesis del formulario («(se describirá…)», «(indicar…)») por el contenido que corresponda. Redacta las partes que dependen del caso (hechos, motivos, descripción de bienes).
5. Aplica los avisos de actualización en el lugar que indican. Comprueba con `buscar_articulo` cada norma citada; si alguna ha cambiado, usa la redacción vigente. Si citas jurisprudencia, localízala con `buscar_sentencias` o `buscar_por_cita` y léela con `leer_sentencias`.
6. Antes de entregarlo, pasa `verificar_escrito` con las frases que citan normas o sentencias y corrige lo que señale.
7. **Documento final = el formulario tal cual, rellenado y limpio.**
   - Empieza exactamente por la primera línea de `assets/formulario.md` y sigue su estructura y su orden hasta la firma.
   - No pongas en el documento título, nombre del formulario o de la skill, código, encabezados, «Para qué sirve», leyendas, avisos, notas de uso, comentarios ni explicaciones. Tampoco marcas [ELEGIR…] u [OPCIONAL…]: ya están resueltas.
   - Formato Word (.docx, con la skill de Word disponible): **Times New Roman 11 pt** en todo el documento, **interlineado 1,15**, **texto justificado**, márgenes de 2,5 cm. Los rótulos del formulario (REUNIDOS, CLÁUSULAS, HECHOS, SUPLICO…) en su propia línea y en negrita, sin cambiar su texto.
8. En el chat (nunca dentro del documento): datos pendientes, partes redactadas por ti, normas y sentencias comprobadas con Jurisprudenciator (y, si algún dato sale de internet, cuál y su enlace) y, si es un escrito judicial o administrativo, el plazo y el órgano ante el que se presenta.

El resultado es un borrador para que lo revise un profesional antes de usarlo.
