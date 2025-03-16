# Patrón de diseño Singleton
## Patrón creacional

Este patrón se utiliza para generar un objeto único para todo el programa, puede ser un acceso a la base de datos por ejemplo, sería redundante tener que generar nuevos accesos a la base de datos cada vez que una instancia de aplicación realice una operación CRUD en la base de datos. Por lo tanto lo mejor es generar un único objeto y privatizar el constructor y evitar generar más instancias redundantes.

Otro ejemplo donde se pueda usar singleton es el patrón Abstract Factory, donde usas una fábrica para crear fábricas más específicas. Dado que pueden concatenarse, es efectivo usar un solo objeto Abtsract Factory para toda la aplicación.

El pseudocódigo de esta implementacións sería así:
```
GetVeryImportantInstance():
  if(VeryImportantInstance == null):
    VeryImportantInstance = new VeryImportantObject(...)
  return VeryImportantInstance
```

Si bien este patrón tiene varias ventajas, su uso puede complicar el mantenimiento y pruebas en el proyecto, ya que al cambiar o refactorizar la clase singleton, podrías causar problemas en los componentes del programa que usan el singleton, dichos problemas serán dificiles de hallar.

Imagen de la clase singleton: ![image](https://github.com/DanyElAlgo/borrador/blob/master/singleton.png "Singleton")

Referencias:

Singleton. (n.d.). https://refactoring.guru/es/design-patterns/singleton <br>
IONOS, E. editorial de. (2021, February 19). Patron singleton: Una Clase Propia. IONOS Digital Guide. https://www.ionos.com/es-us/digitalguide/paginas-web/desarrollo-web/patron-singleton/ 
