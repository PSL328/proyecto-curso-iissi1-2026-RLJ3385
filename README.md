# FilmUS

## Miembros del grupo L1-DF/AM-6

1. Sánchez Limón, Jose
2. Enrique Rosado, Jaime
3. Rafael Trampler Alejo, Mateo
4. Almeida Reyes, Joel

## 1. Introducción al problema

Queremos crear una aplicación que permita a las personas poder guardar sus descubrimientos sobre el cine en una red social, donde puedan compartir con otros usuarios sus gustos y recomendaciones. Cada cliente tendrá una cuenta que podrá ser pública o privada.

Entre los tipos de usuarios, destacan los clientes y administradores.

Podríamos encontrarnos con problemas como que las películas de estreno reciente o poco reconocidas no se encuentren disponibles en la base de datos. También puede haber problemas con nombres o comentarios inapropiados de los clientes, que serán gestionados por los administradores. Esperamos conseguir una aplicación con una experiencia de usuario satisfactoria, crear un ambiente sano y respetuoso y ayudar a la gente a descubrir películas nuevas.

## 2. Glosario de términos

- **Comentario**: Texto opcional que escribe un cliente dentro de un log para dar su opinión sobre una película.
- **Favoritas**: Películas (como máximo 4) que un cliente elige para destacar en su perfil.
- **Like**: Valoración positiva que hace un cliente sobre el log de otro cliente o sobre una película.
- **Lista**: Grupo de películas creado por un cliente.
- **Log**: Es el registro del cliente que indica que ha visto una película en concreto, con una valoración y comentario opcionales.
- **Perfil**: Página de un cliente donde se muestran sus logs, listas y películas favoritas. Puede ser público o privado.
- **Profesional**: Persona que participa en una película (por ejemplo: director, actor, guionista).
- **Rewatch**: Cuando se registra que el cliente ha visto una misma película más de una vez.
- **Seguir**: Acción de un cliente para estar al tanto de la actividad de otro cliente con perfil público.
- **Tags**: Etiqueta que se puede atribuir a una película y que la engloba con otras, por ejemplo: terror, drama, ciencia ficción.
- **Valoración**: Puntuación que un cliente da a una película, entre 0,5 y 5 estrellas.
- **Watchlist**: Lista especial de películas que el cliente tiene pendiente por ver. Cada cliente tiene una.

## 3. Visión general del sistema

### 3.1. Requisitos generales

#### **R.G.01. Registrar películas vistas**
Como cliente

quiero guardar las películas que he visto, valorarlas y escribir comentarios

para tener un registro de mi actividad.

#### **R.G.02. Gestionar listas**
Como cliente

quiero crear listas de películas y tener una watchlist

para organizar las películas que he visto o que quiero ver.

#### **R.G.03. Consultar otros perfiles**
Como cliente

quiero ver los perfiles públicos de otros clientes

para conocer sus películas vistas, valoraciones y listas públicas.

#### **R.G.04. Consultar películas**
Como cliente

quiero consultar la información de las películas

para conocer su título, fecha, duración, sinopsis y profesionales.

#### **R.G.05. Moderar la plataforma**
Como administrador

quiero controlar la actividad de los clientes y eliminar comentarios inapropiados

para mantener un buen ambiente en la plataforma.

### 3.2. Usuarios del sistema

- **Cliente**: Puede registrar películas vistas, valorar películas, escribir comentarios, dar likes, crear listas, seguir a otros clientes y consultar perfiles públicos.
- **Administrador**: Se encarga de controlar la actividad de los clientes y eliminar contenido inapropiado.

## 4. Catálogo de requisitos

### 4.1. Requisitos funcionales

#### **R.F.01. Valorar películas**
Como cliente

quiero poder poner nota a las películas

para poder organizar mi historial según me hayan gustado más o menos.

**- Pruebas de aceptación**

1- Comprobar que un cliente puede asignar una valoración en estrellas a una película dentro de su log.

