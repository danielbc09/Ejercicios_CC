# Ejercicio 7

Haz alguna modificación a tu aplicación en node.js para Heroku, sin olvidar añadir los tests para la nueva funcionalidad,
y configura el despliegue automático a Heroku usando Snap CI o alguno de los otros servicios, como Codeship, 
mencionados en StackOverflow.

Para este ejrecicio se escogio Travis CI como herramienta de despliegue. 

Para ello se crea el .travis.yml con lo siguiente

~~~
language: java
jdk: oraclejdk8
~~~

se configura travis y se selecciona el repositorio al cual le va a hacer seguimiento cuando se realice un PUSH.

https://github.com/danielbc09/spring_heroku

Finalmente se configura heroku para que utilice el repositorio de github en la sección de despliegue, 
ademas se configura que la aplicación se despliegue solo cuando los test pasen.


![heroku_deploy](https://user-images.githubusercontent.com/24718808/48613663-afdd2880-e98c-11e8-9358-392e838ba1b9.png)
