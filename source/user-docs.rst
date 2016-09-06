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

  io.katharsis:katharsis-core:bundle:2.6.0
  +- org.reflections:reflections:jar:0.9.9:compile
  |  +- com.google.guava:guava:jar:15.0:compile
  |  +- org.javassist:javassist:jar:3.18.2-GA:compile
  |  \- com.google.code.findbugs:annotations:jar:2.0.1:compile
  +- net.jodah:typetools:jar:0.4.4:compile
  +- org.slf4j:slf4j-api:jar:1.7.13:compile
  +- com.fasterxml.jackson.core:jackson-databind:jar:2.6.3:compile
  |  \- com.fasterxml.jackson.core:jackson-core:jar:2.6.3:compile
  +- com.fasterxml.jackson.core:jackson-annotations:jar:2.6.3:compile


``katharsis-rs``

.. code-block:: bash

  io.katharsis:katharsis-rs:bundle:2.6.0
  +- io.katharsis:katharsis-core:jar:2.6.0:compile
  |  +- net.jodah:typetools:jar:0.4.4:compile
  |  +- org.slf4j:slf4j-api:jar:1.7.13:compile
  |  \- com.fasterxml.jackson.core:jackson-databind:jar:2.6.3:compile
  |     \- com.fasterxml.jackson.core:jackson-core:jar:2.6.3:compile
  +- com.fasterxml.jackson.core:jackson-annotations:jar:2.6.3:compile
  +- org.reflections:reflections:jar:0.9.9:compile
  |  +- com.google.guava:guava:jar:15.0:compile
  |  +- org.javassist:javassist:jar:3.18.2-GA:compile
  |  \- com.google.code.findbugs:annotations:jar:2.0.1:compile
  +- javax.ws.rs:javax.ws.rs-api:jar:2.0.1:compile
  +- javax.servlet:javax.servlet-api:jar:3.0.1:compile


``katharsis-servlet``

.. code-block:: bash

  io.katharsis:katharsis-servlet:bundle:2.6.0
  +- io.katharsis:katharsis-core:jar:2.6.0:compile
  |  +- net.jodah:typetools:jar:0.4.4:compile
  |  +- com.fasterxml.jackson.core:jackson-databind:jar:2.6.3:compile
  |  |  \- com.fasterxml.jackson.core:jackson-core:jar:2.6.3:compile
  |  \- com.fasterxml.jackson.core:jackson-annotations:jar:2.6.3:compile
  +- org.reflections:reflections:jar:0.9.9:compile
  |  +- org.javassist:javassist:jar:3.18.2-GA:compile
  |  \- com.google.code.findbugs:annotations:jar:2.0.1:compile
  +- com.google.guava:guava:jar:15.0:compile
  +- javax.servlet:javax.servlet-api:jar:3.0.1:provided
  +- org.slf4j:slf4j-api:jar:1.7.6:provided


``katharsis-spring``

.. code-block:: bash

  io.katharsis:katharsis-spring:bundle:2.6.0
  +- org.springframework.boot:spring-boot-starter-web:jar:1.3.1.RELEASE:compile
  |  ...
  +- org.springframework.boot:spring-boot-configuration-processor:jar:1.3.1.RELEASE:compile
  |  +- org.json:json:jar:20140107:compile
  |  \- org.springframework:spring-core:jar:4.2.4.RELEASE:compile
  |     \- commons-logging:commons-logging:jar:1.2:compile
  +- io.katharsis:katharsis-servlet:jar:2.6.0:compile
  |  +- io.katharsis:katharsis-core:jar:2.6.0:compile
  |  |  +- net.jodah:typetools:jar:0.4.4:compile
  |  |  \- org.slf4j:slf4j-api:jar:1.7.13:compile
  |  \- com.google.guava:guava:jar:15.0:compile
  +- org.reflections:reflections:jar:0.9.9:compile
  |  +- org.javassist:javassist:jar:3.18.2-GA:compile
  |  \- com.google.code.findbugs:annotations:jar:2.0.1:compile


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

  ``katharsis-client``

  .. code-block:: bash

  io.katharsis:katharsis-client:bundle:2.6.0
  +- io.katharsis:katharsis-core:jar:2.6.0:compile
  |  +- net.jodah:typetools:jar:0.4.4:compile
  |  +- org.slf4j:slf4j-api:jar:1.7.13:compile
  |  +- com.fasterxml.jackson.core:jackson-databind:jar:2.6.3:compile
  |  |  \- com.fasterxml.jackson.core:jackson-core:jar:2.6.3:compile
  |  \- com.fasterxml.jackson.core:jackson-annotations:jar:2.6.3:compile
  +- org.reflections:reflections:jar:0.9.9:compile
  |  +- com.google.guava:guava:jar:15.0:compile
  |  +- org.javassist:javassist:jar:3.18.2-GA:compile
  |  \- com.google.code.findbugs:annotations:jar:2.0.1:compile
  +- com.squareup.okhttp:okhttp:jar:2.7.5:compile
  |  \- com.squareup.okio:okio:jar:1.6.0:compile

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


