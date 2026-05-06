# Antigravity Skill Manager v1.1

Sistema modular diseñado para la **instalación, validación y registro automatizado** de habilidades (skills) dentro del ecosistema **Google Antigravity**.

## 🚀 Propósito
Este gestor actúa como un "administrador de paquetes" interno, permitiendo que el Agente de IA aprenda y despliegue nuevas capacidades técnicas siguiendo un protocolo estricto de seguridad y orden.

## 🛠️ Estructura del Core
El sistema se basa en dos archivos fundamentales que deben residir en la carpeta `/skill/`:

1. **`skill_manager.md`**: El "cerebro" que contiene la lógica de instalación.
2. **`skills_manifest.json`**: El inventario centralizado de todas las herramientas instaladas.

## 📋 Protocolo de Operación
Cada vez que se instala una nueva skill, el gestor ejecuta 4 pasos:
1. **Analizar**: Extrae Nombre, Descripción y Lógica del contenido.
2. **Escribir**: Crea el archivo físico en el entorno local.
3. **Registrar**: Actualiza el manifiesto central con la nueva entrada.
4. **Confirmar**: Notifica que la herramienta está operativa.

## 💻 Instalación Rápida
Para comenzar, clona este repositorio en tu directorio de trabajo local y asegúrate de que la ruta `/skill/` esté correctamente mapeada en tu proyecto de Antigravity.
