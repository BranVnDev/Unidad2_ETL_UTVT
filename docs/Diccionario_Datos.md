# Diccionario de Datos - DWUTVTVentas

## DimCliente
- IdClienteSK: INT IDENTITY PK
- IdClienteOrigen: INT NOT NULL
- Nombre: VARCHAR(100)
- Apellido: VARCHAR(100)
- Correo: VARCHAR(150)
- Telefono: VARCHAR(20)
- Ciudad: VARCHAR(100)
- Estado: VARCHAR(100)
- Pais: VARCHAR(100)
- FechaRegistro: DATE
- FechaCarga: DATETIME


## DimProducto
- IdProductoSK: INT IDENTITY PK
- IdProductoOrigen: INT NOT NULL
- NombreProducto: VARCHAR(150)
- Categoria: VARCHAR(100)
- Precio: DECIMAL(12,2)
- Costo: DECIMAL(12,2)
- FechaCarga: DATETIME


## FactVentas
- IdVentaSK: INT IDENTITY PK
- IdVentaOrigen: INT NOT NULL
- IdClienteSK: INT FK -> DimCliente
- IdProductoSK: INT FK -> DimProducto
- Cantidad: INT
- PrecioUnitario: DECIMAL(12,2)
- Subtotal: DECIMAL(12,2)
- IVA: DECIMAL(12,2)
- Total: DECIMAL(12,2)
- FechaVenta: DATE
- Sucursal: VARCHAR(100)
- FechaCarga: DATETIME

## LogErrores
- IdError: INT IDENTITY PK
- NombrePaquete: VARCHAR(100)
- NombreFlujo: VARCHAR(100)
- ArchivoOrigen: VARCHAR(150)
- FilaOrigen: VARCHAR(MAX)
- DescripcionError: VARCHAR(500)
- FechaError: DATETIME

## LogProceso
- IdProceso: INT IDENTITY PK
- NombrePaquete: VARCHAR(100)
- FechaInicio: DATETIME
- FechaFin: DATETIME
- DuracionSegundos: INT
- TotalLeidos: INT
- TotalInsertados: INT
- TotalErrores: INT
- Estatus: VARCHAR(50)
- Mensaje: VARCHAR(500)
