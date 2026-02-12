Pasos para usar el proyecto:

1. Lanzar el contenedor de docker con docker:
   docker run -it --rm --name rabbitmq -p 5672:5672 -p 15672:15672 rabbitmq:3.12-management
2. Acceder a localhost:15672 con el user y passwd guest
3. Lanzar el servidor node.js
   npm init -y
   npm install express amqplib
4. Ejecutar el producer y consumer
   node producer.js
   node consumer.js

Para enviar 10 mensajes a la vez con powershell:
----------------------------------------
" 1..10 | ForEach-Object {
$body = "{""id"": $_, ""producto"": ""Item $_"", ""email"": ""pedido$_@hlanz.es""}"
Invoke-RestMethod -Uri "http://localhost:3000/comprar" -Method Post -ContentType "application/json" -Body $body
} "
----------------------------------------

JSON ejemplo por si quiero hacerlo con postman:
{"id": 101, "producto": "Teclado", "email": "alumno@escuela.com"}
