## 1.	Compare las diferencias entre la planeación a corto plazo y largo plazo.
- La planificación a largo plazo se encarga de la selección adecuada de los procesos para su ejecución, los cuales son elegidos desde la cola de almacenamiento masivo y son cargados en la memoria principal para su posterior procesamiento. Por otro lado, la planificación a corto plazo se enfoca en la selección de los procesos ya preparados para su ejecución, a los cuales se les asigna una unidad central de procesamiento (CPU).
- El planificador de la CPU es el más utilizado debido a su función de asignación eficiente de los recursos de la CPU a los procesos. Por lo tanto, la velocidad es un factor importante para garantizar un rendimiento óptimo del sistema operativo. En contraste, el planificador de trabajos se enfoca más en la finalización de procesos, lo que le permite tomar más tiempo en la selección de los procesos adecuados para su carga en la memoria principal desde la cola de almacenamiento masivo. En este caso, aunque la velocidad no es crítica como en el planificador de la CPU, sigue siendo importante para garantizar una gestión adecuada de los recursos del sistema operativo.

## 2.	Caracterice dos procesos que se puedan considerar a mediano plazo.
1. **La gestión de E/S:** implica la transferencia de datos entre dispositivos de E/S y la memoria principal, lo que también puede requerir la interrupción temporal de los procesos que utilizan dichos dispositivos.
2. **La compilación:** este proceso implica varias etapas, como análisis léxico, análisis sintáctico, optimización y generación de código. Dependiendo del tamaño del programa y la complejidad del código, la compilación puede llevar mucho tiempo y requerir una cantidad significativa de recursos del sistema.

En ambos casos, la planificación a medio plazo puede ayudar a mejorar la eficiencia del sistema operativo al equilibrar la cantidad de procesos que compiten por los recursos y al liberar memoria cuando es necesario.

## 3.	Describa las acciones que toma el kernel para el cambio de contexto entre procesos.
1.	El kernel guarda el estado actual del proceso en ejecución, incluyendo los valores de los registros de la CPU, el estado del proceso y la información de gestión de memoria. Este contexto se almacena en la estructura de control de procesos (PCB).
2.	El kernel carga el contexto almacenado del nuevo proceso que se ha decidido ejecutar en la CPU. Esto incluye la restauración de los valores de los registros de la CPU y la información de gestión de memoria del nuevo proceso.
3.	El kernel actualiza sus estructuras de datos internas para reflejar el cambio de contexto. Por ejemplo, actualiza la lista de procesos en espera y la cola de procesos listos. 
4.	Una vez que se ha cargado el contexto del nuevo proceso y se han actualizado las estructuras de datos del kernel, el kernel reanuda la ejecución del nuevo proceso en la CPU.

## 4.	Defina las ventajas y desventajas desde el punto de vista del programador para comunicación síncrona y asíncrona.
- En cuanto a la comunicación síncrona, es más fácil de entender e implementar y se asegura que cada respuesta se reciba antes de continuar con la siguiente operación. Sin embargo, puede ser menos eficiente si se espera una respuesta larga o si hay una gran cantidad de comunicación, y puede bloquear los procesos mientras se espera una respuesta. Además, puede ser menos escalable si hay muchas comunicaciones que ocurren al mismo tiempo.

- Por otro lado, hablando de comunicación asíncrona, permite una mayor eficiencia y escalabilidad, ya que el emisor y el receptor pueden trabajar independientemente. Además, no bloquea los procesos mientras se espera una respuesta, lo que mejora el rendimiento. Sin embargo, puede ser más difícil de implementar y entender, y la integridad de los datos puede ser más difícil de garantizar. También puede ser menos efectivo en situaciones donde se requiere una respuesta inmediata.

## 5.	Defina las ventajas y desventajas desde el punto de vista del OS para envío por copia y envío por referencia.
<table>
  <tr>
    <th>Envío por copia </th>
    <th>Envío por referencia</th>
  </tr>
  <tr>
    <td>Ventajas</td>
    <td></td>
  </tr>
  <tr>
    <td>La seguridad es mayor en el envío por copia ya que el proceso receptor recibe una copia de los datos, lo que evita que pueda modificar directamente los datos del proceso emisor.</td>
    <td>Se requiere menos uso de recursos de memoria y CPU ya que no se realizan copias completas de los datos.</td>
  </tr>
  <tr>
    <td>Los procesos emisor y receptor pueden trabajar de manera independiente y no necesitan compartir memoria directamente</td>
    <td>Puede ser más eficiente que el envío por copia, especialmente cuando se trata de grandes cantidades de datos.</td>
  </tr>
  <tr>
    <td>Desventajas</td>
    <td></td>
  </tr>
  <tr>
    <td>Se requiere un mayor uso de recursos al enviar copias completas de los datos, lo cual puede resultar en un consumo elevado de memoria y CPU, especialmente si se trata de grandes cantidades de datos.</td>
    <td>Presenta menor seguridad ya que el proceso receptor tiene acceso directo a los datos del proceso emisor y puede modificarlos sin restricciones</td>
  </tr>
  <tr>
    <td>Se puede tardar más en realizar el envío de los datos debido a que se requiere copiar los datos completos en lugar de simplemente hacer referencia a ellos.</td>
    <td>Los procesos emisor y receptor necesitan compartir memoria directamente, lo que puede restringir la flexibilidad del sistema operativo.</td>
  </tr>
