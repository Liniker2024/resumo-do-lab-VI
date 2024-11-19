# resumo-do-lab-VI
Armazenamento

Nesse módulo, aprendemos que o Azure oferece várias ferramentas e serviços de armazenamento para atender a diferentes cenários e necessidades, desde armazenamento de arquivos e dados não estruturados até backup, recuperação e migração de dados para a nuvem.

Aqui, vou detalhar os principais serviços de armazenamento do Azure, estratégias de migração, redundância e opções de contas de armazenamento.

1. Ferramentas de Armazenamento do Azure:
   
Aqui estão as principais ferramentas e serviços de armazenamento no Azure:


1.1. Azure Blob Storage

O que é: O Azure Blob Storage é um serviço de armazenamento de objetos que permite armazenar grandes quantidades de dados não estruturados, como documentos, imagens, vídeos, backups, dados de IoT, etc.

Como funciona: Ele organiza os dados em containers e os arquivos são chamados de blobs. Pode ser acessado via HTTP ou HTTPS e suporta diferentes tipos de blobs: block blobs (dados de arquivos), append blobs (dados de log) e page blobs (arquivos de VHD ou discos de máquina virtual).

Uso comum: Armazenamento de arquivos, backups, logs, dados de aplicativos.


1.2. Azure Files

O que é: O Azure Files oferece compartilhamento de arquivos baseado em SMB (Server Message Block), permitindo que você crie e acesse sistemas de arquivos compartilhados na nuvem, como se fossem sistemas de arquivos locais.

Como funciona: Pode ser acessado como um disco mapeado em sistemas Windows ou Linux, o que facilita a migração de cargas de trabalho que dependem de sistemas de arquivos tradicionais.

Uso comum: Compartilhamento de arquivos, colaboração em tempo real, substituição de servidores de arquivos locais.


1.3. Azure Disks

O que é: O Azure Disk Storage oferece discos persistentes para uso em máquinas virtuais (VMs) do Azure.

Como funciona: Ele permite que você adicione discos gerenciados a VMs, que podem ser usados como armazenamento de sistema operacional (OS) ou como armazenamento de dados. O serviço oferece discos SSD e HDD, com opções de alto desempenho.

Uso comum: Armazenamento de VMs e dados de aplicativos em máquinas virtuais no Azure.


1.4. Azure Queue Storage

O que é: O Azure Queue Storage é um serviço de armazenamento de mensagens assíncronas, usado para armazenar mensagens que são lidas e processadas por sistemas distribuídos ou aplicações em nuvem.

Como funciona: As mensagens podem ser adicionadas a uma fila, e as aplicações podem processá-las em ordem. Ideal para comunicação entre serviços ou para execução de tarefas em segundo plano.

Uso comum: Armazenamento de mensagens para sistemas distribuídos e integração de aplicativos.


1.5. Azure Table Storage

O que é: O Azure Table Storage é uma solução de banco de dados NoSQL altamente escalável e de baixo custo, que armazena dados estruturados em tabelas.

Como funciona: A tabela armazena dados em formato de chave-valor, ideal para armazenar dados como logs, dados de telemetria, ou configurações de aplicativos.

Uso comum: Dados NoSQL, dados não relacionais com alto volume e baixa latência.


1.6. Azure Data Lake Storage

O que é: O Azure Data Lake Storage é uma solução de armazenamento de dados em larga escala, otimizada para análise de dados.

Como funciona: Ele combina as capacidades do Azure Blob Storage com a segurança e escalabilidade do Hadoop, sendo ideal para big data e análise de dados estruturados e não estruturados.

Uso comum: Armazenamento de grandes volumes de dados para análise, big data e machine learning.


2. Estratégias para Levar as Informações para a Nuvem

   
2.1. Avaliar a Carga de Trabalho

Antes de mover os dados para a nuvem, é importante entender o tipo de dados e a carga de trabalho. como:

