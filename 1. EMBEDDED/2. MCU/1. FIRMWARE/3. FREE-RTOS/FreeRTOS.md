Es principalmente un kernel, Scheduler y Funciones de Api (Bloques Aislados). Su scheduler se basa en el principio de determinismo. 


El scheduler de FreeRTOS solo se ejecuta durante cada tick, solo en el tick se puede cambiar la tarea de ejecucion. (tick en esp-idf 100Hz)

Es decir, solo se puede cambiar de tarea FreeRTOS de ejecucion durante el tick, este cambio lo hace el scheduler al detectar las tareas Ready y elegir la de mayor prioridad.

Pero el cambio de estado de las tareas no depende del scheduler, sino de funciones aisladas en la api, por ello, eventos basados en (ISR) si cambian inmediatamente el estado de una tarea, aunque este estado no es interpretado hasta llegar al tick del scheduler.

Los vTaskDelay no se gestionan como eventos de ISR, sino como una verificacion que realiza el Scheduler en su ejecucion en funcion de los ticks (cuantos ticks han pasado?), por ello solo puede ser multiplo de los ticks (cualquier otro valor menor se redondea hacia arriba)



Las tareas de FreeRTOS nunca se ejecutan dentro de interrupciones, sino como funciones normales manejadas por el scheduler. Entonces como se relacionan las interrupciones (eventos) con las tareas?
Las interrupciones, aunque nunca deben eejcutar una tarea, si pueden cambiar el estado de las tareas (y prioridades, etc). Por ello FreeRTOS las usa para poner eventos que cambian el estado de las tareas, y ya en el tick el scheduler puede ejecutar la tarea asociada a la interrupcion (si es que es la de mayor prioridad).


Dado que ninguna tarea de FreeRTOS se ejecuta dentro de interrupciones, y el tiempo de ejecucion de las interrupciones que cambian de estado tareas en FreeRTOS es minimo, tenemos una distribucion de interrupciones casi limpia, es decir podemos usarla por fuera de FreeRTOS, si deseamos una ejecucion en tiempo con mayor presicion que la brindada por las tareas de FreeRTOS, con reaccion en el orden de microsegundos (us), podemos usar ISR, sin afectar a las tareas de FreeRTOS, es decir, podemos usar ambos.

Para gestionar tareas de orden >= tick, usar la api de FreeRTOS
Para gestionar tareas de orden <= tick, usar interrupciones por fuera de la api



Sus funciones de la api siguen el formato de la primera letra describe el valor de retorno
vFunction (void)
xFunction (BaseType_t, depende de la arquitectura, en 32 bits -> int32_t)
ulFunction (unsigned long)

---
### LECTURES
- https://www.freertos.org/Documentation/02-Kernel/02-Kernel-features/00-Developer-docs