Guia de instalacion (frecuente uso para aniadir zsh en contenedores docker)

apt update 
apt install zsh git

(OHMYZSH se instalara para el usuario que estemos usando al llamar a este comando, por defecto en docker somos root, se instalara para root)

sh -c "$(wget -qO- https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"


CONFIG
nano /home/mrcode/.zshrc
nano /root/.zshrc

TEMA EN CONTENEDORES
ZSH_THEME="agnoster"

PLUGINS
plugins=(git zsh-autosuggestions zsh-completions fzf-tab)

git clone https://github.com/zsh-users/zsh-autosuggestions /root/.oh-my-zsh/custom/plugins/zsh-autosuggestions

git clone https://github.com/zsh-users/zsh-completions /root/.oh-my-zsh/custom/plugins/zsh-completions

git clone https://github.com/Aloxaf/fzf-tab /root/.oh-my-zsh/custom/plugins/fzf-tab

---
### COMPLETION
Para agregar un autocompletado a zsh completion, se agrega un archivo en ~/.oh-my-zsh/custom/plugins/zsh-completions/src, de nombre \_command, por ejemplo \_ros2 

```
#compdef ros2

local -a subcommands
subcommands=(
  'pkg:Gestión de paquetes'
  'run:Ejecutar un nodo'
  'node:Operaciones con nodos'
  'topic:Interactuar con topics'
  'service:Interactuar con servicios'
  'param:Gestión de parámetros'
  'action:Interactuar con acciones'
  'bag:Operaciones con rosbag2'
  'component:Gestión de componentes'
  'daemon:Control del daemon'
  'doctor:Diagnósticos del sistema'
  'interface:Mostrar interfaces'
  'launch:Ejecutar archivos launch'
  'multicast:Configuración multicast'
  'security:Configuración de seguridad'
  'wtf:Diagnóstico rápido (what went wrong)'
)

_describe 'command' subcommands
```
