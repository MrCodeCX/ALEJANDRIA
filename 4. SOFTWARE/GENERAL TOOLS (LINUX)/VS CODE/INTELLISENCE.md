El Intellisence actúa distinto en lenguajes compilados que en lenguajes interpretados, por ello en vscode cada lenguaje tiene su propio motor de intellisence disponible como una extension.

Para que el Intellisence de un lenguaje compilado funcione debe conocer el lenguaje, el compilador, las macros de compilación, y los archivos de encabezado headers. El motor de intellisence primero re-interpreta sus directorios de include (headers) con las macros de compilación especificadas, luego busca en ellos los objetos lógicos, funciones, variables, etc, y trabaja con su información.

---
### CONFIG
Para que el motor del Intellisence conozca sus elementos, es necesario comunicarle las rutas de estos, para C/C++ esto se logra de dos formas, mediante un archivo genérico con c_cpp_properties.json (en .vscode), o mediante un archivo especifico producto del motor de construcción del proyecto, compile_commands.json.

El c_cpp_properties.json debe seguir la siguiente estructura:

```
c_cpp_properties.json

{
    "configurations": [
        {
            "name": "<name>",
            "compilerPath": "<compiler-path>",
            "includePath": [
                "${workspaceFolder}/**",
                "<other-include-path>",
            ],
            "defines": [
                "<compiler-macros>",
            ],
            "browse": {
                "path": [
	                "${workspaceFolder}/**",
	                "<other-include-path>",
                ],
                "limitSymbolsToIncludedHeaders": true
            },
            "intelliSenseMode": "<compiler-intellisence-mode>",
            "cStandard": "c<version>",
            "cppStandard": "c++<version>"
        }
    ],
    "version": 4
}

```

El compile_commands.json debe ser generado por el sdk o motor de construcción, y cuenta con elementos equivalentes a los del c_cpp_properties.json.

