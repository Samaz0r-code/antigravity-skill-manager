---
name: mcp-installer
description: Guía y automatización para la instalación, registro y actualización de servidores MCP y sus respectivas habilidades (skills) en el entorno Antigravity.
version: 1.0.0
---

# MCP Installer & Manager Skill

Esta habilidad define el procedimiento estandarizado para descargar, instalar, registrar y desplegar servidores de Protocolo de Contexto de Modelo (MCP) y sus habilidades asociadas en el entorno Antigravity de manera robusta y automatizada.

## Procedimiento de Instalación de un MCP

Cuando se te solicite instalar un nuevo servidor MCP desde un repositorio de GitHub u otra fuente:

### 1. Clonación y Análisis
- Clona temporalmente el repositorio del servidor MCP en una carpeta temporal (ej: `temp_mcp`).
- Inspecciona el archivo `README.md` y la estructura del proyecto para identificar:
  - Tipo de servidor (Node.js, Python/uv, Go, binario independiente, etc.).
  - Comandos necesarios para compilar o iniciar el servidor.
  - Dependencias y prerrequisitos del sistema.
  - Existencia de subcarpetas de habilidades (`skills/`, `.claude-plugin/`, `.cursor-plugin/`).

### 2. Preparación y Compilación/Instalación
- **Python (uv)**: Crea el entorno virtual con `uv venv`, sincroniza dependencias con `uv pip install` o `uv sync`, y asegúrate de que el comando de ejecución apunte a `.venv/Scripts/python.exe` (Windows) o `.venv/bin/python` (Unix).
- **Node.js**: Instala las dependencias usando `npm install` o `pnpm install`, compila si es necesario (`npm run build`), y usa `node` con la ruta al archivo de entrada (`dist/index.js` o similar).
- **Go**: Compila el binario usando `go build -o binario` y registra la ruta absoluta del binario generado.

### 3. Registro en `mcp_config.json`
Modifica y sincroniza la configuración de servidores MCP en los siguientes tres directorios críticos de Antigravity del usuario:
1. `C:\Users\samaz\.gemini\config\mcp_config.json`
2. `C:\Users\samaz\.gemini\antigravity-ide\mcp_config.json`
3. `C:\Users\samaz\.gemini\antigravity-backup\mcp_config.json`

Agrega el bloque de configuración del servidor dentro del objeto `"mcpServers"` de la siguiente forma:
```json
    "nombre-del-servidor": {
      "command": "ruta\\absoluta\\al\\ejecutable",
      "args": ["-m", "modulo"] u otros argumentos,
      "env": {
        "VARIABLES_DE_ENTORNO": "valores"
      }
    }
```
*Nota: Recuerda duplicar las barras inclinadas hacia atrás (`\\`) en las rutas de Windows.*

### 4. Gestión de Habilidades (Skills)
Si el repositorio del MCP contiene habilidades bajo `skills/` o carpetas similares:
- Copia recursivamente las carpetas de habilidades a:
  - Directorio del proyecto: `C:\Proyectos\Antigravity\skill\<categoría>\<nombre-mcp>-skills\`
  - Directorio de plugins del agente: `C:\Users\samaz\.gemini\config\plugins\antigravity-project-skills\skills\<categoría>\<nombre-mcp>-skills\`
- Actualiza el archivo `C:\Proyectos\Antigravity\skill\skills_manifest.json`:
  - Incrementa la propiedad `total_skills`.
  - Agrega la entrada de cada habilidad en el array `installed_skills` con su `id`, `category`, `name`, `path` relativo al manifiesto, `description`, `version`, e `installed_on` (fecha de hoy).

### 5. Limpieza y Despliegue en Git
- Elimina la carpeta temporal de clonación.
- Agrega los cambios en el proyecto (`C:\Proyectos\Antigravity`) al área de preparación de Git.
- Realiza el commit correspondiente (ej: `feat: add <mcp-name> MCP server and skills`).
- Realiza un push a la rama principal de GitHub.
