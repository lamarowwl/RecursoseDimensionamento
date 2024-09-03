# Guia para Configurar Recursos e Dimensionamento de Máquinas Virtuais no Azure

Este guia passo a passo irá ajudá-lo a configurar recursos e dimensionar suas máquinas virtuais (VMs) no Azure, garantindo que elas atendam aos requisitos de desempenho e custo da sua aplicação.

## Pré-requisitos

Antes de começar, certifique-se de ter:

1. Uma conta ativa no Azure. Se você não tiver uma, pode criar uma [aqui](https://azure.microsoft.com/free/).
2. Acesso ao [Portal do Azure](https://portal.azure.com/).
3. Uma máquina virtual existente configurada no Azure. Para criar uma VM, consulte [este guia](#).

## Passo 1: Acesse o Portal do Azure

1. Vá para o [Portal do Azure](https://portal.azure.com/) e faça login com suas credenciais.

## Passo 2: Navegar para a Máquina Virtual

1. No painel de navegação à esquerda, clique em **Máquinas Virtuais**.
2. Selecione a máquina virtual que você deseja configurar.

## Passo 3: Configurar Recursos da Máquina Virtual

1. No painel da VM selecionada, vá até **Configurações** e clique em **Tamanho**.

### Dimensionamento da Máquina Virtual

2. **Tamanho da VM**: O tamanho da VM determina a quantidade de vCPUs, memória e armazenamento temporário disponíveis. Para alterar o tamanho da VM:
   - Revise a lista de tamanhos disponíveis. A lista exibirá opções recomendadas com base na configuração atual da VM.
   - Selecione o tamanho desejado com base nos requisitos de carga de trabalho. Cada tamanho tem diferentes combinações de recursos (CPU, memória, etc.).
   - Clique em **Redimensionar** para aplicar as mudanças.

**Observação**: Alguns tamanhos podem não estar disponíveis devido a restrições regionais ou limitações de recursos na sua assinatura.

## Passo 4: Configurar Escalabilidade Automática

1. No painel de configuração da máquina virtual, clique em **Escalabilidade automática** (se aplicável para conjuntos de dimensionamento de máquinas virtuais).

### Criar um Perfil de Escalabilidade Automática

2. Clique em **Configurar** para definir as regras de escalabilidade:
   - **Modo de Escalabilidade**: Selecione **Manual** ou **Automático**.
   - **Contagem mínima e máxima de instâncias**: Defina o número mínimo e máximo de instâncias da VM que o conjunto pode ter.
   - **Regras de escalabilidade**: Configure regras com base em métricas como CPU, memória ou outras métricas personalizadas. Por exemplo:
     - **Métrica**: Percentual de CPU.
     - **Condição**: Maior que 75%.
     - **Ação**: Aumentar o número de instâncias em 1.
   - **Intervalo de escalabilidade**: Defina o intervalo de monitoramento e a frequência das ações de escalabilidade.

3. Clique em **Salvar** para aplicar as configurações de escalabilidade automática.

## Passo 5: Configurar Recursos Adicionais

1. **Discos**: No painel de configuração da máquina virtual, clique em **Discos** para adicionar ou redimensionar discos de armazenamento:
   - **Adicionar Disco de Dados**: Clique em **+ Criar e anexar um novo disco** para adicionar um disco adicional.
   - **Redimensionar Disco Existente**: Selecione um disco existente e clique em **Configurações** para alterar o tipo ou o tamanho do disco.

2. **Rede**: Clique em **Rede** para configurar a interface de rede da VM, incluindo:
   - **Sub-redes e Grupos de Segurança de Rede (NSG)**: Modifique sub-redes e configure regras de firewall para controlar o tráfego de entrada e saída.
   - **Endereço IP Público**: Atribua ou remova um endereço IP público, conforme necessário.

## Passo 6: Monitoramento e Ajustes de Desempenho

1. **Monitoramento**: Utilize o **Azure Monitor** para rastrear o desempenho da sua VM e ajuste os recursos conforme necessário:
   - Configure **alertas de desempenho** para notificar quando certas métricas, como utilização de CPU ou memória, ultrapassarem os limites especificados.
   - Utilize **logs de diagnóstico** para coletar dados adicionais para análise.

2. **Ajustes de Desempenho**: Se observar que a VM está frequentemente sobrecarregada ou subutilizada, considere redimensioná-la novamente ou ajustar as regras de escalabilidade automática.

## Conclusão

Parabéns! Você configurou com sucesso os recursos e o dimensionamento de sua máquina virtual no Azure. Manter suas VMs dimensionadas corretamente é crucial para otimizar o desempenho e controlar os custos. Para mais informações sobre como gerenciar VMs no Azure, consulte a [documentação oficial do Azure](https://docs.microsoft.com/azure/virtual-machines/).