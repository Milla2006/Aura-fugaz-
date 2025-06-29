# Aura-fugaz-
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Aura Fugaz Beauty - Tienda</title>
  <link href="https://fonts.googleapis.com/css2?family=Cinzel+Decorative:wght@700&family=Quicksand:wght@400;600&display=swap" rel="stylesheet" />
  <style>
    body {
      font-family: 'Quicksand', sans-serif;
      background: #1e1b26;
      color: white;
      margin: 0;
      padding: 0 1rem;
      scroll-behavior: smooth;
      position: relative;
    }
    header {
      background: linear-gradient(90deg, #1e1b26, #2e2a47);
      color: white;
      padding: 1rem;
      font-family: 'Cinzel Decorative', cursive;
      box-shadow: 0 4px 10px rgba(0, 0, 0, 0.4);
      position: sticky;
      top: 0;
      z-index: 100;
    }

   .encabezado-contenido {
      display: flex;
      justify-content: space-between;
      align-items: center;
    }

  .logo-header {
      width: 60px;
      height: 60px;
      border-radius: 50%;
    }

  .redes-sociales a {
      font-size: 1.4rem;
      color: #f1c6d4;
      margin-left: 1rem;
      text-decoration: none;
      transition: color 0.3s;
    }

 .redes-sociales a:hover {
      color: #ffffff;
    }

   header h1 {
      text-align: center;
      margin: 0.5rem 0 0;
      font-size: 1.8rem;
    }
    .filtro-categorias {
      margin: 1rem 0;
      text-align: center;
    }
    .filtro-categorias button {
      background: #f1c6d4;
      border: none;
      color: #8e44ad;
      font-weight: bold;
      padding: 0.5rem 1rem;
      margin: 0 0.3rem;
      border-radius: 25px;
      cursor: pointer;
      transition: background-color 0.3s;
    }
    .filtro-categorias button.active,
    .filtro-categorias button:hover {
      background: #8e44ad;
      color: #f1c6d4;
    }
    /* PRODUCTOS EN CARRUSEL */
    .productos {
      display: flex;
      overflow-x: auto;
      gap: 1rem;
      padding: 1rem 0;
      scroll-snap-type: x mandatory;
    }
    .producto {
      background: white;
      color: #2e2a47;
      border-radius: 8px;
      padding: 1rem;
      width: 200px;
      flex-shrink: 0;
      box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
      scroll-snap-align: start;
      text-align: center;
      cursor: pointer;
      position: relative;
      user-select: none;
      transition: transform 0.2s ease;
    }
    .producto:hover {
      transform: scale(1.05);
      box-shadow: 0 5px 15px rgba(0,0,0,0.3);
    }
    .producto img {
      width: 100%;
      border-radius: 6px;
      margin-bottom: 0.5rem;
    }
    .producto button {
      margin-top: 0.5rem;
      background: #f1c6d4;
      border: none;
      color: #8e44ad;
      padding: 0.6rem 1rem;
      border-radius: 5px;
      cursor: pointer;
      font-weight: bold;
    }
    /* BOTÓN FLOTANTE */
    #boton-carrito {
      position: fixed;
      bottom: 20px;
      right: 20px;
      background: #f1c6d4;
      color: #8e44ad;
      font-size: 1.2rem;
      font-weight: bold;
      padding: 0.8rem 1rem;
      border-radius: 50px;
      box-shadow: 0 2px 10px rgba(0,0,0,0.3);
      cursor: pointer;
      z-index: 1000;
      display: flex;
      align-items: center;
      user-select: none;
    }
    #cantidad-carrito {
      background: white;
      color: #8e44ad;
      padding: 0.2rem 0.6rem;
      border-radius: 20px;
      font-size: 0.9rem;
      margin-left: 8px;
    }
    /* CARRITO FLOTANTE */
    #carrito {
      position: fixed;
      bottom: 80px;
      right: 20px;
      width: 280px;
      max-height: 60vh;
      overflow-y: auto;
      background: white;
      color: #2e2a47;
      border-radius: 10px;
      padding: 1rem;
      box-shadow: 0 2px 15px rgba(0,0,0,0.4);
      display: none;
      z-index: 999;
      font-size: 0.9rem;
    }
    #carrito h2 {
      margin-top: 0;
      text-align: center;
      color: #8e44ad;
    }
    #lista-carrito {
      list-style: none;
      padding-left: 0;
      max-height: 160px;
      overflow-y: auto;
      margin-bottom: 1rem;
    }
    #lista-carrito li {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-bottom: 0.5rem;
    }
    .btn-eliminar {
      background: #e74c3c;
      color: white;
      border: none;
      border-radius: 50%;
      width: 22px;
      height: 22px;
      font-size: 14px;
      cursor: pointer;
    }
    form input, form select {
      width: 100%;
      padding: 0.5rem;
      margin-bottom: 0.8rem;
      border-radius: 5px;
      border: 1px solid #ccc;
      font-size: 1rem;
    }
    form button {
      width: 100%;
      padding: 0.8rem;
      background: #8e44ad;
      border: none;
      color: white;
      font-weight: bold;
      border-radius: 6px;
      cursor: pointer;
      font-size: 1.1rem;
    }
    /* MODAL POPUP */
    #modal-fondo {
      position: fixed;
      top: 0; left: 0; right: 0; bottom: 0;
      background: rgba(0,0,0,0.75);
      display: none;
      justify-content: center;
      align-items: center;
      z-index: 2000;
    }
    #modal {
      background: white;
      color: #2e2a47;
      border-radius: 12px;
      max-width: 400px;
      width: 90%;
      padding: 1rem;
      box-shadow: 0 0 15px rgba(0,0,0,0.5);
      position: relative;
    }
    #modal h3 {
      margin-top: 0;
      font-family: 'Cinzel Decorative', cursive;
      color: #8e44ad;
      text-align: center;
    }

  #modal .imagenes-popup {
      display: flex;
      gap: 0.5rem;
      overflow-x: auto;
      margin-bottom: 1rem;
    }

   #modal .imagenes-popup img {
      width: 80px;
      border-radius: 6px;
      cursor: pointer;
      border: 2px solid transparent;
      transition: border-color 0.3s;
    }

   #modal .imagenes-popup img:hover,
    #modal .imagenes-popup img.selected {
      border-color: #8e44ad;
    }

   #modal .imagen-principal {
      width: 100%;
      border-radius: 8px;
      margin-bottom: 1rem;
    }

  #modal .descripcion {
      font-size: 0.95rem;
      line-height: 1.3;
      margin-bottom: 1rem;
    }
    #modal button.cerrar {
      position: absolute;
      top: 8px;
      right: 8px;
      background: #e74c3c;
      color: white;
      border: none;
      border-radius: 50%;
      width: 28px;
      height: 28px;
      font-size: 18px;
      cursor: pointer;
      line-height: 0;
    }
    @media (max-width: 500px) {
      .producto {
        width: 150px;
      }
      #carrito {
        width: 90vw;
        right: 5vw;
        bottom: 90px;
      }
      #modal {
        max-width: 95vw;
      }
    }
  </style>
