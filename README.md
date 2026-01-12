# WhatsDrop Analyzer

Análise técnica de um malware distribuído via WhatsApp Web, com foco em comportamento, fluxo de execução e indicadores observados durante a investigação.

---

## Visão Geral

Este repositório documenta a análise de um malware identificado em ambiente corporativo, cujo objetivo principal era a automação indevida de ações via WhatsApp Web e a comunicação com servidores remotos para recebimento de comandos.

A amostra analisada é composta por múltiplos estágios, incluindo:
- um script VBScript (`.vbs`) responsável pela execução inicial
- scripts em Python utilizados como payload
- automação de navegador por meio de JavaScript

O conteúdo aqui apresentado tem caráter **analítico e descritivo**, sem disponibilizar código malicioso funcional.

---

## Objetivo do Repositório

O objetivo deste projeto é:

- Documentar o funcionamento geral do malware observado
- Registrar indicadores técnicos encontrados durante a análise
- Servir como referência para outros analistas que encontrem artefatos semelhantes
- Compor portfólio técnico com foco em análise de malware

Nenhum conteúdo aqui tem como finalidade facilitar exploração ou reutilização da ameaça.

---

## Funcionamento Resumido

De forma simplificada, o comportamento observado foi:

1. Um **script VBScript** é utilizado como ponto inicial de execução
2. Esse script invoca o interpretador Python de forma silenciosa
3. O payload Python:
   - realiza comunicação com servidores remotos
   - recebe instruções externas
   - carrega scripts JavaScript para automação do WhatsApp Web
4. As ações executadas incluem automação de mensagens e coleta de informações

A comunicação com os servidores externos ocorre por meio de domínios protegidos por serviços de proxy (ex.: Cloudflare).

---

## Indicadores Observados

Durante a análise, foram identificados domínios utilizados na comunicação do malware.

Para evitar acesso acidental ou reutilização indevida, os domínios são apresentados de forma **não clicável**:

empautlipa[.]com

coffe-estilo[.]com

Caminhos observados:


> Não é garantido que esses endereços estejam ativos no momento da publicação.

---

## Relação com Outros Projetos

A análise deste malware levou à identificação de técnicas simples de ofuscação utilizadas no estágio VBScript, documentadas separadamente no repositório abaixo:

- **VBS ASCII Deobfuscation**  
  Análise e desofuscação de strings ASCII utilizadas no estágio inicial do script VBScript.

---

## Considerações de Segurança

Este repositório **não contém**:

- payloads funcionais
- scripts completos do malware
- URLs clicáveis ou infraestrutura ativa
- instruções de execução



## ⚠️ Nota ética

Este repositório tem finalidade exclusivamente defensiva e informativa.
Não são disponibilizados payloads funcionais ou códigos completos de malware.


---

## 📰 Contexto público da ameaça

Campanhas com esse padrão de entrega foram posteriormente associadas por pesquisadores, à famílias de malware conhecidas no Brasil, como o *Boto Cor-de-Rosa*, uma evolução do Astaroth.

Essa campanha se destaca pelo uso do **WhatsApp Web como vetor de propagação**, explorando engenharia social e automação para envio de mensagens a contatos da vítima.


Este repositório documenta observações técnicas feitas antes desta associação pública, com foco em:
- fluxo de execução
- técnicas de ofuscação
- comunicação remota observada

## 📷 Exemplo de vetor de infecção

A imagem abaixo ilustra um exemplo **sanitizado** do vetor inicial de infecção observado durante a análise.

![Exemplo de envio do malware via WhatsApp](exemplo_golpe_do_orçamento.jpg)

Neste cenário, a vítima recebe um arquivo compactado (`.zip`) por meio do WhatsApp, acompanhado de uma mensagem com tom urgente e linguagem informal.  
O nome do arquivo e o conteúdo da mensagem são projetados para parecer legítimos, explorando **engenharia social** e a confiança em contatos conhecidos.

Após a extração do arquivo, um script VBScript (`.vbs`) é executado, iniciando a cadeia de execução do malware.

Pedro Alisson  
GitHub: https://github.com/pedro-alisson