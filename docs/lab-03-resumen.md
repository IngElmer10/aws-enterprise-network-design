# Laboratorio 3 — Seguridad perimetral: Security Groups, NACLs y gateways

**Modalidad:** Ruta B, investigación equivalente · **Informe original:** 32 páginas.

Continuación de la VPC `10.0.0.0/16` y las seis subredes del Laboratorio 2, con enfoque en **mínimo privilegio** y control del tráfico entre las capas web, aplicación y datos.

## Diseño de seguridad

- **Security Groups** con estado y **Network ACLs** sin estado; responsabilidades y criterios diferentes.
- Matriz propuesta: Internet → web por TCP 443 (80 opcional); web → aplicación por TCP 8080; aplicación → PostgreSQL por TCP 5432.
- **Bastión** para administración restringida, en vez de abrir SSH a servidores internos.
- Estudio de **NAT Gateway** para salida iniciada desde las redes privadas.
- Discusión sobre tablas de ruta privadas por capa y disponibilidad multi-AZ.

## Figuras originales

- **Página 12, Figura 1:** arquitectura de seguridad perimetral.
- **Página 12, Figura 2:** flujos autorizados entre capas.

## Limitaciones

El bastión, las reglas, NACL y el NAT Gateway son **componentes propuestos**. El laboratorio no creó ni modificó infraestructura AWS y no demuestra conexiones reales. Los comandos son procedimientos reproducibles descritos, no resultados de ejecución.

[Volver al proyecto](../README.md)

El archivo PDF original se encuentra en el paquete de entrega: `docs/lab-03-network-security.pdf`.