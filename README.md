**Ambiente de desenvolvimento** 

* **Primeiro Instalar o VSCode**

**TEMA E FONTE** (VSCode)

Instalar as extensões:

* **Dracula Official**:  dar um reload, depois em preferências, color theme, escrevo Dracula e dou um enter, que o esquema ficará selecionado
* **FiraCode**:  ir no google chrome buscar sobre a fonte no github: https://github.com/tonsky/FiraCode , ir mais abaixo em Solution.

Depois de baixada, dar dois cliques (Linux e Windows) para instalar a font ou copiar para o caminho de fontes do sistema operacional

Agora digitar o comando ctrl + shift + P e digitar Open settings (JSON), deixar desta forma:

```json
{
    "workbench.colorTheme": "Dracula",
    "editor.minimap.enabled": false,
    "window.zoomLevel": -2,
    "explorer.confirmDelete": false,
    "editor.fontFamily": "Fira Code",
    "editor.fontLigatures": true,
    "editor.fontSize": 16,
    "editor.lineHeight": 24,
}
```

* Vscode Icon: selecionar e dar um install.

  

  **CONFIGURAÇÕES** (VSCode)

  Voltar no Open settings.JSON e acrescentar as linhas:

```json
"editor.formatOnSave": true,
    "editor.rulers": [
        80,
        120
    ],
    "editor.tabSize": 2,
    "editor.renderLineHighlight": "gutter",
    "terminal.integrated.fontSize": 14,
    "emmet.syntaxProfiles": {
        "javascript": "jsx"
    },
    "emmet.includeLanguages": {
        "javascript": "javascriptreact"
    },
    "javascript.updateImportsOnFileMove.enabled": "never",
	"breadcrumbs.enabled": true,
    "editor.parameterHints.enabled": false,
```

**PLUGINS** (VSCode)

​	Buscar as seguintes extensões:

*Color highlight*

*Editorconfig*

*Eslint*

*Prettier*

Agora instalar mais dois snipets:

Rocketseat React Native

RockeseatJS

**TEMA E FONTE NO TERMINAL** (OH MY ZSH)

Dracula Theme (pula)

**Oh my Zsh,** acessar o link https://ohmyz.sh/ e copiar o endereço para instalar sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

Agora iremos instalar um tema, Oh My Zsh Space neste endereço: 

https://github.com/denysdovhan/spaceship-prompt

para instalar usaremos esta opção:

### [oh-my-zsh](http://ohmyz.sh/)

Clone this repo:

```
git clone https://github.com/denysdovhan/spaceship-prompt.git "$ZSH_CUSTOM/themes/spaceship-prompt"
```

Symlink `spaceship.zsh-theme` to your oh-my-zsh custom themes directory:

```
ln -s "$ZSH_CUSTOM/themes/spaceship-prompt/spaceship.zsh-theme" "$ZSH_CUSTOM/themes/spaceship.zsh-theme"
```

Set `ZSH_THEME="spaceship"` in your `.zshrc`.



Agora acessar o caminho nano ~/.zshrc e fazer algumas alterações:

ZSH_THEME="spaceship"



SPACESHIP_PROMPT_ORDER=(
  user          # Username section
  dir           # Current directory section
  host          # Hostname section
  git           # Git section (git_branch + git_status)
  hg            # Mercurial section (hg_branch  + hg_status)
  exec_time     # Execution time
  line_sep      # Line break
  vi_mode       # Vi-mode indicator
  jobs          # Background jobs indicator
  exit_code     # Exit code section
  char          # Prompt character
)

SPACESHIP_PROMPT_ADD_NEWLINE=false
SPACESHIP_CHAR_SYMBOL="❯"
SPACESHIP_CHAR_SUFFIX=" "

**PLUGINS (TERMINAL)**

Vamos buscar o plugin zplugin: https://github.com/zdharma/zplugin

zplugin light zsh-users/zsh-autosuggestions
zplugin light zsh-users/zsh-completions
zplugin light zdharma/fast-syntax-highlighting

**EXTENSÕES CHROME**

**React developer tools** e é possível utilizar o tema dracula dentro dele

Dracula DevTools Theme - abra o seguinte endereço no navegador **chrome://flags** deixar a flag Enabled em Developer Tools Experiments

![image-20191213173439793](/home/daniel/.config/Typora/typora-user-images/image-20191213173439793.png)

**FERRAMENTAS**

Insomnia

devdocs (pula)

-----------------------------------

**INSTALAR O  NODEJS**

Para instalar o nodeJS em boas práticas utilizaremos o Node Version Manager **NVM**, ele permite instalar diferentes versões do Node, acessar este caminho: https://github.com/nvm-sh/nvm depois executar a seguinte linha de comando se você tiver o **curl** instalado, executar este comando *curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.1/install.sh | bash* em seguida é necessário adicionar as variáveis de ambiente no arquivo ~/.zshrc: 

```
export NVM_DIR="$([ -z "${XDG_CONFIG_HOME-}" ] && printf %s "${HOME}/.nvm" || printf %s "${XDG_CONFIG_HOME}/nvm")"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh" # This loads nvm
```

vamos agora instalar a versão LTS do node com a seguinte linha de comando. Não esquecer de verificar a versão mais estável do node

 **nvm install 12.13.1**

**nvm alias defaulf 12.13.1**

**INSTALANDO YARN** 

https://yarnpkg.com/lang/en/

Para debian https://yarnpkg.com/en/docs/install#debian-stable

Vamos seguir o passo a passo da documentação do **Yarn**

**Debian / Ubuntu**

On Debian or Ubuntu Linux, you can install Yarn via our Debian package repository. You will first need to configure the repository:

curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list

On Ubuntu 16.04 or below and Debian Stable, you will also need to configure the NodeSource repository to get a new enough version of Node.js.

Then you can simply:

sudo apt update && sudo apt install yarn

Note: Ubuntu 17.04 comes with cmdtest installed by default. If you’re getting errors from installing yarn, you may want to run sudo apt remove cmdtest first. Refer to this for more information.

If using nvm you can avoid the node installation by doing:

sudo apt update && sudo apt install --no-install-recommends yarn

Note: Due to the use of nodejs instead of node name in some distros, yarn might complain about node not being installed. A workaround for this is to add an alias in your .bashrc file, like so: alias node=nodejs. This will point yarn to whatever version of node you decide to use.
Path Setup

If Yarn is not found in your PATH, follow these steps to add it and allow it to be run from anywhere.

Note: your profile may be in your .profile, .bash_profile, .bashrc, .zshrc, etc.

    Add this to your profile: export PATH="$PATH:/opt/yarn-[version]/bin" (the path may vary depending on where you extracted Yarn to)
    In the terminal, log in and log out for the changes to take effect

To have access to Yarn’s executables globally, you will need to set up the PATH environment variable in your terminal. To do this, add export PATH="$PATH:`yarn global bin`" to your profile, or if you use Fish shell, simply run the command set -U fish_user_paths (yarn global bin) $fish_user_paths

Test that Yarn is installed by running:

yarn --version

**CONFIGURANDO A ESTRUTURA** 

criar uma pasta para o projeto e executar primeiramente **yarn init -y**
