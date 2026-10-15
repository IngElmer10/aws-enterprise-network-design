# Laboratorio 4 — Conectividad híbrida: acceso remoto y enlaces dedicados

**Modalidad:** Ruta B, investigación equivalente · **Informe original:** 28 páginas.

Se investiga cómo dar acceso remoto seguro a personal técnico sin publicar directamente las aplicaciones privadas que se diseñaron en los dos laboratorios anteriores.

## Propuesta técnica

- **AWS Client VPN** administrado, con pool de clientes `10.8.0.0/22`, distinto de las seis subredes de la VPC.
- Autenticación mutua, asociaciones de red, autorizaciones, rutas y políticas para acceso a servicios privados.
- Comparación conceptual con **WireGuard**, **Site-to-Site VPN/IPSec** y **AWS Direct Connect**.
- Diseño híbrido de referencia para LAN `192.168.50.0/24`: Direct Connect primario y VPN Site-to-Site como respaldo, condicionado a rutas, políticas BGP y monitoreo.

## Figuras originales

- **Página 9, Figura 1:** incorporación conceptual de Client VPN.
- **Página 10, Figura 2:** flujo lógico de acceso remoto autorizado.

## Limitaciones

No se crearon endpoints Client VPN, certificados, túneles VPN ni enlaces Direct Connect; tampoco se realizaron pruebas sobre instancias del proyecto. Las verificaciones son **esperadas o propuestas**.

[Volver al proyecto](../README.md)

El archivo PDF original se encuentra en el paquete de entrega: `docs/lab-04-hybrid-connectivity.pdf`.