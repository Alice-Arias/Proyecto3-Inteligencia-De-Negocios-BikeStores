# Proyecto 3 – Inteligencia de Negocios: BikeStores

Proyecto 3 del curso **Bases de Datos II** (TEC).

Solución de Inteligencia de Negocios basada en la base de datos de ejemplo
**BikeStores** de SQL Server. Incluye ETL, orquestador, Data Warehouse, cubo
y dashboards de ventas e inventario, todo con herramientas Microsoft.

## Herramientas

| Herramienta | Uso |
|---|---|
| SQL Server 2022 Developer | Base de datos BikeStores y Data Warehouse |
| SQL Server Management Studio (SSMS) | Scripts SQL |
| Visual Studio 2022 + SSIS | ETL (transformaciones) |
| SQL Server Agent | Orquestador (job que ejecuta el ETL) |
| Visual Studio 2022 + SSAS | Cubo de ventas |
| Power BI Desktop | Dashboards de ventas e inventario |

## Estructura del repositorio


| Carpeta | Contenido |
|---|---|
| `Documentacion` | Diagramas del modelo, informe y capturas de pantalla |
| `Base_De_Datos_Origen_BikeStores` | Scripts para crear y cargar la base original BikeStores |
| `Almacen_De_Datos_DataWarehouse` | Scripts para crear el Data Warehouse (dimensiones y hechos) |
| `ETL_Transformaciones_SSIS` | Proyecto SSIS que extrae, transforma y carga los datos |
| `Orquestador_Job_SQL_Server_Agent` | Script del job que ejecuta el ETL automáticamente |
| `Cubo_Analysis_Services_SSAS` | Proyecto del cubo de ventas |
| `Dashboards_Power_BI` | Dashboards de ventas e inventario (formato .pbip) |

## Modelo del Data Warehouse

- **Dimensiones:** Producto, Órdenes, Sucursales (Store), Clientes, Empleados (Staff), Fecha e Inventario.
- **Hechos:** Ventas (cantidad vendida, total vendido, descuentos, cantidad de facturas, fechas de orden, requerida y envío).
- Unidad mínima de tiempo: **día**.
- Nombres de clientes y empleados en formato **"nombre apellidos"**.
- Al menos **2 dimensiones SCD Tipo 2**; el resto **SCD Tipo 1**.

## Dashboards

- **Ventas:** total vendido y cantidad por producto, cliente, sucursal, empleado y categoría.
  Filtros: cliente, marca y rango de fechas.
- **Inventario:** total de inventario por categoría, marca y sucursal.
  Filtros: sucursal y categoría.

## Cómo ejecutar

1. Ejecutar los scripts de `Base_De_Datos_Origen_BikeStores` para crear y cargar BikeStores.
2. Ejecutar los scripts de `Almacen_De_Datos_DataWarehouse` para crear el Data Warehouse.
3. Abrir el proyecto de `ETL_Transformaciones_SSIS` en Visual Studio y desplegarlo.
4. Ejecutar el script de `Orquestador_Job_SQL_Server_Agent` para crear el job del ETL.
5. Desplegar el cubo de `Cubo_Analysis_Services_SSAS` en Analysis Services.
6. Abrir los dashboards de `Dashboards_Power_BI` en Power BI Desktop.

## Fuente de datos

https://www.sqlservertutorial.net/getting-started/sql-server-sample-database/
