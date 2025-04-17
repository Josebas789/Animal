# Animal

🔷 header { ... }

background image:
→ Usa una imagen de fondo.

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

🧠 ¿Qué es rem en CSS?
rem significa: "root em"
Y es una unidad de medida relativa al tamaño de la fuente raíz del documento, es decir, al valor definido en el <html>. normalmente 1rem = 16px

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

🔷 nav ul li a { ... } (primera versión)

color: #90e0ef;
→ Color celeste claro para los enlaces.

text-decoration: none;
→ Quita el subrayado.

font-weight: bold;
→ Texto en negrita.

transition: color 0.3s ease;
→ Hace que el cambio de color sea suave al pasar el mouse.

🔷 nav ul li a:hover { ... }
✅ :hover (pseudo-clase de CSS)
Es una pseudo-clase que se aplica cuando el puntero del mouse pasa por encima de un elemento, como un botón o enlace.

color: #ffbe0b;
→ Cambia el color al pasar el mouse a amarillo dorado.

🔷 header::before { ... }
Esto crea una capa oscura encima de la imagen, para mejorar el contraste del texto:
✅ ¿Qué es ::before en CSS?
Es una pseudo-elemento que te permite insertar contenido antes del contenido real de un elemento sin tocar el HTML.

content: "";
position: absolute;
top: 0; left: 0;
width: 100%; height: 100%;
background-color: rgba(0, 0, 0, 0.3);
→ Una capa negra semitransparente al 30%, que cubre todo el header.

🔷 .header-content { position: relative; }
→ Esto hace que el contenido dentro del header (título, texto, menú) se muestre por encima de la capa oscura (::before).

🔷 nav ul li a (segunda versión)

color: white;
text-shadow: 1px 1px 2px rgba(0,0,0,0.6);
→ Sobre-escribe el color de los enlaces a blanco + sombra para mejor visibilidad.

----------------------------------------------------------------------

🔷 .bubbles { ... }
Este es el contenedor invisible que va encima del header o sección donde quieres ver las burbujas.

position: absolute;
top: 0;
left: 0;
width: 100%;
height: 100%;
👉 Hace que el contenedor ocupe toda la pantalla o el bloque padre (generalmente el header).

overflow: hidden;
👉 Evita que las burbujas se vean fuera del contenedor (por ejemplo, cuando salen por arriba).

pointer-events: none;
👉 Hace que las burbujas no bloqueen clics sobre los botones o enlaces debajo.

z-index: 1;
👉 Coloca las burbujas por encima del fondo, pero debajo del contenido principal (si el contenido tiene un z-index: 2 o más).

🔷 .bubbles span { ... }
Cada <span> es una burbuja individual:

position: absolute;
bottom: -60px;
👉 Aparece debajo de la pantalla, para luego animarse hacia arriba.

width: 20px;
height: 20px;
border-radius: 50%;
👉 Burbujas redondas de 20x20 píxeles.

background: rgba(255, 255, 255, 0.2);
👉 Color blanco transparente, como una burbuja suave.

animation: rise 8s infinite ease-in;
👉 Aplica la animación rise por 8 segundos, en bucle infinito y empieza lento.

opacity: 0;
transform: scale(0.5);
👉 Al inicio, son pequeñas y transparentes (y se irán haciendo más grandes y visibles al subir).

🔷 .bubbles span:nth-child(...)
Estas líneas colocan cada burbuja en una posición distinta horizontalmente (left: 10%, 20%, etc.)
Y además, les asignan diferentes delays para que no suban todas juntas (se ve más natural).

🔷 @keyframes rise
Esta es la animación que hace subir las burbujas:

0% {
  transform: translateY(0) scale(0.5);
  opacity: 0;
}
🔹 Comienzan abajo, pequeñas, y transparentes.

20% {
  opacity: 0.4;
}
🔹 Comienzan a aparecer.

