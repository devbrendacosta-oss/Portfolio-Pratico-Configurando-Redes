# Portfólio Prático: Configuração de Rede Local LAN com Servidor DHCP — Topologia em Estrela

---

## Identificação Acadêmica

* **Instituição de Ensino:** Centro Universitário do Planalto Central Apparecido dos Santos (UNICEPLAC)
* **Curso:** Engenharia de Software
* **Disciplina:** Comunicação de Dados e Redes de Computadores
* **Orientador:** Profº Hudson Neves

## Aluna:
* Brenda Sousa Costa

---

## Descrição

Projeto prático de infraestrutura de rede local (LAN) em topologia em estrela simulado no **Cisco Packet Tracer**. O projeto contempla a montagem, configuração e validação de uma rede local com servidor dedicado de endereçamento dinâmico (DHCP) para automação de distribuição de IPs e testes de conectividade entre estações de trabalho e o servidor central.

Esta atividade consolida o aprendizado prático de estruturação de redes locais corporativas, aplicando distribuição dinâmica de endereços, automação de serviços essenciais e testes de validação de pacotes via protocolo ICMP e PDU. O documento segue os padrões de documentação técnica para registro e auditoria de arquitetura de redes.

## Objetivos

**Objetivo geral:** Montar, configurar e validar uma rede local básica no Cisco Packet Tracer, implementando um servidor de endereçamento dinâmico (DHCP) para automação de IPs e testando a comunicação entre estações de trabalho e o servidor central.

**Problema que o sistema resolve:** Elimina a necessidade de configuração manual de endereços IP estáticos em cada estação de trabalho, otimizando a administração da rede, reduzindo erros de duplicação de IP e garantindo conectividade automatizada.

**Público-alvo:** Fins acadêmicos e estudo prático de redes de computadores.

---

## Funcionalidades Implementadas

- **Servidor DHCP Dedicado** — Distribuição dinâmica e automatizada de endereços IP para todas as estações conectadas.
- **Topologia em Estrela (Layer 2)** — Interconexão centralizada de dispositivos por meio de Switch Cisco 2960.
- **Testes de Conectividade ICMP (Ping)** — Validação da comunicação bidirecional entre os PCs e o Servidor.
- **Simulação de PDU (Protocol Data Unit)** — Verificação visual da entrega de pacotes de dados no modo simulação.

### Itens da Infraestrutura e Topologia de Rede

- **Switch Layer 2:** 1 unidade — `Switch0` (Modelo Cisco 2960, atuando como concentrador central)
- **Servidor Local:** 1 unidade — `Server0` (Server-PT, configurado com IP estático e serviço DHCP ativo)
- **Dispositivos Finais:** 5 unidades — `PC0` a `PC4` (Computadores clientes configurados em modo DHCP)
- **Cabeamento:** Cabos diretos (Copper Straight-Through) conectando cada dispositivo a uma porta FastEthernet do Switch

---

## Tecnologias Utilizadas

- Cisco Packet Tracer
- Cisco IOS (Switch 2960 e Server-PT)
- Protocolos e Serviços: DHCP (Dynamic Host Configuration Protocol), ICMP (Ping), Ethernet (IEEE 802.3)

---

## Arquitetura da Solução

A organização da rede segue uma topologia física e lógica em estrela centrada no Switch Layer 2:

- **Camada de Concentração/Acesso:** O Switch Cisco 2960 interconecta todas as portas de acesso dos computadores e do servidor.
- **Camada de Serviços:** O `Server0` atua na rede local distribuindo as requisições de DHCP para as estações de trabalho.

### Detalhes Técnicos de Configuração

- **Endereçamento do Servidor:** O `Server0` foi configurado manualmente com o IP estático `192.168.1.10/24` e máscara `255.255.255.0`.
- **Pool do Servidor DHCP:** O serviço DHCP foi ativado no servidor para iniciar a distribuição de endereços IP dinâmicos a partir de `192.168.1.100`.
- **Configuração dos Clientes:** As placas de rede (NIC) dos 5 computadores foram alteradas do modo *Static* para *DHCP*, solicitando e recebendo as configurações automaticamente.

---

## Pré-requisitos

- Cisco Packet Tracer instalado (versão 8.x ou superior)

## Instalação

1. Faça o download ou clone este repositório.
2. Abra o arquivo de simulação da topologia `.pkt` contido na pasta do projeto.

## Como Executar

1. Abra o arquivo no Cisco Packet Tracer.
2. Aguarde a convergência do Switch (todas as luzes dos cabos na cor verde).
3. Acesse as configurações de rede de qualquer PC (`Desktop` -> `IP Configuration`) e confirme se a opção `DHCP` está selecionada e o IP atribuído.
4. Abra o `Command Prompt` em qualquer computador e execute o teste de conectividade:

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

