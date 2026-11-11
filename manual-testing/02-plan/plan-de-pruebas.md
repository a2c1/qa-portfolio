# Plan de pruebas

| | |
| --- | --- |
| Producto | DemoQA — Student Registration Form |
| URL | https://demoqa.com/automation-practice-form |
| Versión del plan | 1.0 |
| Autor | Andrés Colmenares |
| Fecha | Noviembre 2026 |

## 1. Objetivo

Comprobar que el formulario de registro cumple los requisitos RQ-01 a RQ-05 y reportar los
defectos encontrados con evidencia suficiente para reproducirlos.

## 2. Alcance

Incluido:

- Envío con campos obligatorios y validación de campos faltantes.
- Validación de Mobile y Email.
- Dependencia State/City.
- Carga de archivo en Picture.
- Contenido del modal de confirmación.

Excluido:

- Pruebas de rendimiento, seguridad y accesibilidad.
- Otras secciones de DemoQA.
- Persistencia de datos: el sitio es una demo y no guarda los registros.
- La publicidad del sitio, salvo cuando impida usar el formulario.

## 3. Enfoque y técnicas

Pruebas de caja negra diseñadas a partir de los requisitos, complementadas con una sesión
exploratoria para los campos sin requisito formal.

| Técnica | Dónde se aplica | Casos |
| --- | --- | --- |
| Partición de equivalencia | Obligatorios, formato de Email, tipo de archivo | 12 |
| Valores límite | Longitud de Mobile, longitud del TLD de Email | 6 |
| Tabla de decisión | Combinaciones State/City y de campos obligatorios | 8 |
| Transición de estados | Habilitación de City, ciclo del modal, corrección y reenvío | 6 |
| Predicción de errores | Espacios, símbolos, pegado de texto, caracteres especiales, vista móvil | 8 |

Valores límite tiene menos casos que el resto porque el formulario solo tiene dos límites
definidos: los 10 dígitos de Mobile y el mínimo de 2 letras del TLD.

## 4. Niveles y tipos de prueba

- Nivel: pruebas de sistema.
- Tipos: funcionales, de interfaz y de compatibilidad entre navegadores y resoluciones.
- Regresión: se repiten los casos ligados a un bug cuando este se reporte como corregido.

## 5. Ambientes

| Navegador | Resolución | Uso |
| --- | --- | --- |
| Chrome (última versión estable) | 1920x1080 | Ejecución completa de los 40 casos |
| Chrome, emulación de dispositivo | 390x844 | Ejecución completa de los 40 casos |
| Firefox (última versión estable) | 1920x1080 | Casos de prioridad Alta |
| Firefox, vista de diseño adaptable | 390x844 | Casos de prioridad Alta |

Sistema operativo: Windows 11. La versión exacta de cada navegador se registra en el reporte
de cierre.

## 6. Datos de prueba

Todos los datos son ficticios.

| Dato | Valor base |
| --- | --- |
| First Name | Laura |
| Last Name | Mendez |
| Gender | Female |
| Mobile | 8112345678 |
| Email | laura.mendez@correo.com |

Archivos para Picture: `foto.jpg`, `foto.png`, `foto perfil niño.png` y `documento.pdf`.
Cada caso indica en la columna `Datos` qué valores cambia respecto a los valores base.

## 7. Criterios de entrada

- El sitio responde y el formulario carga completo.
- Requisitos y casos de prueba revisados.
- Navegadores instalados y archivos de prueba disponibles.

## 8. Criterios de salida

- 100% de los casos de prioridad Alta ejecutados.
- 0 bugs críticos abiertos.
- Al menos 95% de los casos ejecutados aprobados.

Si algún criterio no se cumple, el reporte de cierre lo indica junto con el riesgo que implica.

## 9. Riesgos

| Riesgo | Impacto | Probabilidad | Mitigación |
| --- | --- | --- | --- |
| El sitio es de terceros y puede cambiar sin aviso | Alto | Media | Registrar fecha de ejecución y guardar evidencia de cada caso fallido |
| La publicidad cubre elementos del formulario | Medio | Alta | Probar en las dos resoluciones y reportarlo como defecto si impide el envío |
| El sitio no está disponible durante la ejecución | Medio | Baja | Reprogramar la sesión; no marcar casos como fallidos por caída del sitio |
| Los requisitos se basan en supuestos | Medio | Media | Supuestos documentados en requisitos.md; cada bug cita el supuesto en que se apoya |
| No hay acceso a base de datos ni a logs | Bajo | Alta | Limitar la validación a lo visible en la interfaz y en el modal |

## 10. Entregables

- Requisitos y supuestos.
- Plan de pruebas.
- 40 casos de prueba con resultado.
- Matriz de trazabilidad.
- Charter de la sesión exploratoria con notas.
- Reportes de bugs con evidencia.
- Reporte de cierre.

## 11. Roles

| Rol | Responsable | Actividades |
| --- | --- | --- |
| QA Engineer | Andrés Colmenares | Análisis, diseño, ejecución, reporte de defectos y cierre |
