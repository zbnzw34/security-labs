# Instalação do Wazuh

## Objetivo

Realizar a implantação do Wazuh em ambiente Ubuntu Server para centralização e monitoramento de eventos de segurança.

## Ambiente

* Ubuntu Server 24.04 LTS
* VMware Workstation
* 8 GB RAM
* 60 GB Disco

## Etapas

### Atualização do Sistema

```bash
sudo apt update
sudo apt upgrade -y
```

### Download do Instalador

```bash
curl -sO https://packages.wazuh.com/4.12/wazuh-install.sh
```

### Permissão de Execução

```bash
chmod +x wazuh-install.sh
```

### Instalação

```bash
sudo ./wazuh-install.sh -a
```

## Evidências

* <img width="1383" height="630" alt="image" src="https://github.com/user-attachments/assets/303c560e-498f-41dc-8c51-b570af8c6fa7" />

* Inserir screenshots do dashboard

## Aprendizados

* Estrutura de componentes do Wazuh
* Processo de instalação e configuração
* Requisitos de infraestrutura
* Boas práticas para laboratórios de monitoramento
