## Kivy

>Neste diretório fica salvo todos os arquivos referentes a documentação especifica do kivy. 

O Kivy é um framework para desenvolvimento de aplicativos mobile com a linguagem python. Esse framework teve seu nascimento em 2011 e possui uma comunidade forte e presente no desenvolvimento de suas soluções. Kivy é totalmente de graça. Mesmo se seu projeto estiver lucrando em cima de soluções desenvolvidas com Kivy, você não deve nada à comunidade Kivy.

Com Kivy tudo é rápido, isso se aplica tanto à velocidade de desenvolvimento quanto à velocidade de execução dos aplicativos criados com Kivy. Para ser rápido, o Kivy foi otimizado de diversas formas. Alguns de seus módulos mais críticos foram feitos inteiramente em C, para utilizar o poder de seus compiladores.

Uma grande característica do Kivy é a questão multiplataforma, que roda tanto em dispositivos mobile como também em desktops. Por ser escrito com python o código do nosso projeto com Kivy fica bem menor comparado a outros frameworks de mercado.

### Estrutura

- Api

Pasta que contém os arquivos referentes a comunicação com a Api.

- Home

Pasta que contém os arquivos referentes a tela principal do aplicativo.

- Imgs

Pasta que contém as imagens utilizadas pelo projeto.

- Login

Pasta que contém os arquivos referentes a tela de login do aplicativo.

- Manager

Pasta que contém os arquivos que gerenciam o comportamento padrão das telas.

- .gitignore

É apenas um arquivo para que no repositório git não seja versionado arquivos temporários.

- Main.py

Arquivo principal que é executado para inicialização da aplicação.

- Readme.md

Arquivo que contém os comandos necessários para executar o aplicativo localmente.

- Requirements.txt

Arquivo onde registramos todos os pacotes necessários para a execução da aplicação.

### Preparando Ambiente

Para executar o aplicativo primeiro é necessário que o Kivy esteja instalado. Para instalar o Kivy precisamos que o Python esteja instalado na nossa máquina, com isso executando os comandos abaixo teremos o Kivy em nosso ambiente e assim estaremos prontos para executar nossa aplicação.

    python -m pip install --upgrade pip wheel setuptools
    python -m pip install docutils pygments pypiwin32 kivy.deps.sdl2 kivy.deps.glew
    python -m pip install kivy.deps.gstreamer
    python -m pip install kivy.deps.angle
    python -m pip install kivy 

### Instalando Dependências

Após instalar o Kivy precisamos baixar todas a dependência especificas e necessárias para o nosso projeto, fazemos isso executando o comaando abaixo.

    pip install -r requirements.txt

### Executando Aplicativo

Agora para abrir o aplicativo entre na pasta do aplicativo e execute o comando abaixo.

    python main.py

Com isso o Kivy abrirá o aplicativo 