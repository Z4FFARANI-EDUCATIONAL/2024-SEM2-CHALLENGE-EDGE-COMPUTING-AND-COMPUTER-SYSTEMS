![banner](./assets/banner.png)

# Formula E-mmersive · Edge Computing & Computer Systems

| Integrante | RM |
|---|---|
| [Guilherme Santos Nunes](https://github.com/sannunez) | RM558989 |
| [Kaique Zaffarani](https://github.com/Z4ffarani) | RM556677 |
| [Kairo da Silva Silvestre de Carvalho](https://github.com/KairoSilvestre) | RM558288 |
| [Rafael Menezes Viana](https://github.com/vianafs) | — |

Challenge 2024.2 · Tech Mahindra · Engenharia de Software · FIAP

---

## O projeto Formula E-mmersive

A **[Tech Mahindra](https://www.techmahindra.com)**, em parceria com a **[FIAP](https://www.fiap.com.br)**, tem como objetivo popularizar a Fórmula E por meio de soluções tecnológicas interativas e práticas.

## Esta entrega: Edge Computing & Computer Systems

Sistema IoT (internet das coisas) que exibe informações em tempo real utilizando a plataforma **[ThingSpeak](https://thingspeak.com)**, da **[MATLAB](https://www.mathworks.com/products/matlab.html)**, que armazena dados em nuvem. Esses dados são coletados por sensores conectados a um simulador de Arduino na plataforma **[Wokwi](https://wokwi.com)** e também são disponibilizados em um site próprio através de uma API (interface de programação de aplicações).

O sistema é estruturado em três pilares:
- **Site** | Sincroniza e exibe dados no front-end por meio de requisições HTTP e chave de API do canal IoT, além de utilizar algoritmos personalizados para interpretar e apresentar os valores de forma intuitiva.
- **Canal IoT** | Processa os dados enviados pelo simulador, apresentando-os em gráficos que facilitam a compreensão e o registro cronológico das informações.
- **Simulador** | Integra sensores conectados a um microcontrolador ESP32, que captam informações ambientais e as transmitem via Wi-Fi para o canal IoT.

| Entregável | Onde |
|---|---|
| Vídeo explicativo | [youtu.be/QZd2da9OijI](https://youtu.be/QZd2da9OijI) |
| Site publicado | [z4ffarani-educational.github.io/2024-SEM2-CHALLENGE-EDGE-COMPUTING-AND-COMPUTER-SYSTEMS](https://z4ffarani-educational.github.io/2024-SEM2-CHALLENGE-EDGE-COMPUTING-AND-COMPUTER-SYSTEMS/) |
| Canal IoT (ThingSpeak) | [thingspeak.com/channels/2665201](https://thingspeak.com/channels/2665201) |
| Simulador (Wokwi) | [wokwi.com/projects/409672865580237825](https://wokwi.com/projects/409672865580237825) |

## Prévia

![site](./assets/banner-site.png)
![canal IoT](./assets/banner-canal-iot.png)
![simulador](./assets/banner-simulador.png)

## Como executar

```bash
git clone https://github.com/Z4FFARANI-EDUCATIONAL/2024-SEM2-CHALLENGE-EDGE-COMPUTING-AND-COMPUTER-SYSTEMS.git
cd 2024-SEM2-CHALLENGE-EDGE-COMPUTING-AND-COMPUTER-SYSTEMS
```

1. Para acessar o site, abra o arquivo `docs/index.html` no navegador.
2. Para rodar o simulador, siga o link do Wokwi e clique no botão de iniciar. Levará algum tempo até que o simulador se conecte à rede pública do Wokwi e ao canal IoT. É possível regular os níveis dos sensores clicando neles, para que sejam registrados no canal IoT após um intervalo de 15 segundos.
3. Para utilização física, execute o código do arquivo `docs/simulator.ino` e instale as bibliotecas dos sensores da pasta `libraries`. O Arduino IDE é adequado para o teste.

## Funções

`docs/simulator.ino`:
- **Inclusão de bibliotecas** | Importa as bibliotecas necessárias para a operação do ESP32 e para a comunicação com os sensores.
- **Definição de portas de entrada** | Estabelece as portas digitais e analógicas do ESP32 que serão usadas para conectar e ler os dados dos sensores.
- **Referenciamento e leitura dos sensores** | Configura e lê os dados dos sensores DHT22, HC-SR04 e LDR, processando as informações de temperatura, umidade, distância e luminosidade para envio posterior.
- **Constantes para conexão Wi-Fi, chave de API e servidor** | Define as credenciais necessárias para a conexão à rede Wi-Fi, a chave de API do ThingSpeak e o endereço do servidor.
- **Envio de dados dos sensores para o canal IoT** | Envia periodicamente os dados lidos dos sensores para o canal IoT, usando a chave de API para autenticação e a formatação adequada das requisições HTTP.

`docs/script.js`:
- **Fetch de API** | Faz uma requisição à API do canal IoT para obter os dados armazenados, usando o método `fetch` do JavaScript de forma assíncrona.
- **Conversão para JSON** | Converte a resposta da requisição para JSON, o que facilita a manipulação e a exibição das informações no front-end.
- **Mapeamento de valores** | Itera sobre os dados recebidos, extraindo os valores relevantes para exibição.
- **innerHTML** | Atualiza o conteúdo HTML da página com os dados processados, inserindo dinamicamente as informações nos elementos da interface.
- **Resposta condicional** | Trata diferentes estados dos dados recebidos, como erros na requisição ou dados ausentes, para que a interface reaja de forma adequada.

## Diagrama

![diagrama](./assets/diagrama.png)

## Montagem do simulador

| Qtd. | Componente | Preço |
|---|---|---|
| 1 | Cabo USB A | R$ 15,00 |
| 1 | ESP32-DevKitC V4 ([documentação](https://docs.espressif.com/projects/arduino-esp32/en/latest/)) | R$ 50,00 |
| 1 | Sensor de distância ultrassônico HC-SR04 ([documentação](https://web.eece.maine.edu/zhu/book/lab/HC-SR04%20User%20Manual.pdf)) | R$ 13,00 |
| 1 | Módulo de sensor de luminosidade (LDR) ([documentação](https://docs.google.com/document/d/1FECtFOYhgblp-J9JyAeC6D070fHu0u49S3C2awSFd5c/edit)) | R$ 10,00 |
| 1 | Sensor de umidade e temperatura DHT22 ([documentação](https://www.mouser.com/datasheet/2/737/dht-932870.pdf)) | R$ 40,00 |
| 1 | Buzzer piezoelétrico ativo de 5V ([documentação](https://wiki-content.arduino.cc/documents/datasheets/PIEZO-PKM22EPPH4001-BO.pdf)) | R$ 4,00 |
| 1 | Resistor de 4,7 kΩ | R$ 2,00 |
| 1 | Placa de ensaio (de preferência com 830 pontos) | R$ 20,00 |
| 12 | Cabos jumper macho-macho (contados com a placa de ensaio incluída) | R$ 3,00 |
| 4 | Cabos jumper macho-fêmea (contados com a placa de ensaio incluída) | R$ 1,00 |
| 1 | Cabo jumper fêmea-fêmea (contado com a placa de ensaio incluída) | R$ 0,25 |
| | **Total** | **R$ 158,25** |

## Observações

- A estabilidade da conexão Wi-Fi é fundamental para o funcionamento do sistema. Verifique se o ESP32 está dentro do alcance da rede sem fio para garantir uma transmissão de dados confiável.
- Os preços dos componentes do simulador estão sujeitos a valorização ou desvalorização.
- O ThingSpeak possui limites de taxa para requisições de dados. Não exceda esses limites para evitar interrupções no serviço; consulte a documentação do ThingSpeak para mais detalhes.
- Caso sejam criadas para uso particular, as credenciais de Wi-Fi e a chave da API não devem ser expostas publicamente.
- O sistema está projetado para monitorar um número limitado de sensores. Para escalabilidade, considere uma arquitetura de microsserviços ou um sistema de mensageria para lidar com múltiplos dispositivos simultaneamente.

---

## Tecnologias

[![Arduino](https://img.shields.io/badge/Arduino-00979D?style=flat-square&logo=arduino&logoColor=white)](https://www.arduino.cc)
[![ESP32](https://img.shields.io/badge/ESP32-E7352C?style=flat-square&logo=espressif&logoColor=white)](https://docs.espressif.com/projects/arduino-esp32/en/latest/)
[![ThingSpeak](https://img.shields.io/badge/ThingSpeak-0076A8?style=flat-square)](https://thingspeak.com)
[![Wokwi](https://img.shields.io/badge/Wokwi-3F3F3F?style=flat-square)](https://wokwi.com)
[![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white)](https://developer.mozilla.org/pt-BR/docs/Web/HTML)
[![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3&logoColor=white)](https://developer.mozilla.org/pt-BR/docs/Web/CSS)
[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=white)](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript)

---

## Referências

| # | Referência | Aplicação no projeto |
|---|---|---|
| 1 | [Arduino — Instalação de bibliotecas no Arduino IDE](https://docs.arduino.cc/software/ide-v1/tutorials/installing-libraries/) | Instalação das bibliotecas da pasta `libraries` |
