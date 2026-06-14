# First Windows Alert

## Objetivo

Validar a integração entre o agente Windows e o servidor Wazuh através da análise de um evento de segurança coletado e correlacionado pela plataforma.

---

## Cenário

Após a instalação e registro do agente Windows `WORKSTATION02`, foi realizada a validação da coleta de eventos através do Dashboard do Wazuh.

Durante a análise dos logs recebidos, foi identificado um alerta relacionado à alteração de grupos locais do Windows.

---

## Endpoint Monitorado

| Campo    | Valor          |
| -------- | -------------- |
| Hostname | PC01           |
| Domínio  | MARVEL.local   |
| Agente   | WORKSTATION02  |
| IP       | 192.168.36.130 |

### Evidência

<img width="1669" height="640" alt="image" src="https://github.com/user-attachments/assets/2c7a29c8-4d8f-4a84-9a9d-f79e7f532e91" />

```text
Agents Management → Summary
```

---

## Evento Detectado

O Wazuh identificou um evento de segurança proveniente do Windows Event Log.

| Campo      | Valor                               |
| ---------- | ----------------------------------- |
| Event ID   | 4732                                |
| Canal      | Security                            |
| Severidade | Audit Success                       |
| Origem     | Microsoft-Windows-Security-Auditing |

### Evidência

<img width="1298" height="473" alt="image" src="https://github.com/user-attachments/assets/67bc7d10-b801-49cc-864d-ccdf3d8198b7" />

```text
Discover
```

---

## Informações do Evento

O evento indica que um membro foi adicionado a um grupo local com segurança habilitada.

### Dados Observados

| Campo      | Valor             |
| ---------- | ----------------- |
| Usuário    | fcastle           |
| Computador | PC01.MARVEL.local |
| Grupo      | Usuários          |
| Event ID   | 4732              |

### Evidência

<img width="1067" height="464" alt="image" src="https://github.com/user-attachments/assets/98e059eb-0a06-4d88-a366-ac167a982e6c" />

* Event ID
* Usuário
* Computador
* Mensagem completa do evento

---

## Correlação Realizada pelo Wazuh

O mecanismo de regras do Wazuh processou o evento e gerou um alerta correspondente.

| Campo     | Valor               |
| --------- | ------------------- |
| Rule ID   | 60170               |
| Nível     | 5                   |

### Evidência

<img width="993" height="278" alt="image" src="https://github.com/user-attachments/assets/bad33a43-9475-4fc3-b1a9-65d4165bfaf0" />

* Rule ID
* Rule Level

---

## Enriquecimento MITRE ATT&CK

O alerta foi automaticamente associado ao framework MITRE ATT&CK.

| Campo   | Valor                |
| ------- | -------------------- |
| Técnica | T1484                |
| Táticas | Defense Evasion      |
| Táticas | Privilege Escalation |

### Evidência

<img width="885" height="177" alt="image" src="https://github.com/user-attachments/assets/25e5cf9e-ba02-42d0-b75c-ff41d8c4609a" />

---

## Fluxo do Evento

```text
Windows Event Log
        ↓
Wazuh Agent
        ↓
Wazuh Manager
        ↓
Engine de Regras
        ↓
Wazuh Indexer
        ↓
Dashboard
```

---

## Aprendizados

* Integração de endpoints Windows ao Wazuh
* Coleta de eventos através do Windows Event Log
* Investigação de alertas de segurança
* Interpretação de Event IDs do Windows
* Correlação automática de eventos
* Enriquecimento com MITRE ATT&CK
* Funcionamento prático de uma arquitetura SIEM

---

## Próximos Passos

* Implantação do Sysmon
* Integração com Active Directory
* Criação de regras customizadas
* Simulação de ataques controlados
* Casos de uso para detecção e resposta a incidentes
