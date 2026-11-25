---
name: indice
description: "Índice de los 27 formularios de Seguridad Social en la empresa, incapacidad y accidentes de trabajo. Úsala cuando el usuario pida un documento de esta materia y no esté claro qué formulario usar: propone el adecuado y lo abre. Requiere Jurisprudenciator."
---

# Seguridad Social en la empresa, incapacidad y accidentes de trabajo: índice de formularios

> Plugin `formularios-seguridad-social-en-la-empresa` · 27 formularios · normativa revisada el 25-11-2026.

## Qué es

Para la Seguridad Social desde la empresa: incapacidad temporal y permanente en la relación laboral, accidentes de trabajo y enfermedad profesional, responsabilidad empresarial, FOGASA, certificaciones de descubiertos y comunicaciones con la mutua y la Tesorería.

## Cómo se usa

Cuéntale a Claude qué documento necesitas y para qué caso. Esta skill busca en la lista de abajo el formulario que mejor encaja (por tipo de documento y por su nombre) y lo abre. Si hay dos o tres que encajan, te los propone para que elijas.

Ejemplos de petición:

- «Demanda de responsabilidad empresarial por un accidente de trabajo»
- «Solicitud de certificación negativa de descubiertos a la Tesorería»
- «Demanda contra el FOGASA por salarios e indemnizaciones»

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

### Cómo elegir

Busca por tipo de documento y por nombre. Cada formulario es una skill de este plugin (`/formularios-seguridad-social-en-la-empresa:<skill>`). Si dudas entre dos, elige el que mejor encaje con los hechos y dilo; si la petición es ambigua, propón al usuario los dos o tres formularios que mejor encajan y pregúntale cuál quiere. Las reglas del tema están en `marco.md`.

### Cómo usar el formulario elegido

Invoca su skill. Si esa skill no aparece en tu lista de skills disponibles (puede pasar cuando hay muchas skills instaladas), lee directamente su fichero `SKILL.md`: está en la carpeta hermana de esta (`../<skill>/SKILL.md`). Síguelo igual que si la hubieras invocado: el formulario que se rellena está en `../<skill>/assets/formulario.md` y la guía del tema es el `marco.md` de esta carpeta.

### Demandas, peticiones y solicitudes iniciales (3)

| Código | Formulario | Skill |
|---|---|---|
| LAB-0620 | Demanda por complemento de maternidad en pensión de jubilación contributiva | `demanda-complemento-maternidad-pension-jubilacion-lab-0620` |
| LAB-0639 | Demanda de indemnización a la ETT y a la usuaria por accidente de trabajo por falta de seguridad | `demanda-indemnizacion-ett-usuaria-accidente-trabajo-lab-0639` |
| LAB-0640 | Demanda contra el FOGASA por salarios o indemnización por despido impagados | `demanda-contra-fogasa-salarios-indemnizacion-despido-lab-0640` |

### Estatutos, actas, certificaciones y escrituras (1)

| Código | Formulario | Skill |
|---|---|---|
| LAB-0635 | Certificación negativa de descubiertos de la subcontratista - solicitud a la Tesorería | `certificacion-negativa-descubiertos-subcontratista-lab-0635` |

### Comunicaciones, requerimientos y cartas (3)

| Código | Formulario | Skill |
|---|---|---|
| LAB-0641 | Aviso de reincorporación tras el alta por denegarse la incapacidad permanente o ser solo parcial | `aviso-reincorporacion-tras-alta-denegarse-incapacidad-lab-0641` |
| LAB-0642 | Solicitud al FOGASA del pago de prestaciones de garantía salarial | `solicitud-fogasa-pago-prestaciones-garantia-salarial-lab-0642` |
| LAB-0644 | Comunicación a la TGSS de la identidad de la empresa principal de la contrata | `comunicacion-tgss-identidad-empresa-principal-contrata-lab-0644` |

### Escritos de trámite y otros (20)

| Código | Formulario | Skill |
|---|---|---|
| LAB-0616 | Respuesta de la empresa a suspensión o permiso por fallecimiento en incendios forestales | `respuesta-empresa-suspension-permiso-fallecimiento-lab-0616` |
| LAB-0617 | Pedir suspensión del contrato por incendios forestales | `pedir-suspension-contrato-incendios-forestales-lab-0617` |
| LAB-0618 | Incapacidad permanente - demanda genérica | `incapacidad-permanente-demanda-generica-lab-0618` |
| LAB-0621 | Respuesta de la empresa a la petición de jubilación parcial | `respuesta-empresa-peticion-jubilacion-parcial-lab-0621` |
| LAB-0622 | Pedir jubilación parcial a la empresa | `pedir-jubilacion-parcial-empresa-lab-0622` |
| LAB-0623 | Muerte por amianto - demanda de responsabilidad contra la empresa | `muerte-amianto-demanda-responsabilidad-contra-empresa-lab-0623` |
| LAB-0624 | Ingreso mínimo vital denegado - demanda al INSS | `ingreso-minimo-vital-denegado-demanda-inss-lab-0624` |
| LAB-0625 | Ingreso mínimo vital denegado - reclamación previa | `ingreso-minimo-vital-denegado-reclamacion-previa-lab-0625` |
| LAB-0626 | Suplicación para elevar la incapacidad permanente de parcial a total | `suplicacion-elevar-incapacidad-permanente-parcial-total-lab-0626` |
| LAB-0627 | Suplicación para elevar la incapacidad permanente de total a absoluta | `suplicacion-elevar-incapacidad-permanente-total-lab-0627` |
| LAB-0628 | Pedir cambio de puesto por embarazo o lactancia | `pedir-cambio-puesto-embarazo-lactancia-lab-0628` |
| LAB-0629 | Daños y perjuicios por accidente de trabajo - papeleta de conciliación | `danos-perjuicios-accidente-trabajo-papeleta-lab-0629` |
| LAB-0630 | Riesgo durante la lactancia natural - demanda contra la Mutua | `riesgo-durante-lactancia-natural-demanda-contra-mutua-lab-0630` |
| LAB-0631 | Prestación por maternidad - demanda de reclamación | `prestacion-maternidad-demanda-reclamacion-lab-0631` |
| LAB-0632 | Aptitud tras el reconocimiento médico - declaración | `aptitud-tras-reconocimiento-medico-declaracion-lab-0632` |
| LAB-0633 | Accidente de trabajo por falta de seguridad en contrata o subcontrata - demanda de indemnización | `accidente-trabajo-falta-seguridad-contrata-subcontrata-lab-0633` |
| LAB-0634 | Determinar la contingencia de la incapacidad temporal - demanda | `determinar-contingencia-incapacidad-temporal-demanda-lab-0634` |
| LAB-0636 | Pensión de viudedad del cónyuge separado judicialmente - demanda | `pension-viudedad-conyuge-separado-judicialmente-demanda-lab-0636` |
| LAB-0637 | Autónomo - demanda de prestación económica por incapacidad | `autonomo-demanda-prestacion-economica-incapacidad-lab-0637` |
| LAB-0638 | Gastos médicos por asistencia urgente y vital - demanda de reintegro (modelo 1) | `gastos-medicos-asistencia-urgente-vital-demanda-lab-0638` |
