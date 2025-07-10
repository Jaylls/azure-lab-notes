# 📘 Azure Lab Notes

Este documento reúne resumos, anotações, comandos e boas práticas sobre o uso da Microsoft Azure. Ideal para estudo, referência rápida e apoio em laboratórios.

---

## 📑 Sumário

- [📖 Conceitos Básicos](#conceitos-básicos)
- [📖 Máquinas Virtuais](#máquinas-virtuais)
- [📖 Comandos Azure CLI](#comandos-azure-cli)
- [💡 Boas Práticas](#boas-práticas)

---

## 📖 Conceitos Básicos

### 📌 Estrutura Hierárquica

- **Conta Azure**: Conta associada a um email.
- **Subscription**: Contêiner para recursos, com controle de cobrança.
- **Resource Group**: Grupo lógico de recursos relacionados.
- **Resource**: Serviço criado dentro de um resource group (VM, Storage, etc).

### 📈 Regiões e Zonas

- **Region**: Localização geográfica do datacenter (Ex: East US, Brazil South)
- **Availability Zone**: Datacenters isolados dentro de uma região para alta disponibilidade.

### 📌 Principais Serviços

- **VMs**: Máquinas Virtuais
- **Blob Storage**: Armazenamento de objetos
- **Virtual Network (VNet)**: Rede privada na nuvem
- **App Services**: Hospedagem de aplicações web
- **Azure SQL Database**: Banco de dados gerenciado

---

## 📖 Máquinas Virtuais

### 📌 Conceitos

- VM é uma instância de computador virtualizada na nuvem.
- Escolha da Image (SO) e SKU (tamanho da VM)
- Network Security Group (NSG) para definir regras de acesso
- Disk Managed para armazenamento

### 📈 Comandos Azure CLI

```bash
# Criar resource group
az group create --name MeuResourceGroup --location eastus

# Criar VM
az vm create   --resource-group MeuResourceGroup   --name MinhaVM   --image UbuntuLTS   --size Standard_B2s   --admin-username azureuser   --generate-ssh-keys

# Listar VMs
az vm list --output table

# Parar VM
az vm stop --name MinhaVM --resource-group MeuResourceGroup
```

---

## 📖 Comandos Azure CLI

### 📌 Autenticação

```bash
az login
az account show
```

### 📌 Resource Group

```bash
az group create --name MeuRG --location eastus
az group list --output table
az group delete --name MeuRG
```

### 📌 Máquinas Virtuais

```bash
az vm list --output table
az vm start --name VMTeste --resource-group MeuRG
az vm stop --name VMTeste --resource-group MeuRG
```

---

## 💡 Boas Práticas

- Defina uma convenção de nomes (Ex: vm-prod-web-01)
- Organize recursos por Resource Groups
- Utilize Tags para categorização
- Defina políticas de segurança (NSG, RBAC)
- Mantenha backups e snapshots periódicos
- Utilize Availability Sets ou Zones para alta disponibilidade
- Sempre revise custos no Azure Cost Management

---

## 📌 Fim do Documento
