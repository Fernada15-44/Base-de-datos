# 📘 Diccionario de Datos – vehiculos



 **Tabla CLIENTES**

| Campo            | Tipo de Dato | Tamaño | PK  | FK  | Nulo | Único | Restricciones / CHECK           | Referencia a        | Descripción                        |
|------------------|--------------|--------|-----|-----|------|--------|---------------------------------|---------------------|------------------------------------|
| NumCliente       | INT          | -      | ✅   | ❌   | ❌   | ✅     | > 0                             | -                   | Identificador único del cliente    |
| Nombre           | NVARCHAR      | 100    | ❌   | ❌   | ❌   | ❌     | Solo letras A-Z, longitud >= 3  | -                   | Nombre del cliente                 |
| ApellidoPaterno  | NVARCHAR     | 20     | ❌   | ❌   | ❌   | ❌     | Solo letras A-Z, longitud >= 3  | -                   | Apellido paterno del cliente       |
| ApellidoMaterno  | NVARCHAR      | 150    | ❌   | ❌   | ❌   | ❌     | Solo letras A-Z, longitud >= 3  | -                   | Apellido materno del cliente       |
| CURP             | NVARCHAR      | 18     | ❌   | ❌   | ❌   | ✅     | Formato válido CURP             | -                   | CURP del cliente                   |
| Telefono         | NVARCHAR      | 15     | ❌   | ❌   | ❌   | ❌     | Solo dígitos, longitud >= 7     | -                   | Teléfono del cliente               |
| Calle            | NVARCHAR      | 50     | ❌   | ❌   | ❌   | ❌     | -                               | -                   | Calle de domicilio del cliente     |
| Num              | NVARCHAR      | 10     | ❌   | ❌   | ❌   | ❌     | Solo dígitos o letras           | -                   | Número exterior/interior domicilio |
| Ciudad           | NVARCHAR      | 50     | ❌   | ❌   | ❌   | ❌     | Solo letras A-Z, longitud >= 3  | -                   | Ciudad de residencia               |



 **Tabla VEHICULO**

| Campo            | Tipo de Dato | Tamaño | PK  | FK  | Nulo | Único | Restricciones / CHECK           | Referencia a        | Descripción                        |
|------------------|--------------|--------|-----|-----|------|--------|---------------------------------|---------------------|------------------------------------|
| NumVehiculo      | INT          | -      | ✅   | ❌   | ❌   | ✅     | > 0                             | -                   | Identificador único del vehículo  |
| Marca            | NVARCHAR      | 15    | ❌   | ❌   | ❌   | ❌     | - | -                   | Marca del vehículo                |
| Anio              | INT          | -      | ❌   | ❌   | ❌   | ❌     | -   | -                   | Año de fabricación del vehículo   |
| Modelo           | NVARCHAR      | 150    | ❌   | ❌   | ❌   | ❌     | -| -            | Modelo del vehículo               |
| Placa            | NVARCHAR      | 7    | ❌   | ❌   | ❌   | ✅     | -        | -                   | Placas del vehículo               |
| NumSucursal      | INT          | -      | ❌   |✅     | ❌   |❌    |-                           |-| Sucursal a la que pertenece       |
| NumCliente      | INT          | -      | ❌   | ✅   |❌     | ❌     | -                             | | Es el cliente que renta el vehiculo       |



 **Tabla SUCURSAL**

| Campo            | Tipo de Dato | Tamaño | PK  | FK  | Nulo | Único | Restricciones / CHECK           | Referencia a        | Descripción                        |
|------------------|--------------|--------|-----|-----|------|--------|---------------------------------|---------------------|------------------------------------|
| NumSucursal      | INT          | -      | ✅   | ❌   | ❌   | ✅     | > 0                             | -                   | Identificador único de la sucursal |
| NombreSucursal           | NVARCHAR      | 20    | ❌   | ❌   | ✅   | ❌     | Solo letras A-Z, longitud >= 3  | -                   | Nombre de la sucursal             |
| Ubicacion        | NVARCHAR      | 20    | ❌   | ❌   | ❌   | ✅    | Solo letras y números, longitud >= 5 | -              | Ubicación de la sucursal          |



 **Tabla RENTA**

| Campo              | Tipo de Dato | Tamaño | PK  | FK  | Nulo | Único | Restricciones / CHECK               | Referencia a        | Descripción                        |
|--------------------|--------------|--------|-----|-----|------|--------|-------------------------------------|---------------------|------------------------------------|
| NumCliente         | INT          | -      | ✅   | ✅   | ❌   | ❌     | > 0                                 | CLIENTES(NumCliente) | Cliente que realiza la renta       |
| NumVehiculo        | INT          | -      | ✅   | ✅   | ❌   | ❌     | > 0                                 | VEHICULO(NumVehiculo)| Vehículo rentado                   |
| NumDiasPrestados   | INT          | -      | ❌   | ❌   | ❌   | ❌     | >= 1 AND <= 365                     | -                   | Número de días de la renta         |
| FechaInicio        | DATE         | -      | ❌   | ❌   | ❌   | ❌     | >= '2000-01-01' AND <= CURRENT_DATE | -                   | Fecha de inicio de la renta        |
| FechaTermino       | DATE         | -      | ❌   | ❌   | ❌   | ❌     | >= FechaInicio                      | -                   | Fecha de término de la renta       |

