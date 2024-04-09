## Diseño Conceptual de la Base de Datos para Aplicación de Entrega de Paquetería

### Entidades Principales:
#### Usuario:
- UserID (clave primaria)
- Nombre
- Apellido
- Rut
- Dirección
- Teléfono
- Correo electrónico
- TipoUserID (clave foránea de la tabla de Catálogo para los tipos de usuarios)
#### Conductor:
- DriverID (clave primaria)
- Nombre
- Apellido
- Teléfono
- Correo electrónico
- Disponibilidad
#### Vehículo:
- VehicleID (clave primaria)
- DriverID (clave foránea de la tabla de Conductores)
- Marca
- Modelo
- Año
- Placa
- TypeID (clave foránea de la tabla de Catálogo de Tipos de Vehículos)
- Estado del vehículo
#### Orden de Envío:
- OrderID (clave primaria)
- UserID (clave foránea de la tabla de Usuarios)
- Fecha de creación
- OrderStatusID (clave foránea de la tabla de Catálogo para Estado de Órdenes)
- Cantidad de puntos
#### Punto de Entrega:
- DeliveryPointID (clave primaria)
- OrderID (clave foránea de la tabla de Órdenes de Envío)
- Dirección de entrega
- Ciudad
- Estado
- Código postal
- DeliveryStatusID (clave foránea de la tabla de Catálogo para Estado de Entrega)

### Tablas de Catálogo:
#### Catálogo para los tipos de usuarios:
- TipoUserID (clave primaria)
- Tipo de usuario
#### Catálogo de Tipos de Vehículos:
- TypeID (clave primaria)
- Tipo de vehículo
#### Catálogo para Estado de Órdenes:
- OrderStatusID (clave primaria)
- Estado de la orden
#### Catálogo para Estado de Entrega:
- DeliveryStatusID (clave primaria)
- Estado de entrega

### Relaciones:
- Un usuario puede tener múltiples órdenes de envío (relación uno a muchos).
- Un conductor puede tener múltiples vehículos (relación uno a muchos).
- Un conductor puede estar asociado a múltiples puntos de entrega (relación uno a muchos).
- Un punto de entrega está asociado a una orden de envío (relación uno a uno).
- Una orden de envío puede tener múltiples puntos de entrega (relación uno a muchos).

Este diseño conceptual refleja las entidades principales de tu sistema y cómo se relacionan entre sí. Las tablas de catálogo ayudan a mantener una estructura estandarizada para ciertos atributos, como los tipos de usuarios y vehículos, mientras que las relaciones establecidas permiten gestionar eficientemente la información en la base de datos.
