# Ejercicio 6
Usar como base la aplicación de ejemplo de heroku y combinarla con la aplicación en node que se ha creado anteriormente. 
Probarla de forma local con foreman. Al final de cada modificación, los tests tendrán que funcionar correctamente;
cuando se pasen los tests, se puede volver a desplegar en heroku.

Para este ejercicio se  definió primero el Procfile en la raíz del directorio de la aplicación
~~~
web: java -Dserver.port=$PORT $JAVA_OPTS -jar target/cc_hito_2_ejercicios-0.0.1-SNAPSHOT.jar
~~~
Luego se ejecuta el comando mvn install para que se instalen las dependecias y se genere el artefacto que esta definido 
en el Procfile.

finalmente se ejecuta el comando de Heroku:
~~~
heroku local
~~~
Y la aplicación se ejecuta en la siguiente dirección http://localhost:5000/



