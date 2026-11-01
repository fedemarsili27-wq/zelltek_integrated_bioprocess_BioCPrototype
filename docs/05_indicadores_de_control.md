# Auditoría Técnica y Estándar de Desempeño: Indicadores de Control

## 1. Introducción y Marco de Aplicación
Este documento define los indicadores de control y los estándares de desempeño para realizar la auditoría técnica del sistema de software integrador BioCPrototype de Zelltek S.A. Este programa se encarga de coordinar en tiempo real dos mundos clave: el cultivo de células en la etapa de upstream y la purificación del producto en la etapa de downstream.

*Aclaración importante:* Los valores que figuran en este trabajo son metas iniciales de diseño para cumplir con el objetivo académico del proyecto. No se tratan de normas oficiales de la industria ni de certificaciones regulatorias de una planta real; son parámetros conceptuales que en un caso real deberían probarse y validarse paso a paso con los equipos y las pruebas de la fábrica.

---

## 2. Detalle de los Indicadores de Desempeño

### 1. Integridad de datos
* **¿Qué mide?** Se fija que la información que mandan los sensores de las máquinas llegue entera y no se pierdan pedazos en el camino.
* **¿Cómo se evalúa?** Controlando que la cantidad de datos válidos que llegan al sistema sea prácticamente total frente a lo que se emite.
* **Objetivo buscado:** Que al menos el 98% de los datos lleguen perfectos y sin campos vacíos.
* **¿Qué se hace si falla?** Se revisa la conexión de red, los cables o la configuración de los aparatos para evitar que se pierda información vital.

### 2. Latencia de adquisición
* **¿Qué mide?** El tiempo exacto que tarda un dato en viajar desde el sensor físico en la planta hasta que aparece reflejado en la pantalla de la computadora.
* **¿Cómo se evalúa?** Midiendo la diferencia de segundos entre el momento exacto en que el sensor toma la medida y el momento en que el sistema la guarda.
* **Objetivo buscado:** Que no tarde más de 5 segundos en llegar a la pantalla.
* **¿Qué se hace si falla?** Se optimiza la velocidad de la red de la fábrica o se ajusta la frecuencia con la que el sistema le consulta a los sensores para que no se atore.

### 3. Sincronización entre Upstream y Downstream
* **¿Qué mide?** Que la primera etapa (la producción) no produzca más rápido de lo que la segunda etapa (la purificación) puede procesar, evitando así embotellamientos o desbordes.
* **¿Cómo se evalúa?** Comparando constantemente el caudal de líquido que sale de la cosecha con la capacidad real de procesamiento que tiene el sector de purificación.
* **Objetivo buscado:** Que ambos flujos estén siempre equilibrados dentro de los márgenes seguros.
* **¿Qué se hace si falla?** El sistema emite una alerta temprana, frena un poco el ritmo de cosecha de forma automática o desvía el líquido hacia tanques de reserva o pulmones de seguridad.

### 4. Ejecución de consignas
* **¿Qué mide?** Que las órdenes que calcula y manda el software sean acatadas de verdad por los aparatos físicos de la planta (los autómatas o PLCs).
* **¿Cómo se evalúa?** Relacionando las órdenes de control que fueron confirmadas por las máquinas frente al total de comandos que envió el software.
* **Objetivo buscado:** Que al menos el 99% de las órdenes se cumplan sin rechazos.
* **¿Qué se hace si falla?** Se revisa el canal de comunicación con los autómatas, se verifica que no haya trabas de seguridad físicas y se reenvía la orden confirmando su recepción.

### 5. Detección de desviaciones
* **¿Qué mide?** Cuánto tarda el sistema en darse cuenta y gritar "¡alerta!" cuando algo en la planta se sale de los parámetros normales.
* **¿Cómo se evalúa?** Contando los segundos que pasan desde que una variable supera el límite seguro hasta que el sistema salta con el aviso visual en la pantalla.
* **Objetivo buscado:** Que las alertas salten en un tiempo menor o igual a 5 segundos.
* **¿Qué se hace si falla?** Se ajusta la sensibilidad de las alarmas en el programa o se optimiza el sistema para que procese los eventos más rápido.

### 6. Disponibilidad del sistema
* **¿Qué mide?** Que el software no se cuelgue, no tire pantallas de error y se mantenga online todo el tiempo que dure la producción.
* **¿Cómo se evalúa?** Calculando la proporción de tiempo real que el programa funcionó sin interrupciones frente al tiempo total programado para la campaña.
* **Objetivo buscado:** Que el sistema esté disponible y operativo al menos el 99% del tiempo de producción.
* **¿Qué se hace si falla?** Se activan servidores de respaldo automáticos o se reinician los servicios del programa si hubo algún bloqueo inesperado.

---

## 3. Utilidad de los Indicadores en una Auditoría Técnica
Si alguien viene a auditar este sistema de software, va a usar estos indicadores para comprobar tres cosas fundamentales:
1. **Confiabilidad:** Revisar el historial para estar seguros de que el sistema toma decisiones basándose en datos reales, limpios y rápidos.
2. **Control real:** Comprobar que la comunicación con las máquinas de la fábrica fluye sin rechazos y mantiene todo sincronizado.
3. **Prevención de riesgos:** Verificar que ante cualquier problema, el sistema avisa a tiempo para evitar pérdidas de material o colapsos en la purificación.
