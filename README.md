# WhatsDrop-Analyzer
An analysis of malware that steals data via WhatsApp Web.

# WhatsDrop Threat Analyzer  
Ferramenta de análise, detecção e documentação de um malware distribuído via WhatsApp Web.

## 📌 Sobre o projeto
Este repositório documenta a análise de um malware encontrado em ambiente corporativo, composto por um script VBScript (`.vbs`) responsável por instalar e executar um payload Python (`whats.py` / `vbiud.py`).  
O malware se comunica com infraestruturas hospedadas atrás da Cloudflare, utilizando-as para exfiltração de dados e automação de ações via WhatsApp Web.

O objetivo deste projeto é:
- Registrar publicamente IOCs (indicadores de comprometimento)
- Documentar funcionamento, comportamento e infraestrutura envolvida
- Disponibilizar ferramentas para detecção (YARA)
- Ajudar analistas e empresas a identificar a ameaça

---

## 🧪 Evidências principais (IOCs)

### 🔗 URLs maliciosas identificadas

https://empautlipa.com/

https://empautlipa.com/altor/gera.php

https://coffe-estilo.com/

https://coffe-estilo.com/altor/gera.php

## 🧠 Funcionamento resumido do malware
- O **VBS inicial** executa silenciosamente o Python.
- O script Python baixa/consulta comandos em:
  - `*/altor/gera.php`
- Carrega um script JS que automatiza o **WhatsApp Web**.
- Executa remotamente ações como:
  - envio de mensagens
  - coleta de dados
  - execução de instruções assíncronas
- Comunicação é sempre proxyada atrás da **Cloudflare**.
