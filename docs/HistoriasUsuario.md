Historias de usuario


1 Historia

Como usuario, quiero iniciar sesión en el sistema, para acceder a mis funcionalidades de acuerdo a mi rol.

Feature: Autenticación de usuarios

Scenario: Inicio de sesión exitoso
  Given: que el usuario está en la pantalla de login
  And: el usuario ingresa un nombre de usuario y contraseña válidos
  When: presiona el botón de iniciar sesión
  Then: el sistema debe permitir el acceso y mostrar el menú principal según el rol del usuario

Scenario: Inicio de sesión fallido
  Given: que el usuario está en la pantalla de login
  And: el usuario ingresa credenciales inválidas
  When: presiona el botón de iniciar sesión
  Then: el sistema debe mostrar un mensaje de error y no permitir el acceso

2 Historia

Como administrador, quiero registrar y editar trenes, estaciones, rutas y vagones, para mantener actualizada la información del sistema.
Feature: Administración de trenes y rutas

Scenario: Registrar un nuevo tren
  Given: que el administrador accede al módulo de trenes
  When: ingresa los datos del tren (nombre, id, capacidad, kilometraje)
  Then: el sistema debe guardar el tren en la base de datos

Scenario: Editar un tren existente
  Given: que el administrador selecciona un tren existente
  When: modifica los datos del tren
  Then:  el sistema debe actualizar la información y mostrar un mensaje de confirmación
  
3 Historia

Como usuario, quiero comprar boletos en la máquina de la estación, para reservar un asiento en el tren de mi elección.
Feature: Compra de boletos

Scenario: Compra exitosa de boleto
  Given: que el usuario accede a la máquina expendedora
  And: selecciona una ruta y horario disponibles
  And: proporciona sus datos personales
  When: realiza el pago
  Then: el sistema debe generar un boleto con la información de viaje y asignar asiento

Scenario: Intento de compra en tren lleno
  Given: que el tren seleccionado ya está a su máxima capacidad
  When: el usuario intenta comprar un boleto
  Then; el sistema debe mostrar un mensaje indicando que no hay cupos disponibles

4 Historia

Como sistema de información, quiero validar los boletos en el momento del abordaje, para garantizar que el pasajero tenga derecho a viajar.
Feature: Validación de boletos

Scenario: Validación correcta de boleto
  Given: que el pasajero presenta un boleto válido
  When: el sistema lo escanea
  Then: el sistema debe permitir el acceso al tren y registrar la validación

Scenario: Validación de boleto inválido
  Given: que el pasajero presenta un boleto ya usado o inexistente
  When: el sistema lo escanea
  Then: el sistema debe rechazar el acceso y mostrar un mensaje de error
  
5 Historia

Como usuario, quiero registrar mi equipaje al comprar el boleto, para asegurarme de que sea transportado correctamente.
Feature: Gestión de equipaje

Scenario: Registro de equipaje exitoso
  Given: que el usuario está comprando un boleto
  When: ingresa la información de su equipaje (id, peso)
  Then: el sistema debe asignar el equipaje a un vagón de carga

Scenario: Exceso de equipaje
  Given: que el usuario registra más de 2 maletas o un peso mayor a 90kg por maleta
  When: intenta confirmar la compra
  Then; el sistema debe rechazar el registro y mostrar un mensaje indicando el exceso de equipaje
  
6 Historia

Como sistema de información, quiero calcular la mejor ruta entre dos estaciones, para ofrecer al usuario la opción más rápida y eficiente.
Feature: Cálculo de la mejor ruta

Scenario: Ruta óptima disponible
  Given: que el usuario selecciona estación de origen y destino
  When: el sistema calcula la ruta
  Then: debe mostrar la ruta con menor distancia y su tiempo estimado

Scenario: Ruta no disponible
  Given: que no existe una ruta entre el origen y destino seleccionados
  When: el sistema intenta calcular la mejor ruta
  Then: debe mostrar un mensaje indicando que no hay conexión disponible
  
7 Historia

Como sistema de información, quiero publicar el orden de abordaje en las pantallas de la estación, para organizar el ingreso de pasajeros de forma ordenada.
Feature: Publicación del orden de abordaje

Scenario: Orden de abordaje según categoría
  Given: que se está por iniciar el abordaje
  When: el sistema genera el orden de ingreso
  Then: debe mostrar en pantalla primero a los pasajeros premium, luego ejecutivos y finalmente estándar, de atrás hacia adelante
  
8 Historia

Como sistema de información, quiero asignar vagones y carga automáticamente, para optimizar la distribución de pasajeros y equipaje.
Feature: Asignación automática de vagones

Scenario: Asignación de vagones correcta
  Given: que un tren tiene un número de pasajeros registrados
  When: el sistema procesa la información
  Then: debe asignar los pasajeros a los vagones disponibles
  And asignar un vagón de carga por cada dos vagones de pasajeros





