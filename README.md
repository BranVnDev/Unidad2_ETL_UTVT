# Proyecto ETL - Comercializadora UTVT S.A. de C.V.

## Descripción
Proceso ETL desarrollado con SQL Server Integration Services (SSIS) para cargar datos de ventas desde archivos CSV hacia el Data Warehouse `DWUTVTVentas`. Incluye limpieza, validación, transformación y automatización del proceso.

## Arquitectura del Proyecto
```
Proyecto_ETL_UTVT/
├── data/
│   ├── entrada/       # Archivos CSV de entrada
│   ├── procesados/    # Archivos procesados y comprimidos
│   └── errores/       # Registro de errores CSV
├── database/          # Script SQL de creación de BD
├── ssis/              # Paquetes SSIS
├── docs/              # Documentación técnica
└── evidencias/        # Capturas y video
```

## Requisitos
- SQL Server (2019+)
- SQL Server Data Tools (SSDT) con SSIS
- PowerShell 5.0+

## Estructura del Paquete SSIS
El paquete orquestador `CargaVentas.dtsx` ejecuta el siguiente flujo:
1. Validar existencia de archivos CSV
2. Registrar inicio en LogProceso
3. Cargar dimensión Clientes
4. Cargar dimensión Productos
5. Cargar tabla de hechos FactVentas
6. Registrar estadísticas
7. Mover archivos a procesados
8. Comprimir archivos (ZIP)
9. Registrar fin en LogProceso

## Base de Datos
- **Nombre:** DWUTVTVentas
- **Tablas:** DimCliente, DimProducto, FactVentas, LogErrores, LogProceso

## Control de Versiones
- Rama `main`: Versión estable
- Rama `feature/clientes`: Carga de dimensión clientes
- Rama `feature/productos`: Carga de dimensión productos
- Rama `feature/ventas`: Carga de tabla de hechos

## Autor
BranVnDev


## Instrucciones de Ejecucion
1. Ejecutar database/create_DWUTVTVentas.sql en SQL Server
2. Colocar archivos CSV en data/entrada/
3. Abrir CargaVentas.dtsx en SSDT
4. Configurar conexion a SQL Server
5. Ejecutar el paquete

## Evidencias
- Las capturas de ejecucion estan en evidencias/
- Los errores se registran en data/errores/Errores.csv
- Los archivos procesados se comprimen en data/procesados/

