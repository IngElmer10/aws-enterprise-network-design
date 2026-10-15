# AWS Enterprise Network Design

**Diseño de arquitectura de red empresarial para una plataforma de comercio electrónico en AWS**  
Diplomado en Cloud Infrastructure & DevSecOps · Módulo 1: Arquitectura de Nube y Redes Empresariales · UAGRM · Octubre de 2026

> [!IMPORTANT]
> **Alcance: Ruta B — investigación y diseño técnico.** Este es un proyecto académico **documentado, no desplegado**. No se aprovisionaron recursos en AWS ni se ejecutaron pruebas reales de conectividad. Los comandos y verificaciones incluidos en los informes son procedimientos propuestos o resultados esperados. Las capturas de documentación oficial de AWS se identifican como referencias, no como evidencia de una implementación propia.

## Descripción

Propuesta de red para una empresa de comercio electrónico con **tres capas (web, aplicación y datos)** y dos zonas de disponibilidad. El caso se desarrolla de manera progresiva en tres laboratorios: **direccionamiento y ruteo**, **seguridad perimetral** y **conectividad remota e híbrida**.

### Laboratorio 2 · VPC, subredes y tablas de ruteo

![Diagrama original de la VPC y las seis subredes propuestas](diagrams/lab-02-vpc-subnets.png)

Se diseñó una **VPC `10.0.0.0/16`**, con seis subredes distribuidas en dos zonas de disponibilidad, dimensionamiento VLSM y tablas de ruteo para separar la exposición pública de la capa web respecto de las capas privadas de aplicación y datos.

**Recursos:** [Informe completo en PDF](docs/lab-02-vpc-routing.pdf) · [Resumen técnico](docs/lab-02-resumen.md) · [Diagrama de tablas de ruteo](diagrams/lab-02-route-tables.png) · [Plan de direccionamiento](addressing/README.md)

### Laboratorio 3 · Seguridad perimetral y mínimo privilegio

![Diagrama original de la arquitectura de seguridad propuesta](diagrams/lab-03-security-architecture.png)

Se amplió la arquitectura con reglas propuestas de **Security Groups y NACL**, flujos permitidos entre capas, estudio de **NAT Gateway** y administración mediante **bastión**. La intención es limitar el tráfico a las comunicaciones justificadas por el caso de negocio.

**Recursos:** [Informe completo en PDF](docs/lab-03-network-security.pdf) · [Resumen técnico](docs/lab-03-resumen.md) · [Diagrama de flujos autorizados](diagrams/lab-03-authorized-flows.png)

### Laboratorio 4 · Acceso remoto y conectividad híbrida

![Diagrama original de AWS Client VPN como extensión conceptual de la VPC](diagrams/lab-04-client-vpn.png)

Se documentó una propuesta de **AWS Client VPN**, con rango de clientes `10.8.0.0/22`, y se analizaron las diferencias entre **VPN de acceso remoto, Site-to-Site VPN/IPSec, WireGuard y Direct Connect**. Se estudió una arquitectura híbrida conceptual con **Direct Connect como conexión primaria y Site-to-Site VPN como respaldo**, considerando el comportamiento del ruteo BGP.

**Recursos:** [Informe completo en PDF](docs/lab-04-hybrid-connectivity.pdf) · [Resumen técnico](docs/lab-04-resumen.md) · [Diagrama del flujo de acceso remoto](diagrams/lab-04-remote-access-flow.png)

## Direccionamiento VLSM

| Capa | Zona A | Zona B | Exposición propuesta |
| --- | --- | --- | --- |
| Web | `10.0.0.0/23` | `10.0.2.0/23` | Pública |
| Aplicación | `10.0.4.0/24` | `10.0.5.0/24` | Privada |
| Datos | `10.0.6.0/26` | `10.0.6.64/26` | Privada |

La VPC utiliza `10.0.0.0/16`; el rango `10.8.0.0/22` del ejemplo de **Client VPN** no corresponde a una séptima subred de esa VPC. [Ver el plan detallado](addressing/README.md).

## Contenido del repositorio

```text
.
├── README.md
├── addressing/
│   └── README.md
├── docs/
│   ├── README.md
│   ├── lab-02-resumen.md
│   ├── lab-02-vpc-routing.pdf
│   ├── lab-03-resumen.md
│   ├── lab-03-network-security.pdf
│   ├── lab-04-resumen.md
│   └── lab-04-hybrid-connectivity.pdf
└── diagrams/
    ├── README.md
    ├── lab-02-vpc-subnets.png
    ├── lab-02-route-tables.png
    ├── lab-03-security-architecture.png
    ├── lab-03-authorized-flows.png
    ├── lab-04-client-vpn.png
    └── lab-04-remote-access-flow.png
```

[Consultar los tres informes](docs/README.md) · [Explorar todos los diagramas](diagrams/README.md)

## Tecnologías y conceptos estudiados

`Amazon Web Services` · `Amazon VPC` · `IPv4 / VLSM` · `Route Tables` · `Internet Gateway` · `Security Groups` · `Network ACLs` · `NAT Gateway` · `Bastion Host` · `AWS Client VPN` · `Site-to-Site VPN` · `AWS Direct Connect` · `IPSec` · `BGP`

---

**Autor:** Elmer Fuentes Lozano · **Contexto:** Diplomado en Cloud Infrastructure & DevSecOps — Universidad Autónoma Gabriel René Moreno (UAGRM).  
**Tipo de proyecto:** académico, Ruta B — diseño e investigación; no es una implementación productiva ni un despliegue validado en AWS.
