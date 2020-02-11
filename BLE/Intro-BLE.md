![](https://tva1.sinaimg.cn/large/006y8mN6gy1g87muwaer1j304o023q2p.jpg)

#  Apresentando Bluetooth Low Energy - LPOO2020

> Sistemas de Informação - Unemat- Sinop



## https://github.com/benevid/ble-ifmt

## O que é Bluetooth Low Energy?

O Bluetooth Low Energy, BLE, para abreviar, é uma variante do Bluetooth que economiza energia. A principal aplicação do BLE é a transmissão a curta distância de pequenas quantidades de dados (baixa largura de banda). Diferentemente do Bluetooth que está sempre ativado, o BLE permanece no modo de suspensão constantemente, exceto quando a conexão é iniciada. Isso reflete em um baixo consumo de energia. O BLE consome aproximadamente 100x menos energia que o Bluetooth (dependendo do caso de uso).

![img](https://i2.wp.com/randomnerdtutorials.com/wp-content/uploads/2018/06/BLE-Intro.png?w=813&ssl=1)

Além disso, o BLE suporta não apenas a comunicação ponto a ponto, mas também o modo de transmissão cliente-servidor e rede em malha.

Dê uma olhada na tabela abaixo que compara o BLE e o [Bluetooth Classic](https://randomnerdtutorials.com/esp32-bluetooth-classic-arduino-ide/) com mais detalhes.

![img](https://i1.wp.com/randomnerdtutorials.com/wp-content/uploads/2018/06/Bluetooth-vs-BLE.png?w=813&ssl=1)

[Ver imagem Souce](https://www.bluetooth.com/bluetooth-technology/radio-versions)

Devido às suas propriedades, o BLE é adequado para aplicativos que precisam trocar pequenas quantidades de dados periodicamente em execução em uma célula de moeda. Por exemplo, o BLE é de grande utilidade nos setores de saúde, fitness, rastreamento, beacons, segurança e automação residencial.

![img](https://i2.wp.com/randomnerdtutorials.com/wp-content/uploads/2018/06/ble-applications.png?w=813&ssl=1)

## Servidor e Cliente BLE

Com o Bluetooth Low Energy, existem dois tipos de dispositivos: o servidor e o cliente. O ESP32 pode atuar como um cliente ou como um servidor. O servidor anuncia sua existência, para que possa ser encontrado por outros dispositivos e contém os dados que o cliente pode ler. O cliente verifica os dispositivos próximos e, quando encontra o servidor que procura, estabelece uma conexão e escuta os dados recebidos. Isso é chamado de comunicação ponto a ponto.

![img](https://i0.wp.com/randomnerdtutorials.com/wp-content/uploads/2018/06/BLE-server-and-client.png?w=813&ssl=1)

Além do modo cliente-servidor, o BLE também suporta o modo de transmissão por espalhamento de **broadcast** e rede de malha:

- **Modo de transmissão Broadcast** : o servidor transmite dados para muitos clientes conectados;
- **Rede em malha** : todos os dispositivos estão conectados, essa é uma conexão muitos para muitos.

> Embora seja possível implementar as configurações de rede de broadcast e malha, elas foram desenvolvidas muito recentemente, portanto, não há muitos exemplos implementados para o ESP32 no momento.

## Como os dispositivos BLE se comunicam?

Os dispositivos BLE enviam e recebem mensagens padrão GATT(*Generic Attribute Profile*). GATT significa **Atributos Genéricos** e define uma estrutura hierárquica de dados que é exposta aos dispositivos BLE conectados. É importante entender essa hierarquia, pois facilitará a compreensão de como usar o BLE e a gravação de seus aplicativos.

![img](https://i2.wp.com/randomnerdtutorials.com/wp-content/uploads/2018/06/GATT-BLE-ESP32.png?w=813&ssl=1)

### Serviço BLE

O nível superior da hierarquia é um perfil, composto por um ou mais serviços. Normalmente, um dispositivo BLE contém mais de um serviço.

**Todo serviço contém pelo menos uma característica** ou também pode fazer referência a outros serviços. Um serviço é simplesmente uma coleção de informações, como leituras de sensores, por exemplo.

Existem serviços predefinidos para vários tipos de dados definidos pelo SIG (Bluetooth Special Interest Group), como: nível da bateria, pressão arterial, freqüência cardíaca, escala de peso, etc. Você pode [verificar aqui outros serviços definidos](https://www.bluetooth.com/specifications/gatt/services) .

![img](https://i0.wp.com/randomnerdtutorials.com/wp-content/uploads/2018/06/gatt-services.png?w=813&ssl=1)

[Ver imagem Souce](https://www.bluetooth.com/specifications/gatt/services)

### Característica BLE

A característica sempre pertence a um serviço e é onde os dados reais estão contidos na hierarquia (valor). A característica sempre tem dois atributos: 

- declaração da característica (que fornece metadados sobre os dados) 
- e o valor da característica.

Além disso, o valor da característica pode ser seguido por **descritores**, que expandem ainda mais os <u>metadados</u> contidos na declaração da característica.

As <u>propriedades</u> descrevem como o valor da característica pode ser interagido. Basicamente, contém as operações e procedimentos que podem ser usados com a característica:

- Difusão
- Ler
- Escreva sem resposta
- Escreva
- Notificar
- Indicar
- Gravar assinadas autenticadas
- Propriedades estendidas

### Descritor de Serviços (UUID)

Cada serviço, característica e descritor possui um **UUID (Universally Unique Identifier)**. Um UUID é um número exclusivo de 128 bits (16 bytes). Por exemplo:

```
55072829-bc9e-4c53-938a-74a6d4c78776
```

Existem UUIDs reduzidos para todos os tipos, serviços e perfis especificados no [SIG (Bluetooth Special Interest Group)](https://www.bluetooth.com/specifications/gatt/services) .

Porém, se seu aplicativo precisar de seu próprio UUID, você poderá gerá-lo usando este [site gerador de UUID](https://www.uuidgenerator.net/) :

- https://www.uuidgenerator.net

Em resumo, o UUID é usado para identificar informações exclusivamente. Por exemplo, ele pode identificar um serviço específico fornecido por um dispositivo Bluetooth.

## Video sobre Beacons

<video width="800" height="600" controls><source src="ble.mp4" type="video/mp4"></video>
