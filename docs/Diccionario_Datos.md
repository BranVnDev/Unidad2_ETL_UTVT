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
