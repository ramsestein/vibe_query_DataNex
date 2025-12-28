# Vibe SQL Copilot - DataNex

Este repositorio contiene el archivo `vibe_SQL_copilot.txt`, una base de conocimiento consolidada de la wiki de DataNex y sus diccionarios de datos, optimizada para ser utilizada como contexto en asistentes de IA (LLMs) para generación de consultas SQL.

## 📋 ¿Qué contiene este archivo?

El archivo `vibe_SQL_copilot.txt` incluye:

1. **Prompt base**: Instrucciones para el asistente de IA sobre cómo generar consultas SQL
2. **Documentación de la wiki**: Contenido completo de las páginas útiles de la wiki de DataNex (sin páginas administrativas o de descarte)
3. **Diccionarios de datos unificados**: Todos los diccionarios CSV consolidados con descripciones de tablas y columnas

## 🚀 Cómo usar este archivo

### Con Claude, ChatGPT u otros LLMs

1. **Copia el contenido completo** del archivo `vibe_SQL_copilot.txt`
2. **Pégalo al inicio de tu conversación** con el asistente de IA
3. **Haz tu pregunta** sobre consultas SQL o análisis de datos de DataNex

Ejemplo:
```
[Pegar contenido de vibe_SQL_copilot.txt]

Usuario: "Necesito una consulta SQL que me muestre todos los pacientes 
que tuvieron una cirugía en los últimos 6 meses"
```

### Con Cursor AI o similares

1. **Añade el archivo como contexto** usando `@vibe_SQL_copilot.txt`
2. El asistente tendrá acceso automático a toda la información
3. **Haz tus preguntas** directamente

### Con APIs de OpenAI, Anthropic, etc.

```python
# Ejemplo con OpenAI API
with open('vibe_SQL_copilot.txt', 'r', encoding='utf-8') as f:
    context = f.read()

response = client.chat.completions.create(
    model="gpt-4",
    messages=[
        {"role": "system", "content": context},
        {"role": "user", "content": "Tu consulta SQL aquí"}
    ]
)
```

## 📊 Estructura del archivo

```
┌─────────────────────────────────────┐
│ PROMPT BASE                         │
│ (Instrucciones para el asistente)  │
├─────────────────────────────────────┤
│ DOCUMENTACIÓN DE LA WIKI            │
│ - Overview                          │
│ - Procedimientos                    │
│ - Diagnósticos                      │
│ - FAQs                              │
│ - etc.                              │
├─────────────────────────────────────┤
│ DICCIONARIOS DE DATOS               │
│ - Tablas y columnas                 │
│ - Descripciones                     │
│ - Referencias (_ref)                │
│ - Descripciones detalladas (_descr) │
└─────────────────────────────────────┘
```

## ⚠️ Consideraciones importantes

### Tamaño del archivo
- El archivo tiene aproximadamente **39,000 líneas**
- Ocupa alrededor de **~2-3 MB** de texto plano
- Algunos LLMs tienen límites de contexto, verifica:
  - GPT-4: 128K tokens (~100K palabras)
  - Claude 3: 200K tokens (~150K palabras)
  - GPT-3.5: 16K tokens (~12K palabras) ⚠️ Puede ser insuficiente

### Limitaciones de contexto
Si tu LLM tiene un contexto limitado:
1. **Divide el contenido**: Usa solo las secciones relevantes para tu consulta
2. **Prioriza**: 
   - Prompt base (siempre incluir)
   - Diccionarios de datos (altamente recomendado)
   - Páginas de wiki específicas según necesidad

### Actualización
Este archivo se actualiza automáticamente mediante un pipeline que:
- Descarga las últimas páginas de la wiki de DataNex
- Filtra páginas según criterios de utilidad
- Unifica diccionarios de datos actualizados
- Genera el archivo final consolidado

## 🔄 Última actualización

El archivo se actualiza automáticamente cada vez que se ejecuta el pipeline de DataNex.

Para ver la fecha exacta de la última actualización, revisa la fecha del último commit en este repositorio.

## 📚 Más información

Para más detalles sobre el proyecto DataNex y el pipeline de generación:
- **Repositorio principal**: [pipeline_datanex](https://github.com/ramsestein/vibe_SQL_Datanex)
- **Wiki de DataNex**: [DataScope Wiki](https://gitlab.com/dsc-clinic/datascope/-/wikis/home)

## 📄 Licencia

Este contenido está basado en la documentación de DataNex/DataScope.


