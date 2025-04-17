# Animal

🔷 header { ... }

background image:
→ Usa una imagen de fondo (un nudibranquio en este caso).

background-size: cover;
→ La imagen cubre todo el espacio disponible del header.

background-position: center;
→ Centra la imagen (evita que se vea cortada en los bordes).

color: white;
→ Color del texto por defecto dentro del header.

text-align: center;
→ Centra horizontalmente el texto dentro del header.

padding: 80px 20px;
→ Añade espacio arriba/abajo (80px) y a los lados (20px).

font-family: 'Poppins', sans-serif;
→ Usa la fuente elegante “Poppins”.

position: relative;
→ Permite que elementos hijos posicionados con absolute se ubiquen respecto al header.

🔷 .header-content h1 { ... }

font-size: 3rem;
→ Tamaño grande del título principal.

margin-bottom: 10px;
→ Espacio entre el h1 y el texto que viene después.

text-shadow: 2px 2px 4px rgba(0,0,0,0.6);
Agrega sombra negra suave al texto para mejorar la lectura sobre el fondo.

🔷 .header-content p { ... }

font-size: 1.3rem;
→ Texto un poco más grande que el normal.

margin-bottom: 20px;
→ Espacio debajo del párrafo antes de los elementos siguientes.

color: #caf0f8;
→ Azul celeste claro, destaca sobre el fondo oscuro.

🔷 nav ul { ... }

list-style: none;
→ Quita los puntos de las listas (<ul>).

padding: 0;
→ Elimina espacio interno que algunos navegadores añaden por defecto.

display: flex;
→ Pone los elementos del menú en fila horizontal.

justify-content: center;
→ Centra el contenido horizontalmente.

gap: 20px;
→ Separa los elementos del menú con un espacio de 20px.

flex-wrap: wrap;
→ Si el menú no cabe, permite que baje a otra línea.