[![Netlify Status](https://api.netlify.com/api/v1/badges/55d0e9f5-8e0d-422e-a3d0-38a79ecf2413/deploy-status)](https://app.netlify.com/sites/lancer-briefings/deploys)

# Lancer Briefings

**[Live Demo](https://lancer.kuenaimaku.com/)** neste link você vera um exemplo original do criador do gerenciador de missões de lancer

Neste Exemplo que você vai estar pegando esta modificado para a IPSN, eu tambem vou estar deixando anexado todas as facções possiveis e existente de Lancer já prontas para facilitar para todos.

## Creditos/Credits

- Alkyama#2737 (discord) for the original [Figma Template](figma.com/community/file/983540597915480981) used as reference.
- [VantaJS](https://www.vantajs.com/) for the slick 3d openGL backgrounds.

Novamente, eu não sou o criador, eu sou somente um mero tradutor

## Requisitos

- Node (v14+)
- Light Text Editor (VSCode Recommended)
- Recommended VSCode extensions:
  - Color Info
  - Color Vision
  - IntelliCode
  - npm Intellisense
  - Path Intellisense
  - JSON Tools
  - SVG
  - TypeScript Vue Plugin (Volar)
  - Vue Language Features (Volar)

## Configuração inicial

`npm install` - começe dando este comando antes de tudo

## Build Scripts

`npm run dev` - Serve the webapp with hot reloads (for development work)  
`npm run build` - Build for production  
`npm run serve OR npm run preview` - Locally preview production build  
`npm run format` - Format all code files using `prettier` based on rules set in `.prettierrc.json` (for development work)  

## Customização

A personalização é feita em alguns locais.

### _base.css

Este arquivo contém a maioria das cores, fontes e tamanhos do aplicativo web. Experimente alterar os valores na seção de personalização marcada.

### Index.html

Este arquivo contém o [VantaJS](https://www.vantajs.com/) plano de fundo usado no aplicativo web. Acesse o site, explore as diferentes opções de efeitos e, quando estiver pronto, substitua o `VANTA.GLOBE` script com o seu personalizado. Observe que, se você usar um efeito diferente, precisará substituir o URL do script acima por um de [their CDN repository](https://cdn.jsdelivr.net/npm/vanta@latest/dist/).

### /pasta "public"

Esta pasta contém todos os arquivos locais de imagem, áudio e vídeo..

- `/faction-logos` - Arquivos SVG com os logotipos de cada facção principal, atualmente usados ​​para mapear ícones para fabricantes de mechas.
- `/icons` - Se você deseja substituir os ícones usados ​​em todo o aplicativo, é aqui que você os troca.
- `/pilots` - Esta seção armazena imagens dos pilotos e suas biografias. Os nomes dos arquivos DEVEM corresponder ao `callsign` das fichas dos pilotos exemplo o do meu personagem é "ARK" ou seja quando for lançar a foto do seu personagem na pasta das fotos não coloque o nome, coloque o codinome dele.
- `/mechs` - É aqui que as imagens dos mechs são armazenadas. Os nomes dos arquivos DEVEM corresponder à propriedade `mech` dos pilotos, o mesmo serve para os mechas, não coloque o nome do seu mecha,mas sim do codinome do piloto.
- `bullet.webp` - Isso substitui o marcador padrão em áreas Markdown..
- `planet.webm` - Este é o vídeo sobre a rotação do planeta usado no cabeçalho..
- `startup.ogg` - Este é o som que toca ao carregar a página, se você trocar o arquivo certifique do formato ser .ogg.

### pasta src/assets
- `/clocks` - Aqui são armazenados os arquivos JSON referentes às missões relevantes ou aos relógios da história principal. Você pode adicionar e configurar relógios adicionando ou modificando objetos JSON à lista, eu já deixei os exemplos de como criar os relógios no codigo junto com os comentarios.
- `/events` - Aqui são armazenados os arquivos JSON referentes às missões relevantes ou aos relógios da história principal. Você pode adicionar e configurar relógios adicionando ou modificando objetos JSON à lista.
- `/LCPs` - É aqui que os arquivos LCP descompactados deverão ser lidos. Incluí um exemplo de como criar uma importação adequada via `wallflower-data`.
- `/missions` - É aqui que ficam armazenados os resumos das missões. O nome do arquivo DEVE corresponder ao `slug` propriedade dentro dos dados do aplicativo, deixei comentarios de instruções para tentar auxiliar melhor.
- `/pilots` - É aqui que os arquivos JSON dos pilotos (exportados do Comp/Con) são armazenados. Os nomes dos arquivos DEVEM corresponder ao `callsign` das fichas dos pilotos.
- `/reserves` - É aqui que ficam armazenados os arquivos JSON de reservas dos pilotos. Quaisquer reservas referentes aos dados exportados de cada piloto também serão adicionadas às reservas,deixei um exmeplo para tentar facilitar com a ficha do meu personagem.
- `/info/general-config.json` - EUse este comando para alterar qual missão é carregada inicialmente, definir as informações do piloto e outras opções de facilidade de uso que foram introduzidas para modificar o funcionamento do site. Abaixo estão os valores que você pode precisar alterar.
  - `initialSlug` - Controla qual arquivo de missão é selecionado na inicialização. Este DEVE corresponder ao slug de um arquivo markdown dentro do `/public/missions/` diretório.
  - `planetPath` - O caminho (relativo ao diretório raiz deste repositório) para o arquivo .webm ou .gif a ser usado como elemento de vídeo do planeta.
[Link do programa que o criador usa para criar os planetas](https://deep-fold.itch.io/pixel-planet-generator)
  - `defaultTitle` - Define o prefixo do título de cada página (o texto que aparece na aba do seu navegador).
  - `icon` - O caminho (relativo ao diretório raiz deste repositório) para a imagem que deve ser usada como favicon. Esta imagem será exibida na aba do navegador para este site.
  - `header` - Lê o objeto JSON `header` para determinar qual texto colocar em cada elemento do componente `Header.vue`.

### /src/components/pilot.vue

Este arquivo contém toda a importação de material relacionado a LCPs. Veja a linha 150 para um exemplo de como extrair e importar LCPs para este site, caso não funcione peço paciencia, tive um pequeno problema na importação de LCPS.


## Recomendações de hospedagem

Recomendação do criador é uma curiosidade, esta hospedagem que ele recomendou é a mesma do compcon

Eu recomendo fortemente o uso de [Netlify](https://www.netlify.com/) Para hospedagem, já que não há custo para hospedagem, possui Implantação Contínua e eles fornecerão um URL. Registre-se para obter uma conta e clique no `New Site from Git` botão.
Na próxima página, escolha o serviço Git que você usou para criar um fork deste repositório e autentique-se. Na próxima página, selecione o `lancer-briefings` repositório. Se você não conseguir ver o repositório listado na página, clique no `Can’t see your repo here? Configure the Netlify app on <git site>` Link na parte inferior da página.
Por fim, certifique-se de que a branch que está sendo implantada seja `master`, o campo `base directory` esteja em branco, o `build command` seja `npm run build` e o diretório de publicação seja `dist`.

Após criar o site remotamente, clique no link fornecido na guia `site overview` e verifique se tudo está correto.

Alternativamente, se você usa o GitHub, provavelmente pode contar com o GitHub Pages. Dê uma olhada no [vite documentation](https://vitejs.dev/guide/static-deploy.html#github-pages) Para mais informações.

Sobre a recomendação da hospedagem eu ainda não testei, assim que hospedar pretendo colocar um tutorial aqui
## Utilização no FoundryVTT

instalar o módulo [Inline Webviewer](https://foundryvtt.com/packages/inlinewebviewer) Use o novo botão do módulo para enviar sites aos seus jogadores, incluindo este aqui. Recomendamos visualizar em 1920x1080.
