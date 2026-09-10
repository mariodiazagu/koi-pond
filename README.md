# Koi pond

Estanque procedural en pixel art. HTML, CSS y JavaScript en un solo archivo, sin dependencias ni recursos externos. Abre `index.html` en un navegador moderno.

## Controles
- Toca o pulsa sobre el agua: ondas y atracción según la curiosidad de cada pez.
- Ajustes: 0–60 peces, ritmo y ciclo de vida.
- F: pantalla completa; H: ocultar o mostrar interfaz; Esc: volver.
- Doble clic / doble toque: salir de la vista limpia.
- Espacio: pausar. Con el lienzo enfocado, Enter crea una onda central.

La pantalla completa depende del soporte del navegador. Si no está disponible, se activa una vista limpia dentro de la ventana.

## Publicar en GitHub Pages
1. Sube `index.html` a la raíz de un repositorio.
2. En Settings → Pages selecciona Deploy from a branch, la rama main y /(root).
3. Guarda y abre la URL que proporciona GitHub.

No necesita compilación, servidor ni claves. También funciona bajo la subruta de un repositorio.

## Reglas de simulación
Cada pez tiene velocidad, curiosidad, fase de movimiento, longitud, anchura y color propios. Las rutas combinan oscilaciones suaves, inercia de giro, separación y rechazo de bordes. Los colores se eligen con pesos: dorado 32%, crema 24%, burdeos 19%, verde azulado 14%, naranja 8% y oscuro 3%. Las marcas son sencillas y aleatorias.

Con ciclo de vida activo, cada 6–11 minutos se intenta un nacimiento si hay dos adultos cerca y espacio en la población. Los alevines crecen durante 8 minutos. Cada 20–35 minutos puede morir un pez con más de 30 minutos de edad simulada; la población se protege por debajo de 3. La muerte es una desaparición gradual. Algunos peces iniciales ya tienen edad adulta. Máximo: 60 peces.

El tiempo transcurre mientras la pestaña está visible y la animación activa. No se conserva el estado al recargar. Modifica `CONFIG` y `palettes` dentro del script para ajustar las reglas.

## Verificación
Sintaxis JavaScript y simulación acelerada de una hora verificadas, incluyendo nacimientos, muertes y ondas. No se pudo realizar una inspección visual en navegador en el entorno de creación.
