# kubernetes-primera-guia

A medida que los contenedores han ganado popularidad en los últimos años, la consultoría de Kubernetes está redefiniendo la forma en que se desarrolla, implementa y mantiene el software. La mayoría de los artículos en Internet declaran que Kubernetes está tomando por asalto la orquestación de contenedores.

Nos preguntábamos sobre su uso, por lo que buscamos encuestas en la web y llegamos a la conclusión de que Kubernetes es la herramienta de orquestación de contenedores más utilizada.

Si hay que creer en las estadísticas de los tres años anteriores, se puede decir con razón e indudable que Kubernetes es la plataforma de gestión de contenido más utilizada. Ha estado dominando el espacio de los contenedores durante un par de años.

**Aquí surge la pregunta: ¿Por qué? ¿Qué? ¿Cuándo? ¿Cómo?**

Te lo explicaremos todo.

Este artículo no es solo para líderes técnicos, sino también para un fundador no técnico que busca desarrollar la aplicación compleja mejorando la eficiencia y simplificando la carga de trabajo.

Entonces, comencemos.


![1_OfdPJUhmzAipyE1JsWAIBg](https://user-images.githubusercontent.com/18565089/125482746-5f590882-cf4c-4e55-b582-57990c780c6c.png)

Antes de Kubernetes: cómo llegó Kubernetes a la existencia
La esencia de los contenedores
Antes, los contenedores eran el mejor concepto para implementar aplicaciones. Dio un nuevo horizonte para desarrollar y mantener software. Con los contenedores, fue fácil para los desarrolladores de software empaquetar una aplicación que incluye componentes como bibliotecas y otras dependencias. Puede enviar un paquete completo sin la necesidad de una máquina virtual tradicional.
Cuando el mundo de la informática se volvió distribuido, más basado en la red y más dependiente de la computación en la nube, las aplicaciones monolíticas migraron a los microservicios. Estos microservicios permitieron a los usuarios escalar funciones clave individualmente y tener la capacidad de manejar millones de clientes. Además de eso, herramientas como Docker Container, Mesos y AWS ECS surgieron en la empresa, creando una manera consistente, portátil y fácil para que los usuarios implementen microservicios.
Pero, una vez que la aplicación madura y se vuelve compleja, será necesario ejecutar varios contenedores en varias máquinas. Debe averiguar cuáles son los contenedores correctos y en el momento adecuado, por supuesto, cómo pueden comunicarse entre sí, abordar la gran necesidad de almacenamiento y lidiar con un contenedor defectuoso. ¡Hacer todo esto manualmente puede ser una pesadilla!
Por lo tanto, para resolver las necesidades de orquestación de la aplicación en contenedores, nació Kubernetes.
Lleve su carrera a nuevas alturas de éxito con Kubernetes Training
Historia de Kubernetes: descripción general rápida
Cuando Docker siguió prosperando en la gestión de microservicios y contenedores, un sistema de gestión de contenedores se convirtió en un requisito primordial. Durante ese tiempo, Google ya estaba ejecutando una infraestructura de administración basada en contenedores durante muchos años y, en esa era, la compañía tomó una decisión audaz de abrir un proyecto interno llamado Borg.
Borg fue clave para ejecutar los servicios de Google como Gmail y Búsqueda de Google. Para mejorar las funcionalidades del sistema de administración de contenedores, la compañía creó Kubernetes , un proyecto de código abierto que automatiza el proceso de implementación y administración de aplicaciones de múltiples contenedores a escala. Kubernetes nació a mediados de 2014 y en un corto período de tiempo creció como una comunidad de código abierto con ingenieros de Google, Red Hat y muchas otras empresas que contribuyeron al proyecto.
¿Qué es Kubernetes?
Kubernetes es un sistema de gestión de contenedores de código abierto que se utiliza en empresas a gran escala en varias industrias verticales para realizar una tarea de misión crítica. Algunas de sus capacidades incluyen:
Gestión de grupos de contenedores
Proporcionar herramientas para implementar aplicaciones
Escalar aplicaciones cuando sea necesario
Gestión de cambios en las aplicaciones existentes en contenedores
Ayudando a optimizar el uso del hardware subyacente debajo de su contenedor
Permitir que el componente de la aplicación se reinicie y se mueva por el sistema cuando sea necesario
Kubernetes ofrece mucho más que el marco básico, lo que permite a los usuarios elegir el tipo de marcos de aplicación, idiomas, herramientas de seguimiento y registro, y otras herramientas de su elección. Aunque no es una plataforma como servicio, se puede utilizar como base para una PaaS completa.
En pocos años, se ha convertido en una herramienta muy popular y una de las mayores historias de éxito en la plataforma de código abierto.
Arquitectura de Kubernetes: cómo funciona

![1_nlS_0ARET4xNvdSeenq9oQ](https://user-images.githubusercontent.com/18565089/125482842-9bae47d8-b2ac-4c50-ba2c-04c2c8b672fd.png)

Arquitectura maestro-esclavo de Kubernetes y sus componentes:
Maestro de Kubernetes:
es la unidad de control principal que administra las cargas de trabajo y la comunicación en todo el sistema. Cada uno de sus componentes tiene un proceso diferente que puede ejecutarse en un solo nodo maestro o en varios nodos maestros. Sus componentes son:
Etcd Storage : es un almacén de datos de valor clave de código abierto desarrollado por el equipo de CoreOS y todos los nodos del clúster pueden acceder a él. Kubernetes usa "Etcd" para almacenar datos de configuración del clúster para representar el estado general del clúster en cualquier momento.
Servidor API : El servidor API es la entidad de gestión central que recibe solicitudes REST para modificaciones, sirviendo como un front-end para controlar el clúster. Además, esto es lo único que se comunica con el clúster Etcd, asegurándose de que los datos se almacenen en Etcd.
Programador: ayuda a programar los pods en varios nodos según la utilización de recursos y decide dónde implementar qué servicio. El planificador tiene la información sobre los recursos disponibles para los miembros, así como el que queda para configurar el servicio para que se ejecute.
Administrador de controladores: ejecuta una serie de procesos de controlador distintos en segundo plano para regular el estado compartido del clúster y realizar una tarea de rutina. Cuando hay algún cambio en el servicio, el controlador detecta el cambio y comienza a trabajar hacia el nuevo estado deseado.
Nodo de trabajo:
esto también se conoce como nodo de Kubernetes o Minion, y contiene la información para administrar la red entre contenedores como Docker y la comunicación entre el nodo maestro al asignar los recursos a los contenedores según la programación.
Kubelet: Kubelet garantiza que todos los contenedores del nodo se estén ejecutando y estén en buen estado. Kubelet supervisa el estado de un pod si no se encuentra en el estado deseado. Si un nodo falla, un controlador de replicación observa este cambio y lanza pods en otro pod en buen estado.
Contenedor : Los contenedores son el nivel más bajo de microservicio, se colocan dentro del pod y necesitan una dirección IP externa para ver el proceso externo.
Proxy de Kube : actúa como un proxy de red y un equilibrador de carga. Además, reenvía la solicitud a los pods correctos a través de redes aisladas en un clúster.
cAdvisor: actúa como un asistente que es responsable de monitorear y recopilar datos sobre el uso de recursos y las métricas de rendimiento en cada nodo.
Ventajas de Kubernetes
Portátil y de código abierto
Kubernetes puede ejecutar contenedores en uno o más entornos de nube pública, máquinas virtuales o bare metal, lo que significa que se puede implementar en cualquier infraestructura. Además, es compatible en varias plataformas, lo que hace que una estrategia de múltiples nubes sea muy flexible y utilizable también.
Escalabilidad de la carga de trabajo
El curso de Kubernetes ofrece varias funciones útiles para fines de escalado:
Escalado de infraestructura horizontal : las operaciones se realizan a nivel de servidor individual para implementar el escalado horizontal. Se pueden agregar o eliminar nuevos servidores fácilmente.
Auto-Scaling: según el uso de los recursos de la CPU u otras métricas de la aplicación, puede modificar la cantidad de contenedores que se están ejecutando.
Escalado manual: puede escalar manualmente el número de contenedores en ejecución mediante un comando o la interfaz.
Controlador de replicación: el controlador de replicación se asegura de que el clúster tenga un número específico de pods equivalentes en condiciones de ejecución. Si hay demasiados pods, el controlador de replicación puede eliminar pods adicionales o viceversa.
Alta disponibilidad
Kubernetes puede manejar la disponibilidad tanto de aplicaciones como de infraestructura. Aborda:
Verificaciones de estado : Kubernetes se asegura de que la aplicación no falle al verificar constantemente el estado de los modos y contenedores. Kubernetes ofrece autorreparación y reemplazo automático si un pod falla debido a un error.
Enrutamiento de tráfico y equilibrio de carga : el equilibrador de carga de Kubernetes distribuye la carga en varias cargas, lo que le permite equilibrar los recursos rápidamente durante el tráfico incidental o el procesamiento por lotes.
Diseñado para implementación:
La contenerización tiene la capacidad de acelerar el proceso de creación, prueba y lanzamiento de software, y la característica útil incluye:
Implementaciones y reversiones automatizadas: Kubernetes maneja la nueva versión y las actualizaciones de su aplicación sin tiempo de inactividad, al mismo tiempo que monitorea el estado durante la implementación. Si ocurre alguna falla durante el proceso, se revierte automáticamente.
Implementaciones Canary : Kubernetes prueba la producción de una nueva implementación y la versión anterior en paralelo, es decir, antes de escalar la nueva implementación y, al mismo tiempo, reducir la escala de la implementación anterior.
Compatibilidad con marcos y lenguajes de programación: Kubernetes es compatible con la mayoría de marcos y lenguajes de programación como Java, .NET, etc., y también cuenta con un gran apoyo de la comunidad de desarrollo. Si una aplicación tiene la capacidad de ejecutarse en un contenedor, también puede ejecutarse en Kubernetes.
Saber más acerca de Certificación Kubernetes Curso
Algunas cosas más para buscar
Kubernetes proporciona administración de DNS, monitoreo de recursos, registro, orquestación de almacenamiento y también aborda la seguridad como una de las cosas principales. Por ejemplo, se asegura de que información como contraseñas o claves ssh se almacenen de forma segura en los secretos de Kubernetes. Las nuevas funciones se lanzan constantemente y pueden estar en Kubernetes GitHub.
Kubernetes y contenedores con estado
Kubernetes StatefulSets proporciona recursos como volúmenes, identificadores de red estables e índices ordinales de 0 a N, etc. para tratar con contenedores con estado. El volumen es una de esas características clave que nos permite ejecutar la aplicación con estado. Los dos tipos principales de volumen admitidos son: -
Volumen de almacenamiento efermal:
el almacenamiento de datos efermal es diferente al de Docker. En Kubernetes, el volumen se tiene en cuenta en todos los contenedores que se ejecutan dentro del pod y los datos se almacenan en todo el contenedor. Pero, si las cápsulas mueren, el volumen se elimina automáticamente.
Almacenamiento persistente:
aquí los datos permanecen durante toda la vida. Cuando el pod muere o se mueve a otro nodo, esos datos permanecerán hasta que el usuario los elimine. Por lo tanto, los datos se almacenan de forma remota.
Kubernetes: sentar las bases para desarrollar aplicaciones en la nube
Algunas de las herramientas de orquestación y administración de contenedores, como Apache Mesos con Marathon, Docker Swarm y AWS EC2 Container Service, ofrecen excelentes funciones pero pesan menos que Kubernetes.
Docker Swarm se incluye estrechamente con el tiempo de ejecución de Docker; por lo tanto, es fácil cambiar de Docker a Swarm y viceversa. Mesos con Marathon puede implementar cualquier tipo de aplicación y no se limita a contenedores. Los usuarios actuales de AWS pueden acceder fácilmente a AWS ECS.
A medida que este marco maduró, comenzaron a duplicarse con otras herramientas en términos de características y funcionalidad. Pero, Kubernetes es el único de todos y seguirá siendo popular debido a su arquitectura, innovación y una gran comunidad de código abierto.
Kubernetes allana el camino para DevOps al permitir que el equipo se mantenga al día con los requisitos para el desarrollo de software. Sin Kubernetes, los equipos de desarrollo de software necesitan programar su propia implementación de software, escalarla manualmente y actualizar los flujos de trabajo. En una gran empresa, un gran equipo se encarga de esta tarea solo. Kubernetes ayuda a aprovechar la máxima utilidad de los contenedores y les permite desarrollar aplicaciones en la nube independientemente de los requisitos específicos de la nube.
Aparte de eso, las empresas están utilizando Kubernetes porque se puede implementar en el centro de datos preexistente de la empresa en las instalaciones en uno de los entornos de nube pública e incluso se puede ejecutar como un servicio. Debido a que Kubernetes abstrae la capa de infraestructura subyacente, los desarrolladores pueden concentrarse en desarrollar aplicaciones y luego implementarlas en cualquiera de esos entornos. Esto aumenta la adopción de Kubernetes por parte de la empresa, ya que puede ejecutarse en las instalaciones sin dejar de desarrollar cualquier estrategia en la nube.
Los casos de uso del mundo real de Kubernetes
Pokémon Go : el juego multijugador en línea es uno de los juegos populares que muestra el poder de Kubernetes. Antes de su lanzamiento, se esperaba que este juego fuera razonablemente el juego más comentado. Pero después de su lanzamiento, recibió 50 veces más tráfico del esperado. Al usar Kubernetes, Pokémon Go pudo escalar alto para mantenerse al día con la demanda inesperada.
Pearson - Pearson es una empresa de educación global que atiende a 75 millones de estudiantes, con el objetivo de llegar a 200 millones en 2025. Pero a medida que suben las escaleras, se enfrentan a dificultades para escalar y adaptar la audiencia en línea. Necesitaban una plataforma que ayudara a escalar y adaptar la audiencia en línea y entregar el producto más rápido. Por lo tanto, implementaron la orquestación de contenedores de Kubernetes debido a su flexibilidad. Después de implementar esta plataforma, hubo mejoras sustanciales en la productividad y la velocidad de entrega. Las cosas que tardaron nueve meses en aprovisionar activos físicos en un centro de datos se redujeron a solo unos minutos para aprovisionar.
Pinterest : Pinterest es una plataforma de redes sociales muy popular que se convirtió en 1000 microservicios y tenía un conjunto variado de herramientas y plataformas. La empresa quería implementar la ruta de producción más rápida sin que los desarrolladores se preocuparan por la infraestructura. El equipo buscó una plataforma de orquestación de contenedores como Kubernetes para simplificar la implementación general y la administración de una infraestructura complicada. Después de implementar Kubernetes, la empresa redujo los tiempos de construcción y la eficiencia alcanzó su punto máximo.
¿Quiere utilizar Kubernetes? ¿Necesitará un cambio su arquitectura existente?
El proceso de inicio puede llevar tiempo:
cuando crea una nueva implementación, debe esperar a que la aplicación se inicie antes de que esté disponible para los usuarios finales. Esto puede ser un obstáculo si el proceso de desarrollo requiere desarrollar nuevas instancias. Al migrar a Kubernetes, debe realizar algunos cambios en la base de código para que el proceso de inicio sea más eficiente para que el usuario final no tenga una mala experiencia de usuario.
La migración a una aplicación sin estado requiere mucho esfuerzo:
Kubernetes tiene la capacidad de escalar los pods hacia arriba y hacia abajo durante la implementación. Pero, si su aplicación no está agrupada en clúster o sin estado, esta funcionalidad no sirve de nada, ya que los pods adicionales no se configurarán y no se podrán utilizar. El proceso de utilizar apátridas en Kubernetes no vale la pena, ya que deberá reelaborar las configuraciones dentro de sus aplicaciones.
Conclusión
En poco tiempo, Kubernetes ha crecido y se ha convertido en una potencia económica. Dado que ofrece una variedad de beneficios, muchas empresas de todos los tamaños buscan desarrollar productos y servicios para satisfacer una necesidad cada vez mayor. Kubernetes tiene la capacidad de trabajar tanto en nubes públicas como privadas y lo ha convertido en una de las herramientas favoritas de las empresas que trabajan con nubes híbridas. Si esto continúa, incluso podemos ver más empresas invirtiendo en Kubernetes y el sistema de gestión de contenedores.



