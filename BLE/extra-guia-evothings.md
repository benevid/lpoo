#Guia de Iniciante do Evothings Studio

O Evothings Studio é uma ferramenta de desenvolvimento para criar aplicativos móveis para a Internet das Coisas (IoT). Ele é baseado em tecnologias da Web e componentes de software de código aberto.

As ferramentas que você usa para desenvolver aplicativos com o Evothings Studio:

- **Evothings Viewer** - aplicativo móvel que executa todos os aplicativos escritos em HTML / JavaScript (instale-o nas lojas de aplicativos). Conecte-se do aplicativo Viewer ao Workbench e receba atualizações ao vivo de todos os aplicativos em que está trabalhando.
- **Evothings Workbench** - Use o Workbench para executar aplicativos no Evothings Viewer. Ele roda em seu laptop ou computador de mesa, próximo ao seu editor de código. O Workbench apresenta uma interface visual com o usuário, aplicativos de exemplo, uma barra de ativação para seus projetos de aplicativos, recarga automática ao vivo nas ferramentas de salvamento de arquivos, registro e avaliação de código. O Evothings Workbench vem com o download do Evothings Studio.
- **Seu editor de texto favorito ou editor de código IDE** (não incluído no download do Evothings Studio). Quando você pressiona salvar no editor, o Evothings Workbench notará o arquivo atualizado e acionará uma recarga do seu aplicativo em execução no Evothings Viewer. Isso permite um fluxo de trabalho de desenvolvimento rápido.

O Evothings Workbench vem com uma coleção de aplicativos de exemplo prontos para uso para vários dispositivos de IoT, por exemplo, beacons Eddystone e iBeacon, Arduino, TI SensorTag e muito mais.

### O que será preciso

Para começar, aqui está uma lista do que será necessário: 

- Computador laptop/desktop executando Windows, OS X ou Linux.
- Celular ou tablet executando iOS (iOS 7 ou posterior) ou Android (para usar o Bluetooth Low Energy, você precisa de um dispositivo com Bluetooth 4.0 ou posterior executando o Android 4.3 ou posterior).
- Download Evothings Studio - Instale o Evothings Workbench descompactando o pacote de download no seu laptop ou computador de mesa.
- Instale o Evothings Viewer - Faça o download na Apple App Store ou no Google Play.
- Para executar os aplicativos de exemplo que acompanham o Evothings Studio, você precisa do hardware usado por cada exemplo; Existem exemplos que funcionam imediatamente e sem hardware especial, como os exemplos do **Cordova Accelerometer** e **BLE Scan**.
- **Para criar aplicativos nativos**, você precisa do sistema de compilação **Apache Cordova**.

### Como editar código

O próximo passo é modificar o código de exemplo:

- Pressione o botão **COPY** no exemplo "Hello World". Isso fará uma cópia do aplicativo e aparecerá na guia "Meus aplicativos".
- Pressione **RUN** para iniciar o aplicativo no telefone ou tablet conectado. Pressionar **RUN** torna o aplicativo atualmente ativo. O aplicativo ativo é monitorado para alterações de código e, quando um arquivo é alterado, o aplicativo é recarregado automaticamente nos dispositivos conectados. É como se o **RUN** fosse pressionado automaticamente por você!
  Pressione o botão **CODE** no aplicativo "Hello World" em "Meus aplicativos". Isso abrirá o navegador de arquivos do sistema para os arquivos do aplicativo.
- Para ver a atualização ao vivo em ação, abra o arquivo index.html em um editor de texto. Você pode usar seu editor ou IDE favorito. Faça algumas alterações interessantes no código, por exemplo modifique o cabeçalho `h1` para dizer "Olá Evothings".
  Salve o arquivo (normalmente pressione **CTRL + S**). Feito! O aplicativo agora é recarregado automaticamente no Visualizador - as alterações são visíveis instantaneamente.

### Crie seu próprio projeto

Para criar seu próprio projeto de aplicativo móvel, você tem três opções:

- Clique no botão **NOVO**. Isso fornecerá um esqueleto de aplicativo em branco.
- Clique no botão **COPIAR** em um aplicativo de exemplo. Você pode modificar o aplicativo e continuar a partir daí.
- Arraste qualquer arquivo **HTML** para a janela Evothings Workbench.

Todos os métodos acima criarão uma entrada na guia "**Meus aplicativos**". Você pode reorganizar as entradas do aplicativo usando arrastar e soltar. Feche-os usando o ícone **Fechar (x)**. Isso não removerá os arquivos no disco.

> ☕︎ Quando você cria um aplicativo usando **NOVO** ou **COPIAR**, os arquivos do aplicativo são salvos em uma pasta no disco. Você pode especificar a pasta em uma caixa de diálogo. Se você deseja mover o aplicativo para outra pasta, exclua o item do aplicativo em "Meus aplicativos" (não excluirá a pasta do aplicativo). Mova a pasta do aplicativo para o novo local. Arraste index.html do navegador de arquivos do sistema para "Meus aplicativos".

#### Criar Aplicativo do zero ou adicionar um existente

- Criar uma pasta com os arquivos do projeto (arquivos HTML / CSS / JavaScript / media).
  É necessário que haja pelo menos um arquivo HTML no projeto - usado como ponto de entrada do aplicativo. 

- Arrastar o arquivo HTML principal, por exemplo o `index.html`, na lista de aplicativos no Evothings Workbench.
- Agora, basta pressionar **RUN** no aplicativo para iniciá-lo no Visualizador. 

> ☕︎ Observe que você pode conectar vários telefones celulares e tablets ao Evothings Workbench. Quando você salva qualquer arquivo no projeto (ou pressiona RUN), o aplicativo é recarregado em todos eles!

Um projeto de aplicativo do Evothings é apenas uma pasta com seus arquivos HTML e JavaScript. Assim como qualquer site. E assim que tudo é alterado, o Workbench o envia a todos os espectadores conectados, assim!

### Configurações do ambiente de trabalho

No menu "Mais", você encontrará a opção de menu "Configurações". Isso abre uma caixa de diálogo na qual é possível alterar o tamanho da fonte usada na janela Ferramentas e o número de níveis de diretório percorridos pelo observador de arquivos recarregado. Você também pode alterar o caminho padrão para a pasta usada pelos botões **NOVO** e **COPIAR**.

> ☕︎ A configuração do endereço do servidor de recarga é destinada aos desenvolvedores do Evothings Studio. Na maioria dos casos, você não deve alterar esse valor. O valor padrão é "https://deploy.evothings.com". O servidor de recarga lida com a comunicação entre o Evothings Workbench e os telefones e tablets conectados.

