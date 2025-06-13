# ✨ 02 - Criação e Configuração de Máquinas Virtuais (VMs)

Criar e configurar uma máquina virtual no Azure é o primeiro passo para hospedar suas aplicações na nuvem. Existem várias opções e considerações importantes.

## Passo a Passo para Criar uma VM 🚀

Você pode criar VMs usando o **Azure Portal**, **Azure CLI** (Command-Line Interface) ou **Azure PowerShell**.

1.  **Escolha da Região:** Selecione a região geograficamente mais próxima de seus usuários para reduzir a latência, ou uma região que atenda aos seus requisitos de conformidade e soberania de dados.
2.  **Imagem (Sistema Operacional):**
    * **Windows:** Escolha entre várias versões do Windows Server ou até mesmo Windows Client para cenários específicos.
    * **Linux:** Grande variedade de distribuições como Ubuntu, RHEL, CentOS, Debian, SUSE, etc.
3.  **Tamanho (SKU da VM):** A "SKU" (Stock Keeping Unit) define a capacidade da VM em termos de vCPUs, RAM, IOPS do disco e tipo de armazenamento.
    * **Dica 💡:** Escolha o tamanho com base nos requisitos de desempenho da sua aplicação e no seu orçamento. O Azure oferece séries otimizadas para diferentes cargas de trabalho (uso geral, computação otimizada, memória otimizada, armazenamento otimizado, GPU).
4.  **Autenticação:**
    * **Windows VMs:** Usuário e senha (Nome de usuário e senha de administrador).
    * **Linux VMs:**
        * **Usuário e Senha:** Menos seguro, geralmente desaconselhado para acesso público.
        * **Par de Chaves SSH (Recomendado):** Mais seguro e a melhor prática. Você gera um par de chaves (pública e privada). A chave pública é colocada na VM, e você usa a chave privada para autenticar o acesso SSH.
            * **Dica 💡:** Sempre proteja sua chave privada SSH com uma senha (passphrase)!

## Discos de VM no Azure 💾

Os discos são essenciais para armazenar o sistema operacional, aplicações e dados das suas VMs.

* **Tipos de Discos Gerenciados (Managed Disks - Recomendado):** O Azure gerencia o armazenamento para você, garantindo durabilidade e alta disponibilidade dos discos.
    * **Standard HDD:** Mais econômico, ideal para cargas de trabalho não críticas ou de desenvolvimento/teste.
    * **Standard SSD:** Bom equilíbrio entre custo e desempenho, adequado para a maioria das cargas de trabalho de produção que exigem consistência.
    * **Premium SSD:** Maior desempenho, menor latência, ideal para cargas de trabalho de produção intensivas em I/O (ex: bancos de dados).
* **Discos Não Gerenciados:** Mais antigos, exigiam que o cliente gerenciasse as contas de armazenamento subjacentes. Quase sempre é recomendado usar Managed Disks hoje em dia.

### Anexar/Desanexar Discos de Dados

* Você pode adicionar discos de dados adicionais a uma VM para armazenar dados de aplicações.
* É possível anexar e desanexar discos de dados a uma VM em execução (hot attach/detach), dependendo do sistema operacional e do tipo de disco.

## Redimensionar VMs (Escalonamento Vertical) 📏

* **Escalonamento Vertical (Scale Up/Down):** Consiste em alterar o tamanho (SKU) de uma VM existente para aumentar (ou diminuir) sua capacidade de vCPUs, RAM ou IOPS.
* **Dica 💡:** Geralmente, um redimensionamento de VM requer uma reinicialização da máquina, causando uma breve indisponibilidade. Planeje essas operações para janelas de manutenção.

## Instalação Básica de Software (Extensões de Script) ✍️

* As **Extensões de Script Personalizado** (Custom Script Extensions) permitem que você execute scripts (PowerShell para Windows, Bash para Linux) na sua VM após ou durante a sua implantação.
* **Uso:** Automatizar tarefas como instalação de software, configuração do SO, ou execução de comandos de bootstrap.
* **Dica 💡:** Útil para tarefas de configuração inicial que não exigem interação manual após a criação da VM.

## Dicas para Otimização de Custos 💰

* Escolha o tamanho de VM correto para sua carga de trabalho, evitando superprovisionamento.
* Desligue VMs que não estão em uso (dev/test).
* Considere reservar instâncias de VM para cargas de trabalho estáveis de longo prazo para obter descontos significativos.
