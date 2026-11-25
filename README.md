# Seguridad Social en la empresa, incapacidad y accidentes de trabajo

> Plugin de Claude Code `formularios-seguridad-social-en-la-empresa` · **27 formularios** · Laboral · normativa revisada el 25-11-2026 · requiere Jurisprudenciator

## Para qué sirve

Para la Seguridad Social desde la empresa: incapacidad temporal y permanente en la relación laboral, accidentes de trabajo y enfermedad profesional, responsabilidad empresarial, FOGASA, certificaciones de descubiertos y comunicaciones con la mutua y la Tesorería.

Cada formulario es una skill: Claude lo rellena contigo paso a paso y te entrega el documento en Word, con las normas comprobadas en el BOE. Cada skill explica en su `SKILL.md` qué es el formulario, para qué sirve, cómo se usa, qué datos necesita y qué avisos normativos lleva; el formulario seco, listo para rellenar, está en `assets/formulario.md` dentro de la carpeta de la skill.

## Qué puedes hacer con él

Estos son los tipos de documento que trae, con algunos ejemplos (la lista completa de los 27 está al final):

- **Demandas, peticiones y solicitudes iniciales** (3). Por ejemplo: Demanda por complemento de maternidad en pensión de jubilación contributiva; Demanda de indemnización a la ETT y a la usuaria por accidente de trabajo por falta de seguridad; Demanda contra el FOGASA por salarios o indemnización por despido impagados.
- **Estatutos, actas, certificaciones y escrituras** (1). Por ejemplo: Certificación negativa de descubiertos de la subcontratista - solicitud a la Tesorería.
- **Comunicaciones, requerimientos y cartas** (3). Por ejemplo: Aviso de reincorporación tras el alta por denegarse la incapacidad permanente o ser solo parcial; Solicitud al FOGASA del pago de prestaciones de garantía salarial; Comunicación a la TGSS de la identidad de la empresa principal de la contrata.
- **Escritos de trámite y otros** (20). Por ejemplo: Respuesta de la empresa a suspensión o permiso por fallecimiento en incendios forestales; Pedir suspensión del contrato por incendios forestales; Incapacidad permanente - demanda genérica.

## Cómo se usa

1. **Pídelo con tus palabras.** Cuéntale a Claude qué documento necesitas y para qué caso; él elige el formulario. Por ejemplo:
   - «Demanda de responsabilidad empresarial por un accidente de trabajo»
   - «Solicitud de certificación negativa de descubiertos a la Tesorería»
   - «Demanda contra el FOGASA por salarios e indemnizaciones»
2. **Si no da con el formulario**, empieza por el índice del plugin: escribe `/formularios-seguridad-social-en-la-empresa:indice` y cuéntale lo que necesitas. Te propondrá el formulario que mejor encaja (o dos o tres para que elijas).
3. **Si ya sabes cuál quieres**, llámalo por su nombre de skill, por ejemplo `/formularios-seguridad-social-en-la-empresa:respuesta-empresa-suspension-permiso-fallecimiento-lab-0616`. Los nombres están en la lista de formularios de abajo.

## Qué hace Claude cuando usas un formulario

1. Comprueba que Jurisprudenciator está conectado. Si no lo está, se para y te dice cómo conectarlo: no redacta nada sin él. Todos los datos jurídicos del documento (artículos vigentes, sentencias con su ECLI, datos registrales) salen de Jurisprudenciator; nunca de memoria.
2. Te pide en una sola tanda los datos del caso (partes, órgano, fechas, importes…). Lo que no sepas queda como hueco visible.
3. Resuelve contigo las opciones que el formulario deja abiertas y decide qué párrafos opcionales entran según los hechos.
4. Aplica las notas de actualización de la revisión del 25-11-2026 (reformas legales, órganos judiciales de la LO 1/2025, plazos).
5. Comprueba en el BOE, con Jurisprudenciator, cada norma que cita el documento; si alguna ha cambiado, usa la redacción vigente y te lo dice.
6. Te entrega el documento en Word **tal cual es el formulario**: empieza por su primera línea, sin títulos, notas ni explicaciones añadidas, en Times New Roman 11, interlineado 1,15 y texto justificado. En el chat te dice lo que queda pendiente y, si es un escrito, el plazo y ante quién se presenta.

