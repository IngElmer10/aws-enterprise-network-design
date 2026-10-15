# Laboratorio 2 — Tablas de ruteo y conectividad entre subredes

**Modalidad:** Ruta B, investigación equivalente · **Informe original:** 37 páginas.

Se diseñó para un escenario de comercio electrónico una **VPC `10.0.0.0/16`**, repartida en **seis subredes** para web, aplicación y datos, a través de `us-east-1a` y `us-east-1b`.

## Decisiones documentadas

- Dimensionamiento manual **VLSM** para necesidades de 500, 250 y 50 hosts por capa y zona, considerando las cinco direcciones reservadas por subred en AWS.
- Separación entre subredes **públicas web** y **privadas de aplicación y datos**.
- Tablas de rutas por función y uso de **Internet Gateway** para la salida prevista de la capa web.
- Diagnóstico conceptual de asociaciones de Route Tables, rutas `local`, `0.0.0.0/0` y condiciones de conectividad.

## Figuras originales

- **Página 10:** arquitectura de VPC y seis subredes (Figura 1).
- **Página 19:** diagrama lógico de tablas de ruteo e Internet Gateway (Figura 2).

## Limitaciones

Se documentaron pasos de consola, comandos de AWS CLI y verificaciones esperadas; **no se crearon recursos AWS ni se hicieron pruebas de red**. Las evidencias de AWS incluidas en el PDF se obtuvieron de la **documentación oficial**, no de instancias propias.

[Volver al proyecto](../README.md) · [Plan VLSM](../addressing/README.md)

El archivo PDF original se encuentra en el paquete de entrega: `docs/lab-02-vpc-routing.pdf`.