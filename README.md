# Sistema IoT para Monitoramento de Umidade com Alertas Inteligentes

Este repositório contém os arquivos e descrições do projeto desenvolvido para a disciplina de Objetos Inteligentes Conectados da Universidade Presbiteriana Mackenzie.

## 🎯 Objetivo

O projeto visa monitorar a umidade do ar em ambientes residenciais e alertar os usuários quando os níveis estiverem abaixo do recomendado. Com base nas leituras dos sensores, o sistema envia alertas visuais (LED), mensagens via WhatsApp e armazena os dados em nuvem para visualização em dashboards.

## 🧩 Componentes principais

- **Dispositivo simulado** (Wokwi com ESP32 + sensor DHT22 + LED)
- **Protocolo MQTT** Comunicação via broker público HiveMQ entre o dispositivo e o Node-RED
- **Plataforma low-code**: Node-RED (hospedado em instância EC2 da AWS), onde são definidas as regras de negócio e integração com APIs
- **Banco de dados em nuvem**: InfluxDB Cloud
- **Dashboard**: Grafana Cloud
- **API de alerta**: CallMeBot, utilizada para envio de mensagens automáticas via WhatsApp quando a umidade está fora dos padrões recomendados

## 🔁 Fluxo geral do sistema

1. Sensor lê a umidade e envia via MQTT.
2. Node-RED interpreta os dados:
   - Armazena no InfluxDB
   - Envia comandos para atuador (LED ON/OFF)
   - Envia alerta por WhatsApp
3. Dados são exibidos em tempo real no Grafana.

## 📂 Estrutura do repositório

- `/dispositivo-simulado`: Arquivo com o código do ESP32 ou o link do circuito no Wokwi.
- `/node-red-fluxo`: Exportação completa do fluxo Node-RED em `.json`.
- `/imagens`: Capturas de tela do dashboard, arquitetura e fluxo.
  
## 📊 Painel de Monitoramento

![image](https://github.com/user-attachments/assets/ce97611e-14df-4ff9-b6d1-0aaa05f9e1a6)


## 📬 Contato dos autores

Bruna Valerio, Danilo Rocha, Fernanda Brazolin, Yasmin Toledo  
Universidade Presbiteriana Mackenzie - 2025

---

Este projeto está alinhado aos Objetivos de Desenvolvimento Sustentável (ODS) da ONU, em especial os ODS 3 (Saúde e Bem-estar) e ODS 11 (Cidades e Comunidades Sustentáveis).