100% {
  transform: translateY(-500px) scale(1);
  opacity: 0;
}
🔹 Suben 500 píxeles hacia arriba, se hacen grandes y se desvanecen al final.

✅ ¿Qué necesitas para usar esto?
Agrega este bloque en tu HTML (por ejemplo dentro del <header>):
<div class="bubbles">
  <span></span>
  <span></span>
  <span></span>
  <span></span>
  <span></span>
  <span></span>
  <span></span>
  <span></span>
  <span></span>
  <span></span>
</div>

Asegúrate de que tu header tenga position: relative para que las burbujas se posicionen bien.

----------------------------------------------------------------------

🔷 .inicio { ... }

background-color: #e0f7fa;
➡️ Fondo celeste claro, da una sensación marina y limpia.

padding: 60px 20px;
➡️ Espaciado interno: 60px arriba/abajo y 20px a los lados.

text-align: center;
➡️ Centra todo el texto e imágenes dentro de la sección.

🔷 .inicio .container { ... }
Contenedor que limita el ancho del contenido para que no se vea demasiado extendido:

max-width: 800px;
➡️ El contenido no crecerá más allá de 800px de ancho.

margin: 0 auto;
➡️ Centra horizontalmente el contenedor en la pantalla.

🔷 .inicio h2 { ... }

font-size: 2.5rem;
➡️ Tamaño de letra grande.

margin-bottom: 20px;
➡️ Espacio debajo del título antes del siguiente elemento.

color: #023e8a;
➡️ Azul profundo, combina bien con el fondo celeste.

🔷 .inicio p { ... }

font-size: 1.1rem;
➡️ Letra un poco más grande que la normal para facilitar la lectura.

color: #333;
➡️ Gris oscuro, muy legible.

line-height: 1.6;
➡️ Espaciado entre líneas, mejora la legibilidad.

margin-bottom: 15px;
➡️ Espacio entre párrafos.

🔷 .boton-explorar { ... }

display: inline-block;
➡️ Se comporta como botón pero sigue dentro del flujo del texto.

margin-top: 20px;
padding: 12px 30px;
➡️ Espacio interior que da tamaño al botón.

background-color: #0077b6;
➡️ Azul intenso, combina con el marino del sitio.

color: white;
text-decoration: none;
➡️ Texto blanco sin subrayado.

border-radius: 30px;
➡️ Bordes redondeados, estilo pastilla o cápsula.

font-weight: bold;
➡️ Texto más grueso.

transition: background-color 0.3s ease;
➡️ Hace que el color cambie suavemente al pasar el mouse.

🔷 .boton-explorar:hover { ... }

background-color: #00b4d8;
➡️ Cambia el color del botón a un celeste más brillante cuando pasas el mouse por encima.

-----------------------------------------------------------------------

🔷 .galeria-inicio { ... }

display: flex;
➡️ Activa flexbox, lo que organiza las imágenes en una fila por defecto.

justify-content: center;
➡️ Centra horizontalmente las imágenes dentro del contenedor.

gap: 20px;
➡️ Espacio de 20px entre cada imagen (separación horizontal y vertical si hay wrap).

flex-wrap: wrap;
➡️ Si las imágenes no caben en una fila, bajan automáticamente a la siguiente línea.

margin-top: 40px;
➡️ Deja un espacio de 40px entre esta galería y el contenido anterior.

🔷 .galeria-inicio img { ... }

width: 300px;
➡️ Cada imagen tendrá 300 píxeles de ancho.

height: auto;
➡️ Mantiene la proporción original de la imagen.

border-radius: 15px;
➡️ Bordes redondeados, estilo suave.

box-shadow: 0 4px 15px rgba(0,0,0,0.2);
➡️ Sombra debajo de la imagen, da un efecto de “tarjeta flotante”.

transition: transform 0.3s ease;
➡️ Al pasar el mouse, cualquier transformación será suave (en este caso, el scale de abajo).

🔷 .galeria-inicio img:hover { ... }

