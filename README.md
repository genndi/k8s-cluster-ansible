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

1. Atualize o arquivo `inventory.ini` com os IPs das máquinas e as chaves SSH.

2. Execute o playbook:
   ```bash
   ansible-playbook -i inventory.ini k8s_cluster.yml
   ```

3. Após a execução, instale o plugin de rede no Master:
   ```bash
   kubectl apply -f https://docs.projectcalico.org/v3.25/manifests/calico.yaml
   ```

4. Verifique o status do cluster:
   ```bash
   kubectl get nodes
   ```

5. Pronto! Seu cluster Kubernetes está configurado. 🚀

## 📚 Estrutura do Repositório
- `inventory.ini`: Configuração das máquinas (Master e Workers).
- `k8s_cluster.yml`: Playbook principal do Ansible para provisionar o cluster.
- `README.md`: Este guia.

## 📌 Observações
- Este playbook foi projetado para ambientes de desenvolvimento ou teste.  
  Para uso em produção, recomenda-se:
  - Implementar medidas adicionais de segurança.
  - Adicionar monitoramento, backup e alta disponibilidade.
- Certifique-se de que as máquinas possam se comunicar sem bloqueios de rede ou firewall.

## 🤝 Contribuição
Contribuições são bem-vindas! Sinta-se à vontade para abrir **issues** ou enviar **pull requests**.

## 📜 Licença
Este projeto está licenciado sob a [MIT License](LICENSE).
