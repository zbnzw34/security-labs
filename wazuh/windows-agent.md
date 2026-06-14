# Integração de Agente Windows

## Objetivo

Integrar uma estação Windows 10 ao ambiente Wazuh para monitoramento centralizado de eventos de segurança.

## Ambiente

* Wazuh Server: Ubuntu Server 24.04
* Endpoint: Windows 10
* Comunicação: Rede interna do laboratório

## Componentes Envolvidos

### Wazuh Agent

Responsável por coletar eventos do endpoint Windows.

### Wazuh Manager

Responsável por receber e processar eventos enviados pelos agentes.

### Wazuh Indexer

Responsável pelo armazenamento dos eventos processados.

### Wazuh Dashboard

Interface utilizada para visualização e investigação dos eventos.

## Arquitetura

```text
Windows 10
    ↓
Wazuh Agent
    ↓
Wazuh Manager
    ↓
Filebeat
    ↓
Wazuh Indexer
    ↓
Wazuh Dashboard
```

O agente é responsável pela coleta de eventos no endpoint Windows.

Os eventos são enviados ao Wazuh Manager, processados por regras de correlação e armazenados no Wazuh Indexer para visualização através do Dashboard.
