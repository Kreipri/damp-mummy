<!-- l10n-sync: source-file="04-design-vibes.md" -->
# Parte 4: Tematización Orientada al Diseño

---

En esta parte, usarás **Plan Mode** para diseñar una transformación de tema completa, y luego **Agent Mode** para implementarla. Esto es desarrollo orientado al diseño — comienza con la visión, itera sobre los elementos visuales y deja que Copilot se encargue del trabajo pesado de CSS.

## Tarea 1: Planifica el Tema Retro

<!-- track:vscode:start -->
Cambia a modo **Plan** en GitHub Copilot Chat.
<!-- track:vscode:end -->

<!-- track:cli:start -->
Usa `/plan` en GitHub Copilot CLI o pulsa **Shift+Tab** hasta activar plan mode.
<!-- track:cli:end -->

Ingresa este prompt:

> Quiero transformar esta página en una experiencia completa de arcade retro. Planifica una renovación visual que incluya: efectos de líneas de barrido CRT en el fondo, un brillo de neón en el título que pulse como un letrero de neón, una insignia VS animada con cambios de degradado, una superposición brillante en las tarjetas de resultados, animaciones de entrada flotante para los campos, texto de carga que cambie entre verde y morado, y efectos de brillo al pasar el cursor sobre los cuadrados de contribuciones. Mantén el fondo oscuro (`#0a0a1a`) y los colores de acento verde (`#5fed83`) y morado (`#8a2be2`). Usa un tema oscuro con la fuente retro Press Start 2P de Google Fonts.

Copilot generará un plan detallado de implementación cubriendo todos los efectos visuales. **No lo aceptes de inmediato** — revisa el plan e itera:

- Sugiere ajustes en la velocidad de las animaciones (por ejemplo, «Haz que el pulso del neón sea más lento, de unos 3 segundos»).
- Pregunta por efectos concretos (por ejemplo, «¿Cómo funcionará la superposición brillante en las tarjetas?»).
- Solicita cambios en el enfoque si algo no te convence

Una vez que estés satisfecho con el plan, pide a Copilot que lo implemente.

## Tarea 2: Implementa el Tema

Pide a Copilot que implemente el plan que acabáis de diseñar:

> Implementa el plan de tema de arcade retro que acabamos de diseñar.

Copilot agregará múltiples animaciones CSS, pseudo-elementos y transiciones en tu hoja de estilos. Esto puede incluir:

- `@keyframes` para scanlines, pulso neón, shimmer y efectos de aparición flotante
- Pseudo-elementos (`::before`, `::after`) para efectos de superposición
- CSS custom properties para los colores del tema
- Transiciones y estados hover para elementos interactivos

<!-- track:cli:start -->
Después de aplicar los cambios, usa `/diff` para revisarlos antes de aprobarlos.
<!-- track:cli:end -->

<!-- track:vscode:start -->
Una vez aplicados los cambios, **revisa la vista previa en tu navegador** para ver la transformación completa al estilo retro arcade.
<!-- track:vscode:end -->

## Tarea 3: Ajusta las Vibras

> **⚠️ ¿No ves los cambios?** Si el nuevo tema o las animaciones no aparecen, detén el servidor de desarrollo (`Ctrl+C`), reinícialo con `npm run dev` y haz una recarga forzada (`Ctrl+Shift+R`) en el navegador.

Mantén la vista previa del navegador abierta e itera sobre el diseño. Prueba prompts como:

> El efecto de líneas de barrido es demasiado intenso; reduce la opacidad a 0.03.

> Añade un sutil parpadeo eléctrico al texto del título.

> La insignia VS debería pulsar con más intensidad.

Esto es **desarrollo orientado al diseño** — estás iterando sobre la salida visual en tiempo real. Cada prompt refina la experiencia hasta que se sienta correcta. No te conformes con "suficientemente bueno" — perfecciona las vibras hasta que la página parezca pertenecer a un gabinete arcade.

## Tarea 4: Actualiza las Instrucciones

<!-- track:vscode:start -->
Las instrucciones del workspace deben reflejar las decisiones de diseño importantes. Pide a Copilot:

> Añade una sección de guía de diseño a copilot-instructions.md que describa el tema de arcade retro: colores, fuentes y estilo de animación.
<!-- track:vscode:end -->

<!-- track:cli:start -->
Pide a Copilot CLI:

> Actualiza las instrucciones del repositorio con una breve guía de diseño para el tema de arcade retro: colores, fuentes, estilo de animación y la regla de que la nueva interfaz mantenga la estética de neón.
<!-- track:cli:end -->

Esto mantiene las interacciones futuras de Copilot alineadas con la identidad visual que has establecido. Cualquier funcionalidad o componente nuevo seguirá la estética retro arcade.

Haz commit de las instrucciones y los cambios de diseño cuando la página esté a tu gusto.

## ✅ Parte 4 Completa

**Lo que aprendiste:**

- **Plan Mode para sistemas de diseño** — esbozar una renovación visual completa antes de escribir código
- **Iterar sobre la salida visual** — usar prompts rápidos de seguimiento para ajustar animaciones, colores y efectos
- **Mantener las instrucciones actualizadas con decisiones de diseño** — documentar tu tema para que Copilot se mantenga consistente
- **Flujo de trabajo de desarrollo orientado al diseño** — comenzar con la visión, implementar con IA, refinar hasta que se sienta correcto