![Apache_Cordova1](https://evomedia.evothings.com/2015/02/Apache_Cordova1.png)

O Apache Cordova é um sistema de construção (build) para criar aplicativos nativos desenvolvidos em HTML/JavaScript. Você pode usar o Evothings Studio sem o Cordova, mas se quiser criar aplicativos nativos, é necessário.

> ☕︎ É útil saber que o próprio Evothings Viewer é um aplicativo Cordova, desenvolvido usando o Evothings Studio.

Os plug-ins Cordova são módulos de código que fornecem funcionalidade nativa do dispositivo, como Bluetooth Low Energy e variação do iBeacon. O Evothings Viewer vem com vários plugins [pré-instalados](https://evothings.com/doc/studio/mobile-app.html#SupportedPlugins). 

Os plugins possuem duas partes, uma implementação de código nativo (geralmente escrita em Objective-C ou Swift no iOS e em Java no Android) e uma biblioteca JavaScript (compartilhada entre plataformas). É possível usar o Evothings Studio sem o Cordova, mas se você deseja criar aplicativos nativos, ele deve ser utilizado.

Um projeto do Evothings é apenas uma pasta com arquivos HTML / JavaScript e outro conteúdo da web. Um projeto do Cordova possui uma estrutura de pastas especial e os arquivos JavaScript / web entram na pasta "www". 

Você pode usar o Cordova apenas, sem usar o Evothings Studio. Mas o fluxo de trabalho será muito mais rápido se você usar o Evothings. Abaixo, os dois fluxos de trabalho.

**Fluxo de trabalho Cordova**

1. Edite seu código (HTML / JS) e salve
2. Compilar o aplicativo (cordova build ios / android)
3. Implantar o aplicativo em um dispositivo (adb install -r caminho para o arquivo apk)
4. Inicie o aplicativo no dispositivo
5. Repita as etapas acima para cada alteração de código

**Fluxo de trabalho de Evothings**

1. Edite seu código (HTML / JS) e salve

2. O aplicativo é recarregado instantaneamente no (s) dispositivo (s)

### Visão geral do download do Evothings Studio

Evothings Studio tem incluso os seguintes itens:

- Aplicativo de desktop do Evothings Workbench
- Aplicativos de exemplo

O Evothings Workbench é executado no mecanismo `nw.js` (que inclui WebKit e node.js). O binário `nw.js` está incluído no download. Todos os pacotes de download (Windows / OS X / Linux) são basicamente idênticos, exceto o binário node-webkit.

Aqui está uma visão geral de alguns dos arquivos e pastas no pacote de download descompactado:

```ASN.1
- examples - aplicativos de exemplo
- hyper - código JavaScript para o Workbench
-- server - código que se comunica com o servidor proxy que encaminha as recargas para o Viewer
-- settings
--- settings.js - configurações que você pode modificar
-- ui - código da interface do usuário
- node_modules - módulos usados pelo node-webkit
- package.json - Configurações do aplicativo Workbench
```



O Evothings Studio oferece várias ferramentas e itens úteis:

- Desenvolva em vários dispositivos móveis simultaneamente - teste seu aplicativo em telefones e tablets iOS e Android ao mesmo tempo
- Execute um aplicativo em todos os dispositivos conectados com um clique
- Ao salvar um arquivo, todos os dispositivos conectados recarregam o aplicativo em execução - você pode ver o resultado instantaneamente
- Liberdade para usar qualquer editor (a atualização ao vivo funciona com todos os editores que salvam dados em arquivos HTML/JS/CSS/mídia, também editores HTML e editores de imagem)
- Comece rapidamente com seus próprios aplicativos, copiando o código dos aplicativos de exemplo (código para exemplos incluídos no download)
- Envie facilmente dados de registro de dispositivos conectados
- Avalie o código JavaScript interativamente em dispositivos conectados, útil para desenvolvimento e depuração
- Crie aplicativos nativos usando o Apache Cordova - não são necessárias ferramentas proprietárias, inclua os plugins do Cordova que você gosta
- Use recarga ao vivo, registro e avaliação de código interativa com qualquer aplicativo Cordova - isso facilita o desenvolvimento e a depuração de aplicativos Cordova
- O [código fonte](https://evothings.com/doc/studio/evothings-studio-overview.html#SourceCode) completo está disponível no GitHub (licença de código aberto Apache)

## Evothings BLE

Este guia mostra como usar a API do Evothings BLE para conectar-se a dispositivos Bluetooth Low Energy a partir do JavaScript. Observe que este guia se aplica ao Evothings Viewer 1.5 ou posterior e ao plug-in Cordova BLE versão 2.0.0 ou posterior (incluído no Evothings Viewer).

Orientamos você nas etapas para detectar e conectar-se a um dispositivo BLE. 

> ☕︎ Você pode usar este guia para basicamente qualquer dispositivo BLE.


O suporte nativo para Bluetooth Low Energy no Android e iOS é fornecido pelo plug-in Cordova BLE. Este plug-in está incluído no Evothings Viewer, que facilita o início do desenvolvimento de um aplicativo BLE em JavaScript. Quando o aplicativo está pronto para teste e implantação, o sistema de compilação Cordova é usado para criar um aplicativo personalizado com o código do aplicativo e o plug-in BLE. 

> ☕︎ Este aplicativo pode ser publicado nas lojas de aplicativos.