ResourceRepository
~~~~~~~~~~~~~~~~~~

Base repository which is used to operate on the resources.
Each resource should have a corresponding repository implementation.
It consist of five basic methods which provide a CRUD for a resource and two parameters: the first is a type of a resource and the second is a type of the resource’s identifier.

The methods are as follows:

* ``findOne(ID id, QueryParams queryParams)``
  Search one resource with a given ID. If a resource cannot be found, a ResourceNotFoundException exception should be thrown.
  It should return an entity with associated relationships.

* ``findAll(QueryParams queryParams)``
  Search for all of the resources. An instance of QueryParams can be used if necessary.
  If no resources can be found an empty Iterable or null must be returned.
  It should return entities with associated relationships.

* ``findAll(Iterable<ID>ids, QueryParams queryParams)``
  Search for resources constrained by a list of identifiers. An instance of QueryParams can be used if necessary.
  If no resources can be found an empty Iterable or null must be returned.
  It should return entities with associated relationships.

* ``save(S entity)``
  Saves a resource. It should not save relating relationships. A Returning resource must include assigned identifier created for the instance of resource.
  This method should be able to both create a new resource and update existing one.

* ``delete(ID id)``
  Removes a resource identified by id parameter.


RelationshipRepository
~~~~~~~~~~~~~~~~~~~~~~

Each relationship defined in Katharsis (annotation @JsonApiToOne and @JsonApiToMany) must have a relationship repository defined.

Base unidirectional repository responsible for operations on relations.
All of the methods in this interface have fieldName field as last parameter.
It solves a problem of many relationships between the same resources.

* ``setRelation(T source, D_ID targetId, String fieldName)``
  Sets a resource defined by targetId to a field fieldName in an instance source. If no value is to be set, null value is passed.

* ``setRelations(T source, Iterable<D_ID> targetIds, String fieldName)``
  Sets resources defined by targetIds to a field fieldName in an instance source. This is a all-or-nothing operation, that is no partial relationship updates are passed. If no values are to be set, empty Iterable is passed.

* ``addRelations(T source, Iterable<D_ID> targetIds, String fieldName)``
  Adds relationships to a list of relationships.

* ``removeRelations(T source, Iterable<D_ID> targetIds, String fieldName)``
  Removes relationships from a list of relationships.

* ``findOneTarget(T_ID sourceId, String fieldName, QueryParams queryParams)``
  Finds one field's value defined by fieldName in a source defined by sourceId.

* ``findManyTargets(T_ID sourceId, String fieldName, QueryParams queryParams)``
  Finds an Iterable of field's values defined by fieldName in a source defined by sourceId .


This interface must be implemented to let Katharsis work correctly, some of the requests are processed using only this kind of repository.
As it can be seen above, there are two kinds of methods: for multiple and single relationships and it is possible to implement only one type of methods, e.g. singular methods.
Nevertheless, it should be avoided because of potential future problems when adding new fields of other sizes.


Annotated repositories
~~~~~~~~~~~~~~~~~~~~~~

