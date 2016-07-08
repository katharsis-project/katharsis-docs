How to use Katharsis in your applications
=========================================

Katharsis provides means to easily expose resources over the REST interface. If you want to take a deeper look on the concepts behind Katharsis, this is page for you!


Requirements
------------

Below are listed dependencies used in Katharsis that project has to meet to be compatibile with latest library version:

.. note::
  Katharis library requires minimum Java 7 to build and run.


``katharsis-core``

.. code-block:: bash

  [INFO] io.katharsis:katharsis-core:jar:2.3.0
  [INFO] +- org.reflections:reflections:jar:0.9.9:compile
  [INFO] |  +- com.google.guava:guava:jar:15.0:compile
  [INFO] |  +- org.javassist:javassist:jar:3.18.2-GA:compile
  [INFO] |  \- com.google.code.findbugs:annotations:jar:2.0.1:compile
  [INFO] +- net.jodah:typetools:jar:0.4.0:compile
  [INFO] +- org.slf4j:slf4j-api:jar:1.7.12:compile
  [INFO] +- com.fasterxml.jackson.core:jackson-databind:jar:2.6.3:compile
  [INFO] |  \- com.fasterxml.jackson.core:jackson-core:jar:2.6.3:compile
  [INFO] +- com.fasterxml.jackson.core:jackson-annotations:jar:2.6.3:compile


``Katharsis-rs``

.. code-block:: bash

  [INFO] io.katharsis:katharsis-rs:jar:2.3.0
  [INFO] +- io.katharsis:katharsis-core:jar:2.3.0:compile
  [INFO] +- com.fasterxml.jackson.core:jackson-annotations:jar:2.6.3:compile
  [INFO] +- javax.ws.rs:javax.ws.rs-api:jar:2.0.1:compile
  [INFO] \- javax.servlet:javax.servlet-api:jar:3.0.1:compile


``katharsis-servlet``

.. code-block:: bash

  [INFO] io.katharsis:katharsis-servlet:jar:2.3.0
  [INFO] +- io.katharsis:katharsis-core:jar:2.3.0:compile
  [INFO] |  +- org.reflections:reflections:jar:0.9.9:compile
  [INFO] |  |  +- org.javassist:javassist:jar:3.18.2-GA:compile
  [INFO] |  |  \- com.google.code.findbugs:annotations:jar:2.0.1:compile
  [INFO] |  +- net.jodah:typetools:jar:0.4.0:compile
  [INFO] |  +- com.fasterxml.jackson.core:jackson-databind:jar:2.6.3:compile
  [INFO] |  |  \- com.fasterxml.jackson.core:jackson-core:jar:2.6.3:compile
  [INFO] |  \- com.fasterxml.jackson.core:jackson-annotations:jar:2.6.3:compile
  [INFO] +- com.google.guava:guava:jar:15.0:compile
  [INFO] +- javax.servlet:javax.servlet-api:jar:3.0.1:provided
  [INFO] +- org.slf4j:slf4j-api:jar:1.7.6:provided


``katharsis-spring``

.. code-block:: bash

  [INFO] io.katharsis:katharsis-spring:jar:2.3.0
  [INFO] +- org.springframework.boot:spring-boot-starter-web:jar:1.2.7.RELEASE:compile
  [INFO] |  +- org.springframework.boot:spring-boot-starter:jar:1.2.7.RELEASE:compile
  ...
  [INFO] +- org.springframework.boot:spring-boot-configuration-processor:jar:1.2.7.RELEASE:compile
  [INFO] |  \- org.json:json:jar:20140107:compile
  [INFO] +- io.katharsis:katharsis-servlet:jar:2.3.0:compile
  [INFO] |  +- io.katharsis:katharsis-core:jar:2.3.0:compile
  [INFO] |  |  +- org.reflections:reflections:jar:0.9.9:compile
  [INFO] |  |  |  +- org.javassist:javassist:jar:3.18.2-GA:compile
  [INFO] |  |  |  \- com.google.code.findbugs:annotations:jar:2.0.1:compile
  [INFO] |  |  +- net.jodah:typetools:jar:0.4.0:compile
  [INFO] |  |  \- org.slf4j:slf4j-api:jar:1.7.12:compile
  [INFO] |  \- com.google.guava:guava:jar:15.0:compile


``katharsis-vertx``

.. code-block:: bash

  +--- io.katharsis:katharsis-core:2.99.0-SNAPSHOT
  |    +--- org.projectlombok:lombok:1.16.8
  |    +--- net.jodah:typetools:0.4.4
  |    +--- org.slf4j:slf4j-api:1.7.13
  |    +--- com.fasterxml.jackson.core:jackson-databind:2.6.3
  |    |    +--- com.fasterxml.jackson.core:jackson-annotations:2.6.0 -> 2.6.3
  |    |    \--- com.fasterxml.jackson.core:jackson-core:2.6.3
  |    \--- com.fasterxml.jackson.core:jackson-annotations:2.6.3
  +--- io.vertx:vertx-core:3.2.1
  ...
  +--- io.vertx:vertx-web:3.2.1
  ...
  +--- org.reflections:reflections:0.9.9
  |    +--- com.google.guava:guava:15.0
  |    +--- org.javassist:javassist:3.18.2-GA
  |    \--- com.google.code.findbugs:annotations:2.0.1
  \--- org.slf4j:slf4j-api:1.7.13


