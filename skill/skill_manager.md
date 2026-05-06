# [SISTEMA] Skill Manager & Installer v1.1
**Objetivo:** Automatizar la creación de archivos y el registro de nuevas funcionalidades en el entorno Antigravity.

## Protocolo de Operación
Al recibir una nueva Skill, debo:
1. **Analizar**: Extraer Nombre, Descripción y Lógica del contenido.
2. **Escribir**: Crear el archivo `.md` en la carpeta `skill/` usando la función `write_to_file`.
3. **Registrar**: Actualizar el `skills_manifest.json` añadiendo la nueva entrada y sumando +1 al contador total.
4. **Confirmar**: Notificar que la instalación ha finalizado.
