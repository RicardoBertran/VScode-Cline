# Instalación y conexión: guía breve

[← Volver al tutorial completo](../README.md)

## 1. Abre tu espacio de trabajo

Instala [Visual Studio Code](https://code.visualstudio.com/docs/setup/windows). Crea `RB-Sampling-Lab` en Documentos y selecciona **Archivo → Abrir carpeta**. Comprueba que su nombre aparece en el Explorador del editor.

## 2. Instala la extensión

Abre Extensiones, busca **Cline** y contrasta la ficha con la [extensión oficial](https://marketplace.visualstudio.com/items?itemName=saoudrizwan.claude-dev). Instálala y abre su panel.

## 3. Comprueba tu servidor

Esta guía supone que ya está instalado. Abre el programa con el que sirves el modelo, activa su API si hace falta y espera a que el modelo esté disponible. Anota dirección, puerto, clave e identificador.

> Un chat funcionando dentro de LM Studio u otra aplicación no demuestra que su API esté encendida.

## 4. Introduce los datos en Cline

En configuración, utiliza **OpenAI Compatible**. Rellena Base URL con la dirección de tu API, API Key con la clave real o dummy cuando proceda, y Model ID con el identificador exacto del servidor. Consulta [los ejemplos y las fuentes](../README.md#6-preparar-los-datos-del-servidor-local).

No pegues una URL de interfaz de chat. No pongas `/chat/completions` en Base URL. No uses una clave dummy si has activado autenticación en el servidor.

## 5. Haz dos pruebas

Pide una respuesta breve. Después crea `prueba.txt`, guarda una frase y pide a Cline que use sus herramientas para leerla. Verifica el contenido y la acción de lectura. [Las instrucciones para copiar están aquí](../README.md#8-comprobar-la-conexión-y-la-carpeta).

> ✅ Si responde y lee el archivo correcto, pasa al [prompt maestro](../prompts/prompt-maestro.md).

Si falla, sigue [la guía de errores](solucion-de-problemas.md). No necesitas reinstalar todo como primer paso.
