CÓMO PONER LOS LOGOS REALES DE CLIENTES
=======================================

La franja "Negocios que ya confían en mí" está en la página redes.html,
justo debajo del hero. Ahora mismo muestra logos de EJEMPLO (recuadros con
texto "Logo cliente 1", "Logo cliente 2"...).

Para poner los reales, dos pasos:

1) SUBE LOS LOGOS A ESTA CARPETA (img/clientes/)
   - Un archivo por cliente, por ejemplo:
       img/clientes/cliente-1.png
       img/clientes/cliente-2.png
       ...
   - Formato recomendado: PNG con fondo transparente (o SVG).
   - Que se lean bien: los logos se muestran en gris/atenuados por defecto y
     a todo color al pasar el ratón. Alto aproximado: 52 px.

2) EDITA CADA BLOQUE EN redes.html
   Busca en redes.html el comentario "FRANJA CONFÍAN EN MÍ".
   Debajo verás varios bloques como este (uno por cliente):

     <!-- CLIENTE 1 -->
     <a class="client-logo" href="#" target="_blank" rel="noopener noreferrer"
        aria-label="Logo cliente 1"><span class="client-ph">Logo cliente 1</span></a>

   En cada bloque cambia 3 cosas:
     a) href="#"            -> la web del cliente (https://www.sucliente.com)
     b) aria-label="..."    -> el nombre real del cliente
     c) sustituye
            <span class="client-ph">Logo cliente 1</span>
        por
            <img src="img/clientes/cliente-1.png" alt="Nombre del cliente">

   Ejemplo ya terminado:
     <!-- CLIENTE 1 -->
     <a class="client-logo" href="https://www.panaderialolo.com" target="_blank"
        rel="noopener noreferrer" aria-label="Panadería Lolo">
        <img src="img/clientes/cliente-1.png" alt="Panadería Lolo"></a>

NOTAS
- Puedes añadir o quitar bloques <a class="client-logo">...</a> libremente
  (no hace falta que sean 6). El desplazamiento en bucle se ajusta solo.
- No hace falta duplicar los logos a mano: el efecto de carrusel infinito se
  genera con JavaScript clonando la fila automáticamente.
