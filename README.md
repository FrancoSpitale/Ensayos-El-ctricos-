El código implementa una aplicación gráfica en Python utilizando PyQt5 para gestionar un sistema de pruebas eléctricas automatizado. La aplicación permite realizar varios ensayos eléctricos controlados por un Arduino conectado al sistema. Los resultados se registran en un archivo Excel.

Descripción General del Código
Interfaz Gráfica:

Botones de Ensayos: Seis botones que representan diferentes pruebas eléctricas como:
Puesta a Tierra
Corriente de Fuga
Resistencia de Aislación
Rigidez Dieléctrica
Corriente
Potencia
Barras de Progreso: Muestran el avance del ensayo.
Pantallas LCD: Visualizan el valor medido para cada ensayo.
Botones de Control:
"Iniciar Ensayos": Ejecuta las pruebas seleccionadas.
"Guardar y Salir": Guarda los resultados en un archivo Excel y cierra la aplicación.
Conexión con Arduino:

Se conecta a través del puerto serie para enviar comandos y recibir datos de las pruebas.
Cada prueba corresponde a un comando que el Arduino interpreta y responde con valores medidos.
Gestión de Ensayos:

Cada ensayo tiene límites predefinidos (mínimo y máximo) almacenados en un diccionario.
Durante el ensayo:
Se compara el valor recibido del Arduino con los límites para determinar si la prueba fue aprobada o reprobada.
El progreso y los valores medidos se reflejan en la interfaz gráfica.
Registro de Resultados:

Los valores medidos se guardan en un archivo Excel (contacts.xlsx), junto con la fecha y hora de ejecución.
Detalles Clave
Configuración Inicial:

Variables como límites de ensayos y puerto del Arduino son inicializadas en initialize_data.
Interactividad:

Los botones permiten activar/desactivar los ensayos y reflejan su estado visualmente cambiando el color.
Flujo de Trabajo:

Los ensayos se realizan secuencialmente en función de los botones seleccionados.
Los valores son leídos en tiempo real del Arduino y se procesan para mostrar resultados inmediatos en la interfaz.
Manejo de Errores:

Se capturan excepciones al conectar con el Arduino o al guardar los datos en el Excel para informar al usuario.
