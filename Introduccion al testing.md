## Qué es el testing
El testing es verificar que el software que se esta construyendo o que esta siendo entregado cumpla según los requisitos solicitados por el cliente. 

Hay tres tipos de pruebas principales:
- Pruebas unitarias
- Pruebas de integración
- Pruebas funcionales

## Puntos claves 

### Pruebas unitarias
Estas pruebas son realizadas por el desarrollador y son base para entregar un buen producto con las lógicas solicitadas sin que este llegue a fallar en producción, teniendo así una gran perdida de esfuerzo, dinero y marca.
En estas pruebas unitarias consisten en verificar todo el código mediante pruebas (A todo el código se refiere a método por método, condición por condición). Se tarda mucho más en escribir los test que en hacer el código mismo dado que el codigo lo escribimos en nuestra cabeza, pero ya en el test unitario toca ir verificando linea por linea.

Ejemplo:
```java
  public void borrarUsuario(String username) { //Se ingresa un usuario al llamar el método 
    Usuario usuario = new Usuario(); //Se instancia la clase Usuario
    usuario.nombreUsuario = username; //Se le asigna el valor de username al atributo usuario.nombreUsuario

    usuariosDB.borrar(usuario);//Se usa el método "borrar" y dentro de el eliminamos al usuario.
  }
```
Cada parte lógica de mi método debe ser verificada, referente a eso deberemos preguntarnos si cada parte es lógicamente funcional, es decir:
- Si ingreso un usuario que no existe, ¿saldrá error? 
- Si el usuario ya existe, ¿lo eliminará? 
Haciendo así una lista de las cosas que se deberán probar.

### Pruebas de integración
Estas pruebas son en base a los módulos y su interaccion entre ellos, se verifica que esten conectados correctamente.

### Pruebas funcionales
Son aquellas en donde se revisa que el sofware si este funcionando, el dar un clic a un botón, buscar un producto, guardar un archivo.

### Prueba de aceptación 
Aquí el cliente ya realiza sus validaciones y da el visto bueno de sí, lo que se le ha entregado es lo que esperaba. Si llegásemos a entregar un carro Toyota en lugar de un Chevrolet, pues por más bien que funcione el Toyota lo van a devolver, porque no era lo que querían. Entonces esta prueba verifica que lo que hemos diseñado cumple con las especificaciones de un tercero, no tiene nada que ver con el código, tiene que ver con lo que el cliente ha pedido.

### Test case
Casos de prueba, cada cosa que yo voy a evaluar debera tener un test case.
Si yo hago algo y se cumple entonces es correcto, si yo hago algo y no se cumple es incorrecto, eso es el test case.

Ejemplo:
```java
  public void borrarUsuario(String username) {
    Usuario usuario = new Usuario(); 
    usuario.nombreUsuario = username; 

    /*
    *Debe de exitir un usuario.
    *Intento borrar un usuario, si el usuario se borra Ok.
    *Sino, No Ok.
    */

    usuariosDB.borrar(usuario);
  }
```
(Estos son test case para pruebas unitarias).

### Test suites y test suites collection
Los test suites se aplican a un unico módulo (Un conjuto de casos de test) y test suites collection es una colección de suites al tener muchos módulos (Se habala de todas las pruebas unitarias que se tienen en todo el código).

### Cómo saber qué se ha testeado: code coverage
Yo puedo hacer todos los test case, pero resulta que en una parte del código no se ejecuta, eso es porque se ha hecho mal los test. ¿Como saber que partes del código se han ejecutado y cuáles no? Mediante el code coverage, habla de por qué partes ha pasado el programa, si el código ha pasado por menos de un 95% significa que se han hecho mal las cosas.

Como correr el code coverage:
En el editor de texto a la derecha de la pantalla se encuentra un icono que pone "run 'EjercicioDiecocho' with Coverage" al darle clic se ejecuta nuestro código

![I1]()

Luego se muestra la jerarquía de nuestro proyecto con sus porcentajes, lo que se le puede llamar "Reporte de Coverage", así me aseguro de que el código pase por todas las partes posibles. 

![I1]() 

Se ha ejecutado al 100% para clases, métodos y lineas, que es el porcentaje ideal de nuestros test, al lado izquiero se pueden observar cuales lineas se han ejecutado y cuales no, como se muestra en el reporte existen dos lineas que no se ejecutaron, esto es por que no fueron utilizadas o no se mostraron.

### En qué se basan los tests
Se basan en que tengo una circunstancia y sobre esas circunstancias voy a generar una serie de acciones **para esperar un resultado**.
