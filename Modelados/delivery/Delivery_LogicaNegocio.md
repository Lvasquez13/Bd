### Entidades Principales
- **Usuarios**
  - UserID (clave primaria)
  - Nombre
  - Apellido
  - Rut
  - Dirección
  - Teléfono
  - Correo electrónico
  - TipoUserID (clave foránea de Tipo de Usuario)
- **Conductores**
  - DriverID (clave primaria)
  - Nombre
  - Apellido
  - Teléfono
  - Correo electrónico
  - Disponibilidad
- **Vehículos**
  - VehicleID (clave primaria)
  - DriverID (clave foránea de Conductores)
  - Marca
  - Modelo
  - Año
  - Placa
  - TypeID (clave foránea de Tipo de Vehículo)
- **Órdenes de Envío**
  - OrderID (clave primaria)
  - UserID (clave foránea de Usuarios)
  - Fecha de creación
  - OrderStatusID (clave foránea de Estado de Órdenes)
  - Cantidad de puntos
- **Puntos de Entrega**
  - DeliveryPointID (clave primaria)
  - OrderID (clave foránea de Órdenes de Envío)
  - Dirección de entrega
  - Ciudad
  - Estado
  - Código postal
  - DeliveryStatusID (clave foránea de Estado de Entrega)
- **Registro de Asignaciones**
  - AssignmentID (clave primaria)
  - DeliveryPointID (clave foránea de Puntos de Entrega)
  - DriverID (clave foránea de Conductores)
  - Fecha de asignación
  - Estado de asignación
- **Registro de Entregas**
  - DeliveryRecordID (clave primaria)
  - AssignmentID (clave foránea de Registro de Asignaciones)
  - Fecha de entrega
  - Hora de entrega
  - Estado de entrega
  - Detalles adicionales
  - DriverID (clave foránea de Conductores)
  - Coordenadas
  - Fotos

### Catálogos
- **Tipos de Usuarios**
  - TipoUserID (clave primaria)
  - Tipo de usuario
- **Tipos de Vehículos**
  - TypeID (clave primaria)
  - Tipo de vehículo
- **Estado de Órdenes**
  - OrderStatusID (clave primaria)
  - Estado de la orden
- **Estado de Entrega**
  - DeliveryStatusID (clave primaria)
  - Estado de entrega


### Relaciones:
- Un usuario puede tener múltiples órdenes de envío (relación uno a muchos).
- Un conductor puede tener múltiples vehículos (relación uno a muchos).
- Un conductor puede estar asociado a múltiples puntos de entrega (relación uno a muchos).
- Un punto de entrega está asociado a una orden de envío (relación uno a uno).
- Una orden de envío puede tener múltiples puntos de entrega (relación uno a muchos).

Este diseño conceptual refleja las entidades principales de tu sistema y cómo se relacionan entre sí. Las tablas de catálogo ayudan a mantener una estructura estandarizada para ciertos atributos, como los tipos de usuarios y vehículos, mientras que las relaciones establecidas permiten gestionar eficientemente la información en la base de datos.

### Modelo Relacional de la BD

![Modelo Relacional de la BD](./ ModeloRelacionalBd.png)
