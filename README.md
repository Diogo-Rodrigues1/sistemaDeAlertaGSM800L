# Sistema de Monitoramento de Enchentes com Arduino + SIM800L
## Monitoramento ultrassônico com alertas automáticos via SMS

Este projeto implementa um sistema de monitoramento de nível de água utilizando um sensor ultrassônico HC-SR04 conectado a um Arduino Uno, enviando alertas via SMS por meio do módulo GSM SIM800L.
O protótipo foi testado em um recipiente transparente, simulando situações reais de enchente.

## Funcionalidades

- Medição contínua da altura da água
- Conexão à rede GSM
- Envio automático de SMS ao atingir níveis de alerta:
  - 15 cm → Nível subindo
  - 10 cm → Nível continua subindo
  - 5 cm → Nível crítico
- Sistema evita alertas duplicados
- Funcionamento totalmente autônomo com baterias

## Hardware Utilizado

- Arduino Uno
- SIM800L GSM Module
- HC-SR04 Ultrasonic Sensor
- Resistores (para divisor de tensão 5V → 3.3V)
- Bateria 3.7V (SIM800L)
- Bateria 9V (Arduino)
- Protoboard e jumpers

## Esquema de Ligações
### HC-SR04 → Arduino
| HC-SR04 | Arduino |
| ------- | ------- |
| VCC     | 5V      |
| GND     | GND     |
| TRIG    | **8**   |
| ECHO    | **9**   |

### SIM800L → Arduino
> [!WARNING]
> O pino RX do SIM800L não aceita 5V, é necessário divisor de tensão.

| SIM800L | Arduino                      |
| ------- | ---------------------------- |
| TX      | 2 (RX do Arduino)            |
| RX      | 3 (TX com divisor de tensão) |
| GND     | GND                          |
| VCC     | 3.7V (bateria dedicada)      |


### Bibliotecas Necessárias

Instalar via Arduino IDE → Sketch → Include Library → Manage Libraries:

HCSR04 (Martin Sosic)

TinyGSM

SoftwareSerial (nativa)

▶️ Como Executar

Conecte o hardware conforme a tabela acima

Insira o chip GSM no SIM800L

Faça upload do código para o Arduino

Conecte as baterias

Acompanhe as leituras pelo Serial Monitor (opcional)

Receba alertas automáticos via SMS
