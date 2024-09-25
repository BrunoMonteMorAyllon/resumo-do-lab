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
