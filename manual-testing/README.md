# Pruebas manuales — DemoQA Practice Form

Documentación de un ciclo de pruebas manuales sobre el formulario de registro de
[DemoQA](https://demoqa.com/automation-practice-form): requisitos, plan, casos, trazabilidad,
sesión exploratoria, reporte de defectos y cierre.

## Objetivo

Verificar que el formulario valida y envía correctamente los datos de registro, y dejar
evidencia ordenada de qué se probó, con qué técnica y qué se encontró.

## Alcance

Incluido:

- Campos obligatorios y envío del formulario (RQ-01).
- Validación de Mobile (RQ-02) y de Email (RQ-03).
- Dependencia entre State y City (RQ-04).
- Carga de archivo en Picture (RQ-05).
- Chrome y Firefox en escritorio (1920x1080) y vista móvil (390x844).

Fuera de alcance: rendimiento, seguridad, accesibilidad y el resto de las secciones del sitio.
Los campos Date of Birth, Subjects, Hobbies y Current Address no tienen casos formales; se
cubren en la sesión exploratoria CH-01.

## Estructura

```text
01-requisitos/     Historias de usuario con criterios de aceptación (RQ-01 a RQ-05)
02-plan/           Plan de pruebas
03-casos/          40 casos de prueba en CSV (CP-01 a CP-40)
04-matriz/         Trazabilidad requisito - caso - bug
05-exploratorias/  Charters de pruebas exploratorias
06-bugs/           Plantilla y reportes de defectos (BUG-001...)
07-cierre/         Reporte de cierre del ciclo
evidencias/        Capturas y videos referenciados desde los bugs
```

## Cómo leer esta carpeta

1. [Requisitos](01-requisitos/requisitos.md): qué se espera del formulario y qué supuestos se tomaron.
2. [Plan de pruebas](02-plan/plan-de-pruebas.md): enfoque, ambientes y criterios de salida.
3. [Casos de prueba](03-casos/casos-de-prueba.csv): GitHub muestra el CSV como tabla; cada caso
   indica el requisito que cubre y la técnica con la que se diseñó.
4. [Matriz de trazabilidad](04-matriz/matriz-trazabilidad.md): cobertura por requisito.
5. [Bugs](06-bugs/) y [reporte de cierre](07-cierre/reporte-de-cierre.md): resultados.

## Resumen de resultados

Ejecución pendiente. Esta sección se llena al cerrar el ciclo con los totales de casos
aprobados y fallidos y la lista de defectos.
