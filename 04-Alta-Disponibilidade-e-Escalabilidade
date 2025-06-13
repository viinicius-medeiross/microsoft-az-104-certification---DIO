# 🚀 04 - Alta Disponibilidade e Escalabilidade em Máquinas Virtuais

Garantir que suas aplicações estejam sempre disponíveis e possam lidar com a demanda variável é crucial na nuvem. O Azure oferece diversas ferramentas para isso.

## Alta Disponibilidade (Resiliência a Falhas) 📈

A alta disponibilidade foca em proteger suas VMs contra falhas inesperadas ou manutenção planejada, garantindo que sua aplicação permaneça online.

### Conjuntos de Disponibilidade (Availability Sets) 🧱

* **O que são:** Um agrupamento lógico de VMs que permite ao Azure distribuir suas máquinas por diferentes domínios de falha e domínios de atualização dentro de um **único datacenter**.
* **Propósito:** Proteger contra falhas de hardware (energia, rede) e manutenção planejada que exigem reinicialização de hosts.
* **Componentes:**
    * **Domínios de Falha (Fault Domains):**
        * **Definição:** Representam um agrupamento físico de hardware que compartilha uma fonte de energia e um switch de rede comuns (pense em um rack de servidores).
        * **Benefício:** Se uma falha de hardware ocorrer em um domínio de falha, apenas as VMs nesse domínio serão afetadas, enquanto as VMs em outros domínios de falha continuarão funcionando.
    * **Domínios de Atualização (Update Domains):**
        * **Definição:** Grupos lógicos de VMs e hardware que podem ser reiniciados ao mesmo tempo durante a manutenção planejada da plataforma Azure.
        * **Benefício:** O Azure realiza a manutenção um domínio de atualização por vez, garantindo que nem todas as suas VMs sejam reiniciadas simultaneamente, minimizando o impacto no aplicativo.

### Zonas de Disponibilidade (Availability Zones) 🌍

* **O que são:** Locais físicos separados, independentes e tolerantes a falhas dentro de uma **região do Azure**. Cada Zona de Disponibilidade tem sua própria energia, resfriamento e rede isolados.
* **Propósito:** Proteger suas aplicações e dados de falhas de datacenter. Se uma Zona de Disponibilidade inteira ficar offline, suas VMs em outras Zonas de Disponibilidade na mesma região continuarão operando.
* **Nível de Proteção:** Oferecem um nível de resiliência superior aos Conjuntos de Disponibilidade, pois protegem contra falhas de infraestrutura mais amplas.

**Dica 💡:** Para a máxima disponibilidade em uma região, combine Zonas de Disponibilidade (para resiliência em datacenter) com Conjuntos de Disponibilidade dentro de cada zona (para resiliência de hardware no rack).

## Escalonamento de Máquinas Virtuais 📈

O escalonamento permite ajustar a capacidade de suas VMs para corresponder à demanda de carga de trabalho.

### Escalonamento Vertical (Scale Up/Down) vs. Escalonamento Horizontal (Scale Out/In) ↔️↕️

* **Escalonamento Vertical (Scale Up/Down):**
    * **O que é:** Aumentar (scale up) ou diminuir (scale down) os recursos (CPU, RAM, disco) de uma **única** máquina virtual.
    * **Exemplo:** Mudar uma VM de um tamanho D2s_v3 para um D4s_v3.
    * **Características:** Geralmente requer uma reinicialização da VM. Há um limite para o quanto uma VM pode crescer.
* **Escalonamento Horizontal (Scale Out/In):**
    * **O que é:** Adicionar (scale out) ou remover (scale in) **mais instâncias** de máquinas virtuais idênticas para lidar com a carga.
    * **Exemplo:** Aumentar de 2 para 4 VMs para lidar com um pico de tráfego.
    * **Características:** Oferece maior resiliência e escalabilidade "ilimitada". Ideal para aplicações distribuídas e sem estado.

### Virtual Machine Scale Sets (VMSS) 🚀

* **O que são:** Um recurso do Azure que permite implantar e gerenciar um conjunto de máquinas virtuais idênticas como uma única unidade lógica. O VMSS é a principal ferramenta para escalonamento horizontal.
* **Principal Vantagem:** **Escala Automática (Autoscale):**
    * Permite aumentar ou diminuir automaticamente o número de instâncias de VM com base em métricas de desempenho (CPU, uso de memória, tráfego de rede) ou em um agendamento.
    * **Exemplo:**
        * **Regra baseada em métrica:** Se o uso da CPU ultrapassar 85% por 5 minutos, adicione uma nova VM. Se o uso da CPU cair abaixo de 15% por 10 minutos, remova uma VM.
        * **Regra baseada em agendamento:** Adicione 2 VMs às 8h da manhã e remova-as às 18h, de segunda a sexta.
    * **Benefícios:** Otimiza custos (paga apenas pelos recursos que realmente usa) e garante que seu aplicativo tenha capacidade para lidar com a demanda sem intervenção manual constante.
* **Gerenciamento Simplificado:** Você gerencia todo o conjunto de VMs como uma única entidade, simplificando implantações e atualizações.

**Dica 💡:** Use VMSS para aplicações web, APIs e microsserviços que precisam de alta disponibilidade e capacidade de resposta a mudanças na demanda.