Qual o volume de dados?, como os dados serão acessados? (leitura, escrita, ou ambos), há requisitos de latência? ou qual o custo de armazenamento desejado?


2.2. Opções de Armazenamento

Para dados não estruturados, como arquivos e imagens, Azure Blob Storage é a opção recomendada.

Para dados compartilhados, Azure Files é a solução.

Para grandes volumes de dados de análise, utilize Azure Data Lake Storage.


2.3. Estrutura de Segurança

Configure criptografia em repouso e em trânsito.

Utilize contas de acesso gerenciadas (managed identities) para maior segurança na autenticação.


2.4. Implementação Gradual

Migre os dados em etapas para evitar sobrecarregar a rede e garantir uma transição sem problemas.


3. Opções de Migração para o Azure


Azure oferece várias ferramentas e métodos para migração de dados:


3.1. Azure Data Box

O que é: Uma solução física de migração de dados em massa, ideal para grandes volumes (mais de 40TB).

Como funciona: Você recebe um dispositivo de armazenamento físico, transfere os dados para ele e o envia para o Azure. O serviço carrega os dados para o seu armazenamento na nuvem.

Uso comum: Migração de grandes volumes de dados que não podem ser transferidos pela rede.


3.2. Azure Migrate

O que é: Uma ferramenta de migração para mover máquinas virtuais, servidores e dados para o Azure.

Como funciona: Permite avaliar, planejar e executar migrações de servidores físicos ou virtuais para o Azure.

Uso comum: Migração de infraestrutura (máquinas virtuais e servidores).


3.3. AzCopy

O que é: Uma ferramenta de linha de comando para copiar dados entre o seu ambiente local e o Azure.

Como funciona: É ideal para a transferência de grandes volumes de dados via rede, utilizando a ferramenta em linha de comando.

Uso comum: Transferência de dados para Azure Blob Storage.


3.4. Azure Site Recovery

O que é: Ferramenta que permite a recuperação de desastres e migração de servidores físicos e virtuais para o Azure.

Como funciona: Ele replica servidores e VMs para a nuvem para recuperação de desastres ou migração contínua.

Uso comum: Migração de infraestruturas para o Azure e recuperação de desastres.


4. Opções de Redundância de Armazenamento
   
O Azure oferece várias opções de redundância para garantir a alta disponibilidade e proteção dos dados:

Locally Redundant Storage (LRS):

Armazena 3 cópias dos dados dentro de um único data center. É a opção mais econômica, mas tem a menor proteção geográfica.

Geo-Redundant Storage (GRS):

Armazena os dados em 3 cópias locais, além de replicar os dados para uma região geograficamente distante. Oferece maior proteção contra falhas regionais.

Read-Access Geo-Redundant Storage (RA-GRS):

Similar ao GRS, mas permite a leitura dos dados da região secundária em caso de falha na região primária.

Zone-Redundant Storage (ZRS):

Armazena os dados em múltiplas zonas de disponibilidade dentro de uma região, garantindo alta disponibilidade sem depender de replicação geográfica.

Premium Storage (para Blobs e Discos):

Usa SSDs para fornecer alta performance e baixa latência, ideal para cargas de trabalho que exigem alto desempenho, como bancos de dados ou VMs com grandes IOPS.


5. Opções de Conta de Armazenamento
   
As contas de armazenamento do Azure podem ser criadas com diferentes tipos de conta e tipos de acesso:

Conta de Armazenamento de Blobs: Focada em dados não estruturados, como arquivos e imagens.

Conta de Armazenamento de Arquivos: Focada no compartilhamento de arquivos SMB.

Conta de Armazenamento de Discos: Usada para armazenar discos de VMs.

Conta de Armazenamento de Dados de Tabela: Armazena dados NoSQL em formato de chave-valor.


Tipos de Acesso:

Hot: Para dados acessados com frequência.

Cool: Para dados acessados esporadicamente.

Archive: Para dados que não são acessados frequentemente, com menor custo de armazenamento.

