# Data Engineer Project - 003
Desenvolvi a concepção do projeto por meio da união de habilidades já adquiridas com a aquisição de novos conhecimentos, visando ampliar e aprimorar minhas competências na área.

# Diagrama Abstrato do Projeto
-------------------------------

### *Análise Geral*

- Criação de alguns recursos dentro do ambiente da Microsoft Azure.
- Upload de arquivo para um Data Lake Gen2.
- Criação de uma aplicação no Azure Active Directory.
- Manuseio do ambiente do Databricks utilizando PySpark e Spark SQL.
- Conexão do Databricks com o Azure Data Lake.
- Processo de ETL (Extract, Transform and Load).
- Migração de dados para Azure SQL via JDBC.
- Integração Databricks + Power BI.

### *Análise detalhada do passo a passo*


## ***1º Etapa***

*Criar alguns recursos no ambiente Microsoft Azure para manipulação dos dados.*

### **1.	Resource Group criado.**

![image](https://user-images.githubusercontent.com/115668126/230512125-f5e44436-8422-450e-9e08-ab2910dff45e.png)

•	No Azure, um Resource Group é um contêiner lógico que serve para agrupar recursos relacionados em uma solução. Ele pode incluir recursos como máquinas virtuais, bancos de dados, redes virtuais, contas de armazenamento e muito mais.
<br><br>


### **1.1.	 Storage Account criado.**

![image](https://user-images.githubusercontent.com/115668126/230512332-18f1ce51-1444-4995-acda-1d5fda57b53a.png)

•	O Azure Storage Account é um serviço de armazenamento em nuvem altamente escalável, seguro e durável oferecido pelo Microsoft Azure. Ele é projetado para armazenar e gerenciar diferentes tipos de dados, como arquivos, imagens, vídeos, documentos, bancos de dados, entre outros.
<br><br>


### **1.2.	  Criação de um Container e Upload do arquivo no Azure Data Lake.**

*•	Container criado.*
![image](https://user-images.githubusercontent.com/115668126/230512434-35b262a1-785a-484e-ba68-fee1a42e4146.png)

*•	Upload do arquivo.*
![image](https://user-images.githubusercontent.com/115668126/230512478-3dfeac91-6e6b-4eaf-8ba1-9822f5998b4e.png)
<br><br>


## ***2º Etapa***

*Crie uma aplicação no Azure Active Directory.*

### **2.	  Aplicação no Azure AD criada.**
![image](https://user-images.githubusercontent.com/115668126/230513485-513f4af0-88cb-4ee7-9935-1417430ab19f.png)

•	Criar um registro de aplicativo (App Registration) no Azure Active Directory permite que você registre seu aplicativo para usar os recursos do Azure, como o Azure AD, o Microsoft Graph API e outros serviços do Azure.

•	Ao criar um registro de aplicativo, você está definindo um objeto de serviço que pode ser usado para autenticar e autorizar solicitações de aplicativos ao seu aplicativo no Azure. Em outras palavras, um registro de aplicativo permite que você autentique usuários em seu aplicativo, obtenha tokens de acesso, gerencie permissões de API e muito mais.
<br><br>



### **2.1.	  Criação da chave de aplicação.**

![image](https://user-images.githubusercontent.com/115668126/230513842-291467a4-4f53-4ef9-9983-a5397e91ca1a.png)

•	Criar uma chave no Azure AD é uma forma de autenticar seu aplicativo ou serviço no Azure Active Directory.

•	Quando você cria uma chave para um registro de aplicativo, o Azure gera um segredo compartilhado que pode ser usado para autenticar o aplicativo ou serviço ao acessar recursos protegidos pelo Azure AD. Essa chave é uma string de caracteres que deve ser mantida em segredo e só deve ser compartilhada com aplicativos confiáveis.
<br><br>



### **2.2.	  Adicionando Role Assignment ao Container (Storage Blob Data Contributor, Storage Blob Data Reader e Storage Blob Data Owner).**

![image](https://user-images.githubusercontent.com/115668126/230513972-c86771d4-3ed9-46fa-91e2-a474eadf1501.png)

•	As funções Storage Blob Data Owner, Contributor e Reader definem diferentes níveis de acesso e permissões para usuários que precisam interagir com dados armazenados em contas de armazenamento do Azure Blob. O objetivo dessas funções é fornecer controle granular sobre as ações que cada usuário pode realizar em relação aos dados, garantindo a segurança e a privacidade das informações armazenadas.
<br><br>


### **2.3.	   Permitindo acesso de Read e Write da chave criada para a aplicação.**

![image](https://user-images.githubusercontent.com/115668126/230514096-a9124fea-e4dc-4902-8292-f35fd8892326.png)

•	Ao dar permissão de leitura e gravação no Gerenciamento de ACL para um contêiner dentro do Azure, você está permitindo que os usuários gerenciem a segurança dos blobs dentro do contêiner, concedendo ou revogando permissões para outros usuários ou grupos em relação aos blobs.
<br><br>


## ***3º Etapa***

*Manuseamento no ambiente do Databricks (Criação de conta no Databricks Community, Cluster...).*

•	Databricks é um ambiente de computação em nuvem projetado para simplificar o processamento de grandes volumes de dados e a análise de dados em larga escala. É uma plataforma de análise de dados que fornece uma interface colaborativa e escalável para cientistas de dados, engenheiros de dados e outros profissionais de análise de dados.

### **3.	Conta no Databricks Community Edition criada.**

![image](https://user-images.githubusercontent.com/115668126/230514264-f2fb2627-64a6-4066-84f1-a2b78641a50b.png)
<br><br>


### **3.1.	  Criando um Cluster.**

![image](https://user-images.githubusercontent.com/115668126/230514330-088905ae-ac20-4c90-a5e5-96aedf560e46.png)

•	Um cluster Databricks é um grupo de máquinas virtuais (VMs) que trabalham juntas para processar cargas de trabalho de processamento de dados em larga escala no ambiente Databricks. Essas VMs são configuradas para executar o software do Apache Spark, que é a base do ambiente Databricks, permitindo a execução de cargas de trabalho de processamento de dados em escala.
<br><br>


### **3.2.	  Conexão do Databricks com o Azure Data Lake.**
### **3.3.	  Conectando o Notebook ao Cluster criado.**

![image](https://user-images.githubusercontent.com/115668126/230514425-708ef64e-147c-4ae5-a519-0325c2c90e64.png)
<br><br>


### **3.4.	Criando um ambiente para montagem da unidade de conexão com o Data Lake.**

![image](https://user-images.githubusercontent.com/115668126/230514797-6fce4a2d-916c-4096-a7b7-e87c6c43b1b3.png)

•	O dbutils é uma biblioteca de utilidades do ambiente Databricks que fornece uma ampla gama de funções para simplificar tarefas de gerenciamento de dados e do ambiente de computação. Ele é um pacote Python personalizado que contém várias classes e funções para trabalhar com os recursos do Databricks, como sistema de arquivos, armazenamento de dados, segredos, clusters, jobs, entre outros.

•	O comando "dbutils.fs.mkdirs("/mnt/ dadosdeproject003")" é usado no ambiente Databricks para criar um diretório chamado "dadosdeproject003" no local de montagem "/mnt".

•	-O comando "dbutils.fs.ls("/mnt")" é usado no ambiente Databricks para listar os diretórios e arquivos no local de montagem (mount point) "/mnt".
<br><br>


## ***4º Etapa***

*Importação dos dados - Data Lake -> Databricks.*

### **4.	  Comando para conexão com o Data Lake.**

![image](https://user-images.githubusercontent.com/115668126/230514954-1409be84-0107-48c7-9a66-7402721b8b2b.png)



        configs = {"fs.azure.account.auth.type": "OAuth",
       "fs.azure.account.oauth.provider.type": "org.apache.hadoop.fs.azurebfs.oauth2.ClientCredsTokenProvider",
       "fs.azure.account.oauth2.client.id": "(APPLICATION (CLIENT) ID DA APLICAÇÃO CRIADA NO AZURE AD)",
       "fs.azure.account.oauth2.client.secret": (VALUE DA KEY SECRET CRIADA NA APLICAÇÃO NO AZURE AD)",
       "fs.azure.account.oauth2.client.endpoint": "(LINK DO ENDPOINT DA APLICAÇÃO CRIADA,  OAuth 2.0 token endpoint (v1)) ",
       "fs.azure.createRemoteFileSystemDuringInitialization": "true"}


        dbutils.fs.mount(
        source = "abfss://(NOME DO CONTAINER)@(NOME DA STORAGE ACCOUNT).dfs.core.windows.net/",
        mount_point = "/mnt/(DIRETÓRIO CRIADO)",
        extra_configs = configs)


•	Esse comando é usado para montar um diretório da Azure Data Lake Storage Gen2 no Databricks. Ele usa o protocolo ABFS (Azure Blob File System) para se conectar ao armazenamento na nuvem. O parâmetro configs define as configurações de autenticação e autorização, como o tipo de autenticação, o ID do aplicativo (cliente) do Azure AD, a chave secreta do aplicativo, o endpoint de autenticação OAuth 2.0 e a opção de criação de um sistema de arquivos remoto durante a inicialização. O parâmetro source especifica o nome do contêiner e o nome da conta de armazenamento, e o parâmetro mount_point especifica o diretório em que o contêiner será montado no Databricks.
<br><br>


### **4.1.	   Conferindo o diretório de destino.**

![image](https://user-images.githubusercontent.com/115668126/230516194-f6bad313-69a6-4c94-8114-e36e74e88673.png)
<br><br>


## ***5º Etapa***

*Faça algumas transformações nesses dados/schema utilizando PySpark.*

### **5.	   Lendo arquivo que foi carregado do Data Lake para a pasta de destino no Databricks.**

![image](https://user-images.githubusercontent.com/115668126/230516305-5535d150-1989-473c-a245-3402ece6f830.png)
<br><br>


## **5.1.	    Alterando alguns DataTypes das colunas.**

*•	Datatypes das colunas antes da alteração*

![image](https://user-images.githubusercontent.com/115668126/230516401-a43d05d4-44fa-4eb8-88d7-ddd15711a5c0.png)


*•	Comando para alteração de DataType.*

![image](https://user-images.githubusercontent.com/115668126/230516439-013debb7-4172-4c49-b7ff-37e973c53184.png)
<br><br>


### **5.2.	  Criação de um Dataframe com uma agregação agrupado pelo restaurant.**

![image](https://user-images.githubusercontent.com/115668126/230516545-9bb4ad4b-7850-4a84-bb09-b58daae7c24d.png)
<br><br>


### **5.3.	   Criação de um dashboard com o Dataframe de agregação dentro do ambiente Databricks**

![image](https://user-images.githubusercontent.com/115668126/230516612-b54a73c0-00ce-4cfb-b7ca-e5ca3a13fc4f.png)
<br><br>


## ***6º Etapa***

*Crie uma base de dados com Spark SQL e Persista uma tabela gerenciada.*

### **6.	    Verificando bases de dados criadas e criando base de dado (dbdbproject003), utilizando PySpark.**

![image](https://user-images.githubusercontent.com/115668126/230516841-3b6358dd-c489-4732-a4be-1774669f249b.png)
<br><br>



### **6.1.	  Persistindo uma tabela gerenciada na base de dados.**

![image](https://user-images.githubusercontent.com/115668126/230516973-2801ba09-aed4-4f0d-848d-ee261f339e59.png)
<br><br>


## ***7º Etapa***

*Faça a ingestão desses dados para uma tabela no Azure SQL Server.*

### **7.	Criando tabela no Azure SQL para migração do Dataframe.**

![image](https://user-images.githubusercontent.com/115668126/230517064-efaa588b-d7e9-4128-aab2-4d547a8a080e.png)
<br><br>


### **7.1.	Lembrar de adicionar uma Firewall Rule no servidor Azure SQL!!!!**

![image](https://user-images.githubusercontent.com/115668126/230517122-c058a39b-c707-4e4b-a6e2-ae7171791817.png)
<br><br>


### **7.2.	   Criando uma conexão JDBC com o banco de dados do Azure SQL.**

Para fazer isso, é necessário as seguintes informações:

•	O nome do servidor do Azure SQL

•	O nome do banco de dados

•	O nome de usuário e senha da conta de login


O driver JDBC (Java Database Connectivity) é um software que permite a conexão de um aplicativo Java a um banco de dados por meio de uma API padrão. Ele atua como um intermediário entre o aplicativo Java e o banco de dados, permitindo a execução de consultas, inserções, atualizações e exclusões de dados no banco de dados.

        jdbc_url = "jdbc:sqlserver://{server_name}.database.windows.net:1433;database={database_name}"
        jdbc_driver = "com.microsoft.sqlserver.jdbc.SQLServerDriver"
        jdbc_username = "<seu_username>"
        jdbc_password = "<sua_senha>"

        connection_properties = {
            "user": jdbc_username,
            "password": jdbc_password,
            "driver": jdbc_driver
        }

        jdbc_url = jdbc_url.format(server_name="<seu_server_name>.database.windows.net", database_name="<seu_database_name>")
        
        
- Este código define as propriedades necessárias para se conectar a um banco de dados SQL Server usando o JDBC. O código cria uma URL JDBC para o banco de dados SQL Server com as informações do nome do servidor e nome do banco de dados. Além disso, define o driver JDBC necessário para se conectar ao banco de dados. Por fim, cria um dicionário com as informações de usuário e senha para a conexão e insere as informações do servidor e banco de dados na URL JDBC.
<br><br>



### **7.3.	   Salvando o DataFrame no banco de dados do Azure SQL.**

É possível executar está tarefa utilizando o método write do DataFrame e o formato JDBC.

        df.write \
          .format("jdbc") \
          .mode("overwrite") \
          .option("url", jdbc_url) \
          .option("dbtable", "<nome_da_tabela>") \
          .option("user", jdbc_username) \
          .option("password", jdbc_password) \
          .option("driver", jdbc_driver) \
          .save()
          
          
          
- Esse código é utilizado para escrever um DataFrame do Spark para uma tabela do SQL Server usando o JDBC (Java Database Connectivity). Ele define as opções de conexão, como a URL do banco de dados, a tabela de destino, as credenciais de usuário e senha, e o driver JDBC. Em seguida, ele chama a função save() para salvar os dados do DataFrame na tabela especificada. O modo overwrite indica que a tabela deve ser sobrescrita, caso já exista.




## ***8º Etapa***

*Faça a integração do Databricks com o Power BI.*

![image](https://user-images.githubusercontent.com/115668126/230517431-2dc9407c-3927-46d9-8204-1be983342e28.png)
<br><br>


### **8.	Executando a integração com Databricks.**

![image](https://user-images.githubusercontent.com/115668126/230517480-57fc80b6-3812-419e-be1d-3eee1edf3ad1.png)
<br><br>


### **8.1.	   Colocando as informações necessárias. (HostName e HTTP são encontrados no Cluster Databricks -> JDBC/ODBC.**

![image](https://user-images.githubusercontent.com/115668126/230517511-6061773c-2977-4493-b84f-687792581858.png)
<br><br>


### **8.2.	   Logar com a conta Databricks.**

![image](https://user-images.githubusercontent.com/115668126/230517566-013dd3b6-0fcb-4c8d-ad8e-3be0d74f5b9f.png)
<br><br>


### **8.3.	   Selecionando tabela.**

![image](https://user-images.githubusercontent.com/115668126/230517599-28293c5b-b349-4626-8106-04ab32330473.png)
<br><br>


### **8.4.	   Dashboard criado apenas para demonstração da integração.**

![image](https://user-images.githubusercontent.com/115668126/230517653-7d90776c-1cbe-4827-9c50-4354d84b271d.png)
<br><br>


*Mini projeto feito para prática e estudo, toda dica será sempre bem vinda!*