</table>




## 6.	Defina las ventajas y desventajas desde el punto de vista del OS para mensajes de tamaño fijo y de tamaño variable.
<table>
  <tr>
    <th>Mensajes de tamaño fijo</th>
    <th>Mensajes de tamaño variable</th>
  </tr>
  <tr>
    <td>Ventajas</td>
    <td></td>
  </tr>
  <tr>
    <td>Se puede simplificar el manejo de la asignación de memoria y hacerlo más predecible</td>
    <td>El sistema operativo solo asigna la cantidad de memoria necesaria para almacenar los datos del mensaje, evitando así el desperdicio de memoria.</td>
  </tr>
  <tr>
    <td>El sistema operativo puede realizar operaciones de lectura y escritura de manera más eficiente en la red o en el disco</td>
    <td>Se puede ajustar el tamaño del mensaje según la cantidad de datos que se deseen enviar, lo que permite enviar grandes cantidades de datos sin limitaciones de tamaño predefinidas.</td>
  </tr>
  <tr>
    <td>Desventajas</td>
    <td></td>
  </tr>
  <tr>
    <td>Desaprovechamiento de memoria en caso de que el mensaje no ocupe todo el espacio reservado</td>
    <td>Requieren que el OS realice operaciones de asignación de memoria más complejas y menos predecibles.</td>
  </tr>
  <tr>
    <td>Si el tamaño del mensaje es reducido, puede haber restricciones en la cantidad de datos que se pueden transmitir.</td>
    <td>Menor eficiencia </td>
  </tr>
</table>



## 7.	Describa los estados de un proceso. 
- **Nuevo:** el proceso ha sido creado, pero aún no ha sido asignado a un procesador para su ejecución
- **Preparado:** el proceso está preparado para su ejecución, pero aún no se le ha asignado el procesador. En este estado, el proceso se encuentra en la cola de procesos listos a ser ejecutados.
- **En ejecución:** Una vez que el procesador está disponible, el proceso pasa al estado En ejecución, lo que significa que el proceso está siendo ejecutado en el procesador asignado.
- **En espera:** el proceso se encuentra temporalmente detenido porque está esperando que se produzca algún suceso externo, como la finalización de una operación de entrada/salida o la llegada de una señal de interrupción
- **Terminado:** en este estado, el proceso ha completado todas las tareas que se le asignaron y se ha liberado la memoria que se había reservado para él.

## 8.	Que datos se encuentran en un PCB. 
<p> El PCB (bloque de control de procesos) contiene información importante para la gestión y control del proceso en el sistema operativo. Esto incluye: </p>

- **Estado del proceso:** indica el estado actual del proceso, como "en ejecución" o "bloqueado".
- **Contador del programa:** indica la dirección de la siguiente instrucción a ejecutar.
- **Registros de la CPU:** incluyen diferentes tipos de registros que almacenan información importante para el proceso.
- **Información de planificación de la CPU:** incluye la prioridad del proceso y cualquier otro parámetro necesario para la planificación de su ejecución.
- **Información de gestión de memoria:** incluye valores de registros base y límites, tablas de páginas o segmentos.
- **Información contable:** incluye estadísticas de uso del CPU, tiempo real utilizado, límites de tiempo asignados y número de proceso.
- **Información del estado del I/O:** incluye la lista de dispositivos de entrada/salida asignados al proceso y la lista de archivos abiertos.

## 9.	Describa un modelo de comunicación Cliente-Servidor
<p> El modelo de comunicación Cliente-Servidor implica la participación de dos entidades independientes en la comunicación (el cliente y el servidor). El cliente es el que inicia la comunicación, y es responsable de solicitar el servicio que necesita. El servidor, por su parte, está diseñado para proporcionar los servicios solicitados por el cliente. Ambos se comunican a través de una red, que puede ser local o remota. Cada una de estas entidades se identifica mediante una dirección IP y un puerto, que juntos forman un punto terminal de la comunicación conocido como socket. </p>

<p> Es crucial que cada conexión se diferencie de las demás, lo que se logra a través de la asignación de una pareja única de sockets a cada conexión. A pesar de que la comunicación mediante sockets se considera de nivel bajo, su eficiencia es alta, debido a que solo permite la transmisión no estructurada de bytes entre los hilos de comunicación. </p>


