# LEXTRACK — Tu proceso bajo control

**Agente orientador jurídico y plataforma de gestión judicial.**
LEXTRACK es el núcleo de **DERECHOS 360**: acompaña al ciudadano a organizar sus procesos, entender cada etapa, controlar plazos y preparar escritos, sin sustituir la asesoría de un abogado.

---

## 1. Qué incluye este proyecto

| Ruta | Función |
| --- | --- |
| `index.html` | Plataforma web de un solo archivo: Centro Operativo, tres herramientas jurídicas, tema claro/oscuro y exportaciones. |
| `.opencode/agents/lextrack.md` | Definición del agente LEXTRACK: identidad, instrucciones y skills. **Se conserva sin cambios.** |
| `opencode.jsonc` | Configuración de OpenCode; `default_agent` es `lextrack`. **Se conserva sin cambios.** |
| `lextrack/` | Memoria del agente: expedientes, documentos, calendario, alertas, plazos y scripts de recordatorios. Consulta su propio `lextrack/README.md`. **Se conserva sin cambios.** |
| `README.md` | Esta guía. |

No hay proceso de compilación ni servidor: la plataforma se abre directamente en el navegador.

---

## 2. Cómo usar LEXTRACK

### Desde OpenCode

El agente está disponible por defecto como `lextrack` y también puede invocarse como subagente:

> «Usa el subagente lextrack para revisar mis vencimientos y actualizar las alertas.»

Puedes pedirle, entre otras cosas:

- `Registra mi caso: expediente 123/2024, juicio oral, Juzgado 2º de Primera Instancia.`
- `¿En qué etapa está mi proceso?`
- `¿Qué tengo pendiente?`
- `Resumen de todos mis casos.`
- `Tengo una audiencia el 25/11/2026 a las 10:00 en el juzgado.`

### Desde la plataforma web

Abre `index.html` en un navegador y pulsa **Abrir Centro de Control**. Necesitas conexión a internet para cargar Tailwind CSS, Lucide, las tipografías y el efecto de confeti; tus datos no salen del equipo.

El Centro Operativo está organizado en tres grupos de pestañas:

- **Gestión:** Expedientes, Semáforo Alertas, Agenda y Audiencias, Bóveda Documental.
- **Herramientas jurídicas:** Analizador de casos, Normas y jurisprudencia, Generador de escritos.
- **Agente y datos:** Simulador LEXTRACK, Exportar Markdown.

---

## 3. Herramientas jurídicas integradas

Las tres herramientas están conectadas entre sí y con los expedientes del Centro Operativo: el resultado de una alimenta a la siguiente.

| Herramienta | Qué hace | Conexión con las demás |
| --- | --- | --- |
| **Analizador inteligente de casos** | Recibe el relato del ciudadano en lenguaje cotidiano (o carga un expediente existente), ordena los hechos, identifica el posible problema jurídico, reconoce derechos posiblemente vulnerados, señala nivel de urgencia y propone una ruta de atención. | Sus temas pasan al buscador y su contenido al generador. |
| **Buscador de normas y jurisprudencia colombiana** | Consulta un catálogo integrado de Constitución, leyes, códigos y decretos; filtra por tema, área y tipo de fuente; muestra la fuente de cada referencia. | El botón **Verificar en fuentes oficiales** abre SUIN-Juriscol, Corte Constitucional, Corte Suprema, Consejo de Estado y Función Pública. **Usar en documento** envía la norma al generador. |
| **Generador de documentos jurídicos** | Elabora derechos de petición, acciones de tutela, reclamaciones, quejas, denuncias y solicitudes generales. Produce un borrador editable que se puede copiar, descargar en `.txt` y guardar. | Puede tomar datos de un expediente, del analizador o de las normas consultadas. |

### Flujo recomendado

1. **Analizador:** escribe el caso y pulsa **Analizar caso**.
2. **Buscador:** pulsa **Buscar normas relacionadas** y verifica la vigencia en los portales oficiales.
3. **Generador:** pulsa **Generar documento**, revisa el borrador y descárgalo o guárdalo.

> Los resultados son orientativos. El buscador muestra referencias y enlaces de verificación; no consulta en tiempo real el texto vigente de cada norma ni afirma que una sentencia específica aplica al caso.

---

## 4. Apariencia

- **Paleta pastel:** rosado empolvado, lila y morado suave, lavanda, azul pastel, blanco cálido y neutros.
- **Tipografías:** DM Sans para textos, botones y etiquetas; Playfair Display para títulos y encabezados.
- **Organización:** pestañas agrupadas con ajuste automático en varias filas, tarjetas de tamaño coherente y diseño responsive para computador y móvil.
- **Modo claro / oscuro:** selector en la barra superior (iconos sol y luna). La elección se recuerda en el navegador y se aplica antes de que cargue la página. El modo oscuro adapta todas las superficies manteniendo la misma paleta suave.

---

## 5. Datos, privacidad y exportación

- Todo se guarda localmente en `localStorage` del navegador:
  - `lextrack_workspace_data_v2`: expedientes, eventos, documentos, notas e historial.
  - `lextrack_herramientas_juridicas_v1`: análisis, normas seleccionadas y borradores.
  - `lextrack_tema`: preferencia de apariencia.
- No hay servidor, cuentas ni rastreo. Los enlaces a fuentes jurídicas solo se abren cuando el usuario los pulsa.
- Se puede exportar a **ZIP Markdown**, copia de seguridad **JSON**, agenda **iCal** y archivos Markdown individuales.

---

## 6. Recordatorios

La generación y programación de recordatorios (modo local o envío por correo) se documenta en `lextrack/README.md`. Los scripts están en `lextrack/scripts/`.

---

## 7. Límites importantes

LEXTRACK es una herramienta de organización y acompañamiento. **No es un abogado ni sustituye la asesoría profesional.**

- Los plazos y las rutas son orientativos: verifícalos con el juzgado, la entidad o tu abogado.
- El analizador no declara vulneraciones definitivas; reconoce posibles derechos a partir de lo que escribe la persona.
- Las normas y sentencias deben confirmarse en las fuentes oficiales antes de citarse en un escrito.
- Los documentos generados son borradores: revisa hechos, destinatario, fundamentos y anexos antes de radicarlos.
