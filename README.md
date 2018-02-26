# MVC-vs-MVP-vs-MVVM

## MVP
Modelo-Vista-Presentador

### Ventajas
Funciona muy bien en Android, porque:
*Es un patrón
*Expandible facilmente, ya que se programa por capas
*Escribir código de manera muy limpia
*Test unitarios de una manera muy sencilla
*Como la vista, por lo general, no va a tener lógica, lo hace más fácil

**Presentador**: Intermediario entre la vista y el modelo
*Vista*: Activitys, fragments, views
~~Modelo~~: Proveedor de datos, base de datos, web service, la lógica de la aplicación
