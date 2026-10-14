<!DOCTYPE html>
<html lang="es">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>SABORÉ | Gastrobar</title>

    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
         :root {
            --negro: #080808;
            --negro-claro: #111111;
            --gris: #b9b9b9;
            --dorado: #c99b50;
            --crema: #a70075;
            --blanco: #ffffff;
        }
        
        html {
            scroll-behavior: smooth;
        }
        
        body {
            font-family: Arial, sans-serif;
            background: var(--negro);
            color: var(--crema);
            line-height: 1.6;
        }
        
        h1,
        h2,
        h3,
        .logo {
            font-family: Georgia, "Times New Roman", serif;
            font-weight: 400;
        }
        
        a {
            text-decoration: none;
            color: inherit;
        }
        
        video {
            width: 100%;
            height: 100%;
            object-fit: cover;
            display: block;
        }
        
        #pantalla-login {
            position: fixed;
            inset: 0;
            z-index: 9999;
            background: linear-gradient( rgba(8, 8, 8, 0.90), rgba(8, 8, 8, 0.96)), url("imagenes/fondo-login.jpg") center/cover no-repeat;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 30px;
        }
        
        .login-contenedor {
            width: 100%;
            max-width: 500px;
            text-align: center;
            background: rgba(17, 17, 17, 0.96);
            border: 1px solid var(--dorado);
            padding: 50px 45px;
            box-shadow: 0 0 40px rgba(0, 0, 0, 0.7);
        }
        
        .login-logo {
            color: var(--crema);
            font-family: Georgia, "Times New Roman", serif;
            font-size: 2.5rem;
            letter-spacing: 7px;
        }
        
        .login-logo span {
            display: block;
            color: var(--dorado);
            font-family: Arial, sans-serif;
            font-size: 0.6rem;
            letter-spacing: 6px;
            margin-top: -5px;
        }
        
        .login-subtitulo {
            color: var(--dorado);
            text-transform: uppercase;
            letter-spacing: 4px;
            font-size: 0.7rem;
            margin-top: 35px;
            margin-bottom: 15px;
        }
        
        .login-contenedor h1 {
            font-size: 3rem;
            line-height: 1.1;
            margin-bottom: 10px;
        }
        
        .login-contenedor h1 span {
            color: var(--dorado);
        }
        
        .login-linea {
            width: 70px;
            height: 2px;
            background: var(--dorado);
            margin: 25px auto;
        }
        
        .login-descripcion {
            color: #999;
            font-size: 0.9rem;
            margin-bottom: 30px;
        }
        
        .login-form {
            border: none;
            padding: 0;
            text-align: left;
        }
        
        .login-form input {
            width: 100%;
            background: transparent;
            border: none;
            border-bottom: 1px solid #555;
            padding: 16px 5px;
            color: white;
            margin-bottom: 25px;
            outline: none;
            font-size: 0.95rem;
        }
        
        .login-form input:focus {
            border-bottom-color: var(--dorado);
        }
        
        .login-form input::placeholder {
            color: #888;
        }
        
        .login-btn {
            width: 100%;
            padding: 16px;
            background: transparent;
            border: 1px solid var(--dorado);
            color: var(--crema);
            text-transform: uppercase;
            letter-spacing: 2px;
            font-size: 0.75rem;
            cursor: pointer;
            transition: 0.3s;
        }
        
        .login-btn:hover {
            background: var(--dorado);
            color: var(--negro);
        }
        
        .login-mensaje {
            min-height: 22px;
            margin-top: 20px;
            color: #d9534f;
            font-size: 0.85rem;
            text-align: center;
        }
        
        .crear-cuenta {
            margin-top: 25px;
            text-align: center;
            color: #888;
            font-size: 0.85rem;
        }
        
        .crear-cuenta a {
            color: var(--dorado);
            cursor: pointer;
            transition: 0.3s;
        }
        
        .crear-cuenta a:hover {
            color: var(--crema);
        }
        
        #pantalla-registro {
            position: fixed;
            inset: 0;
            z-index: 10000;
            background: linear-gradient( rgba(8, 8, 8, 0.90), rgba(8, 8, 8, 0.96)), url("imagenes/fondo-login.jpg") center/cover no-repeat;
            display: none;
            justify-content: center;
            align-items: center;
            padding: 30px;
        }
        
        .registro-contenedor {
            width: 100%;
            max-width: 500px;
            text-align: center;
            background: rgba(17, 17, 17, 0.96);
            border: 1px solid var(--dorado);
            padding: 45px;
            box-shadow: 0 0 40px rgba(0, 0, 0, 0.7);
        }
        
        .registro-logo {
            color: var(--crema);
            font-family: Georgia, "Times New Roman", serif;
            font-size: 2.5rem;
            letter-spacing: 7px;
        }
        
        .registro-logo span {
            display: block;
            color: var(--dorado);
            font-family: Arial, sans-serif;
            font-size: 0.6rem;
            letter-spacing: 6px;
            margin-top: -5px;
        }
        
        .registro-subtitulo {
            color: var(--dorado);
            text-transform: uppercase;
            letter-spacing: 4px;
            font-size: 0.7rem;
            margin-top: 30px;
            margin-bottom: 15px;
        }
        
        .registro-contenedor h1 {
            font-size: 3rem;
            line-height: 1.1;
            margin-bottom: 10px;
        }
        
        .registro-contenedor h1 span {
            color: var(--dorado);
        }
        
        .registro-linea {
            width: 70px;
            height: 2px;
            background: var(--dorado);
            margin: 25px auto;
        }
        
        .registro-form {
            border: none;
            padding: 0;
            text-align: left;
        }
        
        .registro-form input {
            width: 100%;
            background: transparent;
            border: none;
            border-bottom: 1px solid #555;
            padding: 14px 5px;
            color: white;
            margin-bottom: 20px;
            outline: none;
            font-size: 0.95rem;
        }
        
        .registro-form input:focus {
            border-bottom-color: var(--dorado);
        }
        
        .registro-form input::placeholder {
            color: #888;
        }
        
        .registro-btn {
            width: 100%;
            padding: 16px;
            background: transparent;
            border: 1px solid var(--dorado);
            color: var(--crema);
            text-transform: uppercase;
            letter-spacing: 2px;
            font-size: 0.75rem;
            cursor: pointer;
            transition: 0.3s;
        }
        
        .registro-btn:hover {
            background: var(--dorado);
            color: var(--negro);
        }
        
        .registro-mensaje {
            min-height: 22px;
            margin-top: 20px;
            text-align: center;
            font-size: 0.85rem;
        }
        
        .volver-login {
            display: block;
            margin-top: 25px;
            color: var(--dorado);
            font-size: 0.8rem;
            cursor: pointer;
            transition: 0.3s;
        }
        
        .volver-login:hover {
            color: var(--crema);
        }
        
        #contenido-principal {
            display: none;
        }
        
        header {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 85px;
            background: rgba(8, 8, 8, 0.96);
            border-bottom: 1px solid #252525;
            z-index: 1000;
        }
        
        nav {
            max-width: 1400px;
            height: 100%;
            margin: auto;
            padding: 0 40px;
            display: flex;
            align-items: center;
            justify-content: space-between;
        }
        
        .logo {
            color: var(--crema);
            font-size: 2rem;
            letter-spacing: 7px;
        }
        
        .logo span {
            display: block;
            font-family: Arial, sans-serif;
            font-size: 0.6rem;
            letter-spacing: 6px;
            text-align: center;
            margin-top: -4px;
            color: var(--dorado);
        }
        
        .menu {
            display: flex;
            gap: 22px;
            list-style: none;
            align-items: center;
        }
        
        .menu a {
            font-size: 0.72rem;
            letter-spacing: 1px;
            color: #d2d2d2;
            transition: 0.3s;
        }
        
        .menu a:hover {
            color: var(--dorado);
        }
        
        .sociales {
            display: flex;
            gap: 10px;
        }
        
        .social {
            width: 38px;
            height: 38px;
            border: 1px solid var(--dorado);
            border-radius: 50%;
            display: grid;
            place-items: center;
            color: var(--dorado);
            transition: 0.3s;
            cursor: pointer;
        }
        
        .social:hover {
            background: var(--dorado);
            color: var(--negro);
            transform: translateY(-2px);
        }
        
        .btn {
            display: inline-block;
            padding: 15px 25px;
            border: 1px solid var(--dorado);
            color: var(--crema);
            text-transform: uppercase;
            letter-spacing: 2px;
            font-size: 0.72rem;
            transition: 0.3s;
        }
        
        .btn:hover {
            background: var(--dorado);
            color: var(--negro);
        }
        
        #inicio {
            min-height: 100vh;
            position: relative;
            overflow: hidden;
            display: flex;
            align-items: center;
        }
        
        .video-fondo {
            position: absolute;
            inset: 0;
            z-index: -2;
        }
        
        .video-fondo video {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
        
        .capa-oscura {
            position: absolute;
            inset: 0;
            background: linear-gradient( 90deg, rgba(8, 8, 8, .98) 30%, rgba(8, 8, 8, 0.048));
            z-index: -1;
        }
        
        .hero-content {
            padding: 140px 8% 80px;
            max-width: 800px;
        }
        
        .subtitulo {
            color: var(--dorado);
            text-transform: uppercase;
            letter-spacing: 5px;
            font-size: 0.75rem;
            margin-bottom: 20px;
        }
        
        .hero-content h1 {
            font-size: clamp(3rem, 6vw, 6rem);
            line-height: 1;
            margin-bottom: 30px;
        }
        
        .hero-content h1 span {
            color: var(--dorado);
        }
        
        .linea {
            width: 70px;
            height: 2px;
            background: var(--dorado);
            margin: 25px 0;
        }
        
        .hero-content p {
            max-width: 480px;
            color: #c8c8c8;
            font-size: 1.1rem;
            margin-bottom: 35px;
        }
        
        .scroll {
            margin-top: 70px;
            color: #888 !important;
            font-size: 0.7rem !important;
            text-transform: uppercase;
            letter-spacing: 3px;
        }
        
        #conocenos {
            min-height: 100vh;
            padding: 100px 8%;
            background: var(--crema);
            color: var(--negro);
            display: grid;
            grid-template-columns: 1fr 1fr;
            align-items: center;
            gap: 60px;
        }
        
        .conocenos-texto h2,
        .menu-intro h2,
        .bebidas-texto h2,
        .galeria-texto h2,
        .reservas-texto h2 {
            font-size: clamp(2.5rem, 5vw, 4.5rem);
            line-height: 1.1;
            margin-bottom: 25px;
        }
        
        .conocenos-texto p {
            color: #555;
            max-width: 600px;
            margin-bottom: 30px;
        }
        
        .conocenos-video {
            height: 500px;
            overflow: hidden;
        }
        
        .valores {
            grid-column: 1 / -1;
            background: var(--negro-claro);
            color: var(--crema);
            display: grid;
            grid-template-columns: repeat(4, 1fr);
        }
        
        .valor {
            padding: 40px 30px;
            text-align: center;
            border-right: 1px solid #333;
        }
        
        .valor:last-child {
            border-right: none;
        }
        
        .valor .icono {
            font-size: 2rem;
            color: var(--dorado);
            margin-bottom: 15px;
        }
        
        .valor h3 {
            letter-spacing: 1px;
            margin-bottom: 10px;
        }
        
        .valor p {
            color: #999;
            font-size: 0.9rem;
        }
        
        .mision-vision {
            grid-column: 1 / -1;
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 30px;
            margin-top: 10px;
        }
        
        .mision,
        .vision {
            background: var(--negro-claro);
            color: var(--crema);
            padding: 40px;
            border: 1px solid #333;
            border-left: 2px solid var(--dorado);
        }
        
        .mision h3,
        .vision h3 {
            color: var(--dorado);
            font-size: 1.5rem;
            letter-spacing: 2px;
            margin-bottom: 15px;
        }
        
        .mision p,
        .vision p {
            color: #aaa;
            font-size: 0.95rem;
            line-height: 1.8;
        }
        
        #menu {
            padding: 100px 8%;
            background: var(--negro);
        }
        
        .menu-superior {
            display: grid;
            grid-template-columns: 1fr 1.3fr;
            gap: 40px;
            align-items: center;
            margin-bottom: 60px;
        }
        
        .menu-intro h2 {
            font-size: 4rem;
        }
        
        .menu-intro h2 span {
            color: var(--dorado);
        }
        
        .menu-imagen {
            height: 450px;
            overflow: hidden;
        }
        
        .platos-grid {
            display: grid;
            grid-template-columns: repeat(4, minmax(0, 1fr));
            gap: 20px;
        }
        
        .plato {
            background: #151515;
            border: 1px solid #292929;
            overflow: hidden;
            transition: transform 0.3s, border-color 0.3s;
        }
        
        .plato:hover {
            transform: translateY(-10px);
            border-color: var(--dorado);
        }
        
        .plato-imagen {
            width: 100%;
            height: 240px;
            overflow: hidden;
            display: flex;
            justify-content: center;
            align-items: center;
            background: #080808;
        }
        
        .plato-imagen img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            object-position: center center;
            display: block;
            transition: transform 0.5s;
        }
        
        .plato:hover .plato-imagen img {
            transform: scale(1.06);
        }
        
        .plato-info {
            padding: 20px;
            min-height: 145px;
        }
        
        .plato-info h3 {
            font-size: 1.4rem;
            margin-bottom: 8px;
        }
        
        .plato-info p {
            color: #999;
            font-size: 0.85rem;
        }
        
        .precio {
            color: var(--dorado);
            display: block;
            margin-top: 15px;
            font-weight: bold;
        }
        
        #bebidas {
            min-height: 100vh;
            position: relative;
            overflow: hidden;
            padding: 100px 8%;
        }
        
        .bebidas-fondo {
            position: absolute;
            inset: 0;
            z-index: -2;
        }
        
        .bebidas-fondo video {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
        
        .bebidas-capa {
            position: absolute;
            inset: 0;
            background: linear-gradient( 90deg, rgba(8, 8, 8, .95), rgba(8, 8, 8, .6));
            z-index: -1;
        }
        
        .bebidas-texto {
            max-width: 650px;
        }
        
        .bebidas-texto h2 {
            font-size: clamp(3rem, 6vw, 5rem);
        }
        
        .bebidas-texto h2 span {
            color: var(--dorado);
        }
        
        .bebidas-texto p {
            color: #aaa;
            margin-bottom: 35px;
            max-width: 550px;
        }
        
        .bebidas-grid {
            margin-top: 80px;
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 25px;
        }
        
        .categoria-bebida {
            background: rgba(15, 15, 15, .92);
            padding: 35px;
            border: 1px solid #333;
        }
        
        .categoria-bebida h3 {
            color: var(--dorado);
            font-size: 1.8rem;
            margin-bottom: 15px;
        }
        
        .categoria-bebida ul {
            list-style: none;
            color: #aaa;
        }
        
        .categoria-bebida li {
            padding: 10px 0;
            border-bottom: 1px solid #333;
        }
        
        #galeria {
            min-height: 100vh;
            padding: 100px 8%;
            display: grid;
            grid-template-columns: 0.8fr 1.2fr;
            gap: 60px;
            background: #0d0d0d;
        }
        
        .galeria-texto p {
            color: #999;
            max-width: 400px;
        }
        
        .galeria-filtros {
            display: flex;
            gap: 10px;
            margin: 25px 0;
            flex-wrap: wrap;
        }
        
        .filtro {
            border: 1px solid #444;
            padding: 8px 15px;
            font-size: 0.7rem;
            color: #aaa;
            cursor: pointer;
        }
        
        .filtro.activo,
        .filtro:hover {
            border-color: var(--dorado);
            color: var(--dorado);
        }
        
        .galeria-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 15px;
        }
        
        .foto {
            height: 220px;
            overflow: hidden;
        }
        
        .foto img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            object-position: center;
            transition: 0.5s;
            display: block;
        }
        
        .foto:hover img {
            transform: scale(1.1);
        }
        
        #reservas {
            background: var(--negro-claro);
            padding: 100px 8% 0;
        }
        
        .reservas-superior {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 70px;
            padding-bottom: 80px;
        }
        
        .reservas-texto h2 span {
            color: var(--dorado);
        }
        
        .reservas-texto p {
            color: #999;
            max-width: 500px;
        }
        
        #reservaForm {
            border: 1px solid var(--dorado);
            padding: 35px;
        }
        
        .fila {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 20px;
        }
        
        #reservaForm input,
        #reservaForm select {
            width: 100%;
            background: transparent;
            border: none;
            border-bottom: 1px solid #555;
            padding: 15px 5px;
            color: white;
            margin-bottom: 20px;
            outline: none;
        }
        
        #reservaForm input::placeholder {
            color: #999;
        }
        
        #reservaForm select option {
            background: #111;
        }
        
        .form-btn {
            width: 100%;
            background: transparent;
            cursor: pointer;
        }
        
        .contacto-info {
            border-top: 1px solid #333;
            padding: 50px 0;
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 30px;
        }
        
        .contacto-info h3 {
            color: var(--dorado);
            margin-bottom: 15px;
            letter-spacing: 1px;
        }
        
        .contacto-info p {
            color: #999;
        }
        
        .cerrar-sesion {
            position: fixed;
            bottom: 20px;
            right: 20px;
            z-index: 2000;
            background: var(--negro);
            color: var(--dorado);
            border: 1px solid var(--dorado);
            padding: 10px 15px;
            cursor: pointer;
            font-size: 0.7rem;
            letter-spacing: 1px;
            text-transform: uppercase;
            transition: 0.3s;
        }
        
        .cerrar-sesion:hover {
            background: var(--dorado);
            color: var(--negro);
        }
        
        footer {
            border-top: 1px solid #333;
            padding: 35px 8%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            color: #777;
            font-size: 0.75rem;
        }
        
        @media (max-width: 1100px) {
            .menu {
                gap: 12px;
            }
            .menu a {
                font-size: 0.65rem;
            }
        }
        
        @media (max-width: 1000px) {
            .menu {
                display: none;
            }
            #conocenos,
            .menu-superior,
            #galeria,
            .reservas-superior {
                grid-template-columns: 1fr;
            }
            .platos-grid {
                grid-template-columns: repeat(2, minmax(0, 1fr));
                gap: 22px;
            }
            .valores {
                grid-template-columns: repeat(2, 1fr);
            }
            .valor:nth-child(2) {
                border-right: none;
            }
            .bebidas-grid {
                grid-template-columns: 1fr;
            }
            .contacto-info {
                grid-template-columns: 1fr;
            }
            .mision-vision {
                grid-template-columns: 1fr;
            }
        }
        
        @media (max-width: 600px) {
            #pantalla-login,
            #pantalla-registro {
                padding: 20px;
            }
            .login-contenedor,
            .registro-contenedor {
                padding: 40px 25px;
            }
            .login-logo,
            .registro-logo {
                font-size: 2rem;
            }
            .login-contenedor h1,
            .registro-contenedor h1 {
                font-size: 2.4rem;
            }
            nav {
                padding: 0 20px;
            }
            .logo {
                font-size: 1.5rem;
            }
            .sociales {
                display: none;
            }
            #conocenos,
            #menu,
            #bebidas,
            #galeria,
            #reservas {
                padding-left: 25px;
                padding-right: 25px;
            }
            .hero-content {
                padding-left: 25px;
                padding-right: 25px;
            }
            .platos-grid,
            .galeria-grid,
            .valores,
            .fila {
                grid-template-columns: 1fr;
            }
            .plato-info {
                min-height: auto;
            }
            .valor {
                border-right: none;
                border-bottom: 1px solid #333;
            }
            footer {
                flex-direction: column;
                gap: 15px;
                text-align: center;
            }
        }
    </style>
