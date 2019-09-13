## 1. Introdução  

<p  align="justify">&emsp;&emsp;Este documento visa apresentar a arquitetura de software aplicada no desenvolvimento do sistema gerenciador de irrigação, o Irri, garantindo uma facilidade de visualização dos requisitos e da estrutura para com os desenvolvedores.</p>

### 1.1 Finalidade  

<p  align="justify">&emsp;&emsp;Ao esboçar uma visão ampla das arquiteturas associada ao sistema, é possível evidenciar seus aspectos. Sendo assim, este documento procurará transparecer as decisões arquiteturais que foram tomadas, complementando com uma robustez nas informações.</p>

### 1.2 Escopo

<p  align="justify">&emsp;&emsp;A aplicação Irri terá como finalidade gerenciar os sistemas de controle de irrigação de forma dinâmica e eficiente, controlando seus atuadores para que a irrigação, anteriormente agendada, seja feita de forma automática.</p>

<p  align="justify">&emsp;&emsp;O sistema geral corresponde no produto que realizará a irrigação, sendo um sistema de atuadores compondo o sistema de irrigação, em conjunto com sua respectiva central de monitoramento e gerenciamento, com o suporte de módulos medidores que farão a coleta dos dados do solo para serem enviadas à central, que terá a função gerenciar o funcionamento e analisar quando será mais apropriado realizar a irrigação.</p>

<p  align="justify">&emsp;&emsp;Logo, o sistema de irrigação será gerenciado pela aplicação Web/Mobile, fazendo o controle das centrais e dos módulos medidores, realizando agendamentos periódicos para a ativação dos atuadores com o objetivo de irrigar o local no tempo determinado, de forma inteligente, considerando outros fatores que podem influenciar na qualidade da irrigação.</p>

### 1.3 Visão Geral

<p  align="justify">&emsp;&emsp;O documento, através de quatro principais tópicos e suas ramificações, visa detalhar a arquitetura e os requisitos do software. Facilitando o desenvolvimento e esclarecendo dúvidas a respeito deste.</p>

Estrutura do documento:  

<html>
<ul>

<li> Introdução; </li>
<li> Representação da Arquitetura; </li>
<li> Metas e Restrições de Arquitetura; </li>
<li> Visão lógica;   </li>

</ul>
</html>

### 1.4 Definições, Acrônimos e Abreviações

<html>
<ul>

<li>API: Application Programming Interface</li>

</ul>
</html>

### 1.5 Referências


> MELO, Thalisson; ALVES, Álax; MARTINS, Lucas; RICHARD, Matheus; BERNARDO, Matheus de Sousa; Joranhezon. <b>Owla:</b> Documento de Arquitetura. Disponível em: <https://github.com/fga-gpp-mds/2016.2-Owla/wiki/Documento-de-Arquitetura>.

> André; Gabriel; Guilherme; ALMEIDA; Weyler. <b>Cidade Democrática:</b> Documento de Arquitetura. Disponível em: <https://github.com/fga-gpp-mds/2016.2-CidadeDemocratica/wiki/Documento-de-Arquitetura>.

> ENGINE YARD; Setup a Database Replication. Disponível em: <https://support.cloud.engineyard.com/hc/en-us/articles/205408108-Set-Up-Database-Replication>.


## 2. Representação da Arquitetura

### 2.1 Diagrama de Relações

<img src="https://github.com/PI2-Irri/docs/blob/master/Software/Imagens/arquitetura-completa.png?raw=true" class="center">

<p  align="justify">&emsp;&emsp;O projeto foi modelado para uma arquitetura híbrida, envolvendo a arquitetura distribuída vulgarmente denominada de arquitetura mestre/escravo e a arquitetura de microsserviços, a fim de dar uma boa dinamicidade e sendo mais apropriada pela estrutura exigida pelo produto geral.</p>

<p align=”justify”>&emsp;&emsp;O módulo que representa a arquitetura distribuída tem como finalidade trabalhar com pequenos serviços que possuem tarefas específicas, normalmente únicas, concentrando uma rede de informações e permitindo que o servidor supervisor consiga coletar, de forma precisa e já tratada, as informações necessárias solicitadas pelo serviço.</p>

