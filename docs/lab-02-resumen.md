# Laboratorio 2 — Tablas de ruteo y conectividad entre subredes

**Proyecto académico de diseño de arquitectura** · [**Abrir informe completo (PDF, 37 páginas)**](lab-02-vpc-routing.pdf)

Se diseñó una **VPC `10.0.0.0/16`** para un escenario de comercio electrónico, con **seis subredes** distribuidas entre capas web, aplicación y datos, en `us-east-1a` y `us-east-1b`.

## Decisiones documentadas

- Dimensionamiento **VLSM** para necesidades de 500, 250 y 50 hosts por capa y zona, considerando las cinco direcciones IPv4 reservadas por subred en AWS.
- Separación de subredes **públicas web** y **privadas de aplicación y datos**.
- Tablas de ruteo por función e **Internet Gateway** como salida directa a Internet para las subredes web.
- Procedimientos de diagnóstico conceptual para asociaciones de Route Tables, rutas `local` y `0.0.0.0/0`.

## Diagramas

![VPC y subredes propuestas](../diagrams/lab-02-vpc-subnets.png)

[Ver topología completa](../diagrams/lab-02-vpc-subnets.png) · [Ver diseño de tablas de rutas](../diagrams/lab-02-route-tables.png)

[← Inicio](../README.md) · [Plan de direccionamiento](../addressing/README.md)
