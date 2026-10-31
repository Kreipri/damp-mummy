<!-- l10n-sync: source-file="03-agent-mode.md" -->
# Parte 3: Agent Mode — Construir el Juego

---

Agent Mode permite a Copilot planificar e implementar cambios de forma autónoma en múltiples archivos. En lugar de escribir código línea por línea, describes lo que quieres y Copilot determina qué archivos crear o modificar, luego implementa todo de principio a fin.

## Tarea 1: Conecta la Batalla

<!-- track:vscode:start -->
1. Cambia a modo **Agent** en Copilot Chat (selecciona "Agent" en el menú desplegable de modo).

2. Ingresa este prompt:
<!-- track:vscode:end -->

<!-- track:cli:start -->
1. Vuelve al flujo de programación habitual de Copilot CLI (o sigue en autopilot si quieres que Copilot continúe hasta que lo detengas).
2. Si te sirve, añade el archivo de la página como contexto: `@src/pages/index.astro`.
3. Ingresa este prompt:
<!-- track:cli:end -->

   > Añade JavaScript del lado del cliente a la página de batalla para que:
   > 1. Al hacer clic en el botón **Battle**, obtenga los dos nombres de usuario de los campos.
   > 2. Compruebe que ambos estén rellenados (y muestre un error si no lo están).
   > 3. Obtenga en paralelo de nuestra API los datos de contribuciones de ambos usuarios.
   > 4. Muestre los gráficos de contribuciones como cuadrículas de colores: cada día es un cuadrado de color de la paleta de GitHub.
   > 5. Muestre una insignia **VS** entre los dos usuarios.
   > 6. Muestre el nombre de usuario, el total de contribuciones y el intervalo de fechas de cada usuario.
   > 7. Gestione los estados de carga y los errores.
   > 8. También inicie la batalla al pulsar **Enter** en los campos.
   >
   > Usa interfaces de TypeScript para la estructura de datos de contribuciones.

<!-- track:vscode:start -->
3. Deja que Agent Mode implemente los cambios en `index.astro`.
4. Revisa los cambios propuestos en la vista de diferencias antes de aceptarlos.
<!-- track:vscode:end -->

<!-- track:cli:start -->
4. Deja que Copilot CLI implemente los cambios en `src/pages/index.astro`.
5. Inspecciona los cambios generados con `/diff` y apruébalos.
<!-- track:cli:end -->

## Tarea 2: Prueba la Batalla

> **⚠️ ¿No ves los cambios?** Si la página de batalla no se ha actualizado, detén el servidor de desarrollo (`Ctrl+C`), reinícialo con `npm run dev` y actualiza el navegador.

1. Ingresa `octocat` y `torvalds` como nombres de usuario y haz clic en **Battle**.
2. Deberías ver ambos gráficos de contribuciones renderizados lado a lado con cuadrículas de colores.
3. Prueba los casos de error:
   - Deja uno o ambos campos vacíos y haz clic en Battle — deberías ver un error de validación.
   - Ingresa un nombre de usuario inválido — la app debería mostrar un error de la API.
4. Prueba a pulsar **Enter** en cualquiera de los campos — debería iniciar la batalla igual que al hacer clic en el botón.

## Tarea 3: Itera con Agent

Si algo no está del todo bien, dale retroalimentación a Agent directamente en el chat. Por ejemplo:

- *«Los cuadrados de contribuciones son demasiado grandes; hazlos de 12x12px»*
- *«Añade una ayuda emergente al pasar el cursor que muestre la fecha y el número de contribuciones»*
- *«El estado de carga necesita una animación de pulso»*

<!-- track:vscode:start -->
Agent Mode gestiona de forma natural los cambios en varios archivos y las iteraciones. Cada prompt de seguimiento aprovecha el contexto de la conversación, así puedes refinar la implementación poco a poco sin empezar de cero.
<!-- track:vscode:end -->

<!-- track:cli:start -->
Las sesiones de Copilot CLI conservan su historial, por lo que cada prompt de seguimiento se basa en los anteriores. Usa `/session` o `/context` para inspeccionar el contexto que Copilot conserva y ejecuta `/review` después de una iteración importante para buscar errores o mejoras.
<!-- track:cli:end -->

## Consejos para Agent Mode

- **Sé específico sobre lo que quieres** — requisitos claros producen mejores resultados.
- **Divide tareas grandes en prompts más pequeños** si Agent se desvía.
- **Revisa los cambios antes de aceptarlos** — usa la vista de diferencias para entender qué se modificó.
- **Si los resultados no son perfectos, da retroalimentación e itera** — Agent aprende de tus correcciones dentro de la conversación.

## ✅ Parte 3 Completa

Has aprendido a:

- Usar **Agent Mode** para implementaciones complejas en múltiples archivos
- **Iterar sobre los resultados** con retroalimentación dirigida
- Gestionar el **ciclo completo de una funcionalidad** — implementación, revisión, pruebas y mejoras