</head>

<body>



    <div id="pantalla-login">

        <div class="login-contenedor">

            <div class="login-logo">
                SABORÉ
                <span>GASTROBAR</span>
            </div>

            <p class="login-subtitulo">
                Bienvenido
            </p>

            <h1>
                INICIAR
                <br>
                <span>SESIÓN.</span>
            </h1>

            <div class="login-linea"></div>

            <p class="login-descripcion">
                Inicia sesión para entrar a SABORÉ Gastrobar.
            </p>

            <form id="loginForm" class="login-form">

                <input type="email" id="correo" placeholder="Correo electrónico" required>

                <input type="password" id="password" placeholder="Contraseña" required>

                <button type="submit" class="login-btn">
                    INICIAR SESIÓN →
                </button>

                <p id="loginMensaje" class="login-mensaje"></p>

            </form>

            <p class="crear-cuenta">

                ¿No tienes una cuenta?

                <a href="#" id="mostrarRegistro">
                    Crear cuenta
                </a>

            </p>

        </div>

    </div>




    <div id="pantalla-registro">

        <div class="registro-contenedor">

            <div class="registro-logo">
                SABORÉ
                <span>GASTROBAR</span>
            </div>

            <p class="registro-subtitulo">
                Regístrate
            </p>

            <h1>
                CREAR
                <br>
                <span>CUENTA.</span>
            </h1>

            <div class="registro-linea"></div>

            <p class="login-descripcion">
                Crea tu cuenta para disfrutar de la experiencia SABORÉ.
            </p>

            <form id="registroForm" class="registro-form">

                <input type="text" id="nombreRegistro" placeholder="Nombre completo" required>

                <input type="email" id="correoRegistro" placeholder="Correo electrónico" required>

                <input type="password" id="passwordRegistro" placeholder="Contraseña" minlength="6" required>

                <input type="password" id="confirmarPassword" placeholder="Confirmar contraseña" minlength="6" required>

                <button type="submit" class="registro-btn">
                    CREAR CUENTA →
                </button>

                <p id="registroMensaje" class="registro-mensaje"></p>

            </form>

            <span class="volver-login" id="volverLogin">
                ← Volver a iniciar sesión
            </span>

        </div>

    </div>




    <div id="contenido-principal">



        <header>

            <nav>

                <a href="#inicio" class="logo">
                    SABORÉ
                    <span>GASTROBAR</span>
                </a>

                <ul class="menu">

                    <li>
                        <a href="#inicio">INICIO</a>
                    </li>

                    <li>
                        <a href="#conocenos">CONÓCENOS</a>
                    </li>

                    <li>
                        <a href="#menu">MENÚ</a>
                    </li>

                    <li>
                        <a href="#bebidas">BEBIDAS</a>
                    </li>

                    <li>
                        <a href="#galeria">GALERÍA</a>
                    </li>

                    <li>
                        <a href="#reservas">RESERVAS</a>
                    </li>

                </ul>

                <div class="sociales">

                    <a href="https://www.instagram.com/" target="_blank" rel="noopener noreferrer" class="social" aria-label="Instagram">
                        ◎
                    </a>

                    <a href="https://www.facebook.com/" target="_blank" rel="noopener noreferrer" class="social" aria-label="Facebook">
                        f
                    </a>

                </div>

            </nav>

        </header>




        <section id="inicio">

            <div class="video-fondo">

                <video autoplay muted loop playsinline preload="auto" class="video-continuo">

                    <source
                        src="https://www.image2url.com/r2/default/videos/1788546279890-a940be4f-8bc6-4d76-bc96-a3854c1596ef.mp4"type="video/mp4">

                    Tu navegador no soporta videos.

                </video>

            </div>

            <div class="capa-oscura"></div>

            <div class="hero-content">

                <p class="subtitulo">
                    Cocina que inspira
                </p>

                <h1>
                    BUENA COMIDA,
                    <br>
                    <span>MEJORES</span> MOMENTOS.
                </h1>

                <div class="linea"></div>

                <p>
                    Sabores únicos, ingredientes frescos y la mejor selección de bebidas en un ambiente inolvidable.
                </p>

                <a href="#reservas" class="btn">
                    Reserva tu mesa →
                </a>

                <p class="scroll">
                    ↓ Desliza para descubrir
                </p>

            </div>

        </section>




        <section id="conocenos">

            <div class="conocenos-texto">

                <p class="subtitulo">
                    Nuestra esencia
                </p>

                <h2>
                    PASIÓN POR LA
                    <br> BUENA COMIDA
                    <br> Y LOS DETALLES.
                </h2>

                <div class="linea"></div>

                <p>
                    Somos un gastrobar que combina el arte de la cocina con una experiencia pensada para compartir. Cada plato, bebida y momento ha sido creado para convertirse en un recuerdo.
                </p>

                <a href="#inicio" class="btn">
                    volver al inicio →
                </a>

            </div>


            <div class="conocenos-video">

                <video autoplay muted loop playsinline preload="auto" class="video-continuo">

                    <source
                        src="https://www.image2url.com/r2/default/videos/1788546438156-fd1a7d2f-aeb5-4163-a5e8-92f182285399.mp4"type="video/mp4">

                    Tu navegador no soporta videos.

                </video>

            </div>




            <div class="mision-vision">

                <article class="mision">

                    <h3>
                        MISIÓN
                    </h3>

                    <p>
                        Brindar una experiencia gastronómica única, ofreciendo platos de alta calidad, bebidas cuidadosamente seleccionadas y un servicio cercano, en un ambiente acogedor donde cada visita se convierta en un momento especial para compartir y disfrutar.
                    </p>

                </article>


                <article class="vision">

                    <h3>
                        VISIÓN
                    </h3>

                    <p>
                        Ser reconocido como uno de los gastrobares referentes de Ibagué, destacándonos por nuestra creatividad gastronómica, calidad, innovación y excelente servicio, creando experiencias memorables que conquisten a nuestros clientes y nos conviertan en su lugar
                        favorito para disfrutar.
                    </p>

                </article>

            </div>




            <div class="valores">

                <article class="valor">

                    <div class="icono">🌿</div>

                    <h3>
                        INGREDIENTES FRESCOS
                    </h3>

                    <p>
                        Seleccionados cuidadosamente.
                    </p>

                </article>


                <article class="valor">

                    <div class="icono">♨</div>

                    <h3>
                        COCINA DE AUTOR
                    </h3>

                    <p>
                        Creatividad en cada plato.
                    </p>

                </article>


                <article class="valor">

                    <div class="icono">♡</div>

                    <h3>
                        HECHO CON PASIÓN
                    </h3>

                    <p>
                        Una experiencia para recordar.
                    </p>

                </article>


                <article class="valor">

                    <div class="icono">◉</div>

                    <h3>
                        EXPERIENCIAS
                    </h3>

                    <p>
                        Momentos únicos para compartir.
                    </p>

                </article>

            </div>

        </section>




        <section id="menu">

            <div class="menu-superior">

                <div class="menu-intro">

                    <p class="subtitulo">
                        Nuestro menú
                    </p>

                    <h2>
                        CREATIVO,
                        <br> Y
                        <span>APASIONANTE.</span>
                    </h2>

                    <div class="linea"></div>

                    <p>
                        Una fusión de sabores del mundo con el toque único de nuestra cocina.
                    </p>

                    <br>

                    <a href="#galeria" class="btn">
                        ver nuestra galeria →
                    </a>

                </div>


                <div class="menu-imagen">

                    <video autoplay muted loop playsinline preload="auto" class="video-continuo">

                        <source
                            src="https://www.image2url.com/r2/default/videos/1788546595489-3385a09a-1661-4c29-992d-7849e7145b5a.mp4"type="video/mp4">

                        Tu navegador no soporta videos.

                    </video>

                </div>

            </div>




            <div class="platos-grid">

                <article class="plato">

                    <div class="plato-imagen">

                        <img src="https://www.image2url.com/r2/default/files/1788546841533-d168f066-a6a5-432b-97de-ffd533619ebb.jpg" alt="Pulpo a la parrilla">

                    </div>

                    <div class="plato-info">

                        <h3>
                            Pulpo al grill
                        </h3>

                        <p>
                            Pulpo, crema de papa y vegetales frescos.
                        </p>

                        <span class="precio">
                            $45.000
                        </span>

                    </div>

                </article>


                <article class="plato">

                    <div class="plato-imagen">

                        <img src="https://www.image2url.com/r2/default/files/1788547078741-d238c67d-cd69-4559-8088-7483c5dd0da7.webp" alt="Pizza artesanal">

                    </div>

                    <div class="plato-info">

                        <h3>
                            Pizza artesanal
                        </h3>

                        <p>
                            Masa artesanal y productos frescos.
                        </p>

                        <span class="precio">
                            $32.000
                        </span>

                    </div>

                </article>


                <article class="plato">

                    <div class="plato-imagen">

                        <img src="https://www.image2url.com/r2/default/files/1788547413802-ef4d8d08-221e-4dd8-9d69-4fee4941edbb.jpg" alt="Hamburguesa especial">

                    </div>

                    <div class="plato-info">

                        <h3>
                            Hamburguesa especial
                        </h3>

                        <p>
                            Carne premium, queso y vegetales frescos.
                        </p>

                        <span class="precio">
                            $28.000
                        </span>

                    </div>

                </article>


                <article class="plato">

                    <div class="plato-imagen">

                        <img src="https://www.image2url.com/r2/default/files/1788547485171-54784c8e-1b11-4611-9f08-8f6c70455b1b.jpg" alt="Pasta de la casa">

                    </div>

                    <div class="plato-info">

                        <h3>
                            Pasta de la casa
                        </h3>

                        <p>
                            Pasta fresca con salsa especial.
                        </p>

                        <span class="precio">
                            $30.000
                        </span>

                    </div>

                </article>

            </div>

        </section>




        <section id="bebidas">

            <div class="bebidas-fondo">

                <video autoplay muted loop playsinline preload="auto" class="video-continuo">

                    <source
                        src="https://www.image2url.com/r2/default/videos/1788546708671-253233cb-8b5d-4f96-ad71-2d7f9c7df6f1.mp4"type="video/mp4">

                    Tu navegador no soporta videos.

                </video>

            </div>

            <div class="bebidas-capa"></div>


            <div class="bebidas-texto">

                <p class="subtitulo">
                    Bar & Cocktails
                </p>

                <h2>
                    BRINDEMOS POR
                    <br>
                    <span>BUENOS MOMENTOS.</span>
                </h2>

                <div class="linea"></div>

                <p>
                    Descubre nuestra selección de cócteles, vinos y bebidas preparadas para acompañar cada experiencia.
                </p>

                <a href="#reservas" class="btn">
                    Reservar una mesa →
                </a>

            </div>


            <div class="bebidas-grid">

                <article class="categoria-bebida">

                    <h3>
                        CÓCTELES
                    </h3>

                    <ul>
                        <li>Mojito clásico</li>
                        <li>Margarita</li>
                        <li>Piña Colada</li>
                        <li>Gin Tonic</li>
                        <li>Negroni</li>
                    </ul>

                </article>


                <article class="categoria-bebida">

                    <h3>
                        VINOS
                    </h3>

                    <ul>
                        <li>Vino tinto</li>
                        <li>Vino blanco</li>
                        <li>Vino rosado</li>
                        <li>Vino de la casa</li>
                        <li>Selección premium</li>
                    </ul>

                </article>


                <article class="categoria-bebida">

                    <h3>
                        REFRESCOS
                    </h3>

                    <ul>
                        <li>Limonada natural</li>
                        <li>Limonada de coco</li>
                        <li>Jugos naturales</li>
                        <li>Gaseosas</li>
                        <li>Agua mineral</li>
                    </ul>

                </article>

            </div>

        </section>




        <section id="galeria">

            <div class="galeria-texto">

                <p class="subtitulo">
                    Nuestra galería
                </p>

                <h2>
                    MOMENTOS QUE
                    <br>
                    <span>INSPIRAN.</span>
                </h2>

                <div class="linea"></div>

                <p>
                    Conoce algunos de nuestros platos, bebidas. Una experiencia diseñada para disfrutar con todos los sentidos.
                </p>

                <div class="galeria-filtros">

                    <span class="filtro activo">
                        TODOS
                    </span>

                    <span class="filtro">
                        PLATOS
                    </span>

                    <span class="filtro">
                        BEBIDAS
                    </span>

                    <span class="filtro">
                        ESPACIO
                    </span>

                </div>

            </div>


            <div class="galeria-grid">

                <div class="foto">

                    <img src="https://cdn.phototourl.com/free/2026-09-04-5ce6aff5-5b2a-4cab-bd8e-8c57ec7857e3.webp" alt="Mojito">

                </div>

                <div class="foto">

                    <img src="https://cdn.phototourl.com/free/2026-09-04-392adb9e-4720-4ebc-9b83-2f45f36eaf55.webp" alt="Cócteles">

                </div>

                <div class="foto">

                    <img src="https://cdn.phototourl.com/free/2026-09-04-f15c20fc-63f0-4316-898a-3da558dbfd09.webp" alt="Hamburguesa">

                </div>

                <div class="foto">

                    <img src="https://cdn.phototourl.com/free/2026-09-04-3a75b6b7-5b88-49e6-ade0-59bfd66f1acd.jpg" alt="Interior del gastrobar">

                </div>

                <div class="foto">

                    <img src="https://cdn.phototourl.com/free/2026-09-04-5423708f-4aa9-4aba-a534-6b51b99aadb3.jpg" alt="Cóctel">

                </div>

                <div class="foto">

                    <img src="https://user29836.na.imgto.link/public/20260905/image.avif" alt="Pulpo al grill">

                </div>

            </div>

        </section>




        <section id="reservas">

            <div class="reservas-superior">

                <div class="reservas-texto">

                    <p class="subtitulo">
                        Reserva tu experiencia
                    </p>

                    <h2>
                        TU MESA TE
                        <br>
                        <span>ESPERA.</span>
                    </h2>

                    <div class="linea"></div>

                    <p>
                        Reserva tu mesa y disfruta de una experiencia gastronómica única en SABORÉ Gastrobar.
                    </p>

                </div>


                <form id="reservaForm">

                    <div class="fila">

                        <input type="text" placeholder="Nombre" required>

                        <input type="tel" placeholder="Teléfono" required>

                    </div>


                    <div class="fila">

                        <input type="date" required>

                        <input type="time" required>

                    </div>


                    <select required>

                        <option value="">
                            Número de personas
                        </option>

                        <option value="1">
                            1 persona
                        </option>

                        <option value="2">
                            2 personas
                        </option>

                        <option value="3">
                            3 personas
                        </option>

                        <option value="4">
                            4 personas
                        </option>

                        <option value="5">
                            5 personas
                        </option>

                        <option value="6">
                            6 personas
                        </option>

                        <option value="7">
                            7 personas
                        </option>

                        <option value="8">
                            8 personas
                        </option>

                    </select>


                    <button type="submit" class="btn form-btn">
                        Confirmar reserva →
                    </button>

                </form>

            </div>




            <div class="contacto-info">

                <div>

                    <h3>
                        UBICACIÓN
                    </h3>

                    <p>
                        Ibagué, Tolima
                        <br> Colombia
                    </p>

                </div>


                <div>

                    <h3>
                        HORARIOS
                    </h3>

                    <p>
                        Lunes - Domingo
                        <br> 12:00 PM - 11:00 PM
                    </p>

                </div>


                <div>

                    <h3>
                        CONTACTO
                    </h3>

                    <p>
                        +57 3042219085
                        <br> reservas@saboregastrobar.com
                    </p>

                </div>

            </div>

        </section>




        <footer>

            <p>
                © 2026 SABORÉ GASTROBAR.
            </p>

            <p>
                BUENA COMIDA · MEJORES MOMENTOS
            </p>

        </footer>


        <!-- BOTÓN CERRAR SESIÓN -->

        <button id="cerrarSesion" class="cerrar-sesion">
            Cerrar sesión
        </button>

    </div>




    <script>
        document.addEventListener("DOMContentLoaded", function() {



            const loginForm =
                document.getElementById("loginForm");

            const pantallaLogin =
                document.getElementById("pantalla-login");

            const pantallaRegistro =
                document.getElementById("pantalla-registro");

            const contenidoPrincipal =
                document.getElementById("contenido-principal");

            const loginMensaje =
                document.getElementById("loginMensaje");

            const registroForm =
                document.getElementById("registroForm");

            const registroMensaje =
                document.getElementById("registroMensaje");

            const mostrarRegistro =
                document.getElementById("mostrarRegistro");

            const volverLogin =
                document.getElementById("volverLogin");

            const cerrarSesion =
                document.getElementById("cerrarSesion");




            document.body.style.overflow = "hidden";




            const videos =
                document.querySelectorAll("video");




            function prepararVideos() {

                videos.forEach(function(video) {

                    video.autoplay = true;
                    video.loop = true;
                    video.muted = true;
                    video.playsInline = true;

                    video.setAttribute(
                        "autoplay",
                        ""
                    );

                    video.setAttribute(
                        "loop",
                        ""
                    );

                    video.setAttribute(
                        "muted",
                        ""
                    );

                    video.setAttribute(
                        "playsinline",
                        ""
                    );

                    video.setAttribute(
                        "preload",
                        "auto"
                    );

                });

            }




            function reproducirVideos() {

                prepararVideos();

                videos.forEach(function(video) {

                    const promesa =
                        video.play();

                    if (
                        promesa !== undefined
                    ) {

                        promesa.catch(function() {

                            /*
                             El navegador puede bloquear
                             el autoplay temporalmente.
                             Se volverá a intentar.
                            */

                        });

                    }

                });

            }



            videos.forEach(function(video) {

                video.addEventListener(
                    "loadeddata",
                    function() {

                        video.play().catch(
                            function() {}
                        );

                    }
                );


                video.addEventListener(
                    "canplay",
                    function() {

                        video.play().catch(
                            function() {}
                        );

                    }
                );




                video.addEventListener(
                    "ended",
                    function() {

                        video.currentTime = 0;

                        video.play().catch(
                            function() {}
                        );

                    }
                );




                video.addEventListener(
                    "pause",
                    function() {

                        if (
                            contenidoPrincipal.style.display !== "none"
                        ) {

                            setTimeout(
                                function() {

                                    video.play().catch(
                                        function() {}
                                    );

                                },
                                100
                            );

                        }

                    }
                );

            });




            setInterval(
                function() {

                    if (
                        contenidoPrincipal.style.display !== "none"
                    ) {

                        videos.forEach(
                            function(video) {

                                if (
                                    video.paused ||
                                    video.ended
                                ) {

                                    if (
                                        video.ended
                                    ) {

                                        video.currentTime = 0;

                                    }

                                    video.play().catch(
                                        function() {}
                                    );

                                }

                            }
                        );

                    }

                },
                500
            );




            document.addEventListener(
                "visibilitychange",
                function() {

                    if (!document.hidden) {

                        reproducirVideos();

                    }

                }
            );




            window.addEventListener(
                "pageshow",
                function() {

                    setTimeout(
                        function() {

                            reproducirVideos();

                        },
                        100
                    );

                    setTimeout(
                        function() {

                            reproducirVideos();

                        },
                        1000
                    );

                }
            );



            window.addEventListener(
                "focus",
                function() {

                    reproducirVideos();

                }
            );




            mostrarRegistro.addEventListener(
                "click",
                function(event) {

                    event.preventDefault();

                    pantallaLogin.style.display =
                        "none";

                    pantallaRegistro.style.display =
                        "flex";

                    loginMensaje.textContent =
                        "";

                }
            );




            volverLogin.addEventListener(
                "click",
                function() {

                    pantallaRegistro.style.display =
                        "none";

                    pantallaLogin.style.display =
                        "flex";

                    registroForm.reset();

                    registroMensaje.textContent =
                        "";

                }
            );



            registroForm.addEventListener(
                "submit",
                function(event) {

                    event.preventDefault();


                    const nombre =
                        document
                        .getElementById(
                            "nombreRegistro"
                        )
                        .value
                        .trim();


                    const correo =
                        document
                        .getElementById(
                            "correoRegistro"
                        )
                        .value
                        .trim();


                    const password =
                        document
                        .getElementById(
                            "passwordRegistro"
                        )
                        .value
                        .trim();


                    const confirmar =
                        document
                        .getElementById(
                            "confirmarPassword"
                        )
                        .value
                        .trim();


                    if (
                        nombre === "" ||
                        correo === "" ||
                        password === "" ||
                        confirmar === ""
                    ) {

                        registroMensaje.style.color =
                            "#d9534f";

                        registroMensaje.textContent =
                            "Por favor, completa todos los campos.";

                        return;

                    }


                    if (
                        password.length < 6
                    ) {

                        registroMensaje.style.color =
                            "#d9534f";

                        registroMensaje.textContent =
                            "La contraseña debe tener mínimo 6 caracteres.";

                        return;

                    }


                    if (
                        password !== confirmar
                    ) {

                        registroMensaje.style.color =
                            "#d9534f";

                        registroMensaje.textContent =
                            "Las contraseñas no coinciden.";

                        return;

                    }


                    localStorage.setItem(
                        "saboréNombre",
                        nombre
                    );

                    localStorage.setItem(
                        "saboréCorreo",
                        correo
                    );

                    localStorage.setItem(
                        "saboréPassword",
                        password
                    );


                    registroMensaje.style.color =
                        "#c99b50";

                    registroMensaje.textContent =
                        "¡CUENTA CREADA CORRECTAMENTE!";


                    setTimeout(
                        function() {

                            pantallaRegistro.style.display =
                                "none";

                            pantallaLogin.style.display =
                                "flex";

                            document.getElementById(
                                "correo"
                            ).value = correo;

                            document.getElementById(
                                "password"
                            ).value = "";

                            registroForm.reset();

                            registroMensaje.textContent =
                                "";

                            loginMensaje.style.color =
                                "#c99b50";

                            loginMensaje.textContent =
                                "Cuenta creada. Ahora inicia sesión.";

                        },
                        1200
                    );

                }
            );



            loginForm.addEventListener(
                "submit",
                function(event) {

                    event.preventDefault();


                    const correo =
                        document
                        .getElementById("correo")
                        .value
                        .trim();


                    const password =
                        document
                        .getElementById("password")
                        .value
                        .trim();


                    if (
                        correo === "" ||
                        password === ""
                    ) {

                        loginMensaje.style.color =
                            "#d9534f";

                        loginMensaje.textContent =
                            "Por favor, completa todos los campos.";

                        return;

                    }


                    const correoGuardado =
                        localStorage.getItem(
                            "saboréCorreo"
                        );


                    const passwordGuardada =
                        localStorage.getItem(
                            "saboréPassword"
                        );


                    if (
                        correoGuardado &&
                        passwordGuardada
                    ) {

                        if (
                            correo !== correoGuardado ||
                            password !== passwordGuardada
                        ) {

                            loginMensaje.style.color =
                                "#d9534f";

                            loginMensaje.textContent =
                                "Correo o contraseña incorrectos.";

                            return;

                        }

                    }


                    loginMensaje.style.color =
                        "#c99b50";

                    loginMensaje.textContent =
                        "Acceso correcto. Bienvenido a SABORÉ.";


                    setTimeout(
                        function() {

                            pantallaLogin.style.display =
                                "none";

                            contenidoPrincipal.style.display =
                                "block";

                            document.body.style.overflow =
                                "auto";

                            window.scrollTo(
                                0,
                                0
                            );




                            prepararVideos();

                            reproducirVideos();

                        },
                        700
                    );

                }
            );




            cerrarSesion.addEventListener(
                "click",
                function() {

                    contenidoPrincipal.style.display =
                        "none";

                    pantallaLogin.style.display =
                        "flex";

                    loginForm.reset();

                    loginMensaje.textContent =
                        "";

                    window.scrollTo(
                        0,
                        0
                    );

                    document.body.style.overflow =
                        "hidden";

                }
            );




            const enlacesMenu =
                document.querySelectorAll(
                    '.menu a[href^="#"]'
                );


            enlacesMenu.forEach(
                function(enlace) {

                    enlace.addEventListener(
                        "click",
                        function() {

                            /*
                             No se pausa ningún video.
                             Solamente se intenta
                             mantenerlos reproduciendo.
                            */

                            setTimeout(
                                function() {

                                    reproducirVideos();

                                },
                                100
                            );

                        }
                    );

                }
            );



            const filtros =
                document.querySelectorAll(
                    ".filtro"
                );


            filtros.forEach(
                function(filtro) {

                    filtro.addEventListener(
                        "click",
                        function() {

                            filtros.forEach(
                                function(item) {

                                    item.classList.remove(
                                        "activo"
                                    );

                                }
                            );

                            filtro.classList.add(
                                "activo"
                            );

                        }
                    );

                }
            );




            const formularioReserva =
                document.getElementById(
                    "reservaForm"
                );


            formularioReserva.addEventListener(
                "submit",
                function(event) {

                    event.preventDefault();

                    alert(
                        "¡SOLICITUD ENVIADA!\n\n" +
                        "Tu reserva ha sido recibida correctamente.\n" +
                        "Gracias por reservar en SABORÉ Gastrobar."
                    );

                    formularioReserva.reset();

                }
            );



            prepararVideos();

            reproducirVideos();



            setTimeout(
                function() {

                    reproducirVideos();

                },
                500
            );




            setTimeout(
                function() {

                    reproducirVideos();

                },
                1500
            );


        });
    </script>

</body>

</html>