2- Verificar que el sistema rechaza cualquier valor fuera de la escala de 0,5 a 5 estrellas o que no vaya en pasos de 0,5 (por ejemplo: 0, 3,7 o 6).

3- Comprobar que la valoración se guarda correctamente asociada al cliente y a la película.

4- Se debe aplicar la regla de negocio R.N.01.

#### **R.F.02. Consultar fecha y hora de los logs**
Como administrador

quiero que se pueda ver la fecha y hora de los logs que hacen los clientes

para poder diferenciarlos más fácilmente y mantener un control cronológico.

**- Pruebas de aceptación**

1- Comprobar que al consultar cualquier log de un cliente se muestra de forma visible su fecha y hora exacta.

2- Verificar que el sistema asigna automáticamente la fecha y hora del servidor al registrar el log.

3- Se debe aplicar la regla de negocio R.N.05.

#### **R.F.03. Registrar un rewatch**
Como cliente

quiero marcar una película como vista de nuevo (rewatch)

para llevar la cuenta de cuántas veces la he visualizado a lo largo del tiempo.

**- Pruebas de aceptación**

1- Comprobar que, al crear un nuevo log de una película que el cliente ya tenía registrada, el log queda marcado como rewatch.

2- Verificar que el sistema muestra correctamente cuántas veces ha visto el cliente esa película.

3- Se deben aplicar las reglas de negocio R.N.05 y R.N.10.

#### **R.F.04. Dar y retirar likes**
Como cliente

quiero dar o retirar un like en los logs de otros clientes y en las películas

para mostrar mi apoyo o acuerdo con sus valoraciones y reseñas, y destacar las películas que me gustan.

**- Pruebas de aceptación**

1- Comprobar que un cliente puede dar like a un log publicado por otro cliente y que queda registrado correctamente.

2- Comprobar que un cliente puede dar like a una película.

3- Verificar que el sistema impide que un cliente dé like a su propio log.

4- Comprobar que un cliente puede pulsar de nuevo sobre el botón de like para retirarlo.

5- Verificar que no se permite registrar más de un like por el mismo cliente en un mismo log o en una misma película.

6- Se debe aplicar la regla de negocio R.N.07.

#### **R.F.05. Gestionar las películas favoritas del perfil**
Como cliente

quiero seleccionar y ordenar mis 4 películas favoritas en mi perfil

para destacar aquellas obras que más me representan ante el resto de la comunidad.

**- Pruebas de aceptación**

1- Comprobar que el cliente puede añadir una película a su sección de favoritas en el perfil.

2- Verificar que el perfil contiene como máximo 4 películas favoritas, mostrando un mensaje de error si se intenta añadir una quinta.

3- Comprobar que cualquier otro cliente que consulte un perfil público puede ver dichas películas favoritas en el orden elegido.

4- Se debe aplicar la regla de negocio R.N.03.

#### **R.F.06. Seguir a otros clientes**
Como cliente

quiero seguir los perfiles públicos de otros clientes

para estar al tanto de su actividad, nuevas listas y reseñas recientes en mi sección de novedades.

**- Pruebas de aceptación**

1- Comprobar que un cliente puede pulsar el botón "Seguir" en un perfil público.

2- Verificar que el sistema impide seguir a clientes con el perfil privado.

3- Verificar que un cliente no puede seguirse a sí mismo.

4- Comprobar que se puede dejar de seguir a un cliente en cualquier momento y que la lista de seguidos/seguidores se actualiza al instante.

5- Se deben aplicar las reglas de negocio R.N.08 y R.N.11.

#### **R.F.07. Gestionar listas y watchlist**
Como cliente

quiero crear, editar y borrar listas de películas, y añadir o quitar películas de mi watchlist

para organizar las películas que he visto o que quiero ver.

**- Pruebas de aceptación**

1- Comprobar que un cliente puede crear una lista con nombre, descripción y privacidad.

2- Comprobar que un cliente puede añadir y quitar películas de una lista y de su watchlist.

