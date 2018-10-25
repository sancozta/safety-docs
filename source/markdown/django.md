## Django

>Nesta seção podemos verificar todos os itens referentes a documentação específica do site construido com Django. Dentro da estrutura do projeto de integração o site Django tem a função de fornecer uma interface que permita a visualização das decteções de movimento além do registro de usuários e alterações dos dados.

A interface web foi construída para permitir aos usuários a criação de contas dentro do escopo do projeto, além da visualização, alteração e exclusão de dados. Seu desenvolvimento foi realizado sobre o framework web Django, um framework para aplicações web gratuito e de código aberto, escrito em Python.

Diferente do Flask o Django é mais robusto e trás em sua estrutura padrão um conjunto de configuraçãos encapsuladas e já presentes no framework que no caso do Flask você teria que instalar algum pacote para isso, porém no Django ele já trás isso para você e te deixa o trabalho apenas de realizar pequenas configurações como no caso do banco de dados.

A estrutura de um projeto Django já é bem definida e te permite criar mais de um aplicativo dentro da sua estrutura padrão, isso é ótimo pensando em aplicações mais robustas que tem que se comunicar com diversos componentes para ofecere um serviço final para o cliente. Porém para projetos menores frameworks como o Flask pode se bem mais viável.

Um ponto de destaque no Django é sua grande comunidade,  talvez seja a maior comunidade entre os web frameworks python da atualidade, isso significa um maior suporte para novos desenvolvedores, uma quantidade maior de problemas resolvidos e documentados. Tudo isso acaba criando uma atratividade muito grande na comunidade de novos desenvolvedores.

O código da parte web pode se encontrado no repositório [sancozta/safetydjango](https://github.com/sancozta/safetydjango) no Github. Vamos agora explicar sua estrutura e como esse projeto foi disponíbilizado na web atráves da utilização da plataforma heroku.

### Estrutura

- Polls

Aplicação criada dentro da estrutura do Django para criar a plataforma web onde foi desenvolvido todas as funcionalidades da parte web.

- Project

Essa pasta contem os arquivos de configurações gerais do Django, como sistemas de rotas entre as aplicações, configurações de bancos de dados utilizados pelos aplicativos como também configurações gerais.

- Staticfiles

Pasta necessária para que a aplicação esteja no padrão desejado pelo heroku para subir um aplicativo Django.

- Templates

Contém os templates padrões da interface interna do Django, é criada pelo próprio kickstart dos projetos Django. 

- .gitignore

Arquivo onde é colocado o nome dos arquivos e pastas que devem ser ignorados pelo git.

- Manage.py

Arquivo de inicialização do Django.

- Procfile

Arquivo necessário para que nosso projeto seja identificado e instalado pelo heroku.

- Readme.md

Arquivo que contém os comandos básicos para executar o projeto localmente.

- Requirements.txt

Arquivo que contém todos os pacotes necessários para que o projeto seja executado.

### Executando a Aplicação

Recomenda-se utilizar um terminal bash para facilitar o desenvolvimeto e criação do ambiente local. Com isso ceritifique-se que seu ambiente tenha o python instalado e com o Django e pip instalados, com isso podemos prosseguir. 

#### Verificando Ambiente

Você pode verificar se o django esta instalada executando o seguinte comando, assim você poderá verificar a versão do django instalada.

    python -m django --version

#### Criando um Novo Projeto

Para criar um novo projeto como django basta executa o comando abaixo, como já temos o projeto não é necessário executar este comando.

    django-admin startproject project

#### Instalando Dependências

Entre na pasta do projeto e execute o seguinte comando para realizar a instalação dos pacotes necessários.

	pip install -r requirements.txt

#### Preperando o Ambiente

Após instalar os pacotes necessários para o projeto, podemos agora utilizar o servidor local do python para trabalhar na nossa aplicação. Portanto dentro da pasta do nosso projeto execute o comando abaixo. Por padrão o servidor fica disponível na porta 8000 mais isso pode ser alterado colocado o número da porta após o runserver.

    python manage.py runserver

#### Utilizando a Aplicação

A aplicação disponibilizada consulta a api [sancozta/safetyflask](https://github.com/sancozta/safetyflask) portanto verifique a documentação da api antes de qualquer ação. Poís o funcionamento deste aplicativo depende das respostas que a api fornece.

#### Deploy no Heroku

Primerio é preciso que sua aplicação esteja em um repositório no GitHub para que esse tutorial te ajude, caso contrário haverá formas diferentes de se realizar isso. Caso sua aplicação já esteja no Github você pode prosseguir.

Para que tudo funcione corretamente é necessário que na raiz do seu projeto tenha um arquivo chamado **Procfile** com o seguinte código. Esse arquivo é interpretado pelo heroku e facilita a preparação do nosso ambiente para que nossa aplicação construinda com Django funcione perfeitalmente.

    web: gunicorn project.wsgi

Para subir sua aplicação no heroku, primeiro é necessário ter um conta na plataforma [Heroku](https://heroku.com). Depois de já logado na conta
acesse criar novo aplicativo, escolha o nome da aplicação e após sua criação vincule sua aplicação com o seu repositório do GitHub e realize o deploy.
Caso queira que sua aplicação seja atualizada automaticamente em todos os momentos que você realizar um alteração no seu código basta ativar a função de deploy automático.

Assim que você cria um aplicação o Heroku disponíbiliza um DNS com o sufixo herokuapp.com. Por Exemplo após subir nossa aplicação para o heroku dêmos o nome de safetydjango o heroku disponíbilizou a aplicação no DNS [safetydjango.herokuapp.com](https://safetydjango.herokuapp.com) podendo ser acessada pelos protocolos https e http.