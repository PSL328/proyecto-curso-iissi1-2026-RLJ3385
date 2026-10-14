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

- **Comentario**: Texto que escribe un cliente para dar su opinión sobre una película.
- **Like**: Valoración positiva que hace un cliente sobre el log de otro cliente o sobre una película.
- **Lista**: Grupo de películas creado por un cliente.
- **Log**: Es el registro del cliente que indica que ha visto una película en concreto, con una valoración y comentario opcionales.
- **Rewatch**: Cuando se registra que el cliente ha visto una misma película más de una vez.
- **Tags**: Etiqueta que se puede atribuir a una película y que la engloba con otras, por ejemplo: terror, drama, ciencia ficción.
- **Valoración**: Puntuación que un cliente da a una película.
- **Watchlist**: Lista de películas que el cliente tiene pendiente por ver.

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
- **Cliente**: Puede registrar películas vistas, valorar películas, escribir comentarios, crear listas y consultar perfiles públicos.
- **Administrador**: Se encarga de controlar la actividad de los clientes y eliminar contenido inapropiado.

## 4. Catálogo de requisitos

### 4.1. Requisitos funcionales

#### **R.F.01. Valorar peliculas**
Como cliente

quiero poder poner nota a las películas

para poder organizar mi historial según me hayan gustado más o menos.

**- Pruebas de aceptación**

1- Comprobar que un cliente puede asignar una valoración numérica o en estrellas a una película dentro de su log.

2- Verificar que el sistema rechaza cualquier valor que no se encuentre dentro de la escala 0-5 estrellas

3- Comprobar que la valoración se guarda correctamente asociada al usuario y a la película.

#### **R.F.02. Consultar fecha y hora de los logs**
Como administrador

quiero que se pueda ver la fecha y hora de los logs que hacen los clientes

para poder diferenciarlos más fácilmente y mantener un control cronológico.

**- Pruebas de aceptación**

1- Comprobar que al consultar cualquier log de un usuario se muestra de forma visible su marca de tiempo (fecha y hora exacta).

2- Verificar que el sistema asigna automáticamente la fecha y hora del servidor al registrar el log.

3- Se debe aplicar la regla de negocio que impide que la fecha del log sea posterior al momento actual

#### **R.F.03. Registrar un rewatch**
Como cliente

quiero marcar una película como vista de nuevo (rewatch)

para llevar la cuenta de cuántas veces la he visualizado a lo largo del tiempo.

**- Pruebas de aceptación**

1- Comprobar que un cliente puede indicar que ha vuelto a ver una película sobre un log existente o creando uno nuevo asociado a la misma.

2- Verificar que el sistema incrementa o almacena de forma correcta el contador de rewatches de dicha película para ese usuario.

3- Se debe aplicar la regla de negocio de que la fecha del nuevo log no sea futura

#### **R.F.04. Dar y retirar likes en los logs**
Como cliente

quiero dar o retirar un like en los logs de otros usuarios

para mostrar mi apoyo o acuerdo con sus valoraciones y reseñas.

**- Pruebas de aceptación**

1- Comprobar que un cliente puede dar "like" a un log publicado por otro usuario y que este queda registrado correctamente.

2- Verificar que el sistema impide que un usuario dé like a su propio log aplicando la regla de negocio correspondiente.

3- Comprobar que un usuario puede pulsar de nuevo sobre el botón de like para retirarlo.

4- Verificar que no se permite registrar más de un like por el mismo usuario en un mismo log.

#### **R.F.05. Gestionar las películas favoritas del perfil**
Como cliente

quiero seleccionar y ordenar mis 4 películas favoritas en mi perfil

para destacar aquellas obras que más me representan ante el resto de la comunidad.

**- Pruebas de aceptación**

1- Comprobar que el cliente puede añadir una película de su historial de vistas a su sección de favoritos en el perfil.

2- Verificar que se respeta estrictamente la restricción de que el perfil contenga como máximo 4 películas favoritas, mostrando un mensaje de error si se intenta añadir una quinta.

3- Comprobar que cualquier otro usuario que consulte un perfil público puede visualizar dichas películas favoritas.

#### **R.F.06. Seguir a otros usuarios**
Como cliente

quiero seguir los perfiles públicos de otros usuarios

para estar al tanto de su actividad, nuevas listas y reseñas recientes en mi sección de novedades.

**- Pruebas de aceptación**

1- Comprobar que un usuario puede pulsar el botón "Seguir" en un perfil que sea público.

2- Verificar que el sistema impide seguir a usuarios que tienen el perfil configurado como privado.

3- Comprobar que se puede dejar de seguir a un usuario en cualquier momento y que la lista de seguidos/seguidores se actualiza al instante.

#### 4.1.1. Requisitos de información

##### **R.I.01. Información de las películas**

Como cliente 

quiero conocer el título, fecha de estreno, duración y sinopsis de las películas.

##### **R.I.02. Información de los clientes**

Como administrador 

quiero guardar el nombre de usuario, correo electrónico, contraseña y privacidad del perfil de cada cliente.

##### **R.I.03. Información de los logs**

Como cliente 

quiero que cada log guarde la película, la fecha y hora, la valoración y el comentario opcional.

##### **R.I.04. Información de las listas**
Como cliente 

quiero guardar el nombre, descripción, privacidad y películas de cada una de mis listas.

##### **R.I.05. Información de los profesionales**
Como cliente quiero 

conocer el nombre, nacionalidad, fecha de nacimiento y profesión de los profesionales, además de su participación en cada película.

#### 4.1.2. Reglas de negocio

##### **R.N.01. Rango de valoración**
Como cliente

quiero que la valoración de una película esté entre 0 y 5 estrellas, en pasos de 0,5

para que todas las notas sigan la misma escala.

##### **R.N.02. Datos únicos del cliente**
Como administrador

quiero que no haya dos clientes con el mismo nombre de usuario o el mismo correo electrónico

para poder identificar a cada cliente sin confusión.

##### **R.N.03. Máximo de películas favoritas**
Como cliente

quiero que mi perfil tenga como máximo 4 películas favoritas

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

quiero que no se pueda dar like a un log propio, y que solo se pueda dar un like por log

para que los likes reflejen la opinión real de otros clientes.

##### **R.N.08. Privacidad de listas y perfiles**
Como cliente

quiero que mis listas privadas y mi perfil privado solo los pueda ver yo

para proteger mi información.

##### **R.N.09. Duración de la película**
Como administrador

quiero que la duración de una película sea mayor que 0 minutos

para que la información de las películas sea correcta.

### 4.2. Mapa de historias de usuario (opcional)

### 4.3. Requisitos no funcionales (opcional)

**R.N.F. 01. Título requisito no funcional**
Como [tipo de usuario]
quiero [servicio]
para [razón]

-- fin entregable 1 --

## 5. Modelo conceptual

### 5.1. Diagramas de clases UML

- con restricciones.

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
