# vscodium-configs

Minhas configurações e anotações para o [VSCodium](https://vscodium.com/).

## Setup inicial

Antes de iniciar o VSCodium pela priemira vez, criar uma pasta chamada "**data**" dentro da raiz onde o executável do aplicativo está. Isso vai ligar o modo portátil e todas as configurações vão ficar nesta pasta.

Dentro da pasta "**data**", clone o repositório das configurações com `git clone https://github.com/llucasdelima/vscodium-configs.git user-data\User`. A estrutura final deve ser "**data>user-data>User**".

### Habilitando as extenções da Microsoft

O VSCodium não tem acesso ao repositório de extenções da Microsft por padrão, ele busca as extenções em um repositório aberto da comunidade e por isso não tem todas os addons. Para mudar isso modifique esses trechos de código no arquivo "**vscodium\resources\app\products.json**" do VSCodium:

```json
"extensionsGallery": {
  "serviceUrl": "https://open-vsx.org/vscode/gallery",
  "itemUrl": "https://open-vsx.org/vscode/item",
  "latestUrlTemplate": "https://open-vsx.org/vscode/gallery/{publisher}/{name}/latest",
  "controlUrl": "https://raw.githubusercontent.com/EclipseFdn/publish-extensions/refs/heads/master/extension-control/extensions.json"
}
```

Por esse código do "**products.json**" do VSCode:

```json
"extensionsGallery": {
  "serviceUrl": "https://marketplace.visualstudio.com/_apis/public/gallery",
  "itemUrl": "https://marketplace.visualstudio.com/items",
  "controlUrl": "https://main.vscode-cdn.net/extensions/marketplace.json",
  "nlsBaseUrl": "https://www.vscode-unpkg.net/_lp/",
  "publisherUrl": "https://marketplace.visualstudio.com/publishers",
  "resourceUrlTemplate": "https://{publisher}.vscode-unpkg.net/{publisher}/{name}/{version}/{path}",
  "extensionUrlTemplate": "https://www.vscode-unpkg.net/_gallery/{publisher}/{name}/latest"
}
```

### Baixando as extenções

Para baixar todas as extenções de uma vez podemos usar o seguinte comando:

```powershell
"id_extenção", "id_extenção", "id_extenção" | ForEach-Object { codium --install-extension $_ }
```

Onde ""**id_extenção**" é o id da extenção que você quer instalar e codium é o arquivo binário do VSCodium. Geralmente ele fica em "**vscodium\bin\codium.cmd**". No meu caso, depois de entrar na pasta "**vscdoium\bin**" com o terminal, eu uso o comando:

```powershell
"Catppuccin.catppuccin-vsc", "Catppuccin.catppuccin-vsc-icons", "sumneko.lua", "yzhang.markdown-all-in-one", "bierner.markdown-checkbox", "bierner.markdown-footnotes", "TakumiI.markdowntable", "DavidAnson.vscode-markdownlint", "Mesgegra.pico-8-toolkit", "PollywogGames.pico8-ls", "esbenp.prettier-vscode", "alefragnani.project-manager" | ForEach-Object { .\codium.cmd --install-extension $_ }
```

### Finalizando

Agora o VSCodium está pronto para ser inicializado e já vai estar configurado corretamente para meu uso.

## Notas

- O atalho ctrl+shift+o listar as variáveis, funções e etc do arquivo. Colocando dois ponto "**:**" depois de chamar o atalho vai filtrar a lista pelos diferentes tipos.
