Trabajo practico de Traza correspondiente a la catedra de desarrollo de software. Realizado por Matias Fernandez, alumno de 3k10
El objetivo de este trabajo práctico es implementar operaciones CRUD (Crear, Leer, Actualizar y Eliminar) sobre una entidad Empresa, utilizando buenas prácticas de programación en Java. Para ello se aplicó:
  Separación entre modelo y servicio.
  Uso de Lombok para simplificar código repetitivo.
  Patrones de diseño básicos como Builder para instanciación fluida.

Estructura del proyecto: El proyecto se organiza en tres capas principales:
  Modelo (org.example.modelo)
      Contiene la clase Empresa, que representa la entidad principal.
Servicio (org.example.servicio)
  Contiene EmpresaServicio, donde se implementa la lógica Create, Read, Update, Delete.

Main (org.example)
Punto de entrada del programa. Se crean las entidades y se ejecutan las operaciones CRUD.

Clase Empresa: Esta clase define los atributos y relaciones principales. Gracias a Lombok, los métodos getters, setters, toString, equals, hashCode y constructores se generan automáticamente.

Decisiones de diseño:

  @Builder: permite construir instancias con un estilo legible y flexible.
  
  @EqualsAndHashCode.Exclude y @ToString.Exclude: evitan bucles infinitos al imprimir relacione sentre empresa y sucursal
  
  @Builder.Default: inicializa la colección sucursales para evitar NullPointerException.

Clase EmpresaServicio: Esta clase implementa la lógica CRUD sobre una colección en memoria haciendo Set <empresa>.

Principales métodos:
  guardar(Empresa e): agrega una empresa.
  listar(): muestra todas las empresas con detalle de sus sucursales.
  buscarPorId(Integer id): retorna una empresa según su ID.
  buscarPorNombre(String nombre): retorna una empresa según su nombre.
  actualizarCuit(Integer id, Long nuevoCuit): modifica el CUIT de una empresa existente.
  eliminar(Integer id): elimina una empresa por ID.

Decisiones de diseño:
  Uso de Streams para búsquedas rápidas y legibles.
  Validaciones simples (null, colecciones vacías) en lugar de try/catch innecesarios.
  Separación clara de responsabilidades: EmpresaService administra datos, Main los consume.

Conclusiones
  La implementación demuestra cómo aplicar CRUD básico en Java sin necesidad de base de datos, utilizando colecciones en memoria.
  Luego Lombok simplifica el código de   modelos, reduciendo la repetición. 
  El uso de EmpresaServicio permite separar responsabilidades, haciendo que el código sea más mantenible y escalable.
  El patrón Builder facilita la instanciación de entidades complejas.