El resultado es un borrador para que lo revise un profesional antes de usarlo.

## Antes de empezar

- **Dónde funciona:** en Claude Code y en Claude (web, escritorio y Cowork). Se instala desde este repositorio de GitHub o subiendo el ZIP del plugin.
- **Jurisprudenciator es imprescindible:** el plugin trae el conector y cada skill trabaja siempre con él. Sin una cuenta de Jurisprudenciator conectada, las skills se paran y no redactan nada. La primera vez hay que iniciar sesión (en Claude Code, con `/mcp`; o con tu URL personal: https://jurisprudenciator.lexiaipro.org/instalacion). Si ya tienes Jurisprudenciator conectado en Claude, las skills usan ese.
- **Espacio que ocupa:** unos 1.605 tokens en cada conversación mientras esté activado, porque Claude lleva en memoria la descripción de cada skill. Activa solo los plugins que vayas a usar; los demás puedes desactivarlos sin desinstalarlos (`claude plugin disable formularios-seguridad-social-en-la-empresa@formularios-seguridad-social-en-la-empresa`).

## Instalación

En Claude Code, añade el catálogo (solo la primera vez) e instala el plugin:

```
/plugin marketplace add DerechoVirtual/formularios-seguridad-social-en-la-empresa
/plugin install formularios-seguridad-social-en-la-empresa@formularios-seguridad-social-en-la-empresa
```

En Claude (web, escritorio o Cowork): **Personalizar → Plugins → Añadir marketplace** con la dirección `https://github.com/DerechoVirtual/formularios-seguridad-social-en-la-empresa`, o sube el ZIP del plugin ([descargar ZIP](https://github.com/DerechoVirtual/formularios-seguridad-social-en-la-empresa/releases/latest/download/formularios-seguridad-social-en-la-empresa.zip)).

Para comprobar que está instalado: `claude plugin list`.

## Lista completa de formularios (27)

| Código | Formulario | Skill |
|---|---|---|
| LAB-0616 | Respuesta de la empresa a suspensión o permiso por fallecimiento en incendios forestales | `respuesta-empresa-suspension-permiso-fallecimiento-lab-0616` |
| LAB-0617 | Pedir suspensión del contrato por incendios forestales | `pedir-suspension-contrato-incendios-forestales-lab-0617` |
| LAB-0618 | Incapacidad permanente - demanda genérica | `incapacidad-permanente-demanda-generica-lab-0618` |
| LAB-0620 | Demanda por complemento de maternidad en pensión de jubilación contributiva | `demanda-complemento-maternidad-pension-jubilacion-lab-0620` |
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
| LAB-0635 | Certificación negativa de descubiertos de la subcontratista - solicitud a la Tesorería | `certificacion-negativa-descubiertos-subcontratista-lab-0635` |
| LAB-0636 | Pensión de viudedad del cónyuge separado judicialmente - demanda | `pension-viudedad-conyuge-separado-judicialmente-demanda-lab-0636` |
| LAB-0637 | Autónomo - demanda de prestación económica por incapacidad | `autonomo-demanda-prestacion-economica-incapacidad-lab-0637` |
| LAB-0638 | Gastos médicos por asistencia urgente y vital - demanda de reintegro (modelo 1) | `gastos-medicos-asistencia-urgente-vital-demanda-lab-0638` |
| LAB-0639 | Demanda de indemnización a la ETT y a la usuaria por accidente de trabajo por falta de seguridad | `demanda-indemnizacion-ett-usuaria-accidente-trabajo-lab-0639` |
| LAB-0640 | Demanda contra el FOGASA por salarios o indemnización por despido impagados | `demanda-contra-fogasa-salarios-indemnizacion-despido-lab-0640` |
| LAB-0641 | Aviso de reincorporación tras el alta por denegarse la incapacidad permanente o ser solo parcial | `aviso-reincorporacion-tras-alta-denegarse-incapacidad-lab-0641` |
| LAB-0642 | Solicitud al FOGASA del pago de prestaciones de garantía salarial | `solicitud-fogasa-pago-prestaciones-garantia-salarial-lab-0642` |
| LAB-0644 | Comunicación a la TGSS de la identidad de la empresa principal de la contrata | `comunicacion-tgss-identidad-empresa-principal-contrata-lab-0644` |

## Privacidad

Ver `PRIVACY.md`.
