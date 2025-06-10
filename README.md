<!FINANCIAT5 html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" /> 
  <title>FINANCIA-T | Asesoría Financiera</title



/* FUENTE MONTSERRAT AQUI APLICADA */
  <link href="https://fonts.googleapis.com/css2?family=Montserrat&display=swap" rel="stylesheet" /> 

 

  <style>
    /* AJUSTE A TODOS LOS DISPOSITIVOS EN GENERAL */
    body, html {
      margin: 0;
      padding: 0;
      height: 100%;
      font-family: 'Montserrat', sans-serif; 
      background-color: #004080;   /* AQUIIIIIIII*/

      color: #003366;
      overflow-x: hidden; /* Evitar que se deforme en forma horizontal */
      line-height: 1.6; /* Mejora la lectura del texto  */
    }

    /* Contenedor principal */
    #main-container {
      min-height: 100vh; /* Asegura que ocupe al menos la altura de la vista */
      display: flex;
      flex-direction: column; /* Organiza los elementos verticalmente */
    }

    header {
      background-color: #003366;
      color: white;
      padding: 15px; /* Ajuste de padding para pantallas pequeñas */
      display: flex;
      flex-direction: column; /* Stack logo and text on small screens */
      align-items: center;
      justify-content: center;
      gap: 10px; /* Reducir el espacio entre elementos */
      text-align: center;
    }

    header img {
      width: 80px; /* Tamaño más pequeño por defecto */
      height: 80px;
      border-radius: 12px;
    }

    h1 {
      margin: 0;
      font-size: 2em; /* Tamaño de fuente adaptable */
    }

    header p {
      margin: 5px 0 0;
      font-size: 1em; /* Tamaño de fuente adaptable */
    }

    .main-content-section {
      padding: 20px; /* Ajuste de padding */
      max-width: 1000px;
      margin: 20px auto; /* Margen superior y centrado */
      background-color: #ffffff;
      box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
      border-radius: 10px;
      flex-grow: 1; /* Permite que la sección crezca y ocupe espacio disponible */
    }

    h2, h3 {
      color: #003366;
      margin-top: 25px; /* Ajuste de margen superior */
      font-size: 1.5em; /* Tamaño de fuente adaptable */
    }
    h3 {
      font-size: 1.2em; /* H3 un poco más pequeño */
    }

    ul {
      padding-left: 20px;
      margin-bottom: 15px; /* Espacio debajo de las listas */
    }

    .contacto {
      background-color: #e0ecff;
      padding: 15px; /* Ajuste de padding */
      margin-top: 25px;
      border-radius: 10px;
      line-height: 1.5; /* Ajuste de línea */
      font-size: 0.95em; /* Ligeramente más pequeño */
    }

    .contacto p {
      margin: 5px 0;
    }

    .contacto a {
      word-break: break-all; /* Rompe la palabra si es demasiado larga para la pantalla */
    }

    .boton-principal {
      display: block;
      width: 90%; /* Ancho adaptable */
      max-width: 400px; /* Máximo ancho para no estirarse demasiado en pantallas grandes */
      margin: 30px auto 20px;
      padding: 12px 20px; /* Ajuste de padding */
      text-align: center;
      background-color: #0059b3;
      color: white;
      font-weight: bold;
      border-radius: 8px;
      text-decoration: none;
      transition: background-color 0.3s;
      cursor: pointer;
      font-size: 1.1em; /* Tamaño de fuente adaptable */
      border: none; /* Asegurar que no tenga borde */
    }

    .boton-principal:hover {
      background-color: #004080;
    }

    .galeria {
      margin-top: 30px;
      display: flex;
      flex-direction: column; /* Columna por defecto para móviles */
      justify-content: center;
      align-items: center; /* Centrar imágenes en columna */
      gap: 15px; /* Espacio entre imágenes */
    }

    .galeria img {
      width: 100%; /* Las imágenes ocupan todo el ancho disponible */
      max-width: 460px; /* Máximo ancho original */
      height: auto; /* Mantener la proporción */
      border-radius: 10px;
      box-shadow: 0 0 8px rgba(0, 0, 0, 0.2);
    }

    /* --- Estilos de la aplicación interna (Login/Registro/Navegación) --- */

    nav {
      background-color: #003366;
      display: flex;
      flex-wrap: wrap; /* Permite que los elementos se envuelvan */
      justify-content: center;
      gap: 1rem; /* Espacio entre los elementos de navegación */
      padding: 1rem 0.5rem; /* Ajuste de padding */
      font-weight: 700;
      color: white;
      cursor: pointer;
      user-select: none;
      box-shadow: 0 3px 6px rgba(0,0,0,0.3);
      position: sticky;
      top: 0;
      z-index: 10;
    }
    nav span {
      padding: 0.5rem 0.8rem; /* Aumentar área de clic */
      transition: color 0.3s;
    }
    nav span:hover {
      color: #a6c8ff;
    }

    #app-container {
      min-height: calc(100vh - 80px); /* Ajustar altura para dejar espacio al footer y header */
      background: #f4f9ff;
      padding: 2rem 1rem 4rem 1rem; /* Más padding abajo para el footer */
      max-width: 900px;
      margin: 20px auto; /* Centrar y dar margen */
      border-radius: 12px;
      box-shadow: 0 0 20px rgba(0,64,128,0.15);
      color: #003366;
      flex-grow: 1;
    }

    .app-section {
      display: none;
      animation: fadeIn 0.5s ease forwards;
    }
    .app-section.active {
      display: block;
    }

    .app-section h2, .app-section h3 {
      color: #00264d;
      margin-bottom: 1rem;
    }
    .app-section p {
      line-height: 1.6;
      margin-bottom: 1rem;
      font-size: 1rem;
    }

    .service {
      background: #e6f0ff;
      border-radius: 12px;
      padding: 1.5rem;
      margin-bottom: 2rem;
      box-shadow: 0 3px 10px rgba(0,64,128,0.1);
      border: 1px solid #a6c8ff;
      text-align: center; /* Centrar contenido de servicio */
    }
    .service img {
      max-width: 180px; /* Reducir tamaño de imagen de servicio */
      height: auto;
      border-radius: 10px;
      margin: 0 auto 1rem auto; /* Centrar imagen */
      box-shadow: 0 0 10px rgba(0,64,128,0.2);
      display: block;
    }
    .service button {
      background-color: #004080;
      color: white;
      border: none;
      padding: 10px 20px; /* Ajuste de padding */
      border-radius: 8px;
      font-weight: 600;
      cursor: pointer;
      transition: background-color 0.3s ease;
      width: auto; /* Que el botón no ocupe todo el ancho */
    }
    .service button:hover {
      background-color: #00264d;
    }

    /* LOGIN & REGISTRO */
    .login-register-container {
      background: white;
      max-width: 360px;
      margin: 4rem auto; /* Ajuste de margen */
      padding: 2rem 1.5rem; /* Ajuste de padding */
      border-radius: 14px;
      box-shadow: 0 0 25px rgba(0,64,128,0.3);
      color: #004080;
      text-align: center;
      position: relative;
    }
    .login-register-container h2 {
      margin-bottom: 1.5rem;
      color: #003366;
    }
    .login-register-container input {
      width: calc(100% - 24px); /* Ajuste para padding */
      padding: 12px;
      margin-bottom: 1rem; /* Reducir margen */
      border: 2px solid #004080;
      border-radius: 8px;
      font-size: 1rem;
      color: #003366;
    }
    .login-register-container input::placeholder {
      color: #7a9bd1;
    }
    .login-register-container button {
      width: 100%; /* Que el botón ocupe todo el ancho */
      font-size: 1.1rem;
      margin-top: 0.5rem;
      padding: 12px; /* Ajuste de padding */
      background-color: #004080; /* Asegurar color */
      color: white; /* Asegurar color */
      border: none; /* Asegurar que no tenga borde */
      border-radius: 8px; /* Asegurar borde redondeado */
      cursor: pointer;
    }
    .login-register-container p {
      margin-top: 0.8rem; /* Reducir margen */
      font-size: 0.9em; /* Ligeramente más pequeño */
      color: #004080;
    }
    .login-register-container a {
      color: #004080;
      font-weight: 700;
      cursor: pointer;
      text-decoration: none;
    }
    .login-register-container a:hover {
      color: #00264d;
      text-decoration: underline;
    }

    /* REDES SOCIALES ICONOS (RIGHT SIDE) */
    .social-icons {
      position: fixed;
      top: 50%;
      right: 0;
      transform: translateY(-50%);
      display: flex;
      flex-direction: column;
      gap: 8px; /* Reducir espacio entre iconos */
      z-index: 15;
    }
    .social-icons a {
      background-color: #004080;
      width: 40px; /* Tamaño de icono más pequeño */
      height: 40px;
      border-radius: 50%;
      display: flex;
      justify-content: center;
      align-items: center;
      color: white;
      text-decoration: none;
      transition: background-color 0.3s ease;
      box-shadow: 0 2px 5px rgba(0,0,0,0.2); /* Sutil sombra */
    }
    .social-icons a:hover {
      background-color: #00264d;
    }
    .social-icons img {
      width: 18px; /* Tamaño de imagen de icono */
      height: 18px;
      pointer-events: none;
      user-select: none;
    }

    /* FOOTER */
    footer {
      text-align: center;
      padding: 1rem 15px; /* Padding adaptable */
      background-color: #003366; /* Color de footer consistente */
      color: white; /* Color de texto consistente */
      font-size: 0.85em; /* Fuente más pequeña */
      box-shadow: 0 -3px 6px rgba(0,0,0,0.2);
      margin-top: auto; /* Empuja el footer al final si hay espacio */
    }

    /* --- Modal Styles --- */
    .modal {
        display: none;
        position: fixed;
        z-index: 999; /* Mayor z-index para estar por encima de todo */
        left: 0;
        top: 0;
        width: 100%;
        height: 100%;
        overflow: auto;
        background-color: rgba(0,0,0,0.6); /* Fondo más oscuro para el modal */
        padding-top: 20px; /* Reducir padding superior */
    }

    .modal-content {
        background-color: #fefefe;
        margin: 2% auto; /* Margen superior y centrado */
        padding: 20px;
        border: 1px solid #888;
        width: 90%; /* Más ancho en móviles */
        max-width: 700px; /* Máximo ancho en desktop */
        border-radius: 10px;
        box-shadow: 0 4px 8px 0 rgba(0,0,0,0.2), 0 6px 20px 0 rgba(0,0,0,0.19);
        position: relative;
    }

    .close {
        color: #aaa;
        float: right;
        font-size: 28px;
        font-weight: bold;
    }

    .close:hover,
    .close:focus {
        color: black;
        text-decoration: none;
        cursor: pointer;
    }

    #openModal {
        position: fixed;
        bottom: 20px; /* Más cerca del borde inferior */
        right: 20px;
        z-index: 100;
        background-color:#0059b3;
        color:white;
        padding:10px 15px;
        border-radius:5px;
        border:none;
        cursor:pointer;
        font-size: 0.9em; /* Tamaño de fuente más pequeño */
        box-shadow: 0 2px 5px rgba(0,0,0,0.3);
    }

    /* ANIMATION */
    @keyframes fadeIn {
      from {opacity: 0;}
      to {opacity: 1;}
    }

    /* --- Media Queries para Responsividad --- */

    /* Tablets y Laptops pequeñas (mayor que 480px, hasta 768px) */
    @media (min-width: 481px) and (max-width: 768px) {
      header {
        flex-direction: row; /* Logo y texto en línea */
        gap: 20px;
      }
      header img {
        width: 90px;
        height: 90px;
      }
      h1 {
        font-size: 2.2em;
      }
      header p {
        font-size: 1.05em;
      }

      .main-content-section {
        padding: 25px;
        margin-top: 25px;
      }

      .galeria {
        flex-direction: row; /* Dos columnas en tablets */
        flex-wrap: wrap;
        justify-content: space-around; /* Espacio entre imágenes */
      }
      .galeria img {
        width: 48%; /* Dos imágenes por fila */
        max-width: none; /* Desactivar max-width para esta vista */
      }

      .login-register-container {
        max-width: 400px;
        padding: 2.5rem 2rem;
      }
      .login-register-container input {
        width: calc(100% - 24px);
      }

      .social-icons {
        gap: 12px;
      }
      .social-icons a {
        width: 45px;
        height: 45px;
      }
      .social-icons img {
        width: 20px;
        height: 20px;
      }
    }

    /* Desktops y Laptops grandes (mayor que 768px) */
    @media (min-width: 769px) {
      header {
        flex-direction: row;
        gap: 30px;
        padding: 20px;
      }
      header img {
        width: 100px;
        height: 100px;
      }
      h1 {
        font-size: 2.5em;
      }
      header p {
        font-size: 1.1em;
      }

      .main-content-section {
        padding: 30px;
        margin-top: 30px;
      }

      h2 {
        font-size: 1.8em;
      }
      h3 {
        font-size: 1.4em;
      }

      .galeria {
        flex-direction: row; /* Volver a fila para desktops */
        flex-wrap: nowrap; /* No wrapping, mantener en una fila */
        gap: 20px;
      }
      .galeria img {
        width: auto; /* Dejar que el tamaño original mande */
        max-width: 460px; /* Máximo ancho original */
      }

      .login-register-container {
        max-width: 450px;
        padding: 3rem 2.5rem;
      }
      .login-register-container input {
        width: calc(100% - 24px);
      }

      .social-icons {
        gap: 15px;
      }
      .social-icons a {
        width: 48px;
        height: 48px;
      }
      .social-icons img {
        width: 22px;
        height: 22px;
      }
    }

    /* Orientación Horizontal (Landscape) para dispositivos móviles */
    @media screen and (max-height: 500px) and (orientation: landscape) {
        body {
            font-size: 0.9em; /* Reduce el tamaño general del texto */
        }
        header {
            padding: 10px;
            gap: 5px;
        }
        header img {
            width: 60px;
            height: 60px;
        }
        h1 {
            font-size: 1.5em;
        }
        header p {
            font-size: 0.8em;
        }
        .main-content-section, #app-container {
            padding: 15px;
            margin: 10px auto;
        }
        .boton-principal, .login-register-container button {
            padding: 10px 15px;
            font-size: 0.9em;
        }
        .galeria {
            flex-direction: row;
            flex-wrap: wrap;
            gap: 10px;
        }
        .galeria img {
            width: 45%;
        }
        .service {
            padding: 1rem;
            margin-bottom: 1.5rem;
        }
        .service img {
            max-width: 120px;
        }
        .social-icons {
            flex-direction: row;
            position: static;
            transform: none;
            justify-content: center;
            padding: 10px;
        }
        #openModal {
            bottom: 10px;
            right: 10px;
            padding: 8px 12px;
            font-size: 0.8em;
        }
        .modal-content {
            margin: 1% auto;
            width: 95%;
            padding: 15px;
            font-size: 0.9em;
        }
    }
  </style>
