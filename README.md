# Proyecto Base para Agentes de IA

Plantilla estructural optimizada para el desarrollo de software asistido por Inteligencia Artificial y agentes autónomos. Está diseñada para maximizar la eficiencia de tokens y mantener al agente enfocado en el contexto correcto.

## Estructura del Proyecto
- `/.agent`: Cerebro y memoria del agente.
  - `/templates`: Plantillas base (prompts, roadmaps, historial). Usa etiquetas XML para optimizar la comprensión del LLM.
  - `/conventions`: Archivos de convenciones técnicas específicas para que el agente lea solo lo necesario (carga diferida).
  - `/archive`: Archivos históricos para liberar la memoria activa del agente.
- `/docs`: Contexto y guías estáticas.
  - `/requirements`: Definición de lo que se va a construir.
  - `/documentation`: Manuales y referencias técnicas.
  - `/history`: Registro de cambios, comandos ejecutados y decisiones tomadas.
- `/src`: Código fuente de la aplicación.
- `/tests`: Pruebas unitarias y de integración.

## Cómo empezar
1. Clona este repositorio y utilízalo como plantilla para tu proyecto.
2. Copia el archivo `.env.example` a `.env` y añade tus variables locales.
3. Edita `.agent/templates/prompt-template.md` rellenando los campos como el nombre y descripción del proyecto.
4. Instruye a tu agente a que inicialice su contexto leyendo `.agent/system-basic.md` y `.agent/roadmap.md`.
5. Reemplaza el contenido de este README con la información real de tu aplicación una vez comiences el desarrollo.