3- Verificar que el sistema impide añadir dos veces la misma película a una lista o a la watchlist.

4- Comprobar que se pueden añadir a la watchlist películas que todavía no se han estrenado.

5- Se deben aplicar las reglas de negocio R.N.06 y R.N.08.

#### **R.F.08. Eliminar comentarios inapropiados**
Como administrador

quiero eliminar los comentarios inapropiados de los clientes

para mantener un ambiente sano y respetuoso en la plataforma.

**- Pruebas de aceptación**

1- Comprobar que un administrador puede eliminar el comentario de cualquier log.

2- Verificar que, al eliminar el comentario, el resto del log (película, fecha y valoración) se mantiene.

3- Verificar que un cliente no puede eliminar comentarios de otros clientes.

4- Se debe aplicar la regla de negocio R.N.12.

#### 4.1.1. Requisitos de información

##### **R.I.01. Información de las películas**
Como cliente

quiero conocer el título, fecha de estreno, duración, sinopsis y tags de las películas

para decidir qué películas ver.

##### **R.I.02. Información de los clientes**
Como administrador

quiero guardar el nombre de usuario, correo electrónico, contraseña y privacidad del perfil (público o privado) de cada cliente

para poder identificarlos y gestionar sus cuentas.

##### **R.I.03. Información de los administradores**
Como administrador

quiero guardar el nombre de usuario, correo electrónico y contraseña de cada administrador

para poder identificarlos al acceder al sistema.

##### **R.I.04. Información de los logs**
Como cliente

quiero que cada log guarde el cliente, la película, la fecha y hora, la valoración opcional, el comentario opcional y si es un rewatch

para tener un registro completo de las películas que he visto.

##### **R.I.05. Información de las listas**
Como cliente

quiero guardar el nombre, descripción, privacidad y películas de cada una de mis listas

para organizar mis películas.

##### **R.I.06. Información de la watchlist**
Como cliente

quiero guardar las películas que tengo pendientes de ver y la fecha en que las añadí

para recordar qué películas quiero ver.

##### **R.I.07. Información de los profesionales**
Como cliente

quiero conocer el nombre, nacionalidad y fecha de nacimiento de los profesionales, además de su papel (director, actor, guionista...) en cada película en la que participan

para conocer quién ha hecho cada película.

##### **R.I.08. Información de los tags**
Como cliente

quiero conocer el nombre de cada tag y las películas que tiene asociadas

para descubrir películas parecidas.

##### **R.I.09. Información de los likes**
Como cliente

quiero que se guarde qué cliente ha dado like, a qué log o a qué película, y la fecha del like

para saber qué contenido gusta más.

##### **R.I.10. Información de las películas favoritas**
Como cliente

quiero que se guarden mis películas favoritas y su posición (de 1 a 4) en mi perfil

para mostrarlas en el orden que yo elija.

##### **R.I.11. Información de los seguidores**
Como cliente

quiero que se guarde a qué clientes sigo, quién me sigue y desde qué fecha

para ver la actividad de los clientes que me interesan.

#### 4.1.2. Reglas de negocio

##### **R.N.01. Rango de valoración**
Como cliente

quiero que la valoración de una película esté entre 0,5 y 5 estrellas, en pasos de 0,5

para que todas las notas sigan la misma escala.

##### **R.N.02. Datos únicos de los usuarios**
Como administrador

quiero que no haya dos usuarios con el mismo nombre de usuario o el mismo correo electrónico

para poder identificar a cada usuario sin confusión.

##### **R.N.03. Máximo de películas favoritas**
Como cliente

quiero que mi perfil tenga como máximo 4 películas favoritas, sin repetir ninguna

para que mi perfil sea claro y fácil de ver.

##### **R.N.04. Log solo de películas estrenadas**
Como cliente

quiero que no se pueda registrar un log de una película que todavía no se ha estrenado

para que los registros sean reales.

##### **R.N.05. Fecha del log no futura**
Como administrador

quiero que la fecha y hora de un log no sea posterior al momento actual

