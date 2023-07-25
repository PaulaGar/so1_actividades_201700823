# Tipos de Kernel y sus diferencias:
El núcleo o **kernel** es la parte principal del sistema operativo, que es responsable de realizar todas las comunicaciones seguras entre el software y el hardware de la computadora a través de llamadas al sistema, además de proporcionar API y otras funciones esenciales. Por lo tanto, es la parte más importante de cualquier sistema operativo.

Los tipos de kernel son:
1. Kernel monolítico. Un kernel grande para todas las tareas. Es totalmente responsable de la gestión de la memoria y los procesos, la comunicación entre procesos y proporciona funciones de soporte de controladores y hardware. Los sistemas operativos que utilizan núcleos monolíticos incluyen Linux, OS X y Windows.
2. Microkernel. El microkernel se ha diseñado intencionadamente de un tamaño pequeño para que en caso de fallo no paralice todo el sistema operativo. No obstante, para que pueda asumir las mismas funciones que un kernel grande, está dividido en varios módulos. Como ejemplo de aplicación solo existe el componente Mach de OS X, ya que hasta ahora no hay ningún sistema operativo con microkernel.
3. Kernel híbrido. La combinación del kernel monolítico y el microkernel se denomina kernel híbrido. En este caso, el kernel grande se hace más compacto y modulable. Otras partes del kernel pueden cargarse dinámicamente. Esto ya ocurre en cierta medida en Linux y OS X.

## User vs Kernel Mode
#### User Mode:
Cuando se inicia un programa en un sistema operativo, digamos Windows, se inicia el programa en modo de usuario. Y cuando un programa en modo usuario solicita ejecutarse, Windows crea un proceso y un espacio de direcciones virtuales (espacio de direcciones para ese proceso). Los programas de modo de usuario tienen menos privilegios que las aplicaciones de modo de usuario y no se les permite acceder a los recursos del sistema directamente
#### Kernel Mode:
 El kernel es el programa central en el que se basan todos los demás componentes del sistema operativo, se utiliza para acceder a los componentes de hardware y programar qué procesos deben ejecutarse en un sistema informático y cuándo, y también administra la interacción entre el software y el hardware de la aplicación.

 |  User Mode | Kernel Mode  |
| ------------ | ------------ |
|  En modo kernel, el programa tiene acceso directo y sin restricciones a los recursos del sistema. |  En modo usuario, el programa de aplicación se ejecuta y se inicia. |
|  En el modo Kernel, todo el sistema operativo puede dejar de funcionar si se produce una interrupción |   En el modo de usuario, un solo proceso falla si ocurre una interrupción.  |
|  Se conoce como modo maestro, modo privilegiado o modo de sistema. |  Se conoce como modo sin privilegios, modo restringido o modo esclavo. |
|  Todos los procesos comparten un único espacio de direcciones virtuales. | Todos los procesos obtienen un espacio de direcciones virtuales separado  |
|  El bit de modo de kernel-mode es 0. |   El bit de modo del modo de usuario es 1. |