A resource repository can be defined not by implementing ``ResourceRepository`` or ``RelationshipRepository`` interface,
but using ``JsonApiResourceRepository`` or ``JsonApiRelationshipRepository`` annotations from ``io.katharsis.repository.annotations`` package.

Defining the repositories this way has two benefits:

* It's not needed define all of the methods i.e. read-only resources might have just reading methods defined
* Additional parameters can be added to the methods like authentication, request headers or cookies

Along with the required parameters for each methods (like resource identifier in ``JsonApiFindOne``) default supported type is ``QueryParams`` which provides parsed set of query parameters.
Each Katharsis integration provides different set of supported parameters.
This list can be found in JAX-RS and Servlet integration sections.

A list below defines a mapping of ``ResourceRepository`` methods to annotations:

* ``findOne(ID, QueryParams) -> JsonApiFindOne``

  The first parameter has to be resource's id. The method has to return one resource.

* ``findAll(QueryParams) -> JsonApiFindAll``

  The method has to return a list of resources.

* ``findAll(Iterable<ID>, QueryParams) -> JsonApiFindAllWithIds``

  The first parameter has to be a list of resource ids. The method has to return a list of resources.

* ``save(S) -> JsonApiSave``

  The first parameter has to be resource. The method has to return one resource.

* ``delete(ID) -> JsonApiDelete``

  The first parameter has to be resource's id.


A list below defines a mapping of ``RelationshipRepository`` methods to annotations:

* ``setRelation(T, D_ID, String) -> JsonApiSetRelation``

  The requirements for the method parameters are as follows:

  #. Instance of a source resource
  #. Instance of a relationship to be set
  #. Relationship's filed name

* ``setRelations(T, Iterable<D_ID>, String) -> JsonApiSetRelations``

  The requirements for the method parameters are as follows:

  #. Instance of a source resource
  #. ``Iterable`` of relationships to be set
  #. Relationship's filed name

* ``addRelations(T, Iterable<D_ID>, String) -> JsonApiAddRelation``

  The requirements for the method parameters are as follows:

  #. Instance of a source resource
  #. Iterable of relationships to be add
  #. Relationship's filed name

* ``removeRelations(T, Iterable<D_ID>, String) -> JsonApiRemoveRelation``

  The requirements for the method parameters are as follows:

  #. Instance of a source resource
  #. Iterable of relationships to be removed
  #. Relationship's filed name

* ``findOneTarget(T_ID, String, QueryParams) -> JsonApiFindOneTarget``

  The requirements for the method parameters are as follows:

  #. An identifier of a source resource
  #. Relationship's field name
  #. The method has to return a resources.

* ``findManyTargets(T_ID, String, QueryParams) -> JsonApiFindManyTargets``

  The requirements for the method parameters are as follows:

  #. An identifier of a source resource
  #. Relationship's field name
  #. The method has to return an Iterable with resources.


Query parameters
----------------


Katharsis has defined set of query parameters which can be used by the framework during data retrieval and by a developer to perform other operations.
All of the types of parameters can be accessed using ``QueryParams`` object in repository methods.


Filtering
~~~~~~~~~

Resource filtering can be achieved by providing parameters which start with ``filter``.
The format for filters: ``filter[ResourceType][property|operator]([property|operator])* = "value"``

Examples:

* ``GET /tasks/?filter[tasks][name]=Super task``
* ``GET /tasks/?filter[tasks][name]=Super task&[tasks][dueDate]=2015-10-01``
* ``GET /tasks/?filter[tasks][name][EQ]=Super task``
* ``GET /tasks/?filter[tasks][name][][$startWith]=Super&[tasks][name][][$endWith]=task``

Sorting
~~~~~~~


.. note::

  Katharsis implementation differs form JSON API definition of sorting in order to fit standard query parameter serializing strategy and maximize effective processing of data.

Sorting information for the resources can be achieved by providing ``sort`` parameter.
The format for sorting: ``sort[ResourceType][property|operator]([property|operator])* = "value"``

Examples:

* ``GET /tasks/?sort[tasks][name]=asc``
* ``GET /tasks/?sort[projects][shortName]=desc&sort[users][name][firstName]=asc``


Grouping
~~~~~~~~

.. note::

  Grouping itself is not specified by JSON API itself, but the keyword and format it reserved for today and future use in Katharsis.

Grouping information for the resources can be achieved by providing ``group`` parameter.
The format for grouping: ``group[ResourceType] = "property(.property)*"``

Examples:

* ``GET /tasks/?group[tasks]=name``
* ``GET /tasks/?group[users]=name.firstName&include[projects]=team``

Pagination
~~~~~~~~~~

Pagination for the repositories can be achieved by providing ``page`` parameter.
The format for pagination: ``page[offset|limit] = "value", where value is an integer``

Example:

* ``GET /tasks/?page[offset]=0&page[limit]=10``


Sparse Fieldsets
~~~~~~~~~~~~~~~~

.. note::

  Katharsis implementation differs form JSON API definition of sparse field set in
  order to fit standard query parameter serializing strategy and maximize effective processing of data.

Information about fields to include in the response can be achieved by providing ``fields`` parameter.
The format for fields: ``fields[ResourceType] = "property(.property)*"``

Examples:

* ``GET /tasks/?fields[tasks]=name``
* ``GET /tasks/?fields[tasks][]=name&fields[tasks][]=dueDate``
* ``GET /tasks/?fields[users]=name.surname&include[tasks]=author``


Inclusion of Related Resources
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. note::

  Katharsis implementation differs form JSON API definition of sparse field set in
  order to fit standard query parameter serializing strategy and maximize effective processing of data.


Information about relationships to include in the response can be achieved by providing ``include`` parameter.
The format for fields: ``include[ResourceType] = "property(.property)*"``

Examples:

* ``GET /tasks/?include[tasks]=project``
* ``GET /tasks/1/?include[tasks]=project``
* ``GET /tasks/?include[tasks]=author``
* ``GET /tasks/?include[tasks][]=author&include[tasks][]=comments``
* ``GET /tasks/?include[projects]=task&include[tasks]=comments``


Error Handling
--------------

Processing errors in Katharsis can be handled by throwing an exception and providing corresponding exception mapper.
It will define mapping to proper JSON API error response.

Throwing an exception...
~~~~~~~~~~~~~~~~~~~~~~~~

Here is an example of throwing an Exception in the code:

.. code-block:: java

  if (somethingWentWrong()) {
    throw new SampleException("errorId", "Oops! Something went wrong.")
  }


Sample exception is nothing more than a simple runtime exception:

.. code-block:: java

  public class SampleException extends RuntimeException {

    private final String id;
    private final String title;

    public ExampleException(String id, String title) {
      this.id = id;
      this.title = title;
    }

    public String getId() {
      return id;
    }

    public String getTitle() {
      return title;
    }
  }


...and mapping it to JSON API response
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Class responsible for mapping the exception should:

* be annotated with ExceptionMapperProvider
* implements JsonApiExceptionMapper interface

Sample exception mapper:

.. code-block:: java

  @ExceptionMapperProvider
  public class SampleExceptionMapper implements JsonApiExceptionMapper<SampleException> {
    @Override
    public ErrorResponse toErrorResponse(SampleException exception) {
      return ErrorResponse.builder()
        .setStatus(HttpStatus.INTERNAL_SERVER_ERROR_500)
        .setSingleErrorData(ErrorData.builder()
          .setTitle(exception.getTitle())
          .setId(exception.getId())
          .build())
        .build();
    }
  }

Exception mapper classes will be scanned for and registered during application startup.
They should be located in your resource search package.

An exception should be mapped to an ErrorResponse object.
It consists of an HTTP status and ErrorData (which is consistent with JSON API error structure)


Meta Information
----------------

There is a special interface which can be added to resource repositories to provide meta information: ``io.katharsis.repository.MetaRepository``.
It contains a single method ``MetaInformation getMetaInformation(Iterable<T> resources)`` which return meta information object that implements a marker ``interface io.katharsis.response.MetaInformation``.