<p align=”justify”>&emsp;&emsp;No caso do projeto, a arquitetura vem cobrir a necessidade de haver um serviço central que gerencie todos as centrais de controle que estão acopladas a cada sistema de irrigação, realizando um bom gerenciamento dos dados, centralizando no serviço ao qual deve ser feito a análise dos dados coletados.</p>

<img src="https://github.com/PI2-Irri/docs/blob/master/Software/Imagens/mestre-escravo.png?raw=true" class="center">

<p align=”justify”>&emsp;&emsp;Como informado imagem acima, o sistema é composto pelas centrais de controle realizando a coleta dos dados obtidos pelos sensores inclusos nos módulos medidores, onde o serviço central faz o controle de todos as centrais controladoras, centralizando todos os dados coletados.</p>

<p align="justify">&emsp;&emsp;Já, relacionado ao módulo arquitetural de microsserviços, foram definidos três principais, sendo eles o serviço para a obtenção de dados climáticos, o serviço gerenciador das centrais controladoras (servidor mestre da arquitetura distribuída) e o serviço de disponibilização de visualizadores para uma boa análise estatística dos dados coletados pelos módulos medidores e pelos atuadores.</p>

<img src="https://github.com/PI2-Irri/docs/blob/master/Software/Imagens/microsservicos.png?raw=true" class="center">

### 2.2 Tecnologias

#### 2.2.1 Django

<p align=”justify”>&emsp;&emsp;A tecnologia Django é um framework para desenvolvimento _web_, escrito em Python, que utiliza o padrão arquitetural model-template-view (MTV). Ele terá a finalidade de ajudar na construção das API’s de coleta climática como também no sistema gerenciador das centrais controladoras, pois a dinamicidade, praticidade e robustez que ele pode oferecer é de alto valor para o sistema.</p>

#### 2.2.2 VueJS

<p align=”justify”>&emsp;&emsp;O VueJS é um framework progressivo do JavaScript, de código aberto, para a construção da parte de interface para o usuário, popularmente descrita como FrontEnd. Com a facilidade de integração de novas bibliotecas e uma boa organização arquitetural dos componentes dispostos, ele será de fundamental importância para a criação da interface da aplicação, tornando mais prático o desenvolvimento.</p>

#### 2.2.3 Quasar

<p align=”justify”>&emsp;&emsp;O Quasar é um framework que trabalha em conjunto com o VueJS, sendo ideal para a criação de componentes e estruturas comuns em aplicações _web_, permitindo uma boa flexibilidade, garantindo um ambiente responsivo, fornecendo uma boa experiência de usuário tanto em dispositivos _mobile_ quanto em _Desktops_.</p>

## 3. Metas e Restrições de Arquitetura

<p align="justify">&emsp;&emsp;As restrições de arquitetura do projeto são:</p>

<html>
<ul>

<li>Utilização de um Banco de Dados <i>Postgres</i> para os serviços de gerenciamento das centrais controladoras e de coleta de dados climáticos. Já, para o serviço de disponibilização de visualizadores, será associado o banco de dados ElasticSearch, que tem uma boa dinamicidade para trabalhar com o serviço do Kibana para realizar a disponibilidade dos visualizadores.</li>
<li>Utilização da ferramenta Docker para a virtualização dos ambientes de forma prática e adequada.</i>
<li>Conexão com a internet necessária. </li>

</ul>
</html>

<p align="justify">&emsp;&emsp;As metas do projeto são:</p>

<html>
<ul>

<li> Disponibilizar uma aplicação bom uma boa usabilidade a fim de tornar prático e ágil o processo de agendamento de irrigação, como também o gerenciamento das centrais pertencentes ao cliente.</li>
<li>Cobrir os problemas relacionados à irrigação automática, como a necessidade do controle de regagem pela análise dos dados de tempo e do solo.</li>

</ul>
</html>
