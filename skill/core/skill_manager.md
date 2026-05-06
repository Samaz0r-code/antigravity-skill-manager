# [SISTEMA] Skill Manager & Installer v1.1
**Objetivo:** Automatizar la creación de archivos y el registro de nuevas funcionalidades en el entorno Antigravity.

## Protocolo de Operación
Al recibir una nueva Skill, debo:
1. **Analizar**: Extraer Nombre, Descripción y Lógica del contenido.
2. **Categorizar**: Identificar la carpeta adecuada (`marketing/`, `content/`, `ads/`, `automation/`, `design/`, `core/`).
3. **Escribir**: Crear el archivo `.md` en la subcarpeta correspondiente de `skill/`.
4. **Registrar**: Actualizar el `skills_manifest.json` añadiendo la entrada (con su categoría) y sumando +1 al contador total.
5. **Confirmar**: Notificar que la instalación ha finalizado.