If you want to add meta information along with the responses, all repositories, that is those that implement ``ResourceRepository`` and ``RelationshipRepository``, must implement ``MetaRepository``.

When using annotated versions of repositories, a method that provides ``MetaInformation`` object should be annotated with ``JsonApiMeta`` and the first parameter of the method has to be a list of resources.

Links Information
-----------------

There is a special interface which can be added to resource repositories to provide links information: ``io.katharsis.repository.LinksRepository``.
It contains a single method ``LinksInformation getLinksInformation(Iterable<T> resources)`` which return links information object that implements a marker interface ``io.katharsis.response.LinksInformation``.

If you want to add meta information along with the responses, all repositories, that is those that implement ``ResourceRepository`` and ``RelationshipRepository``, must implement ``LinksRepository``.

When using annotated versions of repositories, a method that provides ``LinksInformation`` object should be annotated with ``JsonApiLinks`` and the first parameter of the method has to be a list of resources.


JAX-RS integration
------------------

Katharsis allows integration with JAX-RS environments trough the usage of JAX-RS specification. Under the hood there is a @PreMatching filter which checks each request for JSON API processing.

There are several steps required to integrate Katharsis into JAX-RS application.

Instantiation of a JsonServiceLocator
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Katharsis require an instance of every resources repository it finds. To provide them, ``JsonServiceLocator`` interface has to be implemented. There's a few examples on how to do that with:

* Dropwizard and Guice
* Wildfly and Weld
* without CDI - using SampleJsonServiceLocator which makes new instance of a repository class on every call

Instantiation of a KatharsisFeature
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Created instance of ``JsonServiceLocator`` has to be provided to new instance of ``KatharsisFeature`` along with Jackson Databind ObjectMapper.

Providing a configuration
~~~~~~~~~~~~~~~~~~~~~~~~~

There are three parameters that can be passed to the server to get the configuration.
All of them are defined in KatharsisProperties class:

* ``katharsis.config.core.resource.package``

  It allows configuring from which package should be searched to get models, repositories used by the core and exception mappers used to map thrown from repositories exceptions.

  Multiple packages can be passed by specifying a comma separated string of packages i.e. com.company.service.dto,com.company.service.repository.

* ``katharsis.config.core.resource.domain``

  Domain name as well as protocol and optionally port number used when building links objects in responses i.e. http://katharsis.io.
  The value cannot end with ``/``.

* ``katharsis.config.web.path.prefix (Optional)``

  Default prefix of a URL path used in two cases:

  * When building ``links`` objects in responses
  * When performing method matching

  An example of a prefix ``/api/v1``.

Registration of a KatharsisFeature
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Instantiated ``KatharsisFeature`` has to be registered as a JAX-RS feature.

Repository supported parameters
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

JAX-RS integration allows a developer to pass the following types of parameters in repository methods:

* An instance of ``ContainerRequestContext``
* An instance of ``SecurityContext``
* A cookie. The parameter should be annotated with ``@CookieParam("cookie name")``.
  The type can be either ``Cookie``, ``String`` or any other type that Jackson can handle.
* A header. The parameter should be annotated with ``@HeaderParam("header name")``.
  The type can be either ``String`` or any other type that Jackson can handle.

Servlet integration
-------------------

There are two ways of integrating katharsis using Servlets:

* Adding an instance of ``AbstractKatharsisServlet``
* Adding an instance of ``AbstractKatharsisFilter``

Integrating using a Servlet
~~~~~~~~~~~~~~~~~~~~~~~~~~~

To integrate katharsis using a servlet several steps are required.
The first one is to create a class that extends ``AbstractKatharsisServlet`` and will provide required configuration to the library.
A code below shows a sample implementation.