para que los registros sean correctos.

##### **R.N.06. Películas no repetidas en una lista**
Como cliente

quiero que una película no pueda aparecer dos veces en la misma lista o en la watchlist

para tener mis listas ordenadas.

##### **R.N.07. Likes válidos**
Como cliente

quiero que no se pueda dar like a un log propio, y que cada cliente solo pueda dar un like por log y un like por película

para que los likes reflejen la opinión real de los clientes.

##### **R.N.08. Privacidad de listas y perfiles**
Como cliente

quiero que mis listas privadas y mi perfil privado solo los pueda ver yo

para proteger mi información.

##### **R.N.09. Duración de la película**
Como administrador

quiero que la duración de una película sea mayor que 0 minutos

para que la información de las películas sea correcta.

##### **R.N.10. Rewatch**
Como cliente

quiero que, si registro un log de una película que ya tenía registrada, el nuevo log se marque como rewatch

para saber cuántas veces he visto cada película.

##### **R.N.11. No seguirse a sí mismo**
Como cliente

quiero que un cliente no pueda seguirse a sí mismo ni seguir dos veces al mismo cliente

para que la lista de seguidores sea correcta.

##### **R.N.12. Solo administradores eliminan comentarios ajenos**
Como administrador

quiero que solo los administradores puedan eliminar comentarios de otros clientes

para mantener un buen ambiente en la plataforma.

### 4.2. Mapa de historias de usuario (opcional)

### 4.3. Requisitos no funcionales (opcional)

**R.N.F.01. Seguridad de las contraseñas**
Como cliente

quiero que mi contraseña se guarde cifrada

para que nadie pueda leerla aunque acceda a la base de datos.

-- fin entregable 1 --

## 5. Modelo conceptual

### 5.1. Diagramas de clases UML

![Modelo conceptual de FilmUS](modelo_conceptual.svg)

### 5.2. Escenarios de prueba

- con descripción textual y diagrama de objetos UML.

## 6. Matrices de trazabilidad

- Matriz de trazabilidad entre los elementos del modelo conceptual y los requisitos.

|       | EntidadX   | AsociaciónX  | RestricciónX  | Entidad2 ...   | 
|:------|:-----------|:-----------|:-----------|:-----------|
| RI-1  | X          | X          | X          | X          |
| RI-2  |            | X          |            | X          |
| RF-1  |            | X          |            | X          |
| RF-2  | X          |            | X          | X          |
| RN-1  |            | X          |            |            |
| RN-2  | X          | X          | X          |            |
| ...   |            |            |            |            |

-- fin entregable 2 --

## 7. Modelo relacional en 3FN

- Relaciones obtenidas al aplicar la transformación del modelo conceptual.

### 7.1.  Justificación de la estrategia de transformación de jerarquías

- si se identificaron jerarquías en el MC.


### 8. Matriz de trazabilidad MC/SQL (opcional):

- Restricciones sobre el MC / Elementos del modelo tecnológico (SQL) (Triggers, checks, etc.)
- Incluir Reglas de negocio — Constraints/Triggers en las matrices de trazabilidad para el entregable 3

|       | EntidadX   | AsociaciónX  | RestricciónX  | Entidad2 ...   | 
|:-------|:-------|:-------|:-------|:-------|
| TABLA-1 |        |        |        |        |
| TABLA-2 |        |        |        |        |
| TABLA-3 |        |        |        |        |
| TABLA-4 |        |        |        |        |
| TRIG-1 |        |        |        |        |
| TRIG-2 | X      | X      |        | X      |
| TRIG-3 |        | X      |        | X      |
| TRIG-4 |        |        | X      |        |
| CONST-1 |        |        |        |        |
| CONST-2 | X      | X      |        | X      |
| CONST-3 |        | X      |        | X      |
| CONST-4 |        |        | X      |        |

Se consideran todo tipo de constraints declarativas (aquellas definidas durante el CREATE TABLE).
-- fin entregable 3 --

## Referencias
