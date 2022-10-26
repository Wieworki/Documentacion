# Alcance del módulo

El módulo encargado tiene como objetivo en primer lugar, la gestión de los pedidos de medicamentos a las farmacias, cubriendo el trayecto desde que se recibe la orden médica que especifíca
lo que necesita el afiliado, hasta que se le entrega lo que pidió. El proceso implica la generación, auditoría, envío y confirmación de los pedidos.
También debe ser capaz de llevar un stock de lo que está disponible en la farmacia de la obra social.

## Usuarios del sistema

El sistema contará con los siguientes usuarios:
- Operador de carga
- Médico auditor
- Contador
- Farmacéutico

#### Diagrama de casos de uso

![imagen](https://user-images.githubusercontent.com/45775681/198155312-db9b89f1-9437-4ed2-a627-b7e77c0a3595.png)

### Operador de carga
Encargado de cargar en el sistema lo que recibe está en la orden médica recibida del afiliado. Deberá indicar toda la información pertinente para la auditoría del pedido.
En el caso de los medicamentos que tengan recupero, deberá recibir un aviso por parte del sistema como recordatorio de la información extra que debe pedir al afiliado.
También tendrá la posibilidad de actualizar el listado de medicamentos.

### Médico auditor
Encargado de auditar los pedidos de medicamentos, estableciendo el porcentaje de cobertura que le dará la obra social, o pudiendo también rechazarlos.
Deberá contar con toda la información que pueda llegar a necesitar para evaluar el pedido de forma accesible.

### Contador
Encargado de hacer el pedido de los medicamentos. También puede auditar los medicamentos, modificando los porcentajes de cobertura que se les aplicarán.
Debe poder exportar a planilla de cálculo y a PDF los pedidos, para enviarlos a las droguerías.
Es el encargado de especificar la información de dónde se realizaron los pedidos de los medicamentos, actualizando esta información en el pedido, para que el farmacéutico
sepa de dónde viene, y cuando.

### Farmacéutico
Encargado de recepcionar los medicamentos. Debe indicar cuando se recepcionan los mismos, dando por finalizado el ciclo de vida del pedido. 
Además, debe poder mantener actualizado el stock

## Entidades

### Afiliado

### Pedido farmacia

### Detalle pedido

### Item farmacia

## Base de Datos
