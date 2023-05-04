# Pesonalizando o PowerShell

## Configurações para melhorar a aparência e experiência com PowerShell



<img src="/files/CustomTerminal.png"  width="800" height="360">

## 1 - Instalar a versão mais recente do PowerShell

No PowerShell executar o comando:

`winget install --id Microsoft.Powershell --source winget`

## 2 - Configurar o PowerShell para a nova versão

<img src="/files/PwshConfig1.png"  width="800" height="600">

## 3 - Instalar Módulos

No PowerShell executar os comandos:

Scoop:

`iwr -useb get.scoop.sh | iex`

Curl, sudo, e jq:

`scoop install curl sudo jq`

Neovim, gcc:

`scoop install neovim gcc`

posh-git:

`Install-Module posh-git -Scope CurrentUser -Force`

oh-my-posh:

`winget install JanDeDobbeleer.OhMyPosh -s winget`

Terminal-Icons:

`Install-Module -Name Terminal-Icons -Repository PSGallery -Force`

Z:

`Install-Module -Name z -Force`

PSReadLine:

`Install-Module -Name PSReadLine -AllowPrerelease -Scope CurrentUser -Force -SkipPublisherCheck`

Fzf:

`scoop install fzf`

PSFzf:

`Install-Module -Name PSFzf -Scope CurrentUser -Force`  
`Set-PsFzfOption -PSReadlineChordProvider 'Ctrl+f' -PSReadlineChordReverseHistory 'Ctrl+r'`

## 4 - Configurar a inicialização do Terminal

No PowerShell executar os comandos:

Ir a pasta do seu usuário:  
`cd ~`  

Criar uma pasta para as configurações:  
`mkdir .config/powershell`  

Dentro dessa pasta copie o arquivo **user_profile.ps1** que estão na pasta files aqui nesse repositório.

**IMPORTANTE:** Após copiar o arquivo clique com o botão direito do mouse sobre ele e marque a opção **Unblock**

<img src="/files/SecurityFile.jpeg"  width="360" height="503">


Edite a variavel **$PROFILE.CurrentUserCurrentHost** usando:

`nvim $PROFILE.CurrentUserCurrentHost`

Pressione **INSERT** para editar

na primeira linha coloque:

`. $env:USERPROFILE\.config\powershell\user_profile.ps1`

Precione **ESC** e digite `:wq` então **ENTER**

Feche e Abrar o PowerShell novamente, e Pronto!

## Alterar a fonte:

Faça download e instale o arquivo de fonte **Hack_Bold_Italic_Nerd_Font_Complete_Mono_Windows_Compatible.ttf** que esta na pasta files aqui nesse repositório.  

Configurar a fonte no Terminal:  

<img src="/files/PwshConfig2.png"  width="800" height="600">

## Outros temas para o Terminal:

Acesse:

https://ohmyposh.dev/docs/themes

Escolha um tema, para aplicar edite o arquivo ~\.config\powershell\user_profile.ps1 e altere a linha:

`oh-my-posh init pwsh --config "$env:POSH_THEMES_PATH\cloud-native-azure.omp.json" | Invoke-Expression`

para por exemplo:

`oh-my-posh init pwsh --config "$env:POSH_THEMES_PATH\<ARQUIVO_DO_OUTRO_TEMA>" | Invoke-Expression`

para ver a lista de todos os temas:

`echo $env:POSH_THEMES_PATH`


