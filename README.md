# GuardianDelClimaGIT
--- Descripcion de GuardiánClima ITBA ---
Es una app de consola para:
- Consultar el clima
- Ver historial de consultas
- Generar estadísticas globales
- Recibir consejos de vestimenta con IA
          Usala para obtener informacion facil y rapido y facilitar tus decisiones en el dia a dia!!! 

USO DE CADA OPCIÓN DEL MENÚ Y FLUJO DE LA APLICACIÓN

FLUJO GENERAL:
1. Al iniciar la aplicación, se muestra el Menú de Acceso:
   - Opción 1: Iniciar Sesión
     * El usuario ingresa su nombre y contraseña.
     * Se valida contra el archivo usuarios_simulados.csv.
     * Si es correcto, se accede al Menú Principal.
     * Si es incorrecto, se informa y se permite reintentar.

   - Opción 2: Registrar Nuevo Usuario
     * Se solicita un nombre de usuario único.
     * Luego se pide una contraseña que cumpla con reglas de seguridad.
     * Si la contraseña no cumple, se informa qué falla y se dan sugerencias.
     * Si es válida, se guarda el usuario en usuarios_simulados.csv.
     * Luego se inicia sesión automáticamente y se accede al Menú Principal.

   - Opción 3: Salir de la Aplicación
     * Finaliza el programa.

MENÚ PRINCIPAL (Post-Login):
1. Opción 1: Consultar Clima Actual y Guardar en Historial Global
   - Se solicita el nombre de una ciudad.
   - Se obtiene información de clima actual desde OpenWeatherMap.
   - Se muestra en consola y se guarda en historial_global.csv.

2. Opción 2: Ver Mi Historial Personal de Consultas por Ciudad
   - Se solicita el nombre de una ciudad.
   - Se muestran todas las consultas previas del usuario logueado para esa ciudad.

3. Opción 3: Estadísticas Globales de Uso y Exportar Historial
   - Se procesan todos los datos de historial_global.csv para mostrar:
     * Ciudad más consultada
     * Número total de consultas
     * Temperatura promedio
   - Estos datos pueden exportarse a Excel o usarse para gráficos.

4. Opción 4: Consejo IA: ¿Cómo Me Visto Hoy?
   - Usa la última consulta de clima del usuario.
   - Envía los datos a Google Gemini para obtener un consejo de vestimenta personalizado.

5. Opción 5: Acerca De...
   - Explica el funcionamiento de la aplicación y sus componentes internos.
   - Muestra información del equipo de desarrollo y nombre del grupo.

6. Opción 6: Cerrar Sesión
   - Vuelve al Menú de Acceso.

FUNCIONALIDADES INTERNAS CLAVE:

1. Creación Simulada de Usuarios y Validación de Contraseñas:
   - El usuario puede registrarse, ingresando nombre y contraseña.
   - La contraseña es validada con criterios de seguridad mínimos (como longitud, uso de mayúsculas, números, etc.).
   - Si la contraseña es débil, el sistema informa qué reglas no cumple y sugiere cómo mejorarla.
   - Si la contraseña es aceptada, se almacena junto al nombre de usuario en el archivo usuarios_simulados.csv.

2. Advertencia de Seguridad:
   - Este sistema es solo educativo. Las contraseñas se almacenan en texto plano, lo cual no es seguro.
   - En sistemas reales se recomienda usar hashing (como bcrypt o argon2) y no guardar contraseñas directamente.

3. Consulta de Clima y Registro Global:
   - Los usuarios pueden consultar el clima de una ciudad usando la API de OpenWeatherMap.
   - Los resultados (usuario, ciudad, temperatura, clima, humedad, viento y fecha/hora) se guardan en historial_global.csv.

4. Estadísticas Globales:
   - A partir del historial_global.csv se calcula:
     - Ciudad más consultada
     - Número total de consultas
     - Temperatura promedio
   - El archivo también se puede exportar a Excel para crear gráficos como:
     - Barras: número de consultas por ciudad
     - Líneas: evolución de temperatura
     - Torta: distribución de condiciones climáticas

5. Consejo de Vestimenta por IA:
   - El sistema puede conectarse a la API de Google Gemini.
   - Envía los datos climáticos para recibir un consejo de vestimenta en lenguaje natural adaptado al clima actual de la ciudad indicada.

Este archivo reúne conocimientos de programación en Python, manejo de archivos CSV, consumo de APIs, validación de datos y uso de IA.

--- CREADORES ---
          Creado por: Agustina Restelli, Tomas Mateo, Hilario Proske, Catalina Yellati, Sol Cornejo.
          Nombre del grupo: METEOROLOGOS
