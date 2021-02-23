# Publicación de datos

El objeto de este servicio es la publicación de datos recibidos desde los dispositivos y de la información asociada a los mismos. Para ello se expondrán dos interfaces
* Publicación en tiempo real de la posición de los eventos
* Publicación de datos asociados a cada evento

Para la conexión del Cloud es necesario ponerse en contacto con los responsables de la plataforma y solicitar el correspondiente Certificado Digital de cliente con el que se autenticarán frente a la plataforma.

## Contacto de Soporte

Para solventar cualquier duda o incidencia se ha abierto un buzón de correo en el que se atenderán estas

soporte@cmobility30.es

## Conectividad

Entorno | URL
|:-:|:-:
PRE | 
PRO |

## Flujo de conexión

![Flujo entrada](img/flujo_caso5_out.png)

## Publicación en tiempo real de eventos

Dada la criticidad de los eventos, se publicarán a través de un broker MQTT la información dinámica de los eventos. Los clientes se suscribirán al broker recibiendo la mensajería de acuerdo al API descrito en https://playground.asyncapi.io/?load=https://raw.githubusercontent.com/INSPIDE/DGT3.0Workshop_usecase_5/main/docs/dgt30_caso5_mqtt.yaml

En este mensaje se publica la información mínima relativa al evento, con lo que es posible localizarlo y el tamaño del mismo es lo suficientemente pequeño como para no saturar las comunicaciones.

## Publicación de datos asociados a cada evento

A través de un microservicio se expondrá un API REST para permitir la consulta de los metadatos asociados a un evento. Cada evento se publica con la siguiente información:
```json
{
  "id": "dkmd-9942-da",
  "ts": "2021-04-12T23:20:50.520Z",
  "lon": -3.45362,
  "lat": 40.45362,
  "event": 1,
  "beacon_type": 1,
  "vehicle_type": 1,
  "speed": 25.3
}
```
Si es necesario la consulta de los metadatos asociados, invocará a un servicio REST que expone la información disponible y que enriquece la original. La definición del API de este servicio se encuentra expuesta en xxxxxxxxxxxxx




## Proceso de autenticación

El proceso de autenticación requiere el uso del correspondiente certificado de cliente. 