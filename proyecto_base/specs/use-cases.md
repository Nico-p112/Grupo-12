# Casos de uso

## UC-01: [Liquidar siniestro]

**Actor:** Liquidador de siniestros (principal). Gerente de Siniestros (secundarios, solo en el flujo alternativo)

**Precondición:** El siniestro tiene registrado el informe de pericia (estado en Liquidación)

**Flujo principal:**
1. El liquidador selecciona un siniestro en estado En liquidación
2. Se ejecut UC-02 Consultar informe de pericia (include)
3. El liquidador determina si el siniestro está cubierto
4. El liquidador carga el monto a pagar
5. El sistema verifica si el monto requiere autorización (KAN-14)
6. El sistema registra la liquidación con cobertura, monto y fecha, y deja el siniestro en Oferta enviada

**Flujo(s) alternativo(s):**
- 3a. El siniestro no está cubierto: el sistema registra el rechazo y deja el siniestro en rechazado.
- 5a. El monto requiere autorización: se ejecuta UC-03 solicitar autorización al gerente (extend); el siniestro queda en autorización y, cuando el gerente autoriza continuan el paso 6
- 5b. El gerente no autoriza 

**Postcondición:** La liquidación queda registrada con cobertura, monto y fecha, y el siniestro queda en Oferta enviada, En autorización (si requiere autorización) o Rechazada si no esta cubierto

**Relaciones con otros casos de uso:**

| Relación | Caso de uso relacionado | Tipo (include/extend) | Justificación |
|----------|--------------------------|------------------------|----------------|
|UC-01 --> UC-02 |Consultar informe de pericia |Include |siempre se ejecuta: el liquidador determina cobertura y monto "con el informe" (Caso 3.3), sin informe no hay liquidación |
|UC-03 --> UC-01|Solicitar autorización al gerente|Extend|Solo ocurre si el monto supera cierto importe (Caso 3.3; K. Sosa). Una liquidación por debajo del importe queda sin esto|

Recordar (ver skill/SKILL.md): include = siempre se ejecuta como parte
del flujo, sin excepción. extend = extiende opcionalmente bajo una
condición específica, el flujo base es completo sin ella. Toda relación
sin justificación no cuenta como completa.

## Fragmentos considerados para este caso de uso

Listar qué fragmentos del relevamiento se usaron para armar este caso
de uso, y qué parte del flujo justifica cada uno.

| Fragmento | Qué aporta al caso de uso |
|-----------|------------------------------|
|Caso 3.3 |Da el orden de los pasos (informe, cobertura, monto, autorización, oferta) |
|Voz de K. Sosa|Da el extend|
|Caso S5|Da el contenido del informe (KAN-12)|
