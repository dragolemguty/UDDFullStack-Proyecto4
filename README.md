
# Proyecto 4

Esta es la entrega del proyecto 4 realcionada con la construccion de una logica Backend para un servicio hotelero, implementando la estructura Controlador-Vista


## API Reference

El proyecto logra responder a los siguientes casos endpoints:

### Crear nueva reserva

Genera nuieva reserva al entregarle un body con la información requerida. Retorna el id de la nueva reserva creada.

```http
  POST api/reservas/
```

| Parameter | Type     |
| :-------- | :------- |
| `body` | `json` |


```http
  {
	"id_guest":1,
	"id_room_array":[2,3],
	"arrival_date":"2024-07-17",
	"departure_date":"2024-07-20",
	"guests_qty":4
} 
```


### Reservas de hoy

Entrega las reservas existentes en el día actual.

```http
  GET api/reservas/
```


### Detalles de reserva

Entrega detalles de las reservas existentes segun el id de reserva. Ejemplo de id=2.

```http
  GET api/reservas/id
```

| Parameter | Type     | Description                       |
| :-------- | :------- | :-------------------------------- |
| `id`      | `string` | Id de reserva existente |



### Eliminar reserva

Elimina la reserva segun id. Ejemplo de id=2.

```http
  DELETE api/reservas/id
```

| Parameter | Type     | Description                       |
| :-------- | :------- | :-------------------------------- |
| `id`      | `string` | Id de reserva existente |


### Actualizar reserva

Genera una actualización de la reserva. Se le debe entregar un body de id y estado de cambio de habitacion.

```http
  PUT api/reservas/
```

| Parameter | Type     |
| :-------- | :------- |
| `body` | `json` |


```http
{
	"id":2,
	"is_type_room_change":1
}
```


### Reservas por hotel

Revisa todas las reservas de un hotel dado para el siguiente mes.

```http
  GET api/reservas?hotel=Hotel Shoebill
```

| Parameter | Type     | Description                       |
| :-------- | :------- | :-------------------------------- |
| `hotel`      | `string` |Nombre de hotel existente |



### Fechas de reservas

Retorna todas las reservas existentes entre dos fechas dadas.

```http
  GET api/reservas?fecha_inicio=2024-12-15&fecha_fin=2024-12-30
```

| Parameter | Type     | Description                       |
| :-------- | :------- | :-------------------------------- |
| `fecha_inicio`      | `date` | fecha en formato YYYY-MM-DD |
| `fecha_fin`      | `date` | fecha en formato YYYY-MM-DD |


### Habitaciones de reservas

Entrega todas las reservas asociadas a un tipo de habitacion que existan para el proximo mes.

```http
  GET api/reservas?tipo_habitacion=Suit Familiar
```

| Parameter | Type     | Description                       |
| :-------- | :------- | :-------------------------------- |
| `tipo_habitacion`      | `string` | Nombre de habitacion existente |




### Estado de pago

Entrega estado de pago de reservas, con 0 no pagado y 1 pagado.

```http
  GET api/reservas?estado=0
```

| Parameter | Type     | Description                       |
| :-------- | :------- | :-------------------------------- |
| `estado`      | `numeric` | 0: No pagado , 1: Pagado |




### Filtro de reservas segun cantidad de pasajeros

Entrega todas las reservas que contengan al menos determinada cantidad de huespedes.

```http
  GET api/reservas?num_huespedes=5
```

| Parameter | Type     | Description                       |
| :-------- | :------- | :-------------------------------- |
| `num_huespedes`      | `numeric` |Numero de cantidad de huespedes |



