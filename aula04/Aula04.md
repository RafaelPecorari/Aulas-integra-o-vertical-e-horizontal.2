# Atividade – Sistema Digital de Controle Distribuído (SDCD)

## 1. Papel de cada componente do sistema

**Sensor de Temperatura:**  
Responsável por coletar dados do ambiente ou do processo industrial, como a temperatura de um equipamento, tanque ou linha de produção.

**ESP32:**  
Microcontrolador que recebe os dados do sensor. Ele faz o processamento inicial das informações e envia os dados pela rede para outros sistemas.

**MQTT:**  
Protocolo de comunicação leve muito utilizado em IoT. Ele permite que os dados enviados pelo ESP32 sejam transmitidos de forma rápida e eficiente para o servidor.

**Servidor:**  
Recebe os dados enviados via MQTT, armazena e processa as informações, podendo também aplicar regras ou análises.

**Aplicativo Mobile:**  
Permite que operadores ou gestores acompanhem as informações em tempo real, visualizando os dados coletados na fábrica diretamente no celular.

**Dashboard:**  
Apresenta os dados de forma visual e organizada (gráficos, indicadores e alertas), facilitando a análise e a tomada de decisão pela gestão da fábrica.

---

## 2. Fluxo de dados do sistema

1. O sensor de temperatura mede a temperatura de um equipamento ou ambiente da fábrica.  
2. O ESP32 recebe essa leitura do sensor.  
3. O ESP32 envia os dados pela rede usando o protocolo MQTT.  
4. O servidor recebe os dados, armazena em banco de dados e processa as informações.  
5. O aplicativo mobile acessa o servidor para obter os dados atualizados.  
6. O dashboard exibe as informações em gráficos, indicadores ou alertas para a gestão da fábrica.

**Fluxo resumido:**  
`Sensor → ESP32 → MQTT → Servidor → Aplicativo → Dashboard → Gestão`

---

## 3. Decisões ou ações com base no dashboard

Com as informações exibidas no dashboard, a empresa pode tomar diversas decisões, como:

- Controlar processos industriais ajustando temperaturas ou funcionamento de máquinas  
- Prevenir falhas identificando temperaturas anormais  
- Monitorar equipamentos em tempo real  
- Evitar superaquecimento desligando sistemas automaticamente quando necessário  
- Melhorar a eficiência da produção  
- Planejar manutenções preventivas  

---

## 4. Vantagens de utilizar um sistema distribuído

- **Redução de falhas:** como o controle é distribuído, se um equipamento falhar o restante do sistema continua funcionando.  
- **Menor quantidade de cabos:** os dados são transmitidos pela rede, reduzindo custos de instalação.  
- **Maior escalabilidade:** novos sensores e dispositivos podem ser adicionados facilmente.  
- **Monitoramento em tempo real:** gestores podem acompanhar dados instantaneamente.  
- **Maior eficiência operacional:** permite controle mais preciso dos processos industriais.  
- **Manutenção preventiva:** os dados coletados ajudam a identificar problemas antes que ocorram falhas.