</head>
<body>
  <header>
    <marquee><h5>♥ Envios a todo el país    ♥ Maquillaje tan bonito como tú  ♥ ♥ Envios a todo el país    ♥ Maquillaje tan bonito como tú  ♥ </h5></marquee>
  </header>

<header>
  <div class="encabezado-contenido">
    <img src="imagenes/logo-aura.png" alt="Logo Aura Fugaz" class="logo-header" />
    <div class="redes-sociales">
      <a href="https://www.instagram.com/tuusuario" target="_blank">📸</a>
      <a href="https://www.tiktok.com/@tuusuario" target="_blank">🎵</a>
      <a href="https://wa.me/593912345678" target="_blank">💬</a>
    </div>
  </div>
  <h1>Aura Fugaz Beauty</h1>
  <h4>Bienvenidos</h4>
</header>

<!-- FILTRO DE CATEGORÍAS -->
<div class="filtro-categorias" aria-label="Filtrar productos por categoría">
  <button class="active" data-categoria="todos">Todos</button>
  <button data-categoria="labiales">Labiales</button>
  <button data-categoria="rubores">Rubores</button>
  <button data-categoria="sombras">Sombras</button>
  <button data-categoria="Accesorios">Accesorios</button>
</div>

<!-- PRODUCTOS EN CARRUSEL -->
<section class="productos" aria-live="polite" aria-label="Lista de productos">
  <!-- Producto template -->
  <div class="producto" data-categoria="labiales" tabindex="0"
    data-nombre="Tintas"
    data-precio="2"
    data-descripcion="Labial en tono rosa suave, acabado brillante y duración prolongada."
    data-fotos='["fotitos/1751151081050.jpg","fotitos/1751151081050.jpg","fotitos/1751151081050.jpg"]'>
    <img src="fotitos/1751151081050.jpg" alt="tintas" />
    <h3>Lip tint</h3>
    <p>$2.00</p>
    <button onclick="event.stopPropagation(); agregarAlCarrito('Labial Rosa', 5)">Agregar al carrito</button>
  </div>

  <div class="producto" data-categoria="rubores" tabindex="0"
    data-nombre="Rubor Lila"
    data-precio="6"
    data-descripcion="Rubor en tono lila suave, para un look natural y radiante."
    data-fotos='["imagenes/rubor-lila.jpg","imagenes/rubor-lila2.jpg","imagenes/rubor-lila3.jpg"]'>
    <img src="imagenes/rubor-lila.jpg" alt="Rubor Lila" />
    <h3>Rubor Lila</h3>
    <p>$6.00</p>
    <button onclick="event.stopPropagation(); agregarAlCarrito('Rubor Lila', 6)">Agregar al carrito</button>
  </div>

  <div class="producto" data-categoria="sombras" tabindex="0"
    data-nombre="Sombra Negra"
    data-precio="7"
    data-descripcion="Sombra negra mate con alta pigmentación para un maquillaje intenso."
    data-fotos='["imagenes/sombra-negra.jpg","imagenes/sombra-negra2.jpg","imagenes/sombra-negra3.jpg"]'>
    <img src="imagenes/sombra-negra.jpg" alt="Sombra Negra" />
    <h3>Sombra Negra</h3>
    <p>$7.00</p>
    <button onclick="event.stopPropagation(); agregarAlCarrito('Sombra Negra', 7)">Agregar al carrito</button>
  </div>
  
  <div class="producto" data-categoria="sombras" tabindex="0"
    data-nombre="Sombra Negra"
    data-precio="7"
    data-descripcion="Sombra negra mate con alta pigmentación para un maquillaje intenso."
    data-fotos='["imagenes/sombra-negra.jpg","imagenes/sombra-negra2.jpg","imagenes/sombra-negra3.jpg"]'>
    <img src="imagenes/sombra-negra.jpg" alt="Sombra Negra" />
    <h3>Sombra Negra</h3>
    <p>$7.00</p>
    <button onclick="event.stopPropagation(); agregarAlCarrito('Sombra Negra', 7)">Agregar al carrito</button>
  </div>
  
<div class="producto" data-categoria="sombras" tabindex="0"
    data-nombre="Sombra Negra"
    data-precio="7"
    data-descripcion="Sombra negra mate con alta pigmentación para un maquillaje intenso."
    data-fotos='["imagenes/sombra-negra.jpg","imagenes/sombra-negra2.jpg","imagenes/sombra-negra3.jpg"]'>
    <img src="imagenes/sombra-negra.jpg" alt="Sombra Negra" />
    <h3>Sombra Negra</h3>
    <p>$7.00</p>
    <button onclick="event.stopPropagation(); agregarAlCarrito('Sombra Negra', 7)">Agregar al carrito</button>
  </div>
  
<div class="producto" data-categoria="sombras" tabindex="0"
    data-nombre="Sombra Negra"
    data-precio="7"
    data-descripcion="Sombra negra mate con alta pigmentación para un maquillaje intenso."
    data-fotos='["imagenes/sombra-negra.jpg","imagenes/sombra-negra2.jpg","imagenes/sombra-negra3.jpg"]'>
    <img src="imagenes/sombra-negra.jpg" alt="Sombra Negra" />
    <h3>Sombra Negra</h3>
    <p>$7.00</p>
    <button onclick="event.stopPropagation(); agregarAlCarrito('Sombra Negra', 7)">Agregar al carrito</button>
  </div>
</section>

<!-- BOTÓN FLOTANTE -->
<div id="boton-carrito" onclick="toggleCarrito()" aria-label="Mostrar u ocultar carrito">
  🛒 <span id="cantidad-carrito" aria-live="polite">0</span>
</div>

