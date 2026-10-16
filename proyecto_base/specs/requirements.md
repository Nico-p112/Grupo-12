# Requerimientos

Completar a partir de los fragmentos de relevamiento del caso. Seguir
la convención de `skill/SKILL.md` (atómico, verificable, sin tecnología
mezclada).

## Requerimientos funcionales

| ID | Requerimiento | Fragmento(s) de origen |
|----|---------------|--------------------------|
|KAN-10 |EL sistema debe registrar cada denuncia de siniestro con el canal por el que llego|3.3 acta 3.5 (D. almiron) |
|KAN-11 |El sistema debe asignar un número unico a cada denuncia en el momento de registrarla |Acta 3.5 voz de k. Sosa |
|KAN-12 |El sistema debe registrar el informe de pericia, con sus fotos adjuntas, asociado al siniestro |Caso 3.3 |
|KAN-13 |El sistema debe registrar el estado de cada siniestro eligiendo un valor de una lista definida |Caso 3.3 |
|KAN-14 |El sistema debe impedir ofrecer el monto al asegurado si el siniestro requiere autorizacion y el Gerente de Siniestros no la registró |Caso 3.3 |

## Fragmentos que NO son requerimientos funcionales

Para cada fragmento del relevamiento que no calificó como RF, clasificar
según las categorías de `skill/SKILL.md` (objetivo/meta de negocio,
restricción técnica, RNF, dato de contexto) y justificar en una línea
por qué no es un RF.

| Fragmento | Texto | Categoría | Justificación |
|-----------|-------|-----------|----------------|
|A. Pampin S4 |"rápido, moderno y fácil de usar" |RNF |Sin metrica no se verifica |
|A. Pampin S4 |"antes de que se jubile Hector" |objetivo de negocio |Es un plazo |
|N. Vega S4|reporte de la Superintendencia a mano|Fuera del frente|Es otro frente|
|K. Sosa S4|"me sale en solo lectura... pisamos filas"|datos de contexto|Origina RF-02|

## Conflictos u observaciones detectadas

Si al procesar los fragmentos aparece un conflicto de valores (ver
"Detección de conflictos" en la skill), documentarlo acá aunque no
afecte directamente un RF puntual.

- El caso dice que autoriza el gerente si el monto "supera cierto importe" y no da el importe 
