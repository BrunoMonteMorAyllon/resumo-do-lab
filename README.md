# resumo-do-lab
Resumos do laboratorios do curso de Azure Essentials da DIO

Localizando Servicos por Categoria
1- Eles podem ser encontrados na tab "Todos os servicos", na qual estao organizados em categorias.
2- Os principais topicos focados ate o momento estao em Computacao, Redes e Armazenamento.
3- O Bastion vai ser utilizado para criar jump servers, que permitira criar um canal seguro para a transmissao de dados.
4- Nunca dependa de uma nova ferramenta ou servico em versao Preview, pois o suporte pode parar completamente.

Criando Maquinas Virtuais no Azure
1- Maquinas virtuais nao sao sujeitas as politicas de inatividade (descritas na SLA) dos outros servicos da Azure.
2- Maquinas virtuais podem ser criadas no tab de Computacao.
3- Podem ser criadas maquinas virtuais em ate 3 zonas de disponibilidade, que junto com um sistema de armazenamento com redundancia geografica (criando backups em diferentes zonas), aumentam a disponibilidade do sistema.

Configurando uma instância de Banco de Dados na Azure
1- Sempre e importante verificar as opcoes quando criamos u'a maquina virtual, escolhendo com cuidado as ferramentas necessarias para a tarefa.

Construindo Arquiteturas no Azure
1- Caso um servidor numa regiao brasileira tenha um par fora do Brasil, as leis de LGPD (protecao de dados) dizem que o cliente deve fazer um pedido para a Microsoft, autorizando e solicitando o backup fora do pais.
2- Utilize uma nomenclatura e tags claros, deixando claro o que cada recurso faz e quem deve pagar por eles.
3- Sempre siga o padrao de apenas conceder a minima permissao necessaria para realizar um trabalho, o que evita criar riscos de seguranca.
4- Podemos criar eventos automatizados para o resource group.
5- O log de atividade nos permite ver quem criou os recursos e quais foram as ultimas pessoas a utiliza-los.

Configurando Recursos e Dimensionamentos em Máquinas Virtuais na Azure:

1- Existem diferentes padroes de maquinas virtuais disponiveis, com diferentes prioridades (memoria, teste, etc), permitindo ao usuario escolher a melhor para um servico.
2- O modelo de dimensionamento deve ser cuidadosamente configurado para equilibrar custos e disponibilidade do servico. O tempo de consulta determina a duracao media que se espera de cada usuario.
3- Sempre configurar as portas de entrada para seguir boas praticas de seguranca.
4- Recomendado sempre manter a configuracao de SO de "Excluir com VM", evitando a criacao de discos orfaos.
5- Excluir of IP publico e a NIC quando a maquina virtual for excluida evita que uma placa grafica fique orfa.
6- Backups nao estao habilitados por default, mas ha boas opcoes para configuracoes padrao.
7- Quando escolhemos a linguagem de um aplicativo de funcoes, o sistema operacional e automaticamente escolhido.

Armazenamento na Azure
1- O sistema de desempenho premium possui uma velocidade maior, utilizando melhores discos, mas cobra por toda a alocacao (o standard cobra apenas pelo uso).
2- Quando uma conta de armazenamento e criada, a porta que e usada por default normalmente e 445, com o protocolo SMB. Cuidado que as operadoras normalmente bloqueiam essa porta.
3- Exclusao temporaria de blobs/arquivos retem um item excluido por 7 dias, criando uma seguranca contra apagar por acidente.
4- O AzCopy funciona em diferentes plataformas.

Identidade e Seguranca
1- Quando um usuario e criado na nuvem, ele nao e replicado localmente. Porem, a senha e replicada apenas para usuarios sincronizados.
2- Cuidado quando estiver definindo as regras de permissionamento dentro da nuvem (RBAC), pois e diferente do permissionamento para manipular contas de usuario.
3- On premise synch disabled significa que as contas existem apenas na nuvem.
4- As contas de usuarios que foram excluidos sao retidas por 30 dias, podendo ser restauradas nesse intervalo.
5- Para criar roles personalizados, o uso de Microsoft Premium Entra ID e necessario.
6- O Microsoft Defender for Cloud pode informar que tao conforme a cloud esta com o pardao de seguranca, em diferentes plataformas (AWS e GCP).
7- Alertas de seguranca de cloud podem ser configurados para serem enviados para a equipe.

Otimizando Custos no Azure
1- A pricing TCO calculator da Azure e a ferramenta fundamental para fazer estimativas de custos.
2 Primeiro definimos as cargas de trabalho, como determinar a informacao dos servidores, bancos de dados, armazenamento, rede, ambiente (Windows ou Linux)
3- As suposicoes incluem cobertura de maquina de software (economiza quando maquinas virtuais ou em instancias de maquinas utilizam of SQL server).
4- A estimative mostra diferentes estimativas comparando o armazenamento local com o da nuvem.
5- O preco dos servicos pode variar bastante dependendo da quantidade de horas ativas diarias, licensiamento e plano de reserva que utilizamos.
6- O cost management pode nos mostrar nossos custos atuais, assim como fazer sugestoes de como reduzir os gastors.
7- Podemos criar regras para fazer um recurse receber uma tag quando adicionado ao resource group.

Gerenciando Politicas em Acessos Azure
1- O site do service tr5ust da microsoft possui dados sobre os diferentes padroes regulatorios e recursos de conformidade para os varios paises que atende, que sao muito uteis para auditorias.
2- Podemos adicionar bloqueios a nivel de resource groups ao entrar em Resource Group->Locks. 
3- A partir do momento que um recuso sai do resource group, ele perde of lock, a menos que o lock tenha sido aplicado no proiprio recurso.
4- O Microsoft Purview pode fazer uma analyse de compliance e seguranca, apresentando recomendacoes.
5- O gerenciador de policies pode mostrar os recursos que estao dentro e fora de compliance dentro das politicas de um ambiente.
6- As policies apenas afetam o escopo para o qual foram anexadas.
7- Podemos criar uma politica em modo desabilitado, o que nos permite trabalhar nela ate estar pronta para ser testada.

Ferramentas de Implantação na Azure
1- O Azure Cloud Shell precisa de um storage account para funcionar.
2- ACS permite fazer o download e upload de arquivos com a sua interface.
3- No tab de Automation->CLI, ha uma referencia de diferentes comandos de Azure Cloud Line Interface e Power Shell.
4- Export Template permite criar um template em JSON, que pode ser usado para exportar uma VNET.
5- No azure.github.io/bicep/ contem o Bicep Playground, que permite comparar exemplos em Bicep e em ARM, o que o faz um recurso muito util.

Monitoramento Inteligente com o Azure
1- O Monitor pode nos dar informacao de aplicacoes, containers, VMs, alertas, etc.
2- O Service Health mostra o status de um servico em todas as regioes do mundo.
3- O Advisor score faz recomendacoes de como usar nossos recursos de maineira mais segura e eficiente.