</head>
<body>

  <div id="main-container"></div>

  <script>
    let isLoggedIn = false;

    // Función para renderizar la página principal de "Quiénes Somos"
    function renderMainPage() {
      document.getElementById("main-container").innerHTML = `
        <header>
          <img
            src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcS62frppnqrlpvjLNI898PbtswucibZR_-Kuw&s"
            alt="Logo Financia-T"
          />
          <div>
            <h1>FINANCIA-T</h1>
            <p>Expertos en Asesoramiento Financiero</p>
          </div>
        </header>

        <section class="main-content-section">
          <h2>¿Quiénes Somos?</h2>
          <p>
            FINANCIA-T es una empresa dedicada a brindar asesoría y gestión a las
            diferentes oportunidades financieras con las que cuentan los
            derechohabientes, en materia de seguridad social, sector inmobiliario y
            financiero.
          </p>

          <h2>Misión</h2>
          <p>
            Impulsar los sueños de nuestros clientes, a través de soluciones que les
            permitan financiarse para hacer realidad sus proyectos a corto y mediano
            plazo.
          </p>

          <h2>Visión</h2>
          <p>
            Contribuir a la economía de derechohabientes a nivel nacional, siendo
            empresa líder en la asesoría y gestión de soluciones financieras para el
            trabajador, y ser la alternativa número uno para resolver las
            problemáticas en su vida laboral.
          </p>

          <h2>Servicios Financieros</h2>
          <ul>
            <li>Retiros Totales</li>
            <li>Ayudas por Desempleo</li>
            <li>Pensiones (Modalidad 40)</li>
            <li>Recuperación del saldo de la subcuenta de vivienda</li>
            <li>Crédito Mejoravit / Crédito Mejorasi</li>
          </ul>

          <div class="contacto">
            <h2>Contáctanos</h2>
            <p><strong>Nombre:</strong> Karina Sosa</p>
            <p><strong>Correo:</strong> karina.sosa@finaanciat.com</p>
            <p><strong>Teléfono de Oficina:</strong> 5590559049</p>
            <p><strong>WhatsApp:</strong> 5645553067</p>
            <p>
              <strong>Facebook:</strong>
              <a href="https://n9.cl/financiat1" target="_blank"
                >https://n9.cl/financiat1</a
              >
            </p>
            <p>
              <strong>TikTok:</strong>
              <a href="https://tiktok.com/@financiat4" target="_blank"
                >tiktok.com/@financiat4</a
              >
            </p>
          </div>

          <button class="boton-principal" onclick="renderLogin()">Iniciar Sesión o Registro</button>

          <div class="galeria">
             <img src="https://scontent.fmex11-3.fna.fbcdn.net/v/t39.30808-6/495300403_1010645387940981_2274864196300540329_n.jpg?stp=dst-jpg_p526x296_tt6&_nc_cat=104&ccb=1-7&_nc_sid=127cfc&_nc_ohc=prqSAKhPvzYQ7kNvwEkYlJD&_nc_oc=Adm011eGajQoNbR1exZm_bPIUUl2beCfCJMQFoSQhkCbs1j7WCDzdHcMNDYpxIcJDpsayr6WhardV4ZXjC0G4Hnh&_nc_zt=23&_nc_ht=scontent.fmex11-3.fna&_nc_gid=qosASZsBzsB39R6jQe6obQ&oh=00_AfKxofpIAyRZUND3MWY_0HFOGFAUeA4HJ20dt94f7nJ02g&oe=6845AAEC" alt="Foto 1 Financia-T">
            <img
              src="https://scontent.fmex11-1.fna.fbcdn.net/v/t39.30808-6/500768145_1132161568945579_3359912226161928656_n.jpg?stp=dst-jpg_p526x296_tt6&_nc_cat=103&ccb=1-7&_nc_sid=127cfc&_nc_ohc=inFRsd-iQQ4Q7kNvwFEVQkp&_nc_oc=AdkU2cuDLIbMN3CKNtwkb4_LZ7NYx4k-7FBnaAWiBL7Cu5QEvBdqMcYGkHYTcBuGMRob8Fu13M_xBq_iTiQj5Keb&_nc_zt=23&_nc_ht=scontent.fmex11-1.fna&_nc_gid=VdwHwBSeznI99oi9VpWZWA&oh=00_AfJBJcWy2D5n79277f1Ph0Sly38csf0iYRB-HLYO9sCAnw&oe=68457B3C"
              alt="Foto 2 Financia-T"
            />
          </div>
        </section>

        <footer>
          &copy; 2025 FINANCIA-T. Todos los derechos reservados.
        </footer>
      `;
    }

    function renderLogin() {
      document.getElementById("main-container").innerHTML = `
        <div class="login-register-container">
          <h2>Iniciar Sesión</h2>
          <input type="text" id="loginUser" placeholder="Usuario" autocomplete="username" />
          <input type="password" id="loginPass" placeholder="Contraseña" autocomplete="current-password" />
          <button onclick="login()">Ingresar</button>
          <p>¿No tienes cuenta? <a onclick="renderRegister()">Regístrate</a></p>
          <p><a onclick="renderMainPage()">Volver a la página principal</a></p> </div>
        <div class="social-icons">
          <a href="https://www.facebook.com/people/FinanciaT/100069865874839/" target="_blank" title="Facebook"><img src="https://img.icons8.com/ios-filled/50/ffffff/facebook--v1.png" alt="Facebook"></a>
          <a href="https://www.tiktok.com/@financiat4" target="_blank" title="TikTok"><img src="https://img.icons8.com/ios-filled/50/ffffff/tiktok.png" alt="TikTok"></a>
        </div>
      `;
    }

    function renderRegister() {
      document.getElementById("main-container").innerHTML = `
        <div class="login-register-container">
          <h2>Registro</h2>
          <input type="text" id="regUser" placeholder="Nombre de usuario" autocomplete="username" />
          <input type="email" id="regEmail" placeholder="Correo electrónico (solo @gmail.com)" autocomplete="email" />
          <input type="password" id="regPass" placeholder="Contraseña" autocomplete="new-password" />
          <button onclick="register()">Registrarse</button>
          <p>¿Ya tienes cuenta? <a onclick="renderLogin()">Inicia sesión</a></p>
          <p><a onclick="renderMainPage()">Volver a la página principal</a></p> </div>
        <div class="social-icons">
          <a href="https://www.facebook.com/people/FinanciaT/100069865874839/" target="_blank" title="Facebook"><img src="https://img.icons8.com/ios-filled/50/ffffff/facebook--v1.png" alt="Facebook"></a>
          <a href="https://www.tiktok.com/@financiat4" target="_blank" title="TikTok"><img src="https://img.icons8.com/ios-filled/50/ffffff/tiktok.png" alt="TikTok"></a>
        </div>
      `;
    }

    function renderApp() {
      document.getElementById("main-container").innerHTML = `
        <nav>
          <span onclick="showSection('inicio')">Inicio</span>
          <span onclick="showSection('conocenos')">Conócenos</span>
          <span onclick="showSection('servicios')">Servicios</span>
          <span onclick="showSection('contacto')">Contacto</span>
          <span style="margin-left:auto; cursor:pointer;" onclick="logout()" title="Cerrar sesión">Salir</span>
        </nav>
        <div id="app-container"> <section id="inicio" class="app-section active">
            <h2>Bienvenidos a FINANCIA-T</h2>
            <p>Empresa dedicada a brindar asesoría y gestión a las diferentes oportunidades financieras con las que cuentan los Derechohabientes, en materia de seguridad social, sector inmobiliario y financiero.</p>
            <img src="https://scontent.fmex15-1.fna.fbcdn.net/v/t39.30808-6/308738693_405836048410113_5235564790691032839_n.jpg?_nc_cat=110&ccb=1-7&_nc_sid=6ee11a&_nc_eui2=AeE_ur4TUltGY4cEwA7MeEKX_CBbNy8wrQ_8IFs3LzCtDy_Mv7TXHGHvkg9Gb4L4QEKryXmBr3lcfw440r9qT1kw&_nc_ohc=Tc2QeepSFjsQ7kNvwHBBhrM&_nc_oc=Admtlyx314NX6GZ9ORDWszko_jgrq-ON1KZOc3U16EGyAhrZg0l6-7fSc7E_wEXksEKTz22hdzpH5_Ibzy7Da0zo&_nc_zt=23&_nc_ht=scontent.fmex15-1.fna&_nc_gid=VDNq2KnU8ubxbeRMTy_yLg&oh=00_AfL4hu4bkPvk52z9wC0tOdMpnmOHLNxYEGUmNrK-eoCBGg&oe=684190D9"  alt="Finanzas" style="width:100%; border-radius: 14px; margin-bottom:1.5rem;"/>
          </section>
          <section id="conocenos" class="app-section">
            <h2>¿Quiénes somos?</h2>
            <p>FINANCIA-T</p>
            <p>Empresa dedicada a brindar asesoría y gestión a las diferentes oportunidades financieras con las que cuentan los Derechohabientes, en materia de seguridad social, sector inmobiliario y financiero.</p>

            <p>MISIÓN</p>
            <p>Impulsamos los sueños de nuestros clientes, a través de soluciones que les permiten financiarse para hacer realidad sus proyectos a corto y mediano plazo.</p>

            <p>VISIÓN</p>
            <p>Contribuir a la economía de derechohabientes a nivel nacional, siendo empresa líder en la asesoría y gestión de soluciones financieras para el trabajador. Así como ser la alternativa número uno para dar solución a las diferentes problemáticas que se les presenten en su vida laboral.</p>
            <img src="https://scontent.fmex15-1.fna.fbcdn.net/v/t39.30808-6/482235092_970588201946700_872621995359312906_n.jpg?_nc_cat=110&ccb=1-7&_nc_sid=127cfc&_nc_eui2=AeEN711yj9wEyfehzGnCm4F7QhhqW7AubhBCGGpbsC5uEFxULeU4-06UKPk-xHgBLax2NgouDu7bBU0fDjkWuNVr&_nc_ohc=8oqSca62LCkQ7kNvwGBMb4_&_nc_oc=Adlb1kF_LWPL6tbuv9Zt6bOeEP_MeN2QAgGFcZ1Tlh9UL4oCCPt5p827k349YxQNo_YVOq7QM4pw-Av6ZxhIUOie&_nc_zt=23&_nc_ht=scontent.fmex15-1.fna&_nc_gid=Av7ZDBOOqC-Ikni52oVFAQ&oh=00_AfKgVmmLAhQ9hjsVZkQIroMD0rIqkX2Bx1Hh6DfNkMvvQw&oe=6841BA1D" alt="Equipo" style="width:100%; border-radius: 14px; margin-top:1rem;"/>
          </section>
          <section id="servicios" class="app-section">
            <h2>Nuestros Servicios</h2>

            <div class="service">
              <h3>INFONAVIT</h3>
              <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSd5YcNIF9Xt4zNYubiEBwc2bujpHoo-PRPNQ&s">
              <p>RECUPERACIÓN DEL SALDO DE LA SUBCUENTA DE VIVIENDA</p>
              <p>CRÉDITO MEJORAVIT /CRÉDITO MEJORASI</p>


<form action="https://formspree.io/f/xqabapgr" method="POST">
 <p> <input type="text" name="nombre" placeholder="NOMBRE COMPLETO"></p>
  <p><input type="email" name="email" placeholder="CORREO ELECTRONICO"></p>
  <p><textarea name="mensaje" placeholder="Gracias por escogernos"></textarea></p>
  <p><button type="submit">Contratar Servicio INFONAVIT</button></p>
</form>





              
            </div>

            <div class="service">
              <h3>IMSS</h3>
              <img src="https://www.ler.uam.mx/ServiciosMedicosUAML/wp-content/uploads/2023/10/imssVerde.jpg" alt="IMSS">
              <p> PENSIONES (MODALIDAD 40) </p>

<form action="https://formspree.io/f/xgvyvanz" method="POST">
 <p> <input type="text" name="nombre" placeholder="NOMBRE COMPLETO"></p>
  <p><input type="email" name="email" placeholder="CORREO ELECTRONICO"></p>
  <p><textarea name="mensaje" placeholder="Gracias por escogernos"></textarea></p>
  <p><button type="submit">Contratar Servicio IMSS</button></p>
</form>

                </div>

            <div class="service">
              <h3>AFORE</h3>
              <img src="https://play-lh.googleusercontent.com/jw1dW1mZqZOdwfslRmVEtAHVMui4Po_DzkA_NcyMnVbg4z9jNgtcVe-dgfbdX5QpQKQ" alt="AFORE">
              <p>RETIROS TOTALES</p>
              <p>AYUDAS POR DESEMPLEO</p>
              <form action="https://formspree.io/f/movwveye" method="POST">
 <p> <input type="text" name="nombre" placeholder="NOMBRE COMPLETO"></p>
  <p><input type="email" name="email" placeholder="CORREO ELECTRONICO"></p>
  <p><textarea name="mensaje" placeholder="Gracias por escogernos"></textarea></p>
  <p><button type="submit">Contratar Servicio AFORE</button></p>
</form>            </div>
          </section>
          <section id="contacto" class="app-section">



            <h2>Contacto</h2>
            <p>¿Tienes dudas o quieres más información? Escríbenos y con gusto te atenderemos.</p>
          

<form action="https://formspree.io/f/myzjzedk" method="POST">
 <p> <input type="text" name="nombre" placeholder="NOMBRE COMPLETO"></p>
  <p><input type="email" name="email" placeholder="CORREO ELECTRONICO"></p>
  <p><textarea name="mensaje" placeholder="Escribe tu mensaje y dudas, estamos para atenderte!"></textarea></p>
  <p><button type="submit">Enviar</button></p>
</form>

            <p>Cotización</p>
            <p>Teléfono de oficina: 5590559049</p>
            <p>What´s App: 5645553067</p>
            <p>GMAIL. karina.sosa@finaanciat.com</p>
            </form>
          </section>
        </div>
        <div class="social-icons">
          <a href="https://www.facebook.com/people/FinanciaT/100069865874839/" target="_blank" title="Facebook"><img src="https://img.icons8.com/ios-filled/50/ffffff/facebook--v1.png" alt="Facebook"></a>
          <a href="https://www.tiktok.com/@financiat4" target="_blank" title="TikTok"><img src="https://img.icons8.com/ios-filled/50/ffffff/tiktok.png" alt="TikTok"></a>
        </div>

        <button id="openModal">Abrir Aviso de privacidad</button>

        <div id="modal" class="modal">
          <div class="modal-content">
            <span class="close">&times;</span>
            <footer>Aviso de privacidad | FINANCIA-T</footer>
            <p><strong>Aviso de Privacidad – FinanciaT</strong></p>
            <p>En FinanciaT, la protección de tus datos personales es prioritaria. Este Aviso de Privacidad tiene como propósito informarte sobre cómo recopilamos, usamos, almacenamos y protegemos tu información personal, de acuerdo con la legislación vigente y las mejores prácticas internacionales en comercio digital. 
Aviso de Privacidad</p>

<p>En cumplimiento con la Ley Federal de Protección de Datos Personales en Posesión de los Particulares, FINANCIA-T con domicilio en Calle Campeche, Bo De Dolores Temascalapa C.P 55980(Calle Campeche, Bo De Dolores Temascalapa C.P 55980), es responsable del tratamiento de sus datos personales.</p>

Los datos personales que recabamos serán utilizados para las siguientes finalidades:</p>
<li>Proveer los productos y servicios requeridos por usted.
<li>Informar sobre cambios o nuevos productos o servicios.
<li>Dar cumplimiento a obligaciones contraídas con nuestros clientes.
<li>Evaluar la calidad del servicio.</li>

<p><strong>Derechos ARCO (Acceso, Rectificación, Cancelación y Oposición)</strong></p>
<p>Usted tiene el derecho de acceder, rectificar y cancelar sus datos personales, así como de oponerse al tratamiento de los mismos. Para ejercer estos derechos, puede enviar una solicitud al correo financiateasesorias@gmail.com</p>

<p>Este aviso de privacidad puede ser modificado por FINANCIA-T, dichas modificaciones serán oportunamente informadas a través de nuestra página web.</p>

<p>Derechos ARCO

En cumplimiento con la Ley Federal de Protección de Datos Personales en Posesión de los Particulares, los titulares de datos personales pueden ejercer en todo momento los derechos de:</p>

<li>Acceso:Conocer qué datos personales tenemos y el uso que les damos.</li>
<li>Rectificación: Solicitar la corrección de sus datos personales si están incompletos, inexactos o desactualizados.</li>
<li>Cancelación: Solicitar la eliminación de sus datos cuando considere que no están siendo tratados conforme a los principios y obligaciones legales.</li>
<li>Oposición: Oponerse al uso de sus datos personales para fines específicos.</li>

Para ejercer cualquiera de estos derechos, debe enviar una solicitud al correo [correo electrónico] con copia de su identificación oficial y descripción clara del derecho que desea ejercer.

Lineamientos de PROFECO para Negocios Digitales

<li>Brindar protección transparente y eficaz, no inferior a la del comercio tradicional.</li>
<li>Evitar afirmaciones falsas o engañosas sobre bienes y servicios.</li>
<li>No participar en prácticas engañosas respecto al uso de datos personales.</li>
<li>Garantizar que la publicidad sea veraz y no engañosa.</li>
<li>Implementar mecanismos para que el consumidor pueda decidir sobre recibir o no publicidad.</li>
<li>No ocultar la identidad o ubicación del proveedor.</li>

<p><strong>Código de Conducta para el Comercio Digital</strong></p>

<p>1. Actuar con transparencia, honestidad y responsabilidad.</p>
<p>2. Evitar prácticas comerciales engañosas o fraudulentas.</p>
<p>3. Respetar la privacidad y proteger los datos personales del consumidor.</p>
<p>4. Garantizar el derecho del consumidor a acceder, rectificar, cancelar y oponerse al uso de sus datos.</p>
<p>5. Asegurar que toda publicidad dirigida sea veraz y adecuada a su audiencia.</p>
<p>6. Responder de manera oportuna y adecuada a quejas y solicitudes de los consumidores.</p>
<p>7. Colaborar con autoridades nacionales e internacionales en materia de protección al consumidor digital.</p>

<p><strong><h2>FINANCIA-T</h2></strong></p>


            <p><strong>1. Identidad del responsable</strong></p>
            <p>FinanciaT S.A. de C.V., con domicilio en [domicilio de la empresa], es responsable del tratamiento de tus datos personales.</p>

            <p><strong>2. Finalidades del tratamiento</strong></p>
            <p>Recabamos tus datos para las siguientes finalidades:</p>
            <ul>
              <li>Proveer servicios financieros digitales.</li>
              <li>Validar identidad y realizar operaciones de verificación antifraude.</li>
              <li>Enviarte información sobre nuestros productos y promociones, previa autorización.</li>
              <li>Cumplir con obligaciones legales y contractuales.</li>
            </ul>

            <p><strong>3. Protección y confidencialidad</strong></p>
            <p>Adoptamos medidas técnicas y administrativas para proteger tu información de accesos no autorizados o usos indebidos, incluyendo:</p>
            <ul>
              <li>Códigos de conducta internos y mecanismos de cumplimiento.</li>
              <li>Transparencia en nuestras prácticas comerciales.</li>
              <li>Identificación clara del proveedor en todas nuestras comunicaciones.</li>
            </ul>

            <p><strong>4. Derechos ARCO</strong></p>
            <p>Puedes ejercer tus derechos de Acceso, Rectificación, Cancelación y Oposición (ARCO) enviando una solicitud a: [correo electrónico de contacto].</p>

            <p><strong>5. Transferencias de datos</strong></p>
            <p>No compartiremos tus datos con terceros sin tu consentimiento, salvo que sea necesario para cumplir con disposiciones legales.</p>

            <p><strong>6. Uso de cookies y tecnologías similares</strong></p>
            <p>Nuestro sitio puede utilizar cookies para mejorar la experiencia del usuario. Puedes modificar tus preferencias desde la configuración de tu navegador.</p>

            <p><strong>Términos y Condiciones de Uso – FinanciaT</strong></p>

            <p><strong>1. Uso responsable</strong></p>
            <p>El usuario se compromete a usar el sitio de manera lícita, sin incurrir en prácticas engañosas, fraudes o manipulación de información.</p>

            <p><strong>2. Publicidad clara y veraz</strong></p>
            <p>Nos comprometemos a que toda la publicidad y oferta de servicios sea clara, sin omitir o tergiversar información esencial para el consumidor.</p>

            <p><strong>3. Protección a grupos vulnerables</strong></p>
            <p>Tomamos precauciones adicionales cuando dirigimos campañas a grupos como adultos mayores o personas con condiciones especiales.</p>

            <p><strong>4. Consentimiento informado</strong></p>
            <p>Brindamos mecanismos claros para que los usuarios decidan si desean recibir comunicaciones comerciales o publicitarias.</p>

            <p><strong>5. Autodisciplina y autorregulación</strong></p>
            <p>FinanciaT promueve prácticas de autorregulación basadas en códigos de conducta y lineamientos éticos en materia de comercio digital.</p>

            <p><strong>6. Limitación de responsabilidad</strong></p>
            <p>No nos hacemos responsables por daños derivados del uso indebido del sitio, ni por interrupciones ajenas a nuestro control.</p>
          </div>
        </div>
      `;
      setupModal(); // Asegurarse de que el modal funciona después de renderizar
    }

    function showSection(sectionId) {
      const sections = document.querySelectorAll("#app-container .app-section");
      sections.forEach(s => {
        s.id === sectionId ? s.classList.add("active") : s.classList.remove("active");
      });
      // Asegurar que el scroll esté arriba al cambiar de sección
      window.scrollTo(0, 0);
    }

    function login() {
      const user = document.getElementById("loginUser").value.trim();
      const pass = document.getElementById("loginPass").value.trim();
      if(user === "" || pass === "") {
        alert("Por favor ingresa usuario y contraseña.");
        return;
      }
      // Aquí podrías validar con base de datos o localStorage
      isLoggedIn = true;
      renderApp();
    }

    function register() {
      const user = document.getElementById("regUser").value.trim();
      const email = document.getElementById("regEmail").value.trim();
      const pass = document.getElementById("regPass").value.trim();
      if(user === "" || email === "" || pass === "") {
        alert("Por favor llena todos los campos para registrarte.");
        return;
      }
      // Aquí podrías guardar datos en base de datos o localStorage
      alert("Registro exitoso. Ahora inicia sesión.");
      renderLogin();
    }

    function logout() {
      isLoggedIn = false;
      renderLogin();
    }

    function handleContactForm(e) {
      e.preventDefault();
      alert("Gracias por contactarnos, te responderemos pronto.");
      e.target.reset();
    }

    function setupModal() {
      const modal = document.getElementById("modal");
      const btn = document.getElementById("openModal");
      const span = document.getElementsByClassName("close")[0];

      // Verificar si los elementos existen antes de asignar eventos
      if (modal && btn && span) {
        btn.onclick = function() {
          modal.style.display = "block";
        }

        span.onclick = function() {
          modal.style.display = "none";
        }

        window.onclick = function(event) {
          if (event.target == modal) {
            modal.style.display = "none";
          }
        }
      }
    }

    // Inicializa mostrando la página principal
    renderMainPage();
  </script>

</body>
</html>
