# Resumen de la Empresa

Personal Brand es una agencia de Marketing Personal para clientes que requieren aumentar su exposición en RRSS a través de una estrategia de Marketing Personalizada que apoya su posicionamiento y footprint digital para ser consumida por unidades de RRHH o Head Hunter que buscan perfiles para cubrir posiciones disponibles. 
Personal Brand proporciona su servicio a clientes de todas partes del mundo y de cualquier sector.

# Concepto de la Solución

Debido a los rápidos cambios en la forma de empleabilidad producto del Covid19 acentuando la modalidad de Trabajo Remoto la demanda de los clientes ha crecido exponencialmente desde el 2020 para el producto Personal Web Page.

La Compañía necesita poder escalar su entorno On-Premise, aumentar la disponibilidad, garantizar baja latencia e implementar nuevas capacidades de implementación continua para que los equipos de contenido mantengan actualizadas las Personal Web Page de sus Clientes, porque cada vez que cambian algo deben subir a mano las modificaciones

# Entorno Técnico Existente

Las Páginas Web Personales se encuentran actualmente alojado en un entorno On-Premise Virtualizado, consideraciones:

- La Plataforma Virtual está a punto de entrar a EOL (End of Life) y EOS (End Of Support).
- Los Personal Web Page están basadas en Web Apache en Ubuntu 18.04
- Los Dominios, Certificados SSL y DNS son servicios Externalizados.

# Requisitos Comerciales

-	Incorporar Personal Web Page lo antes posible para los Clientes Nuevos.
-	Disminuir el tiempo de Actualización del Contenido de los Clientes por parte del equipo de contenido.
-	Proporcione una disponibilidad mínima del 99,9% del producto Personal Web Page.
-	Reducir la latencia a todos los clientes que visitan las Personal Web Page de los Clientes.
-	Disminuir los costos de administración de la infraestructura.

# Requerimientos Técnicos

-	Proporcionar una integración CI/CD para los equipos de Operación y Contendido.
-	Proporcione una forma simple de administración de la Plataforma.
-	Proporcione una conexión segura y de baja latencia para los accesos a los perfiles de los clientes alojados en las Personal Web Page.

# Declaración Ejecutiva.

La estrategia local ha funcionado durante años, pero ha requerido una gran inversión de tiempo y dinero para capacitar a los equipos, administrar entornos y responder a interrupciones. Muchos de estas interrupciones han sido el resultado de sistemas mal configurados, capacidad inadecuada para manejar picos de tráfico y prácticas de monitoreo inconsistentes. Se requiere utilizar una plataforma escalable y resistente, que pueda contener estos entornos sin problemas, brindar una experiencia de usuario consistente y estable que nos posicione para el crecimiento futuro.

# 1-Enfoque en la Entrega de Valor al Cliente 

El objetivo es implementar una solución que permita desplegar el producto Personal Web Page cumpliendo con los siguientes requisitos:

-	El sitio debe alojarse de manera sencilla y requerir el mínimo esfuerzo de operación por parte de Personal Brand.
-	Personal Web Page debe visitarse a través de HTTPS usando dominios personalizados y administrados directamente por el equipo de operación.
-	El servicio debe estar disponible el máximo tiempo posible (alta disponibilidad).
-	El servicio debe servirse con baja latencia a todos los interesados que se encuentren en cualquier lugar del mundo.
- Los cambios realizados por el equipo de Contenido deben desplegarse de manera automática en cuanto se cree o actualiza un perfil en Personal Web Page.

En el diseño se estableció utilizar un enfoque Serverlees basado en la nube de AWS con los servicio de almacenamiento de objetos, Amazon S3,  la red de entrega de contenido (CDN) Amazon CloudFront,  Amazon Route 53 para gestionar los registros DNS, y AWS CodePipeline, AWS CodeCommit y AWS CodeBuild para desplegar nuevas versiones de contenido de manera automática y fiable liberando el trabajo Operacional utilizado actualmente y así proporcionando una solución que cubre las necesidades del negocio de manera eficiente, segura, rápida y económica.

