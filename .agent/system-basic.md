## Estructura básica
El proyecto debe seguir esta estructura de carpetas como punto inicial:
```
/
├── .agent/
│   ├── system-prompt.md        # Especifica el rol, objetivos y metodología de trabajo del agente.
│   ├── roadmap.md              # Define las fases, tareas pendientes y el estado actual.
│   ├── system-basic.md         # Restricciones y comportamientos básicos inquebrantables.
│   ├── memory.md               # Registro a corto plazo de aprendizajes, resoluciones de bugs.
│   ├── archive/                # Historial de memoria purgada para ahorrar tokens (ej. memory-archive.md).
│   ├── conventions/            # Reglas específicas por tecnología (ej. react.md, python.md).
│   └── templates/              # Esquemas base (prompt-template.md, roadmap-template.md, etc).
├── .github/                    # (Opcional) Flujos de trabajo de CI/CD automatizados.
├── docs/
│   ├── documentation/          # Explicación técnica de módulos, APIs y arquitectura.
│   ├── requirements/           # Requisitos funcionales y no funcionales del proyecto.
│   └── history/                # Historial de versiones y decisiones arquitectónicas (ADRs).
├── src/                        # Código fuente principal de la aplicación.
├── tests/                      # Batería de pruebas automatizadas.
├── .env                        # Variables de entorno seguras.
├── .env.example                # Plantilla de variables de entorno.
├── .agentignore                # Archivos invisibles para el agente.
├── .gitignore                  # Archivos excluidos del control de versiones.
└── README.md                   # Punto de entrada con objetivos e instalación.
```
## Normativas básicas
El agente deberá cumplir estas directrices de forma estricta en cada interacción:

* **Gestión de contexto optimizada:** Al iniciar una tarea, lee obligatoriamente `.agent/roadmap.md` para entender el estado actual. Consulta los documentos en `/docs/` o `/requirements/` únicamente cuando sean indispensables para la orden recibida, evitando procesar todo el proyecto en cada interacción.
* **Respeto estricto del entorno (Agentignore):** Tienes estrictamente prohibido intentar leer, analizar, modificar o indexar cualquier archivo o directorio listado en el archivo `.agentignore` ubicado en la raíz del proyecto.
* **Control de cambios eficiente:** Realiza confirmaciones de control de versiones (ej. Git) con mensajes descriptivos para modificaciones regulares. Reserva la carpeta `/docs/history/` exclusivamente para documentar hitos de versión, despliegues o cambios de arquitectura.
* **Metodología TDD obligatoria (con excepciones):** Desarrolla toda nueva funcionalidad siguiendo un ciclo cerrado: 1) Escribe el test correspondiente en `/tests/`. 2) Verifica que el test falla. 3) Implementa la lógica mínima necesaria en `/src/`. 4) Verifica que el test pasa. 5) Refactoriza manteniendo la funcionalidad. *Excepción:* El TDD es obligatorio para la lógica de negocio y arquitectura, pero puede omitirse justificadamente para ajustes puramente visuales de la interfaz de usuario o modificaciones menores en scripts de configuración.
* **Calidad y Seguridad explícitas:** Escribe código limpio siguiendo los estándares de estilo oficiales del lenguaje utilizado. Aplica rigurosamente las prácticas de seguridad de OWASP Top 10 para prevenir vulnerabilidades en la arquitectura. No intentes leer o modificar directamente el archivo `.env` real en entornos de producción.
* **Autonomía de validación:** Itera sobre tu propio código de forma autónoma. Asegúrate de ejecutar las pruebas y validar que se cumplen los criterios de aceptación antes de dar una tarea por finalizada y actualizar el estado en el `roadmap.md`.
* **Memoria y Aprendizaje:** Documenta en `.agent/memory.md` cualquier resolución de un problema complejo, bloqueo persistente o configuración peculiar descubierta empíricamente para evitar repetir errores en futuras sesiones.
* **Estandarización de documentos:** Al crear o actualizar roadmaps, historiales o documentación, debes usar estrictamente las estructuras definidas en los archivos de la carpeta `/.agent/templates/` y en formato MarkDown.
* **Límites de acción y seguridad operativa:** Tienes terminantemente prohibido ejecutar comandos destructivos (como borrados masivos de directorios o sobrescritura de historiales como `git push --force`) sin pedir y recibir primero confirmación explícita del usuario.

* * * 
* **Gestión de contexto optimizada:** Al iniciar una tarea, lee obligatoriamente `.agent/roadmap.md` para entender el estado actual. Consulta los documentos en `/docs/` o `/requirements/` únicamente cuando sean indispensables para la orden recibida.
* **Respeto estricto del entorno (Agentignore):** Tienes estrictamente prohibido intentar leer, analizar, modificar o indexar cualquier archivo o directorio listado en el archivo `.agentignore` ubicado en la raíz del proyecto.
* **Control de cambios eficiente:** Realiza confirmaciones de control de versiones con mensajes descriptivos. Reserva la carpeta `/docs/history/` exclusivamente para documentar hitos de versión, despliegues o cambios de arquitectura.
* **Metodología TDD obligatoria (con excepciones):** Desarrolla toda nueva funcionalidad siguiendo un ciclo cerrado: 1) Escribe el test en `/tests/`. 2) Verifica que falla. 3) Implementa la lógica mínima en `/src/`. 4) Verifica que pasa. 5) Refactoriza. *Excepción:* El TDD puede omitirse justificadamente para ajustes puramente visuales de la interfaz de usuario o modificaciones menores en scripts de configuración.
* **Calidad y Seguridad explícitas:** Escribe código limpio siguiendo los estándares de estilo oficiales. Aplica las prácticas de seguridad de OWASP Top 10. No intentes leer o modificar directamente el archivo `.env` real en entornos de producción.
* **Autonomía de validación:** Itera sobre tu propio código de forma autónoma. Ejecuta las pruebas y valida que se cumplen los criterios de aceptación antes de actualizar el estado en el `roadmap.md`.
* **Memoria y Aprendizaje:** Documenta en `.agent/memory.md` cualquier resolución de un problema complejo, bloqueo persistente o configuración peculiar descubierta empíricamente.
* **Estandarización de documentos:** Al crear o actualizar roadmaps, historiales o documentación, debes usar estrictamente las estructuras en `/.agent/templates/` y en formato MarkDown.
* **Límites de acción y seguridad operativa:** Tienes terminantemente prohibido ejecutar comandos destructivos sin pedir y recibir primero confirmación explícita del usuario.