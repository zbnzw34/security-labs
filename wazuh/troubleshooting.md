# Troubleshooting Durante a Implantação do Wazuh

## Problema 1 - Espaço Insuficiente em Disco

### Sintoma

Durante a instalação do Wazuh o processo falhou apresentando erros relacionados à falta de espaço em disco.

### Diagnóstico

Verificação do armazenamento:

```bash
df -h
lsblk
pvs
vgs
lvs
```

Foi identificado que a máquina virtual possuía 75 GB de disco, porém apenas 10 GB estavam disponíveis no sistema operacional devido à configuração inicial do LVM.

### Solução

Expansão da partição, volume físico, volume lógico e sistema de arquivos.

### Resultado

O sistema passou de 10 GB para aproximadamente 72 GB disponíveis.

---

## Problema 2 - Comunicação do Windows com a Internet

### Sintoma

A instalação do agente Wazuh no Windows falhava ao tentar acessar packages.wazuh.com.

### Diagnóstico

A máquina Windows possuía apenas conexão com a rede interna do laboratório.

### Solução

Adição de uma segunda interface de rede configurada em NAT.

### Resultado

A máquina passou a ter acesso à Internet para download do agente sem perder comunicação com o laboratório.

---

## Problema 3 - Transferência de Arquivos Entre Máquinas

### Sintoma

Problemas com copiar e colar entre host e máquinas virtuais.

### Solução

Acesso via SSH e uso de compartilhamento de rede para transferência de arquivos.

### Resultado

Administração remota simplificada e maior produtividade durante a implantação.
