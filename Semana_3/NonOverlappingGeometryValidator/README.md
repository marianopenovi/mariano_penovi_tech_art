<p align="center">
  <a href="#english-version">English</a> | <a href="#spanish-version">Español</a>
</p>

---

<a id="english-version"></a>
# Non-Overlapping Geometry Validator for Maya

A script-based tool for Autodesk Maya designed to validate that two or more objects in a scene do not present overlapping geometry.

Developed as a project for the professional course **TechArt - Max Sarlija Academy**.

## Purpose
Overlapping geometry or mesh intersection occurs when two or more components of a mesh (vertices, edges, or faces) or different meshes occupy the same three-dimensional space at the same time. This situation is generally considered a modeling error or bad practice, especially for video games or 3D printing, as it causes strange visual behaviors, such as flickering textures or errors in rendering. Common problems it can cause are listed below:

*   **Z-Fighting:** It is a visual error where overlapping faces flicker or vibrate when rendering, since Maya does not know which face to show in front.
*   **Problems in 3D printing:** Models with intersections are not watertight, which causes print failures.
*   **Game Engine errors:** When exporting to engines such as Unreal or Unity, overlay geometry can cause lighting or display errors.
*   **Non-manifold mesh:** Creates a complex topology that makes it difficult to animate, skinning, or use sculpting tools.

This tool detects overlapping geometry condition and, if such condition is found, it lists the names of the objects in conflict. Otherwise, a success message will be shown.

## Demo for success scenario
![Demo for success scenario](assets/Tool_Non_Overlapping_Geometry_Success_Scenario.gif)

## Demo for error scenario
![Demo for error scenario](assets/Tool_Non_Overlapping_Geometry_Error_Scenario.gif)

## Usage
1.  **Open Maya** and open the **Script Editor** by clicking semi-colon icon in the lower right corner of the main window.
2.  Create a new **MEL** tab.
3.  Paste the contents of `scripts/Tool_Non_Overlapping_Geometry_Validator.mel` into the tab.
4.  Run the script (Execute) or select all the code and drag it to the top bar by holding middle mouse button. A new **"M"** button should appear in the bar.
5.  Click on that button.
6.  A window titled **"Detector de Superposición"** should appear informing the outcome of the validation process.

## Creation Process
The development followed this approach:
1.  **Input:** A scene that might present objects with overlapping geometry condition.
2.  **Core process:** Create and run a script that utilizes AABB (Axis-Aligned Bounding Box) collision detection. Since calculating face-to-face intersections in dense scenes using a pure MEL script would be extremely slow, the script instead calculates the bounding boxes of each polygonal object in World Space and detects if they are intersecting.
3.  **Result:** A message window that provides clear outcomes for the validation process.

## Credits
*   **Developer:** Mariano Penovi
*   **Academy:** TechArt Studio - Max Sarlija Academy

---

<a id="spanish-version"></a>
# Validador de Geometría No Superpuesta para Maya

Una herramienta basada en script para Autodesk Maya que permite validar que dos o más objetos en una escena no contengan geometría solapada.

Desarrollado como parte de la formación professional **TechArt - Max Sarlija Academy**.

## Propósito
La superposición de geometría en Maya 3D (conocida en inglés como overlapping geometry o mesh intersection) ocurre cuando dos o más componentes de una malla (vértices, aristas o caras) o mallas distintas ocupan el mismo espacio tridimensional al mismo tiempo. Esta situación se considera generalmente un error de modelado o una mala práctica, especialmente para videojuegos o impresión 3D, ya que provoca comportamientos visuales extraños, como el parpadeo de texturas o errores en el renderizado. Los problemas comunes que puede causar se listan abajo:

*   **Z-Fighting:** Es un error visual donde las caras superpuestas parpadean o vibran al renderizar, ya que Maya no sabe cuál cara mostrar al frente.
*   **Problemas en impresión 3D:** Los modelos con intersecciones no son herméticos (watertight), lo que causa fallos de impresión.
*   **Errores en el Game Engine:** Al exportar a motores como Unreal o Unity, la geometría superpuesta puede causar errores de iluminación o visualización.
*   **Malla no manifold:** Crea una topología compleja que dificulta la animación, skinning o el uso de herramientas de escultura.

Esta herramienta detecta geometría solapada y, de darse esta condición, lista los nombres de los objetos en conflicto. De no encontrase objetos con problemas, se mostrará un mensaje de éxito.

## Demo para el caso de éxito
![Demo para caso de éxito](assets/Tool_Non_Overlapping_Geometry_Success_Scenario.gif)

## Demo caso de error
![Demo para caso de error](assets/Tool_Non_Overlapping_Geometry_Error_Scenario.gif)

## Modo de uso
1.  **Ejecutar Maya** y abrir el **Editor de scripts** haciendo click en el icono de punto y coma de la esquina inferior derecha de la ventana principal.
2.  Abrir una pestaña **MEL**.
3.  Pegar el contenido de `scripts/Tool_Non_Overlapping_Geometry_Validator.mel` en dicha pestaña.
4.  Ejecutar el script o seleccionar todo el código y arrastrarlo a la barra superior mientras se mantiene el botón del medio del mouse apretado. Un nuevo icono **"M"** debería mostrarse en la barra.
5.  Hacer click en el mismo.
6.  Una ventana titulada **"Detector de Superposición"** debería aparecer informando el resultado del proceso de validación.

## Proceso de creación de la herramienta
El desarrollo siguió las siguientes consideraciones:
1.  **Input:** Una escena con uno o más objetos que pueden presentar condición de geometría solapada.
2.  **Proceso:** Creación y ejecución de un script con la siguiente lógica: utiliza la detección de colisiones mediante AABB (Axis-Aligned Bounding Box). Dado que calcular la intersección cara por cara (face-to-face) en escenas densas mediante un script puro de MEL sería extremadamente lento; en su lugar, este script calcula las "cajas delimitadoras" de cada objeto poligonal en el espacio mundial (World Space) y detecta si se están cruzando.
3.  **Resultado:** Una ventana con un mensaje que proporciona resultados claros sobre el proceso de validación.

## Créditos
*   **Desarrollador:** Mariano Penovi
*   **Academia:** TechArt Studio - Max Sarlija Academy

---
*Desarrollado como parte del ejercicio de la Semana 03 - Formación Tech Art.*