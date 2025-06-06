# 🌊 Tech Water: Monitor de Enchentes com Arduino

Um sistema inteligente de **monitoramento e alerta de enchentes** com base em sensores ambientais. O projeto coleta dados de nível de água, temperatura e umidade, exibindo as informações em tempo real por LCD, LEDs e sons de alerta.

---

## 🔧 Componentes Utilizados

- Arduino UNO  
- Sensor Ultrassônico HC-SR04  
- Sensor de Temperatura e Umidade DHT22  
- Display LCD 16x2 (interface paralela)  
- Buzzer  
- LEDs: Verde, Laranja e Vermelho  
- Resistores de 220Ω para cada LED  
- Protoboard e Jumpers  

---

## 🧠 Funcionamento do Sistema

O sensor ultrassônico mede a distância entre o sensor e a superfície da água. Essa distância define o risco de enchente:

- ✅ **Verde (Segurança):** > 190 cm  
- ⚠️ **Laranja (Atenção):** entre 50 cm e 190 cm  
- 🚨 **Vermelho (Perigo):** ≤ 50 cm  

Simultaneamente, o DHT22 registra temperatura e umidade. Os dados são exibidos:

- No **LCD 16x2** com alerta de nível da água  
- No **Monitor Serial** com condições ambientais  
- Por **LEDs** coloridos conforme o risco  
- Com **buzzer** em caso de alerta vermelho  

---

## 💻 Arquitetura do Código

- `setup()`: inicializa sensores, LCD e pinos  
- `loop()`: realiza as leituras e ativa respostas visuais/sonoras  

### Bibliotecas Necessárias

- `LiquidCrystal`  
- `DHT sensor library` da Adafruit  
> Instale via **Gerenciador de Bibliotecas** no Arduino IDE.

---

## 🔌 Esquemático de Ligação

| Componente       | Pino Arduino |
|------------------|--------------|
| Trigger HC-SR04  | 9            |
| Echo HC-SR04     | 8            |
| DHT22 Data       | A0           |
| LCD RS           | 2            |
| LCD E            | 3            |
| LCD D4-D7        | 4, 5, 6, 7   |
| LED Verde        | 10           |
| LED Laranja      | 11           |
| LED Vermelho     | 12           |
| Buzzer           | 13           |

---

## 🧪 Como Simular no Wokwi

1. Acesse o projeto no link: https://wokwi.com/projects/432848568294051841  
2. Clique em **"Start Simulation"**  
3. Veja o LCD exibir o nível da água e o alerta  
4. Observe os LEDs mudarem conforme a distância  
5. Use o controle deslizante do sensor para testar diferentes alturas  
6. Acompanhe a saída no **Serial Monitor** da Wokwi  

---

## 📸 Links 

- Projeto no Wokwi: https://wokwi.com/projects/432848568294051841  
- Vídeo demonstrativo: https://www.youtube.com/watch?v=4SIWR4YfxLg  

---

## 📌 Melhorias Futuras

- Envio de dados para nuvem via ESP32  
- Registro de histórico em SD Card  
- App móvel para monitoramento remoto  
- Integração com API meteorológica para análise preditiva  

---

## 📄 Licença

Projeto de código aberto para fins educacionais e pessoais.

---

Desenvolvido com ❤️ por **Vitor Bordalo**
