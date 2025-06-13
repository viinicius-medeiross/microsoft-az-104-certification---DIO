# 🔐 03 - Redes e Segurança em Máquinas Virtuais

A rede e a segurança são pilares fundamentais na implantação de VMs no Azure. Configurações adequadas garantem que suas aplicações estejam acessíveis, mas protegidas.

## Redes Virtuais (VNets) e Sub-redes 🌐

* **Rede Virtual (VNet):** É o bloco de construção fundamental para sua rede privada no Azure. Uma VNet é um isolamento lógico da nuvem pública do Azure, onde você pode lançar suas VMs e outros serviços.
    * **Propósito:** Permite que suas VMs se comuniquem de forma segura entre si, com a internet e com redes locais (via VPN ou ExpressRoute).
* **Sub-redes:** Uma VNet pode ser dividida em uma ou mais sub-redes. As sub-redes permitem que você segmente a VNet em espaços de endereço menores e isolados.
    * **Vantagem:** Facilita a organização, aplicação de regras de segurança específicas (NSGs) para grupos de recursos e roteamento.

## Endereços IP (Público vs. Privado) 🚦

* **Endereço IP Privado:** Atribuído a VMs e outros recursos dentro de uma VNet. Permite a comunicação dentro da VNet e com redes conectadas (ex: sua rede local via VPN). Não é acessível diretamente da internet.
* **Endereço IP Público:** Atribuído a recursos (como VMs, Load Balancers) para permitir a comunicação de e para a internet.
    * **Dica 💡:** Por padrão, as VMs podem ter um IP público atribuído durante a criação para facilitar o acesso inicial, mas a melhor prática é **não expor VMs diretamente à internet** com IPs públicos para acesso administrativo (SSH/RDP).

## Grupos de Segurança de Rede (NSG) 🔒

Os NSGs são o firewall de nível de rede do Azure. Eles permitem ou negam o tráfego de rede para e de recursos do Azure em uma VNet, como VMs.

* **Regras de Segurança:** Os NSGs contêm regras de segurança que especificam:
    * **Direção:** Entrada (Inbound) ou Saída (Outbound).
    * **Prioridade:** Um número (quanto menor, maior a prioridade) que determina a ordem de processamento das regras.
    * **Origem/Destino:** Endereços IP, blocos CIDR, Service Tags ou Grupos de Segurança de Aplicativos (ASGs).
    * **Porta:** Porta de destino ou intervalo de portas.
    * **Protocolo:** TCP, UDP, ICMP, Any.
    * **Ação:** Permitir (Allow) ou Negar (Deny).
* **Regras Padrão de NSG:**
    * **Entrada (Inbound):** Por padrão, permitem tráfego da própria VNet e do Load Balancer do Azure. Há uma regra de baixa prioridade que **nega todo o resto do tráfego de entrada** (`DenyAllInBound`).
    * **Saída (Outbound):** Por padrão, permitem todo o tráfego de saída para a VNet e para a internet (`AllowInternetOutBound`).
    * **Dica 💡:** Sempre use o **Princípio do Menor Privilégio** ao configurar NSGs: permita apenas o tráfego estritamente necessário para que sua aplicação funcione.

## Conectividade Segura a VMs 🛡️

A segurança no acesso remoto às VMs é crítica para evitar ataques.

* **Azure Bastion:**
    * **O que é:** Um serviço PaaS (Platform as a Service) totalmente gerenciado pelo Azure que fornece conectividade SSH e RDP segura às suas VMs diretamente do portal do Azure (via navegador) ou clientes nativos.
    * **Principal Vantagem:** **Não expõe as portas RDP (3389) ou SSH (22) das suas VMs à internet pública.** O tráfego para a VM flui pela rede privada do Azure, aumentando drasticamente a postura de segurança.
    * **Dica 💡:** É a melhor prática para acesso administrativo a VMs no Azure.

* **Autenticação SSH com Par de Chaves:**
    * Para VMs Linux, o uso de pares de chaves SSH é significativamente mais seguro do que senhas.
    * **Funcionamento:** Uma chave pública é colocada na VM durante a criação, e você usa a chave privada correspondente em sua máquina local para autenticar a conexão.
    * **Melhor Prática:** **Proteja sua chave privada SSH com uma senha (passphrase)!** Isso adiciona uma camada extra de segurança, tornando a chave inútil se for roubada sem a senha.

---

**Dicas de Segurança em Rede:**

* Evite atribuir IPs públicos diretamente às suas VMs, a menos que seja estritamente necessário para uma aplicação pública. Use Load Balancers ou Application Gateways na frente de conjuntos de VMs.
* Sempre configure NSGs.
* Utilize o Azure Bastion para acesso remoto administrativo.
* Para conectividade híbrida (do seu datacenter local para o Azure), utilize VPN Gateway ou Azure ExpressRoute.