<!-- CARRITO FLOTANTE -->
<section id="carrito" role="dialog" aria-modal="true" aria-labelledby="titulo-carrito" tabindex="-1">
  <h2 id="titulo-carrito">Tu carrito</h2>
  <ul id="lista-carrito"></ul>
  <p><strong>Subtotal:</strong> $<span id="subtotal">0.00</span></p>
  <p><strong>Envío:</strong> $<span id="envio">0.00</span></p>
  <p><strong>Total:</strong> $<span id="total">0.00</span></p>

  <form onsubmit="return false;">
    <input type="text" id="nombre" placeholder="Tu nombre" required autocomplete="name" />
    <select id="ciudad" required onchange="actualizarCarrito()" aria-label="Selecciona tu ciudad">
      <option value="">Selecciona tu ciudad</option>
      <option value="Quito">Quito</option>
      <option value="Guayaquil">Guayaquil</option>
      <option value="Cuenca">Cuenca</option>
      <option value="Loja">Loja</option>
      <option value="Ambato">Ambato</option>
      <option value="Riobamba">Riobamba</option>
      <option value="Otro">Otra ciudad</option>
        <input type="tel" id="telefono" placeholder="WhatsApp (ej. 0912345678)" required pattern="[0-9]+" autocomplete="tel" />
   <select id="metodo-pago" required>
  <option value="">Selecciona método de pago</option>
  <option value="Efectivo al recibir">💵 Efectivo al recibir</option>
  <option value="Transferencia bancaria">🏦 Transferencia bancaria</option>
  <option value="Deuna">📱 Deuna</option>
  <option value="Peigo">📱 Peigo</option>
</select>
    <button onclick="enviarPedido()">Enviar pedido por WhatsApp</button>
  </form>
</section>

<!-- MODAL POPUP -->
<div id="modal-fondo" role="dialog" aria-modal="true" aria-labelledby="modal-titulo" tabindex="-1">
  <div id="modal">
    <button class="cerrar" aria-label="Cerrar popup" onclick="cerrarModal()">×</button>
    <h3 id="modal-titulo"></h3>
    <img src="" alt="" class="imagen-principal" />
    <div class="imagenes-popup" aria-label="Galería de imágenes del producto"></div>
    <p class="descripcion"></p>
    <button id="btn-agregar-popup" style="background:#f1c6d4; color:#8e44ad; font-weight:bold; padding:0.5rem 1rem; border:none; border-radius:5px; cursor:pointer;">Agregar al carrito</button>
  </div>
</div>

