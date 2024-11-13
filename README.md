# Whisper Transcription Script

## Autor
Este script fue desarrollado por **Sebastián Vilca**.

## Descripción
Este script utiliza el modelo Whisper de OpenAI para transcribir un archivo de audio en formato MP3 y generar un archivo de subtítulos en formato SRT. Además, incluye una barra de progreso para mostrar el porcentaje completado durante la transcripción, lo que facilita el seguimiento del progreso en tiempo real.

## Características
- Transcribe audio a texto utilizando el modelo Whisper.
- Genera un archivo de subtítulos en formato SRT con marcas de tiempo.
- Muestra una barra de progreso con la biblioteca `tqdm`.
- Optimizado para ejecutarse en Google Colab.

## Requisitos
1. **Python 3.8+**
2. Bibliotecas necesarias:
   - `openai-whisper`
   - `tqdm`
   - `ffmpeg`

## Instalación
Sigue los pasos a continuación para configurar el entorno:

1. **Instalar las bibliotecas necesarias**:
   ```bash
   !pip install openai-whisper tqdm
   ```

## Uso
1. **Carga de audio**:
   - Sube tu archivo MP3 al entorno de Google Colab o asegúrate de que esté disponible en tu sistema.

2. **Ejecuta el script**:
   El script transcriba el archivo y genera un archivo SRT llamado `Transcripción.srt`.

3. **Revisar resultados**:
   - La barra de progreso te mostrará cuánto del archivo ha sido procesado.
   - Los resultados finales estarán disponibles en `Transcripción.srt`.

## Cómo funciona el script
1. **Carga del modelo Whisper**:
   El modelo `base` de Whisper se carga para equilibrar velocidad y precisión.

2. **Transcripción del archivo**:
   Utiliza la función `transcribe()` para dividir el audio en segmentos con marcas de tiempo y texto transcrito.

3. **Generación del archivo SRT**:
   Cada segmento se formatea en estilo SRT con marcas de tiempo en formato `hh:mm:ss,msmsms`.

4. **Barra de progreso**:
   Con `tqdm`, se muestra el avance en tiempo real, indicando el número de segmentos procesados y el porcentaje completado.

## Ejemplo
Un archivo de audio cargado como `/content/audio.mp3` generará un archivo de subtítulos con este formato:

```
1
00:00:00,000 --> 00:00:05,000
Hola, esto es un ejemplo de transcripción.

2
00:00:05,001 --> 00:00:10,000
Otro segmento de texto transcrito.
```



