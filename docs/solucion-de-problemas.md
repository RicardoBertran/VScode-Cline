# Solución de problemas

[← Volver al tutorial](../README.md)

> 🔎 Cambia una cosa cada vez y repite una prueba corta. Así sabrás qué resolvió el problema.

## No conecta o aparece «connection refused»

1. Abre el servidor y confirma que su API está encendida.
2. Comprueba el puerto que muestra; compáralo con Base URL.
3. Espera a que el modelo esté cargado.
4. Comprueba si VS Code está ejecutándose en otro entorno, como WSL, un contenedor o un equipo remoto: allí `localhost` puede ser otro lugar.
5. Si sigue fallando, revisa el mensaje del servidor y la conexión. No desactives el cortafuegos como primera solución.

## Aparece `404 Not Found`

Revisa que has seleccionado OpenAI Compatible y que la dirección corresponde a la API. Para los ejemplos del tutorial, la base termina en `/v1`. Evita añadir `/chat/completions` o duplicar `/v1`. Si tu servidor utiliza otra ruta, sigue su documentación.

## Aparece `401` o «Invalid API Key»

Una clave dummy solo funciona cuando el servidor no valida claves. Si has activado autenticación, usa la clave real. Comprueba espacios al copiarla y no la incluyas en capturas ni en GitHub.

## Aparece «Model not found»

El nombre del archivo del modelo y su alias pueden diferir. Revisa la lista de modelos del servidor o su endpoint `/v1/models`. Copia exactamente su `id` en Model ID. No uses automáticamente el identificador de Hugging Face como alias local.

## Responde, pero no trabaja sobre la carpeta

Comprueba que la carpeta correcta está abierta y que has guardado el archivo de prueba. Si estás en Plan, pasa al modo que permite ejecutar acciones. Revisa las solicitudes de aprobación. Observa si realmente utiliza la herramienta de lectura.

Si aparecen errores de llamadas a herramientas, tu combinación de modelo, plantilla y servidor puede necesitar ajustes. Una API que responde a mensajes simples no garantiza que un agente pueda usar herramientas. Consulta la documentación de esas versiones y no actives opciones al azar.

## Tarda mucho, repite texto o se queda sin memoria

Mira los registros del servidor. Una primera carga lenta y un error de memoria no son lo mismo. Prueba una petición breve y una tarea nueva. Reduce el contexto si el servidor informa de falta de memoria, o utiliza un modelo que ya sepas que cabe en tu equipo. No fijes un contexto mayor que el admitido por la configuración real.

## Funciona en Plan, pero falla en Act

Si Cline tiene proveedores separados por modo, revisa ambos: Base URL, clave y Model ID. Guarda y repite la prueba corta en el modo que fallaba.

## La app no encuentra el modelo

Pega `Qwen/Qwen3.6-35B-A3B` completo, sin espacios adicionales. Abre su [ficha oficial](https://huggingface.co/Qwen/Qwen3.6-35B-A3B) en el navegador. Si tampoco abre, comprueba Internet. Si la ficha abre y la app falla, pide a Cline que revise la consulta concreta y el error del navegador.

## La app devuelve menos presets, o demasiados

Compara la ficha actual con las tarjetas. `generation_config.json` puede aparecer como resultado aparte: no equivale a un preset con uso específico. Si se pierde una recomendación, pide revisar el extractor. Si se duplica, pide corregir la deduplicación sin mezclar usos.

Mensaje útil para Cline:

```text
La ficha oficial muestra estas recomendaciones: [pega el fragmento y su URL].
La aplicación muestra: [describe la diferencia].
Revisa la extracción, conserva las fuentes y comprueba el resultado real.
No sustituyas la consulta por resultados fijos.
```

## No funciona «Copiar»

Usa la URL local indicada por el proyecto. Revisa los permisos del navegador y prueba la copia manual del texto mostrado. Si no hay alternativa manual, pide añadirla. Comprueba el contenido pegándolo: un mensaje de «Copiado» no demuestra por sí solo qué contiene el portapapeles.

## No se reconoce `code`

Abre VS Code desde Inicio y utiliza **Archivo → Abrir carpeta**. El comando es opcional. Si acabas de instalar VS Code con PATH, abre una terminal nueva.

## La app no arranca / falta un comando

Abre la terminal en la carpeta de la app y consulta el README generado. Si el comando no coincide con sus archivos reales, pide a Cline que lo corrija y ejecute. No instales herramientas adicionales sin comprobar primero qué requiere ese proyecto.

## Qué aportar para pedir ayuda

Indica el paso que falla, el programa servidor, el Model ID, el error exacto y si la petición breve funcionó. Para errores de la app, añade el modelo buscado y la diferencia observada. Oculta claves y datos privados.
