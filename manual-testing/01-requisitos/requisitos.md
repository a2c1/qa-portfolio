# Requisitos

DemoQA no publica una especificación del formulario. Estos requisitos se redactaron a partir
del análisis del formulario y sirven como base de prueba del ciclo. Donde el comportamiento
esperado no era evidente se tomó un supuesto; todos están listados al final.

| ID | Requisito | Prioridad |
| --- | --- | --- |
| RQ-01 | Envío con campos obligatorios | Alta |
| RQ-02 | Mobile acepta exactamente 10 dígitos | Alta |
| RQ-03 | Email con formato válido | Media |
| RQ-04 | City depende de State | Media |
| RQ-05 | Carga de imagen en Picture | Media |

## RQ-01 — Envío con campos obligatorios

Como estudiante, quiero enviar mi registro capturando solo los datos obligatorios, para
completar el trámite sin llenar información opcional.

Campos obligatorios: First Name, Last Name, Gender y Mobile.

Criterios de aceptación:

- **Given** el formulario vacío, **when** capturo First Name, Last Name, Gender y un Mobile
  válido y doy clic en Submit, **then** se muestra el modal "Thanks for submitting the form"
  con los datos capturados.
- **Given** al menos un campo obligatorio vacío, **when** doy clic en Submit, **then** el
  formulario no se envía y cada campo faltante queda marcado como inválido.
- **Given** un envío rechazado, **when** corrijo los campos marcados y doy clic en Submit,
  **then** el formulario se envía.
- **Given** el modal de confirmación abierto, **when** doy clic en Close, **then** el modal se
  cierra y el formulario queda vacío.

## RQ-02 — Mobile acepta exactamente 10 dígitos

Como administrador, quiero que el teléfono tenga exactamente 10 dígitos numéricos, para poder
contactar al estudiante.

Criterios de aceptación:

- **Given** un Mobile de 10 dígitos numéricos, **when** envío el formulario, **then** el valor
  se acepta y aparece en el modal.
- **Given** un Mobile con menos de 10 dígitos, **when** envío el formulario, **then** el
  formulario no se envía y Mobile queda marcado como inválido.
- **Given** el campo Mobile, **when** intento capturar más de 10 caracteres, **then** el campo
  conserva solo los primeros 10.
- **Given** un Mobile con letras, espacios o símbolos, **when** envío el formulario, **then**
  el formulario no se envía y Mobile queda marcado como inválido.

## RQ-03 — Email con formato válido

Como administrador, quiero que el correo tenga un formato válido cuando se capture, para no
guardar direcciones inservibles.

Email es opcional. Formato válido: `usuario@dominio.tld`, con un TLD de al menos 2 letras.

Criterios de aceptación:

- **Given** el Email vacío y los obligatorios válidos, **when** envío el formulario, **then**
  el formulario se envía.
- **Given** un Email con formato válido, **when** envío el formulario, **then** el valor se
  acepta y aparece en el modal.
- **Given** un Email sin `@`, sin dominio o con un TLD de una sola letra, **when** envío el
  formulario, **then** el formulario no se envía y Email queda marcado como inválido.

## RQ-04 — City depende de State

Como estudiante, quiero que la lista de ciudades corresponda al estado que elegí, para no
seleccionar una combinación que no existe.

| State | City |
| --- | --- |
| NCR | Delhi, Gurgaon, Noida |
| Uttar Pradesh | Agra, Lucknow, Merrut |
| Haryana | Karnal, Panipat |
| Rajasthan | Jaipur, Jaiselmer |

Criterios de aceptación:

- **Given** que no se ha elegido State, **when** intento abrir City, **then** City está
  deshabilitado.
- **Given** un State seleccionado, **when** abro City, **then** solo aparecen las ciudades de
  ese State.
- **Given** un State y una City seleccionados, **when** cambio el State, **then** City se
  limpia.
- **Given** un State y una City seleccionados, **when** envío el formulario, **then** el modal
  muestra ambos valores en "State and City".

## RQ-05 — Carga de imagen en Picture

Como estudiante, quiero adjuntar una fotografía a mi registro, para que se me pueda
identificar.

Picture es opcional. Formatos aceptados: JPG y PNG.

Criterios de aceptación:

- **Given** un archivo JPG o PNG, **when** lo selecciono en Picture y envío el formulario,
  **then** el nombre del archivo aparece en el modal.
- **Given** un archivo que no es imagen, **when** lo selecciono en Picture, **then** el
  archivo se rechaza o el formulario no se envía.
- **Given** un archivo ya seleccionado, **when** selecciono otro, **then** el campo conserva
  solo el último.

## Supuestos

| # | Supuesto | Afecta a |
| --- | --- | --- |
| S1 | Un campo marcado como inválido se muestra con borde rojo; el formulario no muestra mensajes de error. | RQ-01 a RQ-03 |
| S2 | Un valor formado solo por espacios cuenta como vacío. | RQ-01 |
| S3 | State y City son opcionales; se puede enviar con State y sin City. | RQ-04 |
| S4 | Picture solo debe aceptar imágenes. El formulario no lo indica; se toma como lo esperado para un campo de fotografía. | RQ-05 |
| S5 | No se define tamaño máximo de archivo, por lo que no se prueba. | RQ-05 |
