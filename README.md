<p align="center">
  <img src="https://cdn-icons-png.flaticon.com/512/2103/2103633.png" width="160" alt="UCI Logo">
</p>

<h1 align="center">⚛️ Plataforma UCI: Unified Cognitive Intelligence</h1>

<p align="center">
  <b>"La orquestación definitiva: Donde la autonomía agéntica y la inteligencia multimodal convergen en un ecosistema de grado empresarial."</b>
</p>

**Desarrollado por: Msc. Yanet Cesaire Velazquez**

## 📂 Documentación Técnica

Para conocer los detalles de arquitectura, desafíos técnicos superados y comparativas de rendimiento:

👉 [**Descargar Informe Técnico Completo (PDF)**](./documentos/Informe_Tecnico_Final.pdf)

*Nota: Este repositorio es un portafolio de arquitectura y diseño de sistemas de IA. El código fuente es de propiedad privada de la autora.*

## 🧠 Visión Arquitectónica

La Plataforma UCI no es una aplicación, es una infraestructura cognitiva de grado industrial. Ha sido diseñada para transformar la interacción humana con la tecnología mediante una red de microservicios y agentes especializados que colaboran bajo una jerarquía de mando. UCI resuelve los cuatro grandes retos de la IA en la empresa: Escalabilidad, Seguridad, Costo y Confiabilidad.

## 💡 Decisiones de Ingeniería y Preguntas Clave

En la construcción de la Plataforma UCI, se aplicaron principios de ingeniería de software robustos para transformar algoritmos de IA en una infraestructura operativa de grado empresarial. Estas son las respuestas a los pilares de la plataforma:

**¿Por qué una Arquitectura de Microservicios Distribuidos en lugar de una Monolítica?**

Ejecutar 8 agentes especializados junto con modelos multimodales y procesos de búsqueda vectorial requiere una gestión de recursos crítica:

**Escalabilidad Independiente:** El uso de Docker y Nginx permite replicar instancias de la API según la demanda, evitando cuellos de botella en la inferencia del LLM.

**Procesamiento Asíncrono (Celery + Redis):** Se delegaron las tareas pesadas (como el análisis de PDFs de cientos de páginas o el envío de correos masivos) a Workers independientes. Esto garantiza que la interfaz de usuario nunca se bloquee, manteniendo una latencia de respuesta óptima.

**¿Cómo se optimizó el retorno de inversión (FinOps) y la latencia?**

El costo de los tokens y el tiempo de respuesta son los mayores obstáculos para la IA empresarial. La solución fue una Caché Híbrida Multinivel:

**Caché L1 (Redis):** Entrega respuestas instantáneas (latencia cero) ante consultas idénticas.

**Caché L2 (Semántica con ChromaDB):** La plataforma es capaz de identificar si una pregunta nueva es conceptualmente similar a una anterior, reutilizando la respuesta y ahorrando hasta un 70% en costos de tokens.

**Elastic Inference:** Implementación de una lógica de fallback que conmuta automáticamente entre modelos de alto rendimiento (70B) y modelos ligeros (8B) según la complejidad de la tarea.

**¿Cómo se garantiza la Seguridad y Gobernanza en un entorno corporativo?**

La IA en la empresa no puede ser una "caja negra" sin supervisión. UCI implementa:

**RBAC (Control de Acceso por Roles):** El Agente Director tiene conciencia de seguridad; un usuario con rol 'USER' no puede solicitar al agente que analice la base de datos de nóminas o finanzas confidenciales.

**Cloudflare Tunneling:** Se eliminó la exposición de puertos vulnerables, creando un túnel cifrado de capa 7 para el acceso global seguro.

**Human-in-the-Loop (HITL):** Para acciones críticas (como el despacho de correos electrónicos), el sistema requiere una firma de autorización humana, mitigando riesgos reputacionales o de seguridad.

**¿Cuál fue el desafío técnico más complejo?**

El reto principal fue la Orquestación de la Cadena de Pensamiento (LangGraph). Lograr que un "Agente Maestro" descomponga una orden compleja (ej: "Investiga el precio de la competencia en la web, compáralo con nuestra base de datos SQL y envíame un informe detallado por correo") en sub-tareas precisas, las delegue a los agentes correctos en el orden lógico, y valide la calidad del resultado antes de entregarlo, representó el mayor hito de ingeniería cognitiva del proyecto.

## Microservicios
![MICROSERVICIOS](./imagenes/2_Microservicios.png)

## Dockers
![DOCKER](./imagenes/3_Docker.png)

## Arquitectura
![ARQUITECTURA](./imagenes/4_Arquitectura.png)

## Interfaz General
![PROTOTIPO1](./imagenes/1_Prototipo_General.png)

## Agente RAG Documental
![PROTOTIPO2](./imagenes/5_RAG_Documental.png)

## Agente Python Analytics (CSV/Excel)
![PROTOTIPO3](./imagenes/6_Agente_Python_Analytics.png)

## Agente Python Analytics SQL
![PROTOTIPO4](./imagenes/7_Agente_Python_Analytics_SQL.png)

## Agente SQL Specialist (DB)
![PROTOTIPO5](./imagenes/8_Agente_SQL_Specialist_DB.png)

## Agente de Investigación
![PROTOTIPO6](./imagenes/9_Agente_Investigacion.png)
![PROTOTIPO6](./imagenes/9_Agente_Investigacion1.png)

## Agente Vision 
![Factura](./imagenes/10_Agente_Vision.png)

![Agente_Vision](./imagenes/11a_Agente_Vision.png)

![Agente_Vision1](./imagenes/11b_Agente_Vision.png)

