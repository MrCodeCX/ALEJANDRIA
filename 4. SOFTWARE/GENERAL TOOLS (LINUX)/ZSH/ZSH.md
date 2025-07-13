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