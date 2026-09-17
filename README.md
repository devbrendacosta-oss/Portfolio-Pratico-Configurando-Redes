# Portfólio Prático: Configuração de Rede Local LAN com Servidor DHCP — Topologia em Estrela

## Identificação Acadêmica

* **Instituição de Ensino:** Centro Universitário do Planalto Central Apparecido dos Santos (UNICEPLAC)
* **Curso:** Engenharia de Software
* **Disciplina:** Comunicação de Dados e Redes de Computadores
* **Orientador:** Profº Hudson Neves

## Equipe do Projeto

* Brenda Sousa Costa

---

## Descrição

Projeto prático de infraestrutura de rede local (LAN) em topologia em estrela simulado no **Cisco Packet Tracer**. O projeto contempla a montagem, configuração e validação de uma rede local com servidor dedicado de endereçamento dinâmico (DHCP) para automação da distribuição de IPs e testes de conectividade entre estações de trabalho e o servidor central.

Esta atividade consolida o aprendizado prático de estruturação de redes locais, aplicando distribuição dinâmica de endereços, automação de serviços essenciais e testes de validação de pacotes via protocolo ICMP e PDU.

---

## Objetivos

**Objetivo geral:** Montar, configurar e validar uma rede local básica no Cisco Packet Tracer, implementando um servidor de endereçamento dinâmico (DHCP) para automação de IPs e testando a comunicação entre estações de trabalho e o servidor central.

**Problema que o sistema resolve:** Elimina a necessidade de configuração manual de endereços IP estáticos em cada estação de trabalho, otimizando a administração da rede e reduzindo erros de configuração.

**Público-alvo:** Fins acadêmicos e estudo prático de redes de computadores.

---

## Funcionalidades Implementadas

- **Servidor DHCP Dedicado** — Distribuição dinâmica e automatizada de endereços IP para as estações conectadas.
- **Topologia em Estrela (Layer 2)** — Interconexão centralizada dos dispositivos por meio do Switch Cisco 2960.
- **Testes de Conectividade ICMP (Ping)** — Validação da comunicação entre os PCs e o servidor.
- **Simulação de PDU (Protocol Data Unit)** — Verificação visual da entrega de pacotes no modo de simulação.

### Itens da Infraestrutura e Topologia de Rede

- **Switch Layer 2:** 1 unidade — `Switch0` (Cisco 2960)
- **Servidor Local:** 1 unidade — `Server0` (Server-PT, com IP estático e DHCP ativo)
- **Dispositivos Finais:** 5 unidades — `PC0` a `PC4`
- **Cabeamento:** Cabos diretos (Copper Straight-Through) conectando cada dispositivo ao Switch.

### Topologia da Rede
<img width="793" height="717" alt="Captura de tela 2026-09-17 170427" src="https://github.com/user-attachments/assets/2f049a77-4224-4926-9a1c-7066957af67c" />

---

## Tecnologias Utilizadas

- Cisco Packet Tracer
- Cisco IOS
- Switch Cisco 2960
- Server-PT
- DHCP (Dynamic Host Configuration Protocol)
- ICMP (Ping)
- Ethernet (IEEE 802.3)

---

## Arquitetura da Solução

A organização da rede segue uma topologia física e lógica em estrela, centralizada no Switch Layer 2.

- **Camada de Concentração/Acesso:** O Switch Cisco 2960 interconecta todos os computadores e o servidor.
- **Camada de Serviços:** O `Server0` atua como servidor DHCP, distribuindo os endereços IP para as estações de trabalho.

### Detalhes Técnicos de Configuração

- **Endereçamento do Servidor:** O `Server0` foi configurado manualmente com o IP estático `192.168.1.10/24` e máscara `255.255.255.0`.
- **Pool DHCP:** O serviço DHCP foi configurado para iniciar a distribuição de endereços a partir de `192.168.1.100`.
- **Configuração dos Clientes:** Os cinco computadores foram configurados para obter seus endereços automaticamente por DHCP.

---

## Pré-requisitos

- Cisco Packet Tracer instalado (versão 8.x ou superior).

## Instalação

1. Faça o download ou clone este repositório.
2. Abra o arquivo de simulação da topologia `.pkt` no Cisco Packet Tracer.

## Como Executar

1. Abra o arquivo no Cisco Packet Tracer.
2. Aguarde a ativação dos links entre os dispositivos.
3. Acesse qualquer PC em `Desktop` → `IP Configuration`.
4. Confirme se a opção `DHCP` está selecionada e verifique o IP atribuído.
5. Abra o `Command Prompt` e execute:

    ping 192.168.1.10

---

## Tabela de Endereçamento IP

| Dispositivo | Nome no Packet Tracer | Tipo de Endereçamento | Endereço IP / Sub-rede | Gateway Padrão |
|---|---|---|---|---|
| Servidor DHCP | Server0 (Server-PT) | Estático | 192.168.1.10 / 255.255.255.0 | N/A |
| Switch Central | Switch0 (2960) | N/A | Concentrador Layer 2 | N/A |
| Estação 1 | PC0 | Dinâmico (DHCP) | 192.168.1.100 / 255.255.255.0 | N/A |
| Estação 2 | PC1 | Dinâmico (DHCP) | 192.168.1.101 / 255.255.255.0 | N/A |
| Estação 3 | PC2 | Dinâmico (DHCP) | 192.168.1.102 / 255.255.255.0 | N/A |
| Estação 4 | PC3 | Dinâmico (DHCP) | 192.168.1.103 / 255.255.255.0 | N/A |
| Estação 5 | PC4 | Dinâmico (DHCP) | 192.168.1.104 / 255.255.255.0 | N/A |

---

## Tabela de Portas e Alocação de Dispositivos

As portas abaixo foram conferidas de acordo com a topologia apresentada na captura do Cisco Packet Tracer.

| Dispositivo Origem | Interface Origem | Dispositivo Destino | Interface Destino | Tipo de Cabo |
|---|---|---|---|---|
| Server0 | FastEthernet0 | Switch0 | FastEthernet0/1 | Cabo Direto (Straight-Through) |
| PC0 | FastEthernet0 | Switch0 | FastEthernet0/2 | Cabo Direto (Straight-Through) |
| PC1 | FastEthernet0 | Switch0 | FastEthernet0/3 | Cabo Direto (Straight-Through) |
| PC2 | FastEthernet0 | Switch0 | FastEthernet0/4 | Cabo Direto (Straight-Through) |
| PC3 | FastEthernet0 | Switch0 | FastEthernet0/5 | Cabo Direto (Straight-Through) |
| PC4 | FastEthernet0 | Switch0 | FastEthernet0/6 | Cabo Direto (Straight-Through) |

---

## Comandos e Passos de Auditoria

- **Verificação do IP:** Abrir o `Command Prompt` no PC e executar `ipconfig`.
- **Teste ICMP:** Executar `ping 192.168.1.10`.
- **Modo Simulation:** Alterar para `Simulation`, criar uma PDU simples do PC para o servidor e clicar em `Play`.

---

## Exemplos de Uso / Evidências de Validação

### 1. Validação do DHCP

Atribuição automática de IP realizada nos computadores clientes a partir do endereço `192.168.1.100`.
<img width="995" height="717" alt="Captura de tela 2026-09-17 170522" src="https://github.com/user-attachments/assets/3484d6b8-47ed-4138-a90d-f55607e40817" />

### 2. Teste de Conectividade (Ping)

Execução do comando `ping 192.168.1.10` a partir dos computadores clientes:

    C:\> ping 192.168.1.10

    Pinging 192.168.1.10 with 32 bytes of data:

    Reply from 192.168.1.10: bytes=32 time<1ms TTL=128
    Reply from 192.168.1.10: bytes=32 time<1ms TTL=128
    Reply from 192.168.1.10: bytes=32 time<1ms TTL=128
    Reply from 192.168.1.10: bytes=32 time<1ms TTL=128

    Ping statistics for 192.168.1.10:
        Packets: Sent = 4, Received = 4, Lost = 0 (0% loss)

<img width="912" height="702" alt="Captura de tela 2026-09-17 171334" src="https://github.com/user-attachments/assets/8f2c78aa-765a-47d0-9041-05a8f514654d" />

### 3. Teste de Envio de PDU

Demonstração do envio de PDU pelo modo de simulação do Packet Tracer.

<img width="1365" height="713" alt="Captura de tela 2026-09-17 170801" src="https://github.com/user-attachments/assets/849163b4-3aff-4ca3-b50c-0348486b2494" />

---

## Estrutura do Projeto

    Portfolio-Pratico-Configurando-Redes/
    ├── Topologia_Rede_DHCP.pkt
    └── README.md

---

## Relatório dos Entregáveis Obrigatórios

| Entregável | Conteúdo | Status |
|---|---|---|
| 1. Repositório no GitHub | Repositório contendo o arquivo `.pkt` e o `README.md` | Concluído |
| 2. Validação do DHCP | Evidência da recepção automática de IP | Concluído |
| 3. Teste de Ping | Evidência da comunicação ICMP sem perda de pacotes | Concluído |
| 4. Teste de PDU | Evidência da simulação de envio de pacotes | Concluído |

---

## Manutenção e Ferramentas de Gerenciamento

- **Revisão contínua:** Atualizar a documentação caso novos dispositivos ou faixas de IP sejam adicionados.
- **Ferramentas utilizadas:** Cisco Packet Tracer para simulação de rede e GitHub para versionamento e documentação.

---

## Guia Passo a Passo para Execução dos Testes

1. Baixe o arquivo `.pkt` deste repositório e abra-o no Cisco Packet Tracer.
2. Confirme que todos os links físicos apresentam sinalização ativa.
3. Entre no `PC0`, abra `Desktop` → `IP Configuration` e selecione `DHCP`.
4. Confirme o endereço IP recebido.
5. Abra o `Command Prompt` e execute:

    ping 192.168.1.10

6. Alterne para o modo `Simulation`.
7. Selecione a ferramenta de PDU simples.
8. Clique no `PC0` e depois no `Server0`.
9. Execute a simulação e verifique a entrega do pacote.

---

## Status do Projeto

**Concluído** — Entregável acadêmico para a disciplina de Comunicação de Dados e Redes de Computadores.

---

## Melhorias Futuras

- Implementação de VLANs para segmentação da rede.
- Adição de um roteador para comunicação entre diferentes redes.
- Configuração de reservas de IP no servidor DHCP.
- Implementação de mecanismos adicionais de segurança.

---

## Licença

Exercício acadêmico desenvolvido para fins educacionais na disciplina de Comunicação de Dados e Redes de Computadores — UNICEPLAC. Uso restrito aos fins do curso.

---