<script>
  const costosEnvio = {
    Quito: 5,
    Guayaquil: 6,
    Cuenca: 5,
    Loja: 5,
    Otro: 5,
    Riobamba: 0,
    Ambato: 5,
  };

  let carrito = {};
  let categoriaActual = 'todos';

  // Filtrar productos por categoría
  const botonesCategorias = document.querySelectorAll('.filtro-categorias button');
  const productos = document.querySelectorAll('.producto');

  botonesCategorias.forEach(boton => {
    boton.addEventListener('click', () => {
      categoriaActual = boton.getAttribute('data-categoria');

      botonesCategorias.forEach(b => b.classList.remove('active'));
      boton.classList.add('active');

      productos.forEach(p => {
        const cat = p.getAttribute('data-categoria');
        if (categoriaActual === 'todos' || categoriaActual === cat) {
          p.style.display = 'block';
        } else {
          p.style.display = 'none';
        }
      });
    });
  });

  // Agregar al carrito
  function agregarAlCarrito(nombre, precio) {
    if (carrito[nombre]) {
      carrito[nombre].cantidad++;
    } else {
      carrito[nombre] = { precio, cantidad: 1 };
    }
    actualizarCarrito();
  }

  // Eliminar del carrito
  function eliminarDelCarrito(nombre) {
    if (carrito[nombre]) {
      carrito[nombre].cantidad--;
      if (carrito[nombre].cantidad <= 0) {
        delete carrito[nombre];
      }
      actualizarCarrito();
    }
  }

  // Actualizar carrito y mostrar totales
  function actualizarCarrito() {
    const lista = document.getElementById('lista-carrito');
    lista.innerHTML = '';

    let subtotal = 0;
    let cantidadTotal = 0;

    for (const producto in carrito) {
      const item = carrito[producto];
      const li = document.createElement('li');
      li.innerHTML = `${producto} x${item.cantidad} - $${(item.precio * item.cantidad).toFixed(2)}
        <button class="btn-eliminar" onclick="eliminarDelCarrito('${producto}')">×</button>`;
      lista.appendChild(li);

      subtotal += item.precio * item.cantidad;
      cantidadTotal += item.cantidad;
    }

    const ciudad = document.getElementById('ciudad').value;
    const envio = costosEnvio[ciudad] || 0;

    document.getElementById('subtotal').textContent = subtotal.toFixed();
    document.getElementById('envio').textContent = envio.toFixed(2);
    document.getElementById('total').textContent = (subtotal + envio).toFixed(2);
    document.getElementById('cantidad-carrito').textContent = cantidadTotal;

    // Mostrar o esconder carrito si hay productos
    document.getElementById('carrito').style.display = cantidadTotal > 0 ? 'block' : 'none';
  }

  // Mostrar u ocultar carrito al hacer clic en el botón flotante
  function toggleCarrito() {
    const carritoDiv = document.getElementById('carrito');
    if (carritoDiv.style.display === 'block') {
      carritoDiv.style.display = 'none';
    } else if (Object.keys(carrito).length > 0) {
      carritoDiv.style.display = 'block';
      // Poner foco en carrito para accesibilidad
      carritoDiv.focus();
    }
  }

  // Enviar pedido por WhatsApp
  function enviarPedido() {
    if (Object.keys(carrito).length === 0) {
      alert('Tu carrito está vacío.');
      return;
    }

    const nombre = document.getElementById('nombre').value.trim();
    const ciudad = document.getElementById('ciudad').value;
    const telefono = document.getElementById('telefono').value.trim();

    if (!nombre || !ciudad || !telefono) {
      alert('Completa todos los datos');
      return;
    }

    let mensaje = `Hola, quiero hacer un pedido:\n\n`;
    let subtotal = 0;

    for (const producto in carrito) {
      const item = carrito[producto];
      mensaje += `- ${producto} x${item.cantidad} = $${(item.precio * item.cantidad).toFixed(2)}\n`;
      subtotal += item.precio * item.cantidad;
    }

    const envio = costosEnvio[ciudad] || 0;
    const total = subtotal + envio;

    mensaje += `\nSubtotal: $${subtotal.toFixed(2)}\n`;
    mensaje += `Envío (${ciudad}): $${envio.toFixed(2)}\n`;
    mensaje += `Total: $${total.toFixed(2)}\n\n`;
    mensaje += `Nombre: ${nombre}\nCiudad: ${ciudad}\nWhatsApp: ${telefono}`;

    const numeroTienda = "593912345678"; // cambia por tu número
    const url = `https://wa.me/${numeroTienda}?text=${encodeURIComponent(mensaje)}`;
    window.open(url, '_blank');
  }

  // --- MODAL POPUP ---

  const modalFondo = document.getElementById('modal-fondo');
  const modal = document.getElementById('modal');
  const modalTitulo = modal.querySelector('h3#modal-titulo');
  const imagenPrincipal = modal.querySelector('.imagen-principal');
  const galeriaImgs = modal.querySelector('.imagenes-popup');
  const descripcionModal = modal.querySelector('.descripcion');
  const btnAgregarPopup = document.getElementById('btn-agregar-popup');

  // Abrir modal al hacer clic en producto
  productos.forEach(producto => {
    producto.addEventListener('click', () => {
      abrirModalProducto(producto);
    });

    // También abrir con tecla Enter para accesibilidad
    producto.addEventListener('keydown', (e) => {
      if (e.key === 'Enter' || e.key === ' ') {
        e.preventDefault();
        abrirModalProducto(producto);
      }
    });
  });

  function abrirModalProducto(producto) {
    const nombre = producto.getAttribute('data-nombre');
    const precio = parseFloat(producto.getAttribute('data-precio'));
    const descripcion = producto.getAttribute('data-descripcion');
    const fotos = JSON.parse(producto.getAttribute('data-fotos'));

    modalTitulo.textContent = nombre;
    descripcionModal.textContent = descripcion;
    imagenPrincipal.src = fotos[0];
    imagenPrincipal.alt = nombre;

    // Limpiar galería
    galeriaImgs.innerHTML = '';

    fotos.forEach((foto, index) => {
      const img = document.createElement('img');
      img.src = foto;
      img.alt = `${nombre} imagen ${index + 1}`;
      if (index === 0) img.classList.add('selected');
      img.addEventListener('click', () => {
        imagenPrincipal.src = foto;
        // Marcar imagen seleccionada
        galeriaImgs.querySelectorAll('img').forEach(i => i.classList.remove('selected'));
        img.classList.add('selected');
      });
      galeriaImgs.appendChild(img);
    });

    // Botón para agregar producto desde modal
    btnAgregarPopup.onclick = () => {
      agregarAlCarrito(nombre, precio);
      cerrarModal();
    };

    modalFondo.style.display = 'flex';
    modalFondo.focus();
  }

  // Cerrar modal
  function cerrarModal() {
    modalFondo.style.display = 'none';
  }

  // Cerra
