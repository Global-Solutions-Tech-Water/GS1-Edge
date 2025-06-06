# 🌊 Monitor de enchentes com Arduino

Este projeto tem como objetivo criar um **sistema de monitoramento e alerta para enchentes**, utilizando sensores para medir o nível da água e condições ambientais (temperatura e umidade). Um display LCD exibe as informações em tempo real, e LEDs/buzzer alertam sobre possíveis riscos.

## 🔧 Componentes Utilizados

- 1x Arduino UNO
- 1x Sensor Ultrassônico (HC-SR04)
- 1x Sensor de Temperatura e Umidade (DHT22)
- 1x Display LCD 16x2 (com interface paralela)
- 1x Buzzer
- 3x LEDs (Verde, Laranja, Vermelho)
- 3x Resistores (220Ω para os LEDs)
- Jumpers e Protoboard

## 🧠 Funcionamento

O sistema realiza leituras contínuas da distância até a superfície da água usando o **sensor ultrassônico**. Baseado nessa distância, ele classifica o risco de alagamento em 3 níveis:

- ✅ **Verde (Segurança):** Nível de água está baixo (> 190 cm)
- ⚠️ **Laranja (Atenção):** Nível de água moderado (entre 50 e 190 cm)
- 🚨 **Vermelho (Perigo):** Nível crítico de água (≤ 50 cm)

Além disso, o **sensor DHT22** mede a temperatura e umidade do ambiente, exibindo os dados no **Monitor Serial**.

## 💻 Exibição

- **LCD 16x2:** Mostra o nível de água e alerta correspondente
- **Serial Monitor:** Exibe temperatura, umidade e nível da água
- **LEDs:** Representam visualmente os níveis de alerta
- **Buzzer:** Emite som quando o nível está em alerta vermelho

## 📂 Código

O código está dividido em duas partes principais:
- `setup()`: Inicializa sensores, pinos e LCD
- `loop()`: Realiza leituras, calcula distância, exibe dados e ativa os alertas

### ⚙️ Bibliotecas Necessárias

Antes de fazer upload para o Arduino, certifique-se de instalar as bibliotecas:
- `LiquidCrystal` (nativa do Arduino IDE)
- `DHT sensor library` by Adafruit

Instale via **Gerenciador de Bibliotecas** no Arduino IDE.

## 🛠️ Esquemático (Resumo de Conexões)

| Componente       | Pino Arduino |
|------------------|--------------|
| Trigger HC-SR04  | 9            |
| Echo HC-SR04     | 8            |
| DHT22 Data       | A0           |
| LCD RS           | 2            |
| LCD E            | 3            |
| LCD D4-D7        | 4, 5, 6, 7    |
| LED Verde        | 10           |
| LED Laranja      | 11           |
| LED Vermelho     | 12           |
| Buzzer           | 13           |

## 🧪 Como Usar

1. Monte o circuito conforme as conexões acima.
2. Faça o upload do código para o Arduino.
3. Abra o **Monitor Serial** para ver os dados.
4. Observe o LCD e os LEDs para acompanhar o status de alagamento.
5. Em caso de alerta vermelho, o buzzer será ativado.

## 📸 Imagens (opcional)

> *(Aqui você pode incluir imagens do protótipo montado, esquema de ligação ou vídeo de demonstração)*

## 📌 Possíveis Melhorias

- Adicionar envio de dados via Wi-Fi (ESP8266 ou ESP32)
- Registro de histórico em cartão SD
- Monitoramento remoto por aplicativo ou dashboard web

## 📄 Licença

Este projeto é de código aberto e pode ser usado para fins educacionais ou pessoais.

---

Desenvolvido com 💡 por [Seu Nome]
