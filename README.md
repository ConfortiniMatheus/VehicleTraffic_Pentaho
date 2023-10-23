# VehicleTraffic_Pentaho

No mundo atual, é possível obter dados sobre quase todas as coisas, a maioria dos processos executados por empresas registram valores em uma base de dados, e estes, são essenciais para tomadas de decisão. Por conta disso, ter uma estrutura capaz de processar uma grande gama de informações, para que ela esteja num formato ideal e permita uma melhor visualização é essencial. Esse estudo visa trazer os conceitos utilizados para que se possa criar um Data Warehouse, um banco de dados estruturado, para que esse processo possa ser facilitado. Utilizando-se do SQL Server, ferramenta de banco de dados relacional fornecida pela Microsoft, a qual pode operar em nuvem através da Azure, permitindo o acesso desses dados em qualquer lugar, possuindo também redundância e segurança desses dados através de criptografia. Além de abordar uma ferramenta de ETL (do inglês Extraction, Transformation and Loading) open source, que é o Pentaho Data Integration, capaz fornecer uma solução para executar esse processo muito importante, pois é a movimentação e manipulação desses dados, sem agregar um custo em sua versão Community, a qual já atende bem as necessidades. Com essa ferramenta também é possível automatizar um processo utilizando um arquivo .bat e o próprio agendador de tarefas do sistema operacional utilizado.

# Instalação

Para a execução desse projeto, foi necessário a instalação de alguns softwares, dentre ele o Pentaho Data Integration, o Java na versão 8u192 e o Microsoft SQL Server.

https://www.hitachivantara.com/en-us/products/pentaho-platform/data-integration-analytics/pentaho-community-edition.html

https://www.oracle.com/br/java/technologies/javase/javase8-archive-downloads.html

https://learn.microsoft.com/pt-br/sql/ssms/download-sql-server-management-studio-ssms?view=sql-server-2017

# Configuração

Também é preciso fazer a instalação e configuração do driver para comunicação entre o Pentaho e o Sql Server, o driver pode ser encontrado no seguinte link:
https://www.microsoft.com/pt-BR/download/details.aspx?id=11774

O driver deve ser descompactado e movido para a pasta data-integration > lib.
Último passo para estabelecer a comunicação entre as duas ferramentas, é a configuração do jndi, que deve ser feito no arquivo data-integration -> simple-jndi -> jdbc.properties, conforme o seguinte exemplo.

nome_conexão/type=javax.sql.DataSource
nome_conexão/driver=com.microsoft.sqlserver.jdbc.SQLServerDriver
nome_conexão/url=jdbc:sqlserver://ip:porta;databaseName=databaseName
nome_conexão/user=usuário
nome_conexão/password=senha
nome_conexão/maxWait=3600
