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

Todos os trechos e descrições foram **sanitizados**, mantendo apenas informações necessárias para compreensão da técnica e do comportamento observados.

---

## Autor

Pedro Alisson  
GitHub: https://github.com/pedro-alisson
