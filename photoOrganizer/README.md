# Skill: photoOrganizer

Módulo de gobernanza y orquestación para agentes LLM en Google Antigravity y Claude que operan el servidor **PhotOrganizer MCP**.

## Propósito
Permite a cualquier agente automatizar la clasificación, limpieza de duplicados y estructuración de colecciones multimedia complejas siguiendo las directivas de biometría facial, detección corporal y ruteo grupal del proyecto `photOrganizer`.

## Prerrequisitos
- Servidor `photo-organizer` configurado en `mcp_config.json`.
- Entorno Python 3.11+ con `insightface`, `onnxruntime-directml` (o `onnxruntime-gpu`), `ultralytics` y `scikit-learn`.
- Repositorio del motor: `c:\git\photOrganizer`.

## Arquitectura de la Skill
- `SKILL.md`: Contrato operativo y directivas bajo progressive disclosure. Contiene el flujo en 5 fases, los 7 invariantes canónicos de ruteo y el catálogo de herramientas FastMCP.
- `README.md`: Este documento explicativo.

## Integración con el Arnés Antigravity
La skill invoca las herramientas del servidor registrado en `C:\Users\Diego\.gemini\antigravity\mcp_config.json`:
```json
"photo-organizer": {
  "command": "C:\\Users\\Diego\\AppData\\Local\\Programs\\Python\\Python313\\python.exe",
  "args": ["-m", "photo_mcp.server"],
  "env": { "PYTHONIOENCODING": "utf-8" }
}
```

## Entregables y Artefactos Producidos
1. `manifest.json`: Generado en cada carpeta organizada con cabecera `total_files` para auditoría O(1).
2. `embeddings.npy`: Persistencia binaria de los vectores faciales representativos (ilimitados) de cada persona conocida.
3. `reporte_organizacion.json` y `reporte_duplicadas.json`: Reportes detallados de auditoría persistidos en disco para evitar inflar el contexto del modelo.

## Reglas de Seguridad y Buenas Prácticas
1. **Verificación O(1)**: Antes de procesar cualquier carpeta, usar `verify_folder` para evitar re-inferencias innecesarias si la cabecera coincide.
2. **Respaldo de Integridad**: Utilizar siempre `action="dry_run"` antes de `action="move"` en colecciones nuevas.
3. **Embeddings Ilimitados**: No aplicar filtros restrictivos de cantidad a las fotos de personas conocidas en `sync_known_people`; preservar todos los vectores para maximizar el recall biométrico.