transform: scale(1.05);
➡️ Cuando pasas el mouse sobre una imagen, esta aumenta un 5% su tamaño, haciendo un efecto de zoom suave.

-------------------------------------------------------------------------

🔷 .links-externos

background-color: #caf0f8;
➡️ Fondo celeste claro, muy en armonía con tu estilo marino.

padding: 60px 20px;
➡️ Espacio interior: 60px arriba/abajo y 20px a los lados.

text-align: center;
➡️ Centra el texto y los elementos hijos.

🔷 .links-externos .container

max-width: 800px;
margin: 0 auto;
➡️ Limita el ancho del contenido a 800px y lo centra en la pantalla.

🔷 .links-externos h2

font-size: 2.2rem;
color: #03045e;
margin-bottom: 20px;
➡️ Título grande en azul oscuro con espacio debajo. Se ve formal y elegante.

🔷 .links-externos ul

list-style-type: none;
padding: 0;
➡️ Quita los puntitos de la lista y el espacio interno del navegador.

🔷 .links-externos ul li

margin: 10px 0;
➡️ Espacio entre cada enlace (línea).

🔷 .links-externos ul li a

text-decoration: none;
➡️ Quita el subrayado típico de los enlaces.

color: #0077b6;
➡️ Celeste medio (coherente con el resto de tu sitio).

font-weight: bold;
➡️ Texto en negrita para destacar los enlaces.

transition: color 0.3s ease;
➡️ Hace que el color cambie suavemente al pasar el cursor.

🔷 .links-externos ul li a:hover

color: #023e8a;
➡️ Cambia el color del enlace a un azul más oscuro al pasar el mouse.

text-decoration: underline;
➡️ Subraya el enlace al pasar el mouse, indicando que se puede hacer clic.

--------------------------------------------------------------------

🔷 footer

background-color: #03045e;
➡️ Color de fondo azul marino profundo.

color: white;
➡️ Color del texto por defecto (para que contraste con el fondo oscuro).

padding: 40px 20px;
➡️ Espaciado interno: 40px arriba/abajo, 20px a los lados.

text-align: center;
➡️ Centra todos los elementos hijos horizontalmente.

🔷 footer .container

max-width: 800px;
margin: 0 auto;
➡️ El contenido no se expandirá más allá de 800px y estará centrado.

🔷 footer p

margin: 8px 0;
font-size: 0.95rem;
➡️ Pequeño margen vertical entre líneas y tamaño de texto un poco menor que el normal para verse más delicado.

🔷 footer a
color: #90e0ef;
text-decoration: none;
➡️ Enlaces en celeste claro y sin subrayado.

color: #ffbe0b;
➡️ Cuando pasas el mouse, el enlace cambia a amarillo fuerte (llamativo y bonito sobre azul).

🔷 .footer-links

list-style: none;
➡️ Quita los puntitos típicos de listas <ul>.

padding: 0;
margin-top: 15px;
➡️ Quita espacio interno y deja un poco de espacio arriba de la lista.

display: flex;
justify-content: center;
gap: 20px;
flex-wrap: wrap;
➡️ Pone los elementos de la lista en fila, centrados, con separación de 20px y permite que se acomoden si no caben (ideal para responsive).

🔷 .footer-links li a

font-weight: 500;
➡️ Peso medio de fuente (ni muy delgado ni muy grueso).

transition: color 0.3s ease;
➡️ Suaviza el cambio de color al pasar el mouse.

------------------------------------------------------------------------

🔷 .fichas-info

padding: 60px 30px;
➡️ Añade espacio interno arriba/abajo (60px) y a los lados (30px).

margin-top: 0px;
➡️ No deja espacio hacia arriba respecto al bloque anterior (probablemente porque ya lo tiene el bloque anterior o quieres que se pegue al header).

padding-bottom: 0px;
➡️ Quita espacio interno en la parte inferior (quizás porque las fichas tienen su propio padding).