Supported requests
------------------

Currently Katharsis covers most of the JSON API specification request types. The following table describes available requests that are currently accepted:

.. csv-table:: A summary of the supported requests
  :header:  HTTP method, Kind of request, Sample URL,  Multiplicity of resource

  GET,	resources, "http://host.local/tasks or http://host.local/tasks/1,2", multiple
  ,resource,	http://host.local/tasks/1,	single
  ,relationship,	http://host.local/tasks/1/relationships/project,	single
  ,field,	http://host.local/tasks/1/project,	single
  POST,	resource,	http://host.local/tasks,	single
  ,field,	http://host.local/tasks/1/project,	single
  ,relationship,	http://host.local/tasks/1/relationships/project,	single
  PATCH,	resource,	http://host.local/tasks/1,	single
  ,relationship,	http://host.local/tasks/1/relationships/project,	single
  DELETE,	resource,	http://host.local/tasks/1,	single
  ,relationship,	http://host.local/tasks/1/relationships/project,	single



Relationships
-------------

One of the main features of JSON API and Katharsis is support of managing relations between resources. To achieve that, two steps are required:

* Add a field annotated with JsonApiToOne or JsonApiToMany (depending on multiplicity of the relation) which will represent a unidirectional relation.
* Add a repository which defines operations that can be made on models.


Models
------

There are several annotations which can be assigned to models. By default all fields of the model are reflected in JSON API communication except synthetic fields. The annotations described below should be associated with either a field or a getter.


JsonApiResource
~~~~~~~~~~~~~~~

It is the most important annotation which defines a resource. It requires type parameter to be defined that is used to form a URLs and type field in passed JSONs. According to JSON API standard, the name defined in type can be either plural or singular

The example below shows a sample class which contains a definition of a resource.

.. code-block:: java

  @JsonApiResource(type = "tasks")
  public class Task {
    // fields, getters and setters
  }


JsonApiId
~~~~~~~~~

Defines a field which will be used as an identifier of a resource.
Each resource requires this annotation to be present on a field which type implements ``Serializable`` or is of primitive type.

The example below shows a sample class which contains a definition of a field which contains an identifier.

.. code-block:: java

  @JsonApiResource(type = "tasks")
  public class Task {
    @JsonApiId
    private Long id;

    // fields, getters and setters
  }

JsonApiToOne
~~~~~~~~~~~~

Indicates an association to single value which need to be handled by a separate ``RelationshipRepository``.
 A type of the field has to be a valid resource.

The example below shows a sample class which contains this kind of relationship.


.. code-block:: java

  @JsonApiResource(type = "tasks")
  public class Task {

    // ID field

    @JsonApiToOne
    private Project project;

    // fields, getters and setters
  }

JsonApiToMany
~~~~~~~~~~~~~

Indicates an association to many values which need to be handled by a separate ``RelationshipRepository``.
A type of the field has to be an ``Iterable`` or its derived classes (e.g.``List``) of valid resources.
By default, relationship is considered to be lazy, that is the relationship is not shown in the Top Level JSON.
To change that, pass parameter ``@JsonApiToMany(lazy = false)``.

The example below shows a sample class which contains this kind of relationship.

.. code-block:: java

  @JsonApiResource(type = "tasks")
  public class Task {

    // ID field

    @JsonApiToMany(lazy = false)
    private List<Project> projects;

    @JsonApiToMany // not shown in Top Level JSON
    private List<Log> logs;

    // fields, getters and setters
  }



JsonApiIncludeByDefault
~~~~~~~~~~~~~~~~~~~~~~~

Indicates additional resources that should be included by default (will be available
in included field of Top level JSON object) with every primary resource.
The field can be added to every relationship defined by ``JsonApiToOne`` or ``JsonApiToMany``.
Otherwise, ``ResourceException`` will be thrown at the initialization phrase.

The example below shows a sample model with this annotation.

.. code-block:: java

  @JsonApiResource(type = "tasks")
  public class Task {

    // ID field

    @JsonApiToOne
    @JsonApiIncludeByDefault
    private Project project;

    // fields, getters and setters
  }

JsonApiLookupIncludeAutomatically
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Field or getter annotated with ``JsonApiLookupIncludeAutomatically`` willl be automatically populated by Katharsis on ``GET`` requests.
It can be added to every relationship defined by ``JsonApiToOne`` or ``JsonApiToMany``.

The example below shows a sample class which will always contain a relationship's resource.

.. code-block:: java

  @JsonApiResource(type = "tasks")
  public class Task {

    // ID field

    @JsonApiToOne
    @JsonApiLookupIncludeAutomatically
    private Project project;

    // fields, getters and setters
  }


The framework support fields inheritance, it is possible to define fields in superclasses.

Repositories
------------

The model definition must have corresponding resource repository.
In addition, each relation also must have a corresponding repository.

Those repositories can be defined in one of the two ways:

* Implementing a repository interface:

  * ResourceRepository for a resource
  * RelationshipRepository for resource relationships

* Annotated with a repository annotation:

  * JsonApiResourceRepository for a resource
  * JsonApiRelationshipRepository for resource relationships