.. code-block:: java

  import io.katharsis.invoker.KatharsisInvokerBuilder;
  import io.katharsis.locator.JsonServiceLocator;
  import io.katharsis.locator.SampleJsonServiceLocator;

  import javax.servlet.ServletConfig;
  import javax.servlet.ServletException;

  public class SampleKatharsisServlet extends AbstractKatharsisServlet {

      private String resourceSearchPackage;
      private String resourceDefaultDomain;

      @Override
      public void init(ServletConfig servletConfig) throws ServletException {
          super.init(servletConfig);
          resourceSearchPackage = servletConfig
              .getInitParameter(KatharsisProperties.RESOURCE_SEARCH_PACKAGE);
          resourceDefaultDomain = servletConfig
              .getInitParameter(KatharsisProperties.RESOURCE_DEFAULT_DOMAIN);
      }

      /**
       * NOTE: A class extending this must provide a platform specific {@link JsonServiceLocator}
       *       instead of the (testing-purpose) {@link SampleJsonServiceLocator} below
       *       in order to provide advanced dependency injections for the repositories.
       */
      @Override
      protected KatharsisInvokerBuilder createKatharsisInvokerBuilder() {
          return new KatharsisInvokerBuilder()
              .resourceSearchPackage(resourceSearchPackage)
              .resourceDefaultDomain(resourceDefaultDomain)
              .jsonServiceLocator(new SampleJsonServiceLocator());
      }

  }

The newly created servlet has to be added to ``web.xml`` file or other deployment descriptor.
A code below shows a sample ``web.xml`` file with properly defined and configured servlet

.. code-block:: java

  <web-app>
    <servlet>
      <servlet-name>SampleKatharsisServlet</servlet-name>
      <servlet-class>io.katharsis.servlet.SampleKatharsisServlet</servlet-class>
      <init-param>
        <param-name>katharsis.config.core.resource.package</param-name>
        <param-value>io.katharsis.servlet.resource</param-value>
      </init-param>
      <init-param>
        <param-name>katharsis.config.core.resource.domain</param-name>
        <param-value>http://localhost:8080</param-value>
      </init-param>
    </servlet>
    <servlet-mapping>
      <servlet-name>SampleKatharsisServlet</servlet-name>
      <url-pattern>/api/v1/ *</url-pattern>
    </servlet-mapping>
  </web-app>


Integrating using a filter
~~~~~~~~~~~~~~~~~~~~~~~~~~

To integrate katharsis using a filter several steps are required.
The first one is to create a class that extends ``AbstractKatharsisFilter`` and will provide required configuration to the library.
A code below shows a sample implementation.

.. code-block:: java

  import io.katharsis.invoker.KatharsisInvokerBuilder;
  import io.katharsis.locator.JsonServiceLocator;
  import io.katharsis.locator.SampleJsonServiceLocator;

  import javax.servlet.FilterConfig;
  import javax.servlet.ServletException;

  public class SampleKatharsisFilter extends AbstractKatharsisFilter {

      private String resourceSearchPackage;
      private String resourceDefaultDomain;

      public void init(FilterConfig filterConfig) throws ServletException {
          super.init(filterConfig);
          resourceSearchPackage = filterConfig
              .getInitParameter(KatharsisProperties.RESOURCE_SEARCH_PACKAGE);
          resourceDefaultDomain = filterConfig
              .getInitParameter(KatharsisProperties.RESOURCE_DEFAULT_DOMAIN);
      }

      @Override
      public void init(FilterConfig filterConfig) throws ServletException {
          super.init(filterConfig);
          resourceSearchPackage = filterConfig
              .getInitParameter(KatharsisProperties.RESOURCE_SEARCH_PACKAGE);
          resourceDefaultDomain = filterConfig
              .getInitParameter(KatharsisProperties.RESOURCE_DEFAULT_DOMAIN);
      }

      /**
       * NOTE: A class extending this must provide a platform specific {@link JsonServiceLocator}
       *       instead of the (testing-purpose) {@link SampleJsonServiceLocator} below
       *       in order to provide advanced dependency injections for the repositories.
       */
      @Override
      protected KatharsisInvokerBuilder createKatharsisInvokerBuilder() {
          return new KatharsisInvokerBuilder()
              .resourceSearchPackage(resourceSearchPackage)
              .resourceDefaultDomain(resourceDefaultDomain)
              .jsonServiceLocator(new SampleJsonServiceLocator());
      }
  }

