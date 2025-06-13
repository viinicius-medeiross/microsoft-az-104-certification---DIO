# 💡 06 - Troubleshooting e Dicas Úteis

Lidar com problemas em VMs é uma parte comum da administração. Aqui estão algumas dicas e soluções para desafios frequentes no Azure.

## Problemas Comuns de Conectividade 🕸️

Quando você não consegue se conectar à sua VM (via SSH ou RDP), as causas mais comuns estão relacionadas à rede:

1.  **Grupo de Segurança de Rede (NSG):**
    * **Sintoma:** Conexão recusada ou tempo limite.
    * **Solução:** Verifique as regras de entrada do NSG associado à sua VM (ou à sub-rede da VM). Certifique-se de que a porta de acesso (22 para SSH, 3389 para RDP) esteja permitida a partir do seu endereço IP de origem. Lembre-se que as regras são processadas por prioridade.
2.  **Firewall do Sistema Operacional (SO):**
    * **Sintoma:** Mesmo com o NSG correto, a conexão ainda falha.
    * **Solução:** Verifique o firewall interno do SO da VM. Para Windows, o Firewall do Windows Defender. Para Linux, `ufw` ou `firewalld`. Certifique-se de que as portas SSH/RDP estão abertas lá também.
3.  **Porta 445 Bloqueada (para Azure Files):**
    * **Sintoma:** Problemas ao mapear um compartilhamento de arquivos do Azure Files em sua máquina local (SMB).
    * **Problema:** Muitos provedores de internet (ISPs) e redes corporativas bloqueiam a porta 445 devido a preocupações de segurança históricas com o SMB.
    * **Solução:**
        * Verifique se a porta 445 está liberada no seu firewall local e no seu roteador.
        * Se seu ISP bloqueia, considere usar uma **Máquina Virtual no Azure** (VNet-to-VNet ou VM em Hub-Spoke) para acessar o compartilhamento de arquivos, ou uma VPN para o Azure.
        * Utilize o Azure File Sync ou AzCopy para transferências.

## Acesso Remoto Bloqueado ou Credenciais Inválidas 🚫

* **SSH (Linux):**
    * **Sintoma:** "Permission denied (publickey)".
    * **Solução:** Verifique se você está usando a chave privada SSH correta e se as permissões do arquivo da chave privada estão corretas (geralmente `chmod 400 sua_chave.pem` no Linux/macOS).
* **RDP (Windows):**
    * **Sintoma:** "Your credentials did not work".
    * **Solução:** Verifique o nome de usuário e a senha. Se esqueceu, você pode redefinir a senha da conta de administrador da VM através do portal do Azure (opção "Redefinir Senha" no painel da VM).

## Como Acessar Logs de Diagnóstico de VM 📜

* **Diagnóstico de Boot:** O Azure pode capturar logs de console serial e capturas de tela do processo de boot da sua VM. Isso é inestimável para solucionar problemas de inicialização da VM.
    * **Acesso:** No portal do Azure, navegue até sua VM e clique em "Diagnóstico de boot" em "Suporte + solução de problemas".
* **Logs do Sistema Operacional:** Para logs mais detalhados dentro da VM:
    * **Windows:** Visualizador de Eventos (Event Viewer).
    * **Linux:** `journalctl`, `dmesg`, logs em `/var/log`.

## Dicas para Otimização de Custos em VMs 💸

* **Desligar VMs Ociosas:** VMs paradas (status "Stopped (Deallocated)") não cobram por computação, apenas por armazenamento de disco. Desligue VMs de desenvolvimento/teste quando não estiverem em uso.
* **Redimensionar VMs (Scale Down):** Se uma VM estiver superdimensionada (CPU/memória subutilizados), redimensione-a para uma SKU menor que atenda às suas necessidades.
* **Reservas de Instâncias de VM:** Para cargas de trabalho estáveis e de longo prazo (1 ou 3 anos), comprar instâncias de VM reservadas pode gerar grandes descontos em comparação com o preço pay-as-you-go.
* **Azure Hybrid Benefit:** Se você tem licenças Windows Server ou SQL Server on-premises com Software Assurance, pode reutilizá-las no Azure para reduzir custos de VM.
* **Azure Advisor:** Use o Azure Advisor para obter recomendações personalizadas de otimização de custos e desempenho.

**Dica 💡:** Monitore o uso de recursos de suas VMs com o Azure Monitor para identificar oportunidades de otimização de custos.

---
