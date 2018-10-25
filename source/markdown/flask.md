## Flask

>Nesta seção podemos verificar todos os itens referentes a documentação especifica da api Flask. Dentro da estrutura do projeto de integração a api tem um papel de grande importância pois tem o função de centralizar ações e registrar dados no nosso banco de dados.

Sendo considerada junto com o banco um componente central dentro do esquema do projeto que foi desenhado inicialmente a api junto com o banco de dados foi contruida primeiro e esteve presente durante todo o desenvolvimento do projeto, tanto pela plataforma web com django como também a aplicação mobile construida com kivy, assim também como a dectação dos movimento do o arduino enviando registro para a api.

Para construir a api foi utilizando o Flask que é um web framework de código aberto lançado em 2010 amplamente utilizado para Python. Seu funcionamento é bastante granular e extensivo, onde os desenvolvedores podem construir o que quiserem apenas juntanto partes do seus componentes, tornando o Flask fácil de entender e usar.

Seu desenvolvimento é muito rápido e pode chegar a surpreender, seu código é bastante simples é bem organizado por se tratar da linguagem python que tem uma das caracteristicas do seu design pattern a indenteção e poucas linhas de código comparadas a outras linguagens do mercado como java, c e php. A facilidade em integrar o banco de dados com a api não foi um problema, pelo contrário foi bastante rápida, ao contrário de outros web frameworks, o Flask não tem uma camada adicional de acesso ao banco de dados nem depende do ORM (Object-Relational Mapping). 

Outro ponto que podemos destacar no Flask foi sua simplicidade no trabalho com os verbos http tendo funções bem simples e de fácil utilização no trabalho com esses verbos. Isso mostrou-se uma caracteristica de destaque que embora esteja presente em outros frameworks no Flask isso ganha um caracter bastante simplista durante o desenvolvimento.

Outro ponto de destaque foi a criação de um middleware de autenticação para todas a rotas, podendo validar tokens que são enviados nas requisições de maneira simples e com poucas linhas de código.

O código da api pode se encontrado no repositório [sancozta/safetyflask](https://github.com/sancozta/safetyflask) no Github. Vamos agora explicar sua estrutura e como esse projeto foi disponíbilizado na web atráves da utilização da plataforma heroku.

### Estrutura

- Database

Pasta onde contém todos os dados para a criação e entendimento do banco de dados utilizado pela api para registrado os dados da integração.

- Docs

Dentro desta pasta esta presente um arquivo .json que pode ser carregado no aplicativo Postman, você pode fazer o download [aqui](https://www.getpostman.com/apps). Ao carregar esse arquivo no postman será possível visualizar todas a rotas que estão presentes na api e como testa-las. O postman é um aplicativo muito utilizado em projeto que trabalham com webservices e pode ajudar muito nesses trabalhos.

- Flaskr

Dentro desta pasta podemos visualizar o arquivo principal onde desenvolvemos todos as nossas rotas, o arquivo flaskr.py. Nele esta todas as rotas e
e as configurações para que o núcleo da api funcione.

- .gitignore

É apenas um arquivo para que no repositório git não seja versionado arquivos temporários.

- Procfile

Esse arquivo é imprescindível para hospedarmos nossa api na plataforma heroku, visto que ele é responsável por dizermos ao heroku como nossa aplicação deve ser tratada e qual tecnologia ela utiliza.

- Readme.md

O arquivo readme.md contém comando básico para que qualquer desenvolvedor possa executar a aplicação localmente em sua máquina apenas com simples comandos.

- Requirements.txt

Nesse arquivo podemos encontrar todos os pacotes necessários para que a aplicação seja executada. Executando o comando de instalação todos os pacotes são baixados, configurados e disponibilizados para a nossa aplicação.

### Executando a Aplicação

Recomenda-se utilizar um terminal bash para facilitar o desenvolvimeto e criação do ambiente local. Com isso ceritifique-se que seu ambiente tenha o python instalado e com o pip instalado, com isso podemos prosseguir. 

#### Preperando o Ambiente

Certifique-se que de baixar o projeto [sancozta/safetyflask](https://github.com/sancozta/safetyflask) e que esteja dentro da pasta do projeto. 
Com isso execute os comandos a seguir no terminal bash.

	pip install virtualenv
	virtualenv env
	source env/bin/activate

#### Instalando Dependências

Após preparar o ambiente com o virtualenv execute o seguinte comando para baixar, configurar e disponibilizar o pacotes para a nossa aplicação.

	pip install -r requirements.txt

#### Determinando Path do Diretório

Com os pacotes instalado e dentro da pasta do projeto execute o seguinte comando. 

	export FLASK_APP=flaskr/flaskr.py

#### Para Ambiente de Desenvolvimento

Para ativar o modo debug do flask execute o comando abaixo, assim poderemos ver com maior nível de detalhes os erros do flask.

	export FLASK_DEBUG=true

#### Executando Projeto

E por fim para executar o projeto localmente o flask nos permite subir um servidor local para facilitar nosso desenvolvimento, disponível em **localhost:5000**

	flask run

#### Deploy no Heroku

Primerio é preciso que sua aplicação esteja em um repositório no GitHub para que esse tutorial te ajude, caso contrário haverá formas diferentes de se realizar isso. Caso sua aplicação já esteja no Github você pode prosseguir.

Para que tudo funcione corretamente é necessário que na raiz do seu projeto tenha um arquivo chamado **Procfile** com o seguinte código. Esse arquivo é interpretado pelo heroku e facilita a preparação do nosso ambiente para que nossa api construinda com flask funcione perfeitalmente.

    web: gunicorn --chdir flaskr flaskr:app	

Para subir sua aplicação no heroku, primeiro é necessário ter um conta na plataforma [Heroku](https://heroku.com). Depois de já logado na conta
acesse criar novo aplicativo, escolha o nome da aplicação e após sua criação vincule sua aplicação com o seu repositório do GitHub e realize o deploy.
Caso queira que sua aplicação seja atualizada automaticamente em todos os momentos que você realizar um alteração no seu código basta ativar a função de deploy automático.

Assim que você cria um aplicação o Heroku disponíbiliza um DNS com o sufixo herokuapp.com. Por Exemplo após subir nossa aplicação para o heroku dêmos o nome de safetyflask o heroku disponíbilizou a aplicação no DNS [safetyflask.herokuapp.com](https://safetyflask.herokuapp.com) podendo ser acessada pelos protocolos https e http.