text-align: center;
➡️ Centra todo el contenido dentro de la sección (ideal para título y fichas).

🔷 .fichas-info h2

font-size: 2.2rem;
➡️ Título grande y llamativo (más que un párrafo pero más chico que un h1).

color: #023e8a;
➡️ Azul marino fuerte, consistente con tu paleta.

margin-bottom: 40px;
➡️ Espacio entre el título y las fichas que vienen después.

-------------------------------------------------------------------------

🧃 Sección general de tarjetas

🔷 .tarjetas

display: flex;
flex-wrap: wrap;
justify-content: center;
gap: 30px;
➡️ Muestra todas las tarjetas una al lado de otra, centradas, y si no caben, bajan a la siguiente fila. El gap crea separación entre ellas.

max-width: 1000px;
margin: 0 auto;
padding: 40px 0;
padding-top: 20px;
➡️ Define un ancho máximo para que no se estiren mucho, las centra y da espacio arriba y abajo.

🃏 Tarjeta individual

🔷 .tarjeta

width: 300px;
height: 450px;
perspective: 1200px;
overflow: hidden;
margin-bottom: 10px;
✅ ¿Qué hace?

Define tamaño fijo de cada tarjeta.

perspective: crea el efecto 3D para girar.

overflow: hidden: oculta lo que se sale del área.

margin-bottom: pequeño espacio debajo.

🔷 .contenido

Es la parte que gira dentro de la tarjeta:
position: relative;
width: 100%;
height: 100%;
transform-style: preserve-3d;
transition: transform 0.8s;
✅ ¿Qué hace?

preserve-3d: mantiene los lados frontal y reverso en 3D.

transition: suaviza la animación de rotación.

🔷 .tarjeta:hover .contenido

transform: rotateY(180deg);
➡️ Cuando pasas el mouse sobre una tarjeta, gira 180 grados en eje Y, mostrando el reverso.

🔷 .frente, .reverso
Las dos caras de la tarjeta:

position: absolute;
width: 100%;
height: 100%;
backface-visibility: hidden;
✅ ¿Qué hace?

Ocultan la “espalda” de cada cara cuando no está al frente.

Se superponen una sobre la otra, pero solo se ve una a la vez.

🔷 .frente

background: #caf0f8;
display: flex;
flex-direction: column;
align-items: center;
justify-content: center;
✅ Esta es la cara visible por defecto.

Tiene fondo celeste.

Contiene una imagen y un título (h3).

Centrado vertical y horizontal.

.frente img

width: 100%;
height: 200px;
object-fit: cover;
✅ Imagen en la parte superior, recortada para llenar el ancho.

.frente h3

margin: 10px 0;
color: #0077b6;
➡️ El nombre del nudibranquio, con color azul y espacio arriba y abajo.

🔷 .reverso.tipo-carta

background: none;
padding: 0;
display: flex;
align-items: center;
justify-content: center;
transform: rotateY(180deg);
overflow: hidden;
✅ Esta es la cara trasera que se muestra al dar vuelta la tarjeta.

rotateY(180deg): está girada por defecto, se alinea con el giro del .contenido.

Centrado vertical y horizontal.

Puede contener otra imagen o información visual.

.reverso.tipo-carta img

width: 100%;
height: 100%;
object-fit: contain;
border-radius: 15px;
✅ Imagen del reverso (puede ser una ficha informativa o ilustración estilo Pokémon).

------------------------------------------------------------------------

🔷 .tabla-desplegable
Este es el estilo general del contenedor <details>:

max-width: 800px;
margin: 40px auto;
margin-top: 0px;
padding: 10px;
border: 2px solid #00b4d8;
border-radius: 12px;
font-family: Arial, sans-serif;
✅ ¿Qué hace?

max-width: 800px: limita el ancho del bloque para que no se vea tan largo en pantallas grandes.

margin: 40px auto: centra el contenedor y da espacio vertical (pero se anula con margin-top: 0px).

