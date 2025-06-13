# 🔍 05 - Gerenciamento e Monitoramento de Máquinas Virtuais

Após a implantação, o gerenciamento contínuo e o monitoramento são essenciais para garantir o desempenho, a saúde e a segurança das suas VMs no Azure.

## Monitoramento Básico de VMs com Azure Monitor 📊

O **Azure Monitor** é o serviço de monitoramento centralizado do Azure que coleta, analisa e age sobre dados de telemetria de seus ambientes Azure e híbridos.

* **Métricas de Desempenho:** Você pode monitorar métricas chave de suas VMs, como:
    * Uso da CPU (percentual).
    * Uso de memória (percentual).
    * IOPS (operações de entrada/saída por segundo) do disco.
    * Latência do disco.
    * Bytes de rede de entrada/saída.
* **Visualização:** Os dados podem ser visualizados em gráficos e dashboards no portal do Azure.
* **Dica 💡:** Configure o Azure Monitor para coletar dados de diagnóstico de boot e logs do sistema operacional para facilitar a resolução de problemas.

### Alertas e Notificações 🔔

* Você pode configurar **alertas** no Azure Monitor para serem acionados quando uma métrica (ou um log) exceder um limite definido.
* **Exemplo:** Receber um alerta por e-mail ou SMS se o uso da CPU de uma VM ultrapassar 90% por mais de 5 minutos.
* **Ações:** Os alertas podem disparar várias ações, como enviar notificações, executar um webhook, iniciar um runbook de automação ou disparar uma ação de escalonamento automático.
* **Dica 💡:** Configure alertas para condições que indicam problemas de desempenho ou possíveis falhas iminentes.

## Azure Backup para VMs 💾

O **Azure Backup** é o serviço nativo do Azure para fazer backup e restaurar dados em ambientes de nuvem, incluindo suas máquinas virtuais.

* **Propósito:**
    * **Recuperação de Desastres:** Restaurar VMs inteiras em caso de falha de hardware grave ou desastre de datacenter (se combinado com replicação).
    * **Recuperação de Exclusão Acidental/Corrupção de Dados:** Restaurar arquivos individuais ou o sistema operacional para um ponto no tempo anterior a um incidente.
* **Funcionamento:**
    * Você configura uma **política de backup** que define a frequência dos backups (diário, semanal) e o período de retenção (por quanto tempo os backups são mantidos).
    * Os backups são armazenados em um **Cofre dos Serviços de Recuperação (Recovery Services Vault)**, que é um local seguro e replicado para seus dados de backup.
* **Recuperação:** Você pode restaurar:
    * Uma VM inteira (para o local original ou um novo).
    * Discos específicos.
    * Arquivos ou pastas individuais (recuperação de nível de item).

**Dica 💡:** O backup é uma responsabilidade do cliente no modelo IaaS. **Sempre configure o Azure Backup para suas VMs de produção.**

## Exclusão Reversível (Soft Delete) para Blob Storage 🗑️

Embora não seja exclusivo para VMs, o conceito de Exclusão Reversível é fundamental para a proteção de dados em armazenamento, incluindo os VHDs (discos rígidos virtuais) das suas VMs ou quaisquer blobs de log.

* **O que é:** Um recurso de proteção de dados que permite que você recupere dados que foram acidentalmente excluídos ou sobrescritos por um período configurável.
* **Funcionamento:** Quando a exclusão reversível está habilitada, um blob (ou snapshot, ou versão) excluído não é permanentemente apagado, mas sim marcado como "excluído suavemente" e retido por um determinado número de dias.
* **Benefício:** Atua como uma "lixeira" para seus dados de armazenamento, oferecendo uma janela de tempo para "desfazer" exclusões acidentais, minimizando a perda de dados.
* **Dica 💡:** Habilite a exclusão reversível em suas contas de armazenamento para uma camada extra de proteção contra erros humanos.
