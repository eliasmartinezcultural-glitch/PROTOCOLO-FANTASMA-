# Modelo de datos y sistema visual — siguiente capa

**Objetivo:** transformar evidencia dispersa en un mapa navegable, visual y auditable, sin tocar la aplicación congelada hasta aprobar una integración.

## 1. Principio visual

**La pantalla tiene que revelar complejidad sin obligar a leerla toda.** El primer golpe de vista resume; cada tarjeta abre una ficha; cada ficha llega a su evidencia.

Jerarquía recomendada:
1. **Panorama:** qué cambió recientemente, asuntos abiertos, evidencia nueva y documentos faltantes.
2. **Mapa territorial:** temas por área/barrio/paraje solo cuando la ubicación sea pública y suficientemente amplia.
3. **Política e instituciones:** cargos, expedientes, votaciones y relaciones documentadas.
4. **Gestión y dinero:** presupuesto, compromisos, compras, obras y rendiciones.
5. **Pulso social:** temas mencionados, procedencia, fecha y diversidad de fuentes.
6. **Archivo:** fuentes primarias, prensa, fotografías, actas, ordenanzas y versiones.

No llenar el panorama de tarjetas pequeñas. Mantener pocas señales principales y permitir profundizar con un clic.

## 2. Entidades de información

### Evidencia
- `id`, título, URL, fuente/emisor, autor, tipo, fecha del hecho, fecha de publicación.
- Tema, subtema, zona amplia, resumen fiel, citas breves.
- Estado de verificación, nivel de evidencia, vigencia, contradicciones y próximos pasos.
- Archivos relacionados, actor(es), expediente(s), obra(s) o compromiso(s).

### Actor / institución
- ID, nombre, tipo (persona pública, organismo, partido/espacio, empresa contratista, organización).
- Cargo y período, con fuente oficial.
- Declaraciones públicas, proyectos, votos, funciones, actos y vínculos documentados.
- No inferir afinidad privada ni relación personal a partir de una foto o coincidencia.

### Expediente / decisión
- ID, título, organismo, fechas clave, materia, estado y resultado.
- Número de expediente, nota, ordenanza, decreto, acta o resolución.
- Votos nominales, mayoría exigida y fundamento documentado.
- Alegaciones de cada parte separadas de las decisiones formales.
- Estado actual y documentación faltante.

### Obra / programa
- Nombre, ubicación general, organismo responsable, fuente de financiación.
- Anuncio, presupuesto oficial, monto adjudicado, contrato, modificaciones, pagos, plazo.
- Avance físico y financiero con fecha de medición.
- Recepción, puesta en funcionamiento y beneficiarios reportados.
- No mostrar “avance” si solo hay un anuncio o una adjudicación.

### Indicador presupuestario
- Período fiscal, categoría, monto, unidad, fuente y fecha.
- Tipo: presupuesto inicial / modificado / devengado / pagado / saldo.
- Regla de cálculo y cobertura.
- Los montos de diferentes etapas no se comparan como si fueran el mismo indicador.

### Señal social
- Fecha, tema, fuente y tipo de fuente (testimonio, reunión pública, reclamo formal, encuesta, prensa).
- Tono descriptivo opcional, pregunta/tema, estado de seguimiento y respuesta institucional.
- No guardar nombre, teléfono, dirección exacta ni datos sensibles de un vecino salvo necesidad legítima, autorización y almacenamiento seguro.
- Un testimonio no representa a todo el barrio ni a toda la población.

## 3. Visualizaciones útiles y qué deben probar

| Visual | Pregunta que responde | Datos necesarios |
|---|---|---|
| Línea de tiempo | ¿Qué pasó y en qué orden? | Eventos con fecha, fuente y estado |
| Grafo de actores | ¿Qué vínculos públicos están documentados? | Actores, tipo de relación, evidencia y fecha |
| Matriz de votaciones | ¿Quién votó qué expediente y con qué resultado? | Acta o registro nominal |
| Presupuesto en capas | ¿Qué se aprobó, modificó, ejecutó y pagó? | Series comparables y definiciones |
| Tablero de obras | ¿En qué etapa está cada obra? | Documentación de cada hito |
| Mapa temático | ¿Dónde se concentran asuntos documentados? | Ubicación pública y criterio consistente |
| Radar social | ¿Qué temas aparecen en las fuentes registradas? | Registros fechados, origen y diversidad |
| Cumplimiento de compromisos | ¿Qué promesas tienen evidencia de avance? | Compromiso explícito, indicador y fuente |
| Matriz de incertidumbre | ¿Qué sabemos y qué falta? | Estado de evidencia y preguntas abiertas |

## 4. Semáforo documental

- **Verde — confirmado documentalmente:** documento primario localizado y pertinente.
- **Azul — declaración atribuida:** alguien identificable afirmó algo públicamente.
- **Amarillo — en verificación:** una fuente lo informa, falta documento primario o contraste.
- **Naranja — contradictorio:** existen versiones incompatibles o una impugnación no resuelta.
- **Gris — dato faltante/desactualizado:** no hay evidencia suficiente o la información perdió vigencia.

El color debe acompañarse siempre con texto y fecha; nunca ser la única señal.

## 5. Imágenes y material gráfico

Cada imagen debe llevar:
- Autor o institución que la publica.
- Fecha y ubicación general cuando estén confirmadas.
- URL original y licencia/permiso de uso cuando corresponda.
- Pie que describa lo visible, sin sugerir que prueba hechos que no muestra.
- Etiqueta de material ilustrativo si no documenta el hecho.

Usos recomendados:
- Fotografías oficiales de obras, con fecha y etapa identificada.
- Capturas de documentos originales, con página/artículo visible y enlace al documento completo.
- Mapas esquemáticos de instituciones y expedientes.
- Diagramas de proceso normativo.
- Gráficos hechos desde tablas oficiales, con unidad, período y fuente.
- Retratos de personas públicas solo desde fuentes confiables y con contexto.

No usar imágenes generadas por IA como prueba documental ni imágenes de personas inventadas para representar a protagonistas reales.

## 6. Ciclo de trabajo

1. Detectar noticia o tema.
2. Abrir un expediente de investigación.
3. Buscar documento primario.
4. Guardar evidencia y registrar metadatos.
5. Contrastar con una fuente independiente cuando sea posible.
6. Separar hechos, declaraciones, interpretaciones y vacíos.
7. Construir visual desde datos verificables.
8. Revisar fecha de actualización y enlazar cada señal a su evidencia.
9. Recién después evaluar integrar la información en la aplicación.

## 7. Condiciones antes de integrar en la interfaz

- La base congelada no se edita.
- Las nuevas funciones se desarrollan en rama de trabajo y en archivos separados.
- Ningún dato se incorpora a un indicador sin fuente, fecha y definición.
- Ningún índice de temperatura social se convierte en aprobación de gobierno.
- No se publica información sensible de vecinos ni información de trabajo confidencial.
- La clave visual de una web estática pública no es seguridad real: los documentos internos no deben incluirse en un repositorio público.