padding: 10px: agrega espacio interior para que no esté apretado.

border: bordes celestes (#00b4d8).

border-radius: bordes suavemente redondeados.

font-family: usa Arial, clara y fácil de leer.

🔷 .tabla-desplegable summary

cursor: pointer;
font-weight: bold;
font-size: 1.2rem;
color: #0077b6;
padding: 10px;
✅ Estilo del botón desplegable que el usuario debe hacer clic para ver la tabla.

cursor: pointer: cambia el cursor al pasar el mouse (como botón).

font-weight: bold: lo hace más visible.

color: #0077b6: azul suave para que destaque.

padding: espacio interior que mejora el clic.

🔷 .tabla-desplegable table

width: 100%;
margin-top: 15px;
border-collapse: collapse;
 Estilo general de la tabla:

Ocupa todo el ancho disponible del contenedor.

border-collapse: collapse: une los bordes de celdas (más limpio y profesional).

margin-top: espacio entre el <summary> y la tabla.

🔷 .tabla-desplegable th, td
🧱 ¿Qué es <th>?
➤ Significa: Table Header (Encabezado de tabla)
Se usa para definir las celdas del encabezado (títulos de columnas o filas).

🔹 El texto dentro de <th> aparece en negrita y centrado por defecto.
🔹 Ayuda a que la tabla sea más accesible y clara.

🧱 ¿Qué es <td>?
➤ Significa: Table Data (Dato de tabla)
Se usa para definir las celdas normales que contienen los datos reales.

🔹 Aparece como texto normal (no en negrita, no centrado, a menos que tú lo estilices).
🔹 Se coloca debajo de los <th> en cada fila.

border: 1px solid #90e0ef;
padding: 12px;
text-align: center;
✅ Estilo de cada celda:

Borde azul clarito (#90e0ef) para separar.

padding: da aire dentro de cada celda.

text-align: center: todo centrado (ideal para tablas de comparación).

🔷 .tabla-desplegable th

background-color: #0077b6;
color: white;
✅ Títulos de columnas:

Fondo azul marino intermedio.

Texto blanco: contraste claro y visible.


🔷 .tabla-desplegable tr:nth-child(even)

background-color: #e0f7fa;
✅ Aplica un color de fondo alternado en las filas pares. Mejora la lectura tipo “zebra” 🦓.

----------------------------------------------------------------------

🔷 html, body { ... }

background-color: #e0f7fa;
margin: 0;
padding: 0;
✅ ¿Qué hace?

background-color: #e0f7fa: aplica un color celeste claro como fondo general de toda la página, muy coherente con tu tema marino 🌊.

margin: 0; padding: 0;: elimina los márgenes y padding que vienen por defecto en los navegadores, para tener un diseño limpio y controlado desde cero.

🔷 .centrado { ... }

text-align: center;
margin-bottom: 30px;
✅ ¿Qué hace?

text-align: center: centra horizontalmente todo el contenido dentro del elemento que tenga esta clase (puede ser un botón, un título, un párrafo, etc.).

margin-bottom: 30px: deja espacio hacia abajo, para separar visualmente de lo que venga después.

-----------------------------------------------------------------------

🖼️ .carrusel-css

background-color: #e6f7ff;
padding: 40px 0;
text-align: center;
position: relative;
🔹 Define el fondo celeste de la sección.
🔹 Centra todo el contenido.
🔹 position: relative permite ubicar elementos dentro con position: absolute (como las flechas).

🔤 .carrusel-css h2

font-size: 2rem;
color: #023e8a;
margin-bottom: 20px;
🔹 Título del carrusel, tamaño grande y en azul profundo.

🔘 input[type="radio"]

display: none;
🔹 Oculta los input de tipo radio, que controlan qué slide se muestra.
(Están en el HTML pero no se ven visualmente).

🎞️ .slides

position: relative;
width: 80%;
max-width: 500px;
height: 300px;
margin: auto;
overflow: hidden;
border-radius: 16px;
box-shadow: 0 0 15px rgba(0, 0, 0, 0.2);
🔹 Es el contenedor que guarda todas las imágenes.
🔹 Tiene un borde redondeado y una sombra suave.
🔹 overflow: hidden oculta las imágenes fuera de su marco.

🖼️ .slide

position: absolute;
width: 100%;
height: 100%;
opacity: 0;
transition: opacity 0.8s ease-in-out;
🔹 Cada imagen (.slide) se apila encima de las otras.
🔹 Solo una tiene opacity: 1 a la vez.
🔹 Las demás están invisibles (opacity: 0).
🔹 La transición hace que el cambio entre imágenes sea suave.

📷 .slide img

width: 100%;
height: 100%;
object-fit: cover;
border-radius: 16px;
🔹 La imagen llena todo el slide.
🔹 object-fit: cover recorta para que se adapte sin deformarse.
🔹 Bordes redondeados como el contenedor.

🔘 Selector de slide activo

#slide1:checked ~ .slides .s1,
#slide2:checked ~ .slides .s2,
...
🔹 Cuando un input de tipo radio está seleccionado, muestra la slide correspondiente (opacity: 1 y z-index: 1).
🔹 Esto hace que solo una imagen se muestre a la vez, controlada por los botones (prev/next).

⬅️ ➡️ .prev, .next

position: absolute;
top: 50%;
transform: translateY(-50%);
🔹 Coloca las flechas al centro vertical del carrusel.

background-color: #0077b6;
color: white;
font-size: 2rem;
padding: 6px 12px;
border-radius: 50%;
cursor: pointer;
z-index: 2;
🔹 Las flechas tienen forma redonda, se ven claras y están por encima de la imagen.

.prev:hover, .next:hover {
  background-color: #023e8a;
}
🔹 Al pasar el mouse por encima, el fondo se oscurece.

.prev {
  left: 10px;
}

.next {
  right: 10px;
}
🔹 Posiciona la flecha izquierda y derecha en sus lados respectivos.

----------------------------------------------------------------------

🔷 .modal

position: fixed;
top: 0;
left: 0;
width: 100%;
height: 100%;
background: rgba(0,0,0,0.8);
opacity: 0;
pointer-events: none;
transition: opacity 0.4s ease;
z-index: 999;
✅ ¿Qué hace?

position: fixed: hace que el popup cubra toda la pantalla, sin importar cuánto scroll tenga la página.

background: rgba(0,0,0,0.8): fondo negro semi-transparente → da ese efecto de oscurecer el fondo.

opacity: 0 + pointer-events: none: el modal está invisible y no interactuable por defecto.

transition: opacity: hace que aparezca y desaparezca suavemente.

z-index: 999: asegura que el popup esté por encima de todo lo demás en la página.

🔷 .modal:target
✅ :target (pseudo-clase CSS)
➤ ¿Qué es?
:target es una pseudo-clase de CSS que se activa cuando un elemento con un id específico es el destino actual de la URL.
🎯 ¿Para qué sirve?
Te permite:

✅ Mostrar/ocultar cosas
✅ Crear popups o modales
✅ Desplegar detalles
✅ Simular comportamiento de JavaScript solo con HTML + CSS

opacity: 1;
pointer-events: auto;
✅ ¿Qué hace?

Cuando haces clic en un enlace que lleva a #idDelModal, como href="#galeria-popup", esta clase se activa automáticamente.

opacity: 1: el modal se vuelve visible.

pointer-events: auto: se puede hacer clic dentro (activando el contenido del popup).

💡 Este truco es posible solo con HTML + CSS usando :target.

🟨 .modal-contenido

position: relative;
max-width: 700px;
margin: 60px auto;
background: #e6f7ff;
padding: 30px;
border-radius: 15px;
box-shadow: 0 0 30px rgba(0,0,0,0.3);
✅ Es el bloque interior visible del modal, donde está el contenido real:

position: relative: sirve para posicionar elementos dentro (como el botón de cerrar).

max-width: 700px: no será más ancho que 700px.

margin: 60px auto: lo centra horizontalmente y deja 60px de espacio arriba.

background: #e6f7ff: fondo azul claro, coherente con tu diseño marino.

padding: da espacio interior para que no se vea apretado.

border-radius: bordes redondeados suaves.

box-shadow: sombra suave para dar efecto de "ventana flotante".

-----------------------------------------------------------------------

🔷 .cerrar

position: absolute;
top: 15px;
right: 15px;
➡️ Ubica el botón en la esquina superior derecha del contenedor, a 15px del borde superior y derecho.

width: 36px;
height: 36px;
line-height: 36px;
➡️ Define un botón cuadrado de 36x36px, y al usar el mismo line-height, el texto (la "✕") queda centrado verticalmente.

text-align: center;
font-size: 22px;
➡️ Centra el ícono "✕" horizontalmente y lo hace de buen tamaño.

background-color: #0077b6;
color: white;
➡️ Fondo azul y texto blanco: buen contraste visual.

border-radius: 50%;
➡️ Convierte el botón en un círculo perfecto.

text-decoration: none;
font-weight: bold;
➡️ Quita subrayado (en caso de que sea un <a>) y aplica negrita.

z-index: 1000;
➡️ Se asegura de que el botón esté por encima de todos los demás elementos del modal.

box-shadow: 0 2px 6px rgba(0,0,0,0.3);
➡️ Sombra suave para dar efecto flotante.

transition: background 0.3s;
➡️ Suaviza el cambio de color cuando se pasa el mouse encima.

🔷 .cerrar:hover

background-color: #023e8a;
➡️ Cambia el fondo a un azul más oscuro al pasar el mouse.7

-----------------------------------------------------------------------

🧾 .galeria-preview

background-color: #e6f7ff;
padding: 40px 20px;
text-align: center;
🔹 Define el fondo de toda la sección de la galería.
🔹 Añade espacio alrededor del contenido (40px arriba/abajo, 20px a los lados).
🔹 Centra todo el texto dentro.

📦 .galeria-flex

display: flex;
flex-wrap: wrap;
justify-content: center;
gap: 20px;
max-width: 1000px;
margin: 30px auto;
🔹 Activa Flexbox para ordenar las imágenes.
🔹 flex-wrap: wrap: las imágenes bajan a una nueva línea si no caben.
🔹 justify-content: center: centra las imágenes horizontalmente.
🔹 gap: 20px: espacio entre cada miniatura.
🔹 max-width: limita el ancho para no extenderse demasiado.
🔹 margin: 30px auto: espacio vertical y centrado horizontalmente.

🖼️ .item-galeria

width: 180px;
text-align: center;
font-family: Arial, sans-serif;
🔹 Contenedor individual de cada miniatura con su nombre.
🔹 Ancho fijo de 180px.
🔹 Texto centrado debajo de cada imagen.
🔹 Usa una fuente sencilla y legible.

📷 .item-galeria img

width: 100%;
height: 150px;
object-fit: cover;
border-radius: 12px;
box-shadow: 0 2px 8px rgba(0,0,0,0.1);
transition: transform 0.3s ease;
🔹 Las imágenes llenan todo el contenedor.
🔹 object-fit: cover: mantiene proporciones sin deformarse, recortando si es necesario.
🔹 border-radius: bordes redondeados suaves.
🔹 box-shadow: una sombra suave que las hace parecer tarjetas.
🔹 transition: al pasar el mouse, el cambio (zoom) será suave.

🖱️ .item-galeria img:hover

transform: scale(1.05);
🔹 Aplica un pequeño efecto de zoom al pasar el mouse por encima.
🔹 Hace que se vean interactivas y más vivas.

📝 .item-galeria p

margin-top: 8px;
font-size: 0.95rem;
color: #023e8a;
🔹 Texto descriptivo debajo de cada imagen.
🔹 Espacio superior pequeño para separarlo.
🔹 Tamaño de letra más pequeño.
🔹 Color azul profundo para que combine con el resto del sitio.

-----------------------------------------------------------------------

🔵 .formulario-contacto

max-width: 500px;
margin: 50px auto;
background-color: #e6f7ff;
padding: 30px;
border-radius: 12px;
box-shadow: 0 0 15px rgba(0,0,0,0.1);
font-family: Arial, sans-serif;
✅ Contenedor principal del formulario:

Ancho máximo de 500px.

Centrado (margin: 50px auto).

Fondo azul claro, suave.

Bordes redondeados y sombra suave para dar efecto de tarjeta.

Usa fuente clara y legible.

🟣 .formulario-contacto h2

text-align: center;
color: #023e8a;
margin-bottom: 10px;
✅ Estilo del título del formulario:

Centrado.

Azul marino fuerte.

Espacio debajo para separar del texto.

🟠 .formulario-contacto p

text-align: center;
margin-bottom: 20px;
✅ Descripción breve o subtítulo centrado.

🟢 .formulario-contacto form

display: flex;
flex-direction: column;
gap: 15px;
✅ Organiza los elementos del formulario (labels, inputs, botón) en una columna vertical, con 15px de espacio entre ellos.

🔵 .formulario-contacto label

font-weight: bold;
color: #0077b6;
✅ Las etiquetas (por ejemplo "Nombre:", "Correo:") se ven destacadas y en azul medio.

🔷 .formulario-contacto 

padding: 10px;
border: 1px solid #90e0ef;
border-radius: 6px;
font-size: 1rem;
✅ Campos de entrada suaves, redondeados, con borde celeste claro y tamaño de texto cómodo.

🔶 .formulario-contacto button

padding: 12px;
background-color: #0077b6;
color: white;
border: none;
border-radius: 6px;
font-size: 1rem;
cursor: pointer;
transition: background-color 0.3s ease;
✅ Botón bien visible, azul intenso con texto blanco, y una animación de cambio de color al pasar el mouse.

🟡 .formulario-contacto button:hover

background-color: #023e8a;
✅ Al pasar el cursor sobre el botón, se oscurece para dar retroalimentación visual.

----------------------------------------------------------------------

🟩 .mensaje-gracias

display: none;
background-color: #d1f7e0;
padding: 30px;
text-align: center;
border-radius: 12px;
margin: 50px auto;
max-width: 500px;
font-family: Arial, sans-serif;
color: #065f46;
box-shadow: 0 0 12px rgba(0, 0, 0, 0.1);
✅ Este bloque define cómo se ve el mensaje de éxito (cuando aparece):

display: none: está oculto por defecto.

Fondo verde clarito (#d1f7e0) y texto verde más oscuro (#065f46) para transmitir positividad.

padding: espacio interior para que no esté apretado.

border-radius: esquinas redondeadas para suavidad visual.

margin y max-width: centrado y limitado en tamaño.

box-shadow: sombra sutil para que parezca flotante

🟦 #gracias:target

display: block;
✅ Este selector se activa cuando en la URL aparece #gracias, lo que ocurre al enviar el formulario con un action="#gracias".
Eso hace visible el mensaje que estaba oculto.

🟨 .boton-volver

display: inline-block;
margin-top: 20px;
padding: 10px 20px;
background-color: #0077b6;
color: white;
text-decoration: none;
border-radius: 8px;
transition: background 0.3s ease;
✅ Botón para volver al formulario o a otra sección:

Se ve como botón (aunque es un enlace).

Azul marino, con letras blancas y bordes redondeados.

Transición suave al cambiar de color al pasar el mouse.

🟧 .boton-volver:hover

background-color: #023e8a;
✅ Al pasar el mouse, el botón se oscurece ligeramente, mostrando que es interactivo