Passos recomendados para auditar o estado de funcionamento da rede:

- **Verificação do IP via Prompt:** Abrir o `Command Prompt` no PC e digitar `ipconfig` para validar a concessão do IP via DHCP.
- **Teste ICMP:** Digitar `ping 192.168.1.10` para verificar se há resposta de eco por parte do servidor.
- **Modo Simulation:** Alterar a visualização para o modo `Simulation`, adicionar um envelope PDU Simples do PC ao Servidor e clicar em `Play` para acompanhar o tráfego.

---

## Exemplos de Uso / Evidências de Validação

### 1. Validação do DHCP

Atribuição automática de IP realizada com sucesso em todos os 5 computadores clientes a partir do endereço `192.168.1.100`.

<img width="905" height="573" alt="Atribuição Dinâmica de IP via DHCP" src="https://github.com/user-attachments/assets/a56eec14-1da0-4f18-9678-f50764a80fe9" />

### 2. Teste de Conectividade (Ping)

Execução do comando `ping 192.168.1.10` a partir dos computadores clientes demonstrando 0% de perda de pacotes:

C:\> ping 192.168.1.10

Pinging 192.168.1.10 with 32 bytes of data:

Reply from 192.168.1.10: bytes=32 time<1ms TTL=128
Reply from 192.168.1.10: bytes=32 time<1ms TTL=128
Reply from 192.168.1.10: bytes=32 time<1ms TTL=128
Reply from 192.168.1.10: bytes=32 time<1ms TTL=128

Ping statistics for 192.168.1.10:
    Packets: Sent = 4, Received = 4, Lost = 0 (0% loss)

### 3. Teste de Envio de PDU

Demonstração do envio de PDU pelo modo de simulação do Packet Tracer, confirmando o status de transmissão como *Successful*.

---

## Estrutura do Projeto

    ATIVIDADE-REDES/
    ├── Topologia_Rede_DHCP.pkt
    └── README.md

---

## Relatório dos Entregáveis Obrigatórios

| Entregável | Conteúdo | Status |
|---|---|---|
| 1. Repositório no GitHub | Repositório público contendo o arquivo da topologia `.pkt` e o documento `README.md` estruturado | Concluído |
| 2. Validação do DHCP | Evidência em captura de tela da recepção do IP automático a partir de 192.168.1.100 | Concluído |
| 3. Teste de Ping | Evidência em captura de tela da comunicação ICMP sem perda de pacotes | Concluído |
| 4. Teste de PDU | Evidência em captura de tela da simulação com status Successful | Concluído |

---

## Manutenção e Ferramentas de Gerenciamento

* **Revisão contínua:** A documentação deve ser mantida atualizada caso novos dispositivos ou faixas de IP sejam adicionados.

* **Ferramentas utilizadas:** Cisco Packet Tracer para simulação de rede; GitHub para versionamento de código e documentação.

---

## Guia Passo a Passo para Execução dos Testes

1. Baixe o arquivo `.pkt` deste repositório e execute-o no Cisco Packet Tracer.

2. Confirme que todos os links físicos (cabos) apresentam sinalização verde.

3. Entre no `PC0`, abra a janela `IP Configuration` e marque a opção `DHCP` para obter o endereço automático.

4. Abra o `Command Prompt` do `PC0` e execute:

    ping 192.168.1.10

5. Alterne para o modo de simulação, selecione a ferramenta de PDU simples, clique no `PC0` e depois no `Server0` para checar a confirmação de sucesso.

---

## Status do Projeto

**Concluído** — Entregável acadêmico completo para a disciplina de Comunicação de Dados e Redes de Computadores.

---

## Melhorias Futuras

* Implementação de segmentação de rede por meio de VLANs no Switch Cisco 2960.

* Adição de um Roteador para permitir o roteamento Inter-VLAN e saída de tráfego para redes externas.

* Configuração de reserva de IP no servidor DHCP para dispositivos específicos.

---

## Licença

"Projeto acadêmico desenvolvido para fins educacionais na disciplina de Comunicação de Dados e Redes de Computadores — UNICEPLAC. Uso restrito aos fins do curso."

---

## Conclusão

O projeto demonstrou com êxito a montagem e operacionalização de uma rede local em topologia em estrela acoplada a um servidor DHCP. A automação de endereçamento IP provou ser eficiente, e os testes efetuados no Cisco Packet Tracer (Ping e PDU) confirmaram a total conectividade e integridade do tráfego de dados entre as estações de trabalho e o servidor central.