El siguiente diagrama muestra la arquitectura referencial de la solución:

![image](https://user-images.githubusercontent.com/74636101/142863174-9fd57a58-f100-4bb2-b60c-e366fbdc7992.png)


# 2-Desarrollo Ágil

Para efectos de poder disminuir el tiempo de Actualización del Contenido de los Clientes por parte del equipo de contenido, se proporciona un Pipeline de Continuos Deployment que automáticamente aplicará los cambios desde el momento en el que se incorporen al repositorio de código CodeCommit. 
Para ello se proporcionan los siguientes servicios para el equipo de Contenido.

-	AWS CodeCommit.
-	AWS CodeBuild.
-	AWS CodePipeline.

![image](https://user-images.githubusercontent.com/74636101/142863286-d98fb358-05e7-43ce-b750-50f76e160107.png)

1.	El Equipo de Contenido realiza un cambio en el repositorio de AWS CodeCommit.
2.	AWS CodeCommit dispara un evento que lanza una nueva ejecución de AWS CodePipeline.
3.	AWS CodePipeline se descarga el código del repositorio y lo pone a disposición de la siguiente etapa del pipeline.
4.	Un job de AWS CodeBuild empaqueta los ficheros y los almacena como artefactos para el siguiente paso.
5.	El pipeline sube los artefactos al bucket del sitio web, estableciendo las cabeceras de caché adecuadas.

# 3-Servicios Gestionados de Próxima Generación

El equipo TI Personal Brand normalmente es responsable de adquirir, diseñar, implementar, configurar y mantener los componentes físicos y virtuales que componen la infraestructura de TI. En concreto, el equipo TI Personal Brand debe adoptar Servicios Gestionados de Próxima Generación para ofrecer y mantener diversos servicios, aplicaciones y tecnologías necesarias en la Operaciones del Negocio de una Compañía.

Los alcances que debe incorporan a las Operaciones TI Personal Brand son:

- Gestión de la infraestructuras Modernas: 

Preparar la Infraestructura y el Software para facilitar el proceso de desarrollo del software, dispositivos personales para codificación, un repositorio para la gestión de versionamiento, ambientes para la integración y fusión de código, y un entorno de desarrollo dedicado para la creación y prueba de código, sumado a esto la implementación, monitoreo, mantenimiento, y actualización del back-end de la aplicación web que se ejecuta en los ambientes pre-productivos y productivos.

- Gestión de Aplicaciones Modernas:

Hacer que todos los equipos de desarrollo empresarial de una empresa practiquen la metodología DevOps, el equipo TI especifica que todo el equipo de desarrollo de software debe enviar sus formularios de solicitud de un ambiente de desarrollo con un SLA establecido para que el departamento de TI tenga un período adecuado para cumplir con los requisitos.

- Gestión de la seguridad de infraestructuras Modernas:

Garantizar la seguridad de Infraestructura y el Software, esto amplia su alcance a dispositivos de codificación personal, Infraestructura de desarrollo y producción para las aplicaciones, el control de acceso a los repositorios dedicados para la integración y fusión de código (normalmente alojado en Github o Gitlab ),  que esté bien cubierto la revisión de facultades y el control de acceso.

- Gestión de la Confiablidad:

Asegurar que la infraestructura configurada en producción sea tolerante a fallas, además que la solución cuente con mecanismos y procesos para hacer frente a interrupciones, ciberataques, adopción de SRE y recuperación ante desastres.


# Conclusión

En este artículo se ha querido ejemplificar como abordamos las necesidades de nuestros clientes desde la Alineación de las Necesidades de Negocio hasta la Propuesta de Valor definiendo los pasos de acción para alcanzar los objetivos del Negocio, siempre teniendo en cuenta la gestión financiera de nuestros clientes para proporcionar una inversion viables en la implementación de Infraestructuras Modernas adoptando las mejores prácticas para la implementación con un enfoque colaborativo multifuncional que favorece la co-creacion, en este caso usando servicios totalmente gestionados, sin necesidad de administrar ni un solo servidor como se indico el los requisitos comerciales levantados en conjunto con el Cliente.

