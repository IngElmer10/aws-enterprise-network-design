# Plan de direccionamiento (VLSM)

**Escenario académico:** comercio electrónico en AWS, VPC `10.0.0.0/16`, región `us-east-1`, dos zonas de disponibilidad.

| Subred | AZ | Hosts requeridos | CIDR | IP asignables según reservas de AWS | Tipo |
|---|---|---:|---|---:|---|
| `sn-web-zona-a` | `us-east-1a` | 500 | `10.0.0.0/23` | 507 | Pública |
| `sn-web-zona-b` | `us-east-1b` | 500 | `10.0.2.0/23` | 507 | Pública |
| `sn-app-zona-a` | `us-east-1a` | 250 | `10.0.4.0/24` | 251 | Privada |
| `sn-app-zona-b` | `us-east-1b` | 250 | `10.0.5.0/24` | 251 | Privada |
| `sn-datos-zona-a` | `us-east-1a` | 50 | `10.0.6.0/26` | 59 | Privada |
| `sn-datos-zona-b` | `us-east-1b` | 50 | `10.0.6.64/26` | 59 | Privada |

De acuerdo con el informe del Laboratorio 2, AWS reserva cinco direcciones por subred. La capacidad asignable se calcula restando esas cinco direcciones del tamaño de cada bloque.

## Rutas documentadas

**Lab 2:** tabla pública `rt-publica-ecommerce`, asociada a Web A/B, con `10.0.0.0/16 → local` y `0.0.0.0/0 → IGW`; tabla privada `rt-privada-ecommerce`, asociada a App A/B y Datos A/B, con solo `10.0.0.0/16 → local`.

**Lab 3:** propuesta de NAT Gateway y ruta por defecto en la tabla privada compartida para simplificar el ejercicio. El informe advierte que convendría separar las tablas de las capas de aplicación y datos y evaluar NAT zonal por disponibilidad.

**Lab 4:** pool de clientes `10.8.0.0/22` para AWS Client VPN, conceptualmente separado de las seis subredes. Ejemplo conceptual de LAN corporativa `192.168.50.0/24` conectada por Direct Connect y VPN Site-to-Site de respaldo.
