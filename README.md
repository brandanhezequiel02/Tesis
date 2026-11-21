# Tesis — Proyecto Integrador II

Proyecto LaTeX del informe final. Compila con **pdfLaTeX + BibTeX**.

## Compilar en TeXworks

1. Abrir `main.tex`.
2. En el desplegable de arriba a la izquierda elegir **pdfLaTeX+MakeIndex+BibTeX**.
3. Apretar el triángulo verde. **La primera vez correrlo dos veces**, para que se
   resuelvan el índice y las citas.

## Compilar en Overleaf

Subir la carpeta entera (`New Project → Upload Project` con un .zip).
El compilador por defecto ya funciona; no hay que configurar nada.

## Organización

    main.tex              orquesta todo, casi no se toca
    preambulo.tex         paquetes, estilo y macros
    referencias.bib       bibliografía
    figuras/              todas las imágenes van acá
    secciones/            un archivo por capítulo

## Para trabajar rápido en un solo capítulo

En `main.tex`, descomentar y ajustar:

    \includeonly{secciones/02-introduccion}

Compila solo ese capítulo pero mantiene la numeración y las referencias
cruzadas correctas. Acordate de volver a comentarlo antes de la entrega.

## Convenciones

- **Usar las macros del preámbulo** (`\Rs`, `\OSNR`, `\EVM`, `\Df`, …) en vez de
  escribir los símbolos a mano. Si después hay que cambiar una notación, se
  cambia en un solo lugar.
- **Usar `siunitx` para todo número con unidad**: `\SI{32}{\giga\baud}`. Se
  encarga solo del espaciado, del separador decimal (coma, ya configurado) y de
  que no se parta el renglón entre el número y la unidad.
- **Usar `\cref`** para referencias cruzadas: `\cref{fig:tal}` escribe
  "figura 3.2" solo.
- **`\todo{...}`** deja una marca roja visible en el PDF. Antes de entregar,
  redefinirlo en el preámbulo como `\newcommand{\todo}[1]{}` y desaparecen todas
  de una vez.

## Figuras

Guardarlas en `figuras/` en **PDF o PNG a 200 dpi o más**. Desde MATLAB:

    exportgraphics(gcf, 'figuras/nombre.pdf', 'ContentType', 'vector')

El PDF vectorial es preferible: no se pixela al hacer zoom y pesa menos.
