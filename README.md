# Transcripciones
Descripción


Este script utiliza el modelo Whisper de OpenAI para transcribir un archivo de audio en formato MP3 y generar un archivo de subtítulos en formato SRT. Además, incluye una barra de progreso para mostrar el porcentaje completado durante la transcripción, lo que facilita el seguimiento del progreso en tiempo real.

Características

Transcribe audio a texto utilizando el modelo Whisper.

Genera un archivo de subtítulos en formato SRT con marcas de tiempo.

Muestra una barra de progreso con la biblioteca tqdm.

Optimizado para ejecutarse en Google Colab con soporte de GPU.

Requisitos

Python 3.8+

Bibliotecas necesarias:

openai-whisper

tqdm

ffmpeg (para procesar y convertir el audio si es necesario)

Instalación

Sigue los pasos a continuación para configurar el entorno:

Instalar las bibliotecas necesarias:

!pip install openai-whisper tqdm

Verificar el soporte de GPU en Google Colab:
Asegúrate de que el entorno de ejecución esté configurado para usar GPU:

Ve a Entorno de ejecución > Cambiar tipo de entorno de ejecución.

Selecciona GPU como hardware acelerador.

Verifica la GPU ejecutando:

!nvidia-smi

Uso

Carga de audio:

Sube tu archivo MP3 al entorno de Google Colab o asegúrate de que esté disponible en tu sistema.

Ejecuta el script:
El script transcriba el archivo y genera un archivo SRT llamado output.srt.

Revisar resultados:

La barra de progreso te mostrará cuánto del archivo ha sido procesado.

Los resultados finales estarán disponibles en output.srt.

Cómo funciona el script

Carga del modelo Whisper:
El modelo base de Whisper se carga para equilibrar velocidad y precisión.

Transcripción del archivo:
Utiliza la función transcribe() para dividir el audio en segmentos con marcas de tiempo y texto transcrito.

Generación del archivo SRT:
Cada segmento se formatea en estilo SRT con marcas de tiempo en formato hh:mm:ss,msmsms.

Barra de progreso:
Con tqdm, se muestra el avance en tiempo real, indicando el número de segmentos procesados y el porcentaje completado.

Ejemplo

Un archivo de audio cargado como /content/WhatsApp-Ptt-2024-11-11-at-7.12.03-PM.mp3 generará un archivo de subtítulos con este formato:

1
00:00:00,000 --> 00:00:05,000
Hola, esto es un ejemplo de transcripción.

2
00:00:05,001 --> 00:00:10,000
Otro segmento de texto transcrito.

Limitaciones

La precisión depende del modelo seleccionado. Modelos más ligeros (e.g., tiny) son rápidos pero menos precisos.

Archivos largos pueden tardar más tiempo en procesarse.

Autor

Este script fue desarrollado por Sebastián Vilca.

Licencia

Este proyecto se proporciona bajo la Licencia MIT. Puedes usarlo y modificarlo libremente.

