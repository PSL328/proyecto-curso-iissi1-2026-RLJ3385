# FilmUS

## Miembros del grupo L1-DF/AM-6

1. Sánchez Limón, Jose
2. Enrique Rosado, Jaime
3. Rafael Trampler Alejo, Mateo
4. Almeida Reyes, Joel

## 1. Introducción al problema

- Descripción del problema para poner en contexto el proyecto, incluyendo información sobre los clientes y usuarios, la situación actual, problemas, expectativas, etc. Se valorará la presencia de información multimedia (fotos, gráficos, documentos escaneados, etc.).

Queremos crear una aplicación que permita a las personas poder guardar sus descubrimientos sobre el cine en una red social, donde puedan compartir con otros usuarios sus gustos y recomendaciones. Cada cliente tendrá una cuenta pública que otros clientes puedan consultar.

Entre los tipos de usuarios, destacan los clientes y administradores.

Podríamos encontrarnos con problemas como, películas con un estreno reciente o incluso películas poco reconocidas no se encuentren disponibles en la base de datos, también hay problemas como gestionar nombres o comentarios inapropiados de los clientes (la función principal de los administradores). Esperamos conseguir una aplicación que tenga una experiencia de usuario satisfactoria, convertir el cine en un ambiente sano y respetuoso, además de que la gente pueda descubrir películas nuevas que merece la pena que sean vistas.

## 2. Glosario de términos

-Log: Es el registro del cliente que indica que ha visto una película en concreto, con una valoración y comentario opcionales.
-Rewatch: Cuando se registra que el cliente ha visto una misma película más de una vez.
-Watchlist: Lista de películas que el cliente tiene pendiente por ver.
-Tags: Etiqueta que se puede atribuir a una película y que la engloba con otras, por ejemplo: terror, drama, ciencia ficción...
-Like: Valoración positiva que hace un cliente sobre el log de otro cliente o sobre una película.

## 3. Visión general del sistema

### 3.1. Requisitos generales

#### R.G.01. Registrar películas vistas

Como cliente quiero guardar las películas que he visto, valorarlas y escribir comentarios para tener un registro de mi actividad.

#### R.G.02. Gestionar listas

Como cliente quiero crear listas de películas y tener una watchlist para organizar las películas que he visto o que quiero ver.

#### R.G.03. Consultar otros perfiles

Como cliente quiero ver los perfiles públicos de otros clientes para conocer sus películas vistas, valoraciones y listas públicas.

#### R.G.04. Consultar películas

Como cliente quiero consultar la información de las películas para conocer su título, fecha, duración, sinopsis y profesionales.

#### R.G.05. Moderar la plataforma

Como administrador quiero controlar la actividad de los clientes y eliminar comentarios inapropiados para mantener un buen ambiente en la plataforma.





### 3.2. Usuarios del sistema

- Cliente: Puede registrar películas vistas, valorar películas, escribir comentarios, crear listas y consultar perfiles públicos.
- Administrador: Se encarga de controlar la actividad de los clientes y eliminar contenido inapropiado.

## 4. Catálogo de requisitos

### 4.1. Requisitos funcionales

#### R.F.01. Título requisito funcional

Como [tipo de usuario]
quiero [servicio]
para [razón]


Como cliente quiero poder poner nota a películas para poder organizar mis películas según me hayan gustado más o menos

Como administrador quiero que se pueda ver la fecha y hora de los logs que hacen los clientes para poder diferenciarlos más facilmente

Como cliente quiero que en mi perfil se puedan ver mis 4 películas favoritas para poder compartirlo con otras personas



**Prueba de aceptación**
- Descripción de la primera comprobación a realizar
- Descripción de la segunda comprobación a realizar
- Se debe aplicar la regla de negocio R.N.XX.
- ...

#### 4.1.1. Requisitos de información

##### R.I.01. Título requisito de información

Como [tipo de usuario]
quiero [servicio]
para [razón]

**Prueba de aceptación**
- Descripción de la primera comprobación a realizar
- Descripción de la segunda comprobación a realizar
- ...

#### 4.1.2. Reglas de negocio

##### R.N.01. Título regla negocio

Descripción de la regla de negocio.

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

