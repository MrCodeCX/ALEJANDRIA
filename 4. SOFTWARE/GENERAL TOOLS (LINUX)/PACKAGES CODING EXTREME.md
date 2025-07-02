
---
### TERMINAL 

| Paquete          | Descripción                                             |
| :--------------- | ------------------------------------------------------- |
| `gnome-terminal` | Terminal clásica (Ubuntu Default)                       |
| `zsh`            | Shell compatible con plugins                            |
| `zsh-common`     | Listas de auto-completado                               |
| `fzf`            | Fuzzy Finder motor de búsqueda (necesario para fzf-tab) |

| Plugins               | Descripción                                                 |
| :-------------------- | ----------------------------------------------------------- |
| `oh-my-zsh`           | Gestiona plugins para zsh                                   |
| `zsh-completion`      | Mejora el motor de auto-completado de zsh                   |
| `zsh-autosuggestions` | Muestra sugerencias de auto-completado basado en historial  |
| `fzf-tab`             | Muestra sugerencias interactivas de auto-completado con TAB |

---
### GENERAL PURPOSE

| Paquete          | Descripción                                                   |
| :--------------- | ------------------------------------------------------------- |
| `code`           | Editor VSCode                                                 |
| `git`            | Herramienta de Control de Versiones                           |
| `dconfig-editor` | Editor de base de datos dconfig (Registro de Configuraciones) |

---
### BUILD ESSENTIAL FOR C/C++
libc6-dev | libc-dev, gcc (>= 4:12.3), g++ (>= 4:12.3), make, dpkg-dev (>= 1.17.11)

| Paquete     | Descripción                                                              |
| ----------- | ------------------------------------------------------------------------ |
| `gcc`       | Compilador para C                                                        |
| `g++`       | Compilador para C++                                                      |
| `make`      | Herramienta de construcción de proyectos (Makefiles)                     |
| `libc6-dev` | Archivos de desarrollo de la biblioteca estándar de C (glibc)            |
| `dpkg-dev`  | Herramientas para construir paquetes `.deb`                              |
| `cmake`     | Facilita generación de make files (instalación fuera de build-essential) |

---
### ESP-IDF
SDK para trabajar con esp32, guía de instalación:
https://docs.espressif.com/projects/esp-idf/en/stable/esp32/get-started/linux-macos-setup.html#get-started-get-esp-idf

alias get_idf='. $HOME/esp/esp-idf/export.sh'

---
### STM32 CUBE IDE
SDK oficial de stm, instalación por script sh