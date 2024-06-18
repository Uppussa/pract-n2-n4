* Implementación del Sistema de Autenticación
Este documento describe los pasos seguidos para implementar el sistema de autenticación utilizando JSON Web Tokens (JWT) en una aplicación Express.

Pasos Implementados
1. Configuración Básica
Primero, se configura el servidor Express y se define una ruta básica de bienvenida.
2. Ruta de Login
Se define una ruta /api/login que genera un token JWT al autenticar al usuario.
3. Middleware de Verificación de Token
Se implementa una función verifyToken que verifica la presencia del token en los encabezados de autorización.
4. Ruta Protegida
Se define una ruta protegida /api/posts que solo permite acceso si el token es válido.
5. Configuración del Servidor
Se inicia el servidor en el puerto 5000.

Manejo de la Expiración de Tokens
El token JWT generado en la ruta de login tiene una duración de 30 minutos (expiresIn: '30m'). Esto asegura que el token sea válido solo por un tiempo limitado, mejorando la seguridad.

Ruta de Verificación de Tokens
La verificación del token se realiza en la ruta /api/posts, donde el middleware verifyToken extrae el token del encabezado de autorización y jwt.verify valida el token.

Consideraciones de Seguridad
1. Secreto del Token: Utilizamos una clave secreta ('secretkey') para firmar los tokens. En una aplicación real, esta clave debería ser más compleja y almacenarse de forma segura, como en una variable de entorno.
2. Expiración del Token: Los tokens tienen una expiración definida para minimizar el riesgo en caso de que un token sea comprometido.
3. Uso de HTTPS: En producción, se debe utilizar HTTPS para asegurar la transmisión de datos.


Esta implementación proporciona una base sólida para la autenticación en una aplicación Node.js utilizando JWT.