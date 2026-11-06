# Kino TV · Obsidiana

Plugin de **temas de la app** (`apiVersion 18`) para Kino TV, tallado por completo en **obsidiana**: negro volcánico, esquinas afiladas, bordes con destellos violeta y un logo de esquirla facetada, en el celular y en el TV.

| Tema | `id` | Look |
|---|---|---|
| **Kino TV · Obsidiana** | `obsidiana` | Negro puro con un velo violeta casi invisible, superficies de vidrio oscuro, acento lila iridiscente `#A99BFF` y foco claro. |

El tema cambia colores, fondo en degradado, esquinas, bordes, sombras, movimiento, controles del reproductor y **el logo de Kino** (menú lateral, cabecera del celular y riel del TV) por un logo vectorial propio.

> Proyecto de fans. Solo usa formas vectoriales originales; no incluye imágenes, fuentes ni arte con derechos de autor. Es gratis y no cobra kinos.

## Requisitos

- **Kino 0.9.81 o posterior** (`"apiVersion": 18`). Los Kino anteriores muestran «Este plugin necesita una versión más nueva de Kino».
- Los bordes (`*Border`, `colors.border`) necesitan **Kino 0.9.82**; en 0.9.81 se ignoran y el tema se ve igual, sin bordes.
- Sin red ni datos: `"hosts": []` y ninguna capacidad.

## Instalación

1. Publica esta carpeta en un repositorio de GitHub (por ejemplo `tu-usuario/kino-theme-obsidiana`).
2. En Kino: **Ajustes ▸ Plugins ▸ Agregar** y escribe `tu-usuario/kino-theme-obsidiana`.
3. Ve a **Ajustes ▸ Apariencia**, elige *Obsidiana* y toca **Usar este tema**. Kino preguntará si quieres la experiencia completa (recomendada: bordes y sombras).

Para volver al aspecto original: **Apariencia ▸ Tema de Kino**.

## Archivos

```
kino-plugin.json   Manifiesto con el appTheme (colores, logo, ajustes...)
plugin.js          Punto de entrada; el tema es solo datos y no ejecuta nada
README.md          Este archivo
icon.png           Ícono del plugin (propuesta visual, 256×256)
```

## Qué puede ajustar la persona

En **Apariencia ▸ Personalizar** (solo lo marcado como `adjustable`):

- **Color de acento**: lila (original), brasa naranja, turquesa y plata.
- **Color del borde**: tres muestras.
- **Redondeo de las tarjetas**: de 0 a 16 (por defecto 4, para el corte afilado).
- **Escala del texto**: de 1,0 a 1,2.
- **Fondo**.

## Paleta

| Token | Color |
|---|---|
| Acento | `#A99BFF` |
| Texto sobre acento | `#0B0814` |
| Fondo (degradado) | `#000000 → #07060B → #100C1C` |
| Superficie / superficie alta | `#0E0D14` / `#171522` |
| Texto / texto secundario | `#F2F0F8` / `#A9A5BC` |
| Foco (TV) | `#E6E1FF` |
| Borde | `#4A4562` |

Contrastes calculados: texto sobre fondo 18,6:1, texto secundario sobre superficie 8,1:1 y texto sobre acento 8,3:1; todas las muestras de acento superan 7:1 con el texto oscuro.

## Forma y movimiento

- Esquinas casi rectas: tarjetas y canales 4, botones 6, diálogos 6, entradas 4.
- Borde de 1 px en tarjetas, paneles, menús y cabecera; 2 px en diálogos.
- Sombras profundas (tarjetas 0,70, diálogos 0,90) y velo del héroe al 90 %.
- Zoom de foco 1,06 (1,05 en TV), fundido de 320 ms y deriva suave de la imagen principal.
- Reproductor con botones redondeados y botón de play al 120 %.

## Logo propio

- `wordmark` (111×30): la esquirla de obsidiana con un play y un destello, y las letras **KINO** en blanco y **TV** en el acento, todas en trazos angulares.
- `mark` (30×30): solo la esquirla (riel cerrado del TV).
- Solo vectores de líneas rectas (`M L Z`), con `fill` ligado al tema (`accent`, `onAccent`, `textPrimary`), así el logo cambia con el acento que elija la persona. Kino mantiene su propio logo en la pantalla de inicio y en las pantallas que piden una decisión.

## Probar en local

Con el kit del repositorio [kinotvapp/kino-plugins](https://github.com/kinotvapp/kino-plugins):

```
node sdk/validate.mjs .      # formato, rangos y protecciones de legibilidad (celular y TV)
```

El kit no dibuja colores: revisa el resultado en Kino (**Ajustes ▸ Apariencia ▸ vista previa**) en un celular y en un TV.

## Notas para quien edite el tema

- **Nunca cambies el `id` del tema** (`obsidiana`) tras publicar: de él cuelgan la elección y los ajustes de cada persona.
- Un valor fuera de rango no rompe nada: Kino lo descarta con una advertencia. Un error de formato rechaza todo el manifiesto.
- El manifiesto tiene un tope de 16 KB (este pesa unos 5 KB).
- Si cambias el manifiesto, súbelo con una versión nueva (`version`).

Documentación oficial: <https://kinotvapp.github.io/kino-plugins/themes/>

## Licencia

Código y manifiesto bajo MIT.