The newly created filter has to be added to ``web.xml`` file or other deployment descriptor.
A code below shows a sample ``web.xml`` file with properly defined and configured filter

.. code-block:: java

  <web-app>
    <filter>
      <filter-name>SampleKatharsisFilter</filter-name>
      <filter-class>io.katharsis.servlet.SampleKatharsisFilter</filter-class>
      <init-param>
        <param-name>katharsis.config.web.path.prefix</param-name>
        <param-value>/api/v1</param-value>
      </init-param>
      <init-param>
        <param-name>katharsis.config.core.resource.package</param-name>
        <param-value>io.katharsis.servlet.resource</param-value>
      </init-param>
      <init-param>
        <param-name>katharsis.config.core.resource.domain</param-name>
        <param-value>http://localhost:8080</param-value>
      </init-param>
    </filter>
    <filter-mapping>
      <filter-name>SampleKatharsisFilter</filter-name>
      <url-pattern>/api/v1/ *</url-pattern>
    </filter-mapping>
  </web-app>


Repository supported parameters
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Servlet integration allows a developer to pass the following types of parameters in repository methods:

* An instance of ``ServletContext``
* An instance of ``HttpServletRequest``
* An instance of ``HttpServletResponse``


Spring integration
------------------

Katharsis provide a simple Spring Boot integration using a ``@Configuration`` annotated class ``KatharsisConfigV2``.
Using this class the only thing needed to allow Katharsis process requests is to configure parameters.
An example ``application.properties`` file is presented below.

.. code-block:: bash

  katharsis.resourcePackage=io.katharsis.spring.domain
  katharsis.domainName=http://localhost:8080
  katharsis.pathPrefix=/api

Spring integration uses katharsis-servlet ``AbstractKatharsisFilter`` to fetch the requests.

Repository supported parameters
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Spring integration allows a developer to pass all of the types supported by Spring which doesn't operate on the response.


Vertx integration
-----------------

Katharsis provides ``Handler`` that intercepts requests and delegates them to Katharsis.

.. code-block:: bash

  dependencies {
      compile 'io.katharsis:katharsis-vertx:<version>'
  }


Simple usage example that creates the handler:

.. code-block:: java

  KatharsisHandler katharsisGlue = KatharsisHandlerFactory.create(Main.class.getPackage().getName(), "/api");
  router.route("/api/*").handler(katharsisGlue);

Advanced usage that shows how you can inject custom paramters in Katharsis repository methods.

.. code-block:: java

  ParameterProviderFactory factory = new SpringParameterProviderFactory(Json.mapper, context);

  KatharsisHandler katharsisGlue = KatharsisHandlerFactory.create(Main.class.getPackage().getName(), "/api",
  Json.mapper, new CustomParameterProviderFactory(Json.mapper, context));
  router.route("/api/*").handler(katharsisGlue);


Client
-----------------

Since v2.6.0 there is a new Katharsis client support for Java projects to allow
communicating with JSON-API compliant servers. `OkHttp <http://square.github.io/okhttp>`_
library has been used to allow usage in both Android and server applications and services.

.. note::
  This functionality should be considered experimental and used on your own risk.

The client requires to define resources in the same manner as defined in the `Models`_ section.
To start using the client just create an instance of ``KatharsisClient`` and pass the service
URL and the location to the package where the models are defined.

The client has two methods:

* ``KatharsisClient#getRepository(Class)`` to build a resource repository
* ``KatharsisClient#getRepository(Class, Class)`` to build a relationship repository

The interface of the repositories is as same as defined in `Repositories`_ section.

An example of the usage:

.. code-block:: java

  KatharsisClient client = new KatharsisClient("http://localhost:8080/api", "models");
  ResourceRepositoryStub<Task, Long> taskRepo = client.getRepository(Task.class);
  List<Task> tasks = taskRepo.findAll(new QueryParams());

Enjoy.
