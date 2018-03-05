# MVC-vs-MVP-vs-MVVM


## MVC
Modelo-Vista-Controlador

El enfoque de modelo, vista y controlador separa su aplicación en un nivel macro en 3 conjuntos de responsabilidades:

**Controlador**: El controlador es el *pegamento* que une la aplicación. Es el controlador maestro de lo que sucede en la aplicación. Cuando la Vista le dice al controlador que un usuario hizo clic en un botón, el controlador decide cómo interactuar con el modelo en consecuencia. En el caso de una aplicación de Android, el controlador casi siempre está representado por una Actividad o Fragmento.

**Vista**: Es la Representación del Modelo, pues tiene la responsabilidad de representar la interfaz de usuario (UI) y comunicarse con el controlador cuando el usuario interactúa con la aplicación.

**Modelo**: Proveedor de datos, base de datos, web service, la lógica de la aplicación. Es el cerebro de nuestra aplicación, por así decirlo. No está vinculado a la vista o al controlador, y debido a esto, es reutilizable en muchos contextos.

### Conclusión

MVC hace un gran trabajo al separar el modelo y la vista. Ciertamente, el modelo se puede probar fácilmente porque no está vinculado a nada y la vista no tiene mucho que probar a nivel de prueba unitaria. Sin embargo, el controlador tiene algunos problemas.

### Peeeeeeeeero, hay algunas fallas dependiendo...

**Testability**: El controlador está tan ligado a las API de Android que es difícil de probar en una unidad.

**Modularity & Flexibility**: Los controladores están estrechamente acoplados a las vistas. Podría ser una extensión de la vista. Si cambiamos la vista, tenemos que regresar y cambiar el controlador.

**Maintenance**: Con el tiempo, particularmente en aplicaciones con modelos anémicos, cada vez más códigos comienzan a transferirse a los controladores, haciéndolos hinchados y quebradizos.


## MVP
Modelo-Vista-Presentador

MVP rompe el controlador para que el acoplamiento de vista / actividad natural pueda ocurrir sin vincularlo al resto de las responsabilidades del "controlador".


**Presentador**: Intermediario entre la vista y el modelo. Este es esencialmente el controlador de MVC, excepto que no está en absoluto vinculado a la Vista, solo una interfaz. Esto aborda las inquietudes de la capacidad de prueba, así como las preocupaciones de modularidad / flexibilidad que teníamos con MVC. 

**Vista**: Activitys, fragments, views...El único cambio aquí es que la Actividad / Fragmento ahora se considera parte de la vista. Dejamos de luchar contra la tendencia natural de que vayan de la mano. Una buena práctica es hacer que la Actividad implemente una interfaz de visualización para que el presentador tenga una interfaz para codificar. Esto elimina el acoplamiento a cualquier vista específica y permite la prueba de unidades simples con una implementación simulada de la vista.

**Modelo**: Proveedor de datos, base de datos, web service, la lógica de la aplicación

### Ventajas
Funciona muy bien en Android, porque:

* Es un patrón

* Expandible facilmente, ya que se programa por capas

* Escribir código de manera muy limpia

* Test unitarios de una manera muy sencilla

* Como la vista, por lo general, no va a tener lógica, lo hace más fácil

Aqui esta un ejemplo sencillo de MVP: https://github.com/Diegitsen/MVP-Example




