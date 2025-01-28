# Kubernetes Cluster Automation with Ansible 🚀

Este repositório contém um **playbook Ansible** projetado para configurar automaticamente um cluster Kubernetes com **1 Control Plane (Master)** e **2 Workers**. Ele automatiza todas as etapas, desde a instalação das dependências até a configuração do cluster, permitindo uma implantação eficiente e consistente.

## ✨ Recursos
- Configuração automatizada de um cluster Kubernetes usando **kubeadm**.
- Suporte à configuração de rede Docker para compatibilidade com Kubernetes.
- Desativação automática de `swap` e otimização do sistema operacional.
- Integração simplificada de Workers ao cluster com comandos dinâmicos.
- Compatível com **Calico** para provisionamento de redes.

## 🛠️ Pré-requisitos
- **Máquinas**:
  - 1 para o Master (Control Plane).
  - 2 para os Workers (Nodes).
- **Requisitos mínimos para cada máquina**:
  - CPU: 2 núcleos.
  - RAM: 2 GB.
  - Sistema Operacional: Ubuntu 20.04 ou superior.
- **Configuração SSH**:
  - Chave SSH configurada para acesso entre as máquinas (sem senha).

## 📋 Como usar
1. Clone o repositório:
   ```bash
   git clone https://github.com/seu-usuario/seu-repositorio.git
   cd seu-repositorio
