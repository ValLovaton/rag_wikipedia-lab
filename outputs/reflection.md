Reflexión: Comparación entre Multi-Agent Workflow y RAG
1. Manejo de ambigüedad y contradicciones

En la tarea de multi-agentes, el sistema manejaba la ambigüedad principalmente mediante razonamiento conversacional: el Investigador interpretaba preguntas abiertas, generaba múltiples búsquedas y el Redactor sintetizaba resultados incluso si eran contradictorios. En ese flujo, la coherencia final dependía de la capacidad del Redactor y del Revisor para armonizar fuentes diversas; es decir, los agentes podían suavizar contradicciones, pero no necesariamente detectarlas o validarlas con precisión.

En cambio, el enfoque RAG maneja ambigüedad de manera más estructurada. Al depender de documentos específicos recuperados desde el vector store, la respuesta se limita al contenido realmente disponible. Eso reduce contradicciones, pero también restringe el alcance: si el corpus no incluye información relevante, el sistema no puede “suavizar” o rellenar huecos.

2. Manejo de factualidad y cobertura

En el sistema RAG, la factualidad depende directamente del dataset y del vector store. Si los embeddings y los documentos recuperados son correctos, la respuesta es mucho más precisa y basada en evidencia. Además, el proceso es trazable: se puede ver exactamente qué textos fueron recuperados y utilizados. Sin embargo, la cobertura depende totalmente de lo que esté en la base; si la información no está ahí, el modelo no puede inventarla.

En el enfoque multi-agente, la factualidad es más variable. El Investigador tiene acceso a toda la web y puede recuperar fuentes amplias, pero el Redactor podría mezclar información o cometer errores de síntesis. Aunque los agentes usan múltiples pasos y roles para mejorar la claridad, no existe un mecanismo de grounding explícito como en RAG. Por eso, tiene más cobertura, pero menos control sobre exactitud.

3. ¿Qué enfoque es mejor para cada tipo de pregunta?

Preguntas abiertas o exploratorias:
El enfoque multi-agente es superior. Puede navegar más fuentes, generar interpretaciones amplias y construir textos más largos y flexibles.

Preguntas factuales o puntuales:
El enfoque RAG es claramente mejor. Recupera información específica, basada en un corpus concreto, evitando alucinaciones y manteniendo alta precisión.
