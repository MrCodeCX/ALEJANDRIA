SH Scripts
Aprender scripting sh y bash
Ver permisos de archivos, grupos de permisos, etc

Comandos hacer guia de comandos general de shell

Instalar ollama, analizar su script sh

Las variables de entorno estan agrupadas en env
env:Variable

Enseniar configuración de intellisence avanzado cambiando el intellisence mode, explicando las rutas del compiler, de los headers, etc

"C_Cpp.default.compilerPath": "${env:HOME}/.espressif/tools/xtensa-esp-elf/esp-14.2.0_20241119/xtensa-esp-elf/bin/xtensa-esp32-elf-gcc"

c_cpp_properties.json vs compile_commands.json

| Elemento                | `c_cpp_properties.json`         | `compile_commands.json` (✅ reemplaza) |
| ----------------------- | ------------------------------- | ------------------------------------- |
| `compilerPath`          | Tú lo defines                   | Viene en `"command"`                  |
| `includePath`           | Lo pones manualmente            | Viene de `-I` reales del build        |
| `defines` (macros `-D`) | Lo escribes tú                  | Lo obtiene automáticamente            |
| `browse.path`           | Usado para búsqueda de símbolos | Ya no necesario, puede ignorarse      |
| `intelliSenseMode`      | Obligatorio                     | Se usa solo como fallback (opcional)  |

Hay variables SHELL
variables PATH
variables ENV