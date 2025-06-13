# 📖 01 - Conceitos Básicos do Microsoft Azure

## Introdução ao Azure e Máquinas Virtuais (VMs) 🖥️

O Microsoft Azure é uma plataforma de computação em nuvem que oferece uma vasta gama de serviços, permitindo que empresas e desenvolvedores construam, testem, implantem e gerenciem aplicativos e serviços por meio de uma rede global de datacenters.

Entre os serviços mais fundamentais do Azure, as **Máquinas Virtuais (VMs)** se encaixam no modelo **IaaS (Infrastructure as a Service)**.

* **IaaS (Infrastructure as a Service):** Neste modelo de nuvem, o Azure gerencia a infraestrutura subjacente (como os servidores físicos, a rede de hardware, a virtualização e o datacenter). Como cliente, você é responsável pelo sistema operacional convidado, aplicações, dados, configurações de rede específicas e segurança dentro da VM.

## Modelo de Responsabilidade Compartilhada 🤝

É crucial entender o **Modelo de Responsabilidade Compartilhada** ao usar serviços em nuvem como o Azure. Ele define claramente quem é responsável por cada camada de segurança e gerenciamento:

* **Responsabilidade da Microsoft (Segurança *da* Nuvem):**
    * Infraestrutura física (data centers, cabos, hardware de rede).
    * Rede física (switches, roteadores do datacenter).
    * Host de virtualização (hypervisor).
    * Disponibilidade da plataforma Azure.
* **Responsabilidade do Cliente (Segurança *na* Nuvem):**
    * **Sistema operacional da VM:** Gerenciamento, aplicação de patches, atualizações, configuração de firewall do SO.
    * **Aplicações:** Instalação, configuração e segurança das aplicações rodando na VM.
    * **Dados:** Gerenciamento dos dados armazenados nos discos da VM (incluindo backup e criptografia).
    * **Configuração de rede dentro da VM:** Regras de firewall internas, portas.
    * **Identidades e Acessos:** Gerenciamento de quem pode acessar a VM e suas aplicações.

**Dica 💡:** Sempre revise e compreenda suas responsabilidades para garantir que suas VMs estejam seguras, atualizadas e em conformidade com as políticas da sua organização.

## Recursos e Grupos de Recursos 📦

No Azure, tudo o que você cria e gerencia é considerado um **recurso**. Para organizar e gerenciar esses recursos de forma eficiente, utilizamos **Grupos de Recursos**.

* **Recursos:** Uma instância de um serviço que você provisiona, como uma Máquina Virtual, um Disco de Armazenamento, uma Rede Virtual, um Banco de Dados SQL, etc. Cada recurso tem um tipo, nome e está associado a uma assinatura e um grupo de recursos.
* **Grupos de Recursos:** São contêineres lógicos que agrupam recursos relacionados para um projeto, aplicação ou ambiente (ex: "AmbienteDeDesenvolvimento", "AppVendasProducao").
    * **Vantagens:**
        * **Gerenciamento do Ciclo de Vida:** Facilita a criação, atualização e exclusão de um conjunto completo de recursos como uma unidade única.
        * **Permissões e Políticas:** Permite aplicar permissões de controle de acesso baseado em função (RBAC) e políticas do Azure em todo o grupo, garantindo consistência.
        * **Faturamento:** Ajuda a organizar os custos, pois o faturamento é muitas vezes associado aos grupos de recursos.

**Dica 💡:** Planeje seus grupos de recursos cuidadosamente! Agrupe recursos que compartilham o mesmo ciclo de vida e que você gerencia em conjunto.
