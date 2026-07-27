He construido un buscador de alojamientos con IA que analiza, puntúa y detecta posibles estafas en segundos. 🏨🤖

La idea era clara: no quería solo buscar hoteles en un listado interminable. Quería una IA que evaluara las opciones según mis verdaderas prioridades y que actuara como filtro de seguridad si detectaba patrones sospechosos en precios o descripciones.
![Arquitectura del Workflow](WORKFLOW.JPG)
He desplegado una arquitectura en n8n conectada a Google Hotels (vía SerpAPI), Gemini 2.5 Flash y Gmail con este flujo arquitectónico:

✅ Formulario nativo multicanal: El usuario introduce destino, fechas y su presupuesto. Un código JS interno valida al instante las fechas y calcula las pernoctaciones.
![Formulario Página 1](FORMULARI.JPG)
![Formulario Página 2](PAGINA_2.JPG)

✅ Puntuación dinámica (0 al 10): Adaptada 100% a los criterios del usuario (ubicación, precio, wifi, etc.), ponderando matemáticamente las variables en el prompt de la IA.
✅ "Coeficiente de estafa": Calculado algorítmicamente si la oferta tiene precios sospechosamente bajos, valoraciones de 4.8 con apenas 15 reseñas o ausencia total de amenidades.

![Email de Resultados Obtenidos (1)](EMAIL1.JPG)
![Email de Resultados Obtenidos (2)](EMAIL2.JPG)

✅ Generación de interfaz sin frontend: Un nodo de código compila los datos procesados en una tabla HTML con estilos limpios y etiquetas de colores (verde, naranja o rojo según el riesgo) que se entrega directamente en pantalla y por email.

📈 Evolución continua y aprendizaje transversal:
Quienes me conocéis sabéis que me gusta cruzar disciplinas: ingeniería informática, innovación, salud y deporte, e incluso economía y redes sociales.

Este verano estoy dedicando tiempo a dominar la automatización de procesos (BPA). Es genial comparar la evolución técnica entre mis últimos desarrollos:
🔸 Proyecto 1 (ERP & Facturas): Gmail (Trigger) ➔ Google Sheets (BBDD) ➔ Looker Studio (Dashboard BI).
🔸 Proyecto 2 (Buscador IA): Formulario Web (Trigger) ➔ SerpAPI & Gemini IA (Motor de análisis) ➔ Gmail & Custom HTML (Output visual).

Sigo aprendiendo sin prisa, con el objetivo de mantener mis habilidades actualizadas para el mercado del presente y del futuro. Espero que esto inspire a cualquier estudiante, autónomo o profesional a mantener una curiosidad incansable y a seguir aprendiendo día tras día, se comparta o no con el mundo. 💡

(Adjunto en las imágenes esquemas del flujo y fragmentos de la lógica que hace funcionar el algoritmo en el backend).
![Arquitectura del Workflow](PARSE_SORT.JPG)

#n8n #IA #Automation #SoftwareEngineering #Innovation #BPA
> 🔒 **Nota sobre privacidad y código fuente:** 
> Por motivos de seguridad, privacidad y protección de infraestructura (credenciales, endpoints y estructuración de datos), he decidido no adjuntar el archivo bruto `.json` del flujo en este repositorio público. 
> 
> No obstante, es relevante señalar que en plataformas como n8n, toda la arquitectura visual que se muestra en las imágenes (los nodos, el enrutamiento condicional y los scripts en JS/Python) se compila, serializa y almacena de forma nativa en un archivo **JSON**. Este formato actúa como la verdadera columna vertebral y alternativa agnóstica de la herramienta, permitiendo tratar el "no-code/low-code" como código real que se puede versionar, replicar y auditar de manera profesional.
