# Workshop Code Engine
## Crear mi instancia del servicio 
1. Ingresar a una cuenta en IBM CLOUD 
2. Ir al catálogo de recursos y buscar Code Engine
3. Crear un proyecto
4. Abrir el proyecto

## Crear la aplicación
1. Poner source code
2. URL github: https://github.com/kevin-anadon/rest-api-sample-js
3. Specify build details strategy with dockerfile PENDIENTE(Output Docker.io)
3. Puerto 8080
4. Bajar maximo numero de instancias a 1
5. Domain mappings: Public
6. Variables de entorno ya está pronto el PORT

## Probar la aplicación
1. Probar los 3 endpoints y con varios ejemplos entrando al readme del repo de la api

## Eliminar la aplicación
1. Eliminar instancia
2. Eliminar proyecto

# Workshop Watsonx Assistant

## Crear mi instancia del servicio 
1. Ingresar a una cuenta de IBM CLOUD
2. Ir al catálogo de recursos y buscar Watson Assistant
3. Crear una instancia Lite (Version gratis)
4. Abrir la instancia

## Desarrollar un chatbot en mi instancia

### Saludo al Usuario y obtener su nombre
1. Ir a las acciones "Set By Assistant" y modificar "Greet Customer"
2. Saludar al usuario y preguntar su nombre, esperar una respuesta free text en el primer paso
3. En un segundo paso guardar la respuesta del primer paso en una variable nueva llamada Nombre
4. Luego crear otro paso donde el asistente diga "Hola $nombre en que te puedo ayudar?"

### Crear Acciones Simples 

#### Acción 1: "Sucursales"
1. El usuario accede a la acción diciendo por ejemplo : "Donde estan sus sucursales?" o "sucursales" Agregar al menos 3 formas distintas. 
2. La respuesta del asistente debe indicar una sucursal ficticia de la librería con los siguientes datos: 
   - Nombre de la librería
   - País
   - Localidad
   - Calle
   - Número
  
#### Acción 2: "Préstamos"
1. Agregar 3 formas distintas por las cuales el usuario accede a la acción "Préstamos"
2. En el primer paso preguntar al usuario si el libro a prestar tiene fines Educativos o Recreativos
3. Configurar una respuesta del usuario con estas 2 opciones
4. En el segundo paso agregar una condición, si la respuesta del paso 1 es "Educativos", entonces el asistente responde "El préstamos de libros con fines Educativos es gratis y por un tiempo de hasta 1 año."
5. En un tercer paso agregar una condición, si la respuesta del paso 1 es "Recreativos", entonces el asistente responde 3 opciones distintas: 
   - "El préstamo de libros con fines Recreativos tiene un costo de 1200$ por mes."
   - "El préstamo de libros con fines Recreativos tiene un costo de 400$ por semana."
   - "El préstamo de libros con fines Recreativos tiene un costo de 80$ por día y el tiempo es indeterminado."

#### Acción 3: Libre 
Deben utilizar al menos 2 de las siguientes herramientas (Condiciones, Variable, Respuesta por Confirmación, Respuesta por Opciones)

### Agregar una REST API
1. Ir a la seccion de Integrations
2. Click en create custom extension
3. Seguir los pasos y subir la Open Api Specification de nuestra REST API
4. Verificar que los endpoints, los parametros y las respuestas parezcan correctas

### Crear Acciones Complejas

#### Acción 4: "Reservado"
1. Agregar 3 formas distintas de acceder a la acción
2. En el primer paso preguntar el nombre del libro que el usuario desea chekear de la lista de libros y esperar una respuesta del usuario
3. En el segundo paso usar la extensión con el endpoint correspondiente y asignarle el valor de la respuesta del paso 1 al parámetro
4. En el último paso el asistente debe responder la variable de respuesta que recibe de la extensión
5. El resultado final debería ser "El libro ... esta reservado es $respuesta.extension"

#### Acción 5: "Autor"
1. Agregar 3 formas distintas de acceder a la acción
2. En el primer paso preguntar por que libro de la lista de libros desea consultar
3. En el segundo paso utilizar la extension con el endpoint correspondiente y asignarle la respuesta del paso 1 al parametro de la extensión
4. En el último paso el asistente debe responder la variable de respuesta que recibe de la extensión
5. El resultado final debería ser "El libro $nombre-del-libro fue escrito por $respuesta.autor"

#### Acción 6: "Informacion de un libro"
1. Agregar 3 formas distintas de acceder a la acción
2. En el primer paso preguntar por que libro de la lista de libros desea consutar
3. Luego utilizar la extensión con el endpoint correspondiente y asignarle la respuesta del paso 1 al parametro de la extensión
4. En el ultimo paso el asistente debe responder "El libro $respuesta.nombre fue escrito por $respuesta.autor y es del género $respuesta.genero"
