# CH-01 — Campos sin requisito formal

| | |
| --- | --- |
| Tester | Andrés Colmenares |
| Fecha | Pendiente |
| Duración | 45 minutos |
| Ambiente | Chrome, 1920x1080 y 390x844 |

## Misión

Explorar los campos que no tienen casos formales (Date of Birth, Subjects, Hobbies y Current
Address) y el comportamiento general del formulario, para encontrar defectos que los casos
CP-01 a CP-40 no cubren.

## Área

- Date of Birth: selector de fecha y captura manual.
- Subjects: autocompletado y selección múltiple.
- Hobbies: casillas de verificación.
- Current Address: área de texto.
- Modal de confirmación: formato de los datos mostrados.
- Navegación con teclado y diseño en vista móvil.

## Ideas de prueba

- Date of Birth: fecha futura, 29 de febrero, borrar el contenido del campo, escribir texto.
- Date of Birth: comparar el formato del campo con el que muestra el modal.
- Subjects: texto sin coincidencias, elegir la misma materia dos veces, quitar una materia.
- Hobbies: marcar todas, desmarcar, enviar sin ninguna.
- Current Address: texto largo, saltos de línea, caracteres especiales.
- Recorrer todo el formulario con Tab y enviar con Enter.
- Recargar la página a mitad de la captura.
- Vista móvil: girar a horizontal, zoom al 200%, elementos que se enciman.
- Doble clic rápido en Submit.

## Notas de la sesión

Pendiente. Se llenan durante la sesión, con hora aproximada de cada hallazgo.

## Bugs encontrados

Pendiente.

## Preguntas abiertas

Pendiente.
