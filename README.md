<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Redirigiendo a Tarjeta W VISA...</title>
    <style>
        /* Estilo básico para el cuerpo, mínimo para una redirección directa */
        body {
            background-color: #f0f0f0;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            margin: 0;
            font-family: sans-serif; /* Fuente genérica */
            color: #333;
        }
        /* Estilo para el mensaje de JavaScript deshabilitado */
        noscript {
            text-align: center;
            padding: 20px;
            background-color: #fff;
            border-radius: 8px;
            box-shadow: 0 4px 10px rgba(0,0,0,0.1);
        }
        noscript ul {
            list-style: none;
            padding: 0;
            margin-top: 15px;
        }
        noscript li {
            margin-bottom: 10px;
        }
        noscript a {
            display: inline-block;
            padding: 10px 20px;
            background-color: #007bff;
            color: white;
            text-decoration: none;
            border-radius: 5px;
        }
        noscript a:hover {
            background-color: #0056b3;
        }
    </style>
    <script type="text/javascript">
        document.addEventListener('DOMContentLoaded', function() {
            // Obtén la cadena de User-Agent del navegador
            const userAgent = navigator.userAgent || navigator.vendor || window.opera;
            console.log("User-Agent detectado:", userAgent); // **IMPORTANTE PARA DEPURACIÓN**

            // URLs de la aplicación "Tarjeta W VISA"
            const androidAppUrl = "https://play.google.com/store/apps/details?id=pe.com.tarjetaw.android.client.prod";
            const iosAppUrl = "https://apps.apple.com/pe/app/tarjeta-w-visa/id6452389174";

            function redirectToStore(url) {
                console.log("Redirigiendo a:", url);
                window.location.href = url;
            }

            // Lógica de detección y redirección inmediata
            if (/android/i.test(userAgent)) {
                // Detección de Android (insensible a mayúsculas/minúsculas)
                console.log("Detectado: Android");
                redirectToStore(androidAppUrl);
            } else if (/ipad|iphone|ipod/i.test(userAgent) && !window.MSStream) {
                // Detección de iOS (iPad, iPhone, iPod - insensible a mayúsculas/minúsculas)
                // y asegura que no es un navegador de Windows que podría simular un User-Agent de iOS.
                console.log("Detectado: iOS");
                redirectToStore(iosAppUrl);
            } else {
                // Este bloque se ejecuta si el dispositivo no es detectado explícitamente como Android o iOS.
                // Esto incluye navegadores de escritorio o dispositivos móviles con User-Agents inusuales.
                // Como quieres una redirección directa sin landing page, el mejor fallback
                // es redirigir a la App Store de iOS, ya que es un destino más general
                // para usuarios no Android o de escritorio que buscan una app móvil.
                console.log("Detectado: Dispositivo no Android/iOS o User-Agent desconocido. Redirigiendo al App Store de iOS como fallback.");
                redirectToStore(iosAppUrl); // Fallback a la tienda de iOS
            }
        });
    </script>
</head>
<body>
    <noscript>
        <p>Tu navegador no tiene JavaScript habilitado. Por favor, haz clic en el enlace para descargar la aplicación:</p>
        <ul>
            <li><a href="https://play.google.com/store/apps/details?id=pe.com.tarjetaw.android.client.prod" target="_blank">Descargar para Android</a></li>
            <li><a href="https://apps.apple.com/pe/app/tarjeta-w-visa/id6452389174" target="_blank">Descargar para iOS</a></li>
        </ul>
    </noscript>
</body>
</html>
