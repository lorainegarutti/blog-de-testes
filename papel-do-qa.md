<h1>O papel do QA em iterações ágeis</h1>

<p>
  Segundo Lisa Crispin e Janet Gregory no livro "Agile Testing", desenvolver e testar são duas etapas do mesmo processo de desenvolvimento de software, e a entrega ocorre quando os dois papéis trabalham de forma próxima para contribuir incrementalmente a cada iteração ágil.
</p>
<p>
  Diferente do gerenciamento Cascata, em ambientes ágeis o QA tem diferentes atividades ao longo de toda iteração (e mesmo antes dela começar). O time todo deve ser responsável pelas atividades de teste, mas nós somos responsáveis pela cultura de qualidade e por levantar questões sobre o que será desenvolvido.
</p>


<h2>O que adiantar antes mesmo da iteração começar?</h2>

<strong>1) Fazer planejamento de testes</strong>
<p>
  É realizado com intuito de mitigar os riscos analisados, conhecer as histórias e caminhos que serão automatizados, quais recursos de infraestrutura serão necessários para os ambientes de teste e como será disponibilizada a massa para testes.  
  <br />
  O maior benefício é permitir endereçar preocupações e antever soluções de bugs de alto risco. Neste momento não decidimos "como testar cada história" e sim "quais tipos de testes serão feitos" (pensando nos quadrantes de testes).  
  <br />
  Um dos objetivos deve ser preparar a infraestrutura de integração contínua para que os testes automatizados possam ser rodados numa pipeline e os builds serem feitos em ambiente estável o suficiente para os demais testes serem realizados.  
</p>
<br />

<strong>2) Obter ampla visão do produto</strong>
<p>
  Devemos entender como cada história afetará o sistema como um todo (principalmente os legados). 
  <br />
  É preciso coordenar previamente o envolvimento de terceiros no projeto, planejar tempo extra para testar a aplicação em conjunto, já que essa integração sempre tem alto risco e altas incertezas. É recomendado começar os testes de interfaces o mais cedo possível. 
  <br />
  Se for trabalhar em uma funcionalidade nova e com ferramentas novas, seja realista e considere os riscos envolvidos no processo.  
  <br />
  Caso tenha tido iterações anteriores e exista bugs reportados do sistema em produção, é importante priorizar e estimar a solução desses pois afetam diretamente o valor gerado para o cliente. 
</p>
<br />


<h2>O que fazer para não negligenciar os testes para o final da iteração?</h2>

<strong>1) Ajudar na definição das histórias a serem desenvolvidas</strong>
<p>
  Participamos das reuniões de planejamento de iteração com o objetivo principal de questionar aspectos da funcionalidade e definição do valor a ser entregue.  
  <br />
  Mantemos constante colaboração com clientes e desenvolvedores para escrever testes de alto nível, que guiarão o desenvolvimento das funcionalidades, elucidarão dúvidas e ilustrarão exemplos de usuários reais (testes de aceitação ou User Acceptance Tests).  
  <br />
  Também precisamos considerar todos os pontos de vista da mesma história, ajudando na definição de cenários alternativos. 
</p>
<br />

<strong>2) Auxiliar nas estimativas, na priorização e na análise de risco</strong>
<p>
  Precisamos fazer estimativas das atividades de programação e de teste, tanto para codificação de testes unitários quanto pra desenvolvimento de cenários end to end. Outra abordagem comum é a criação de colunas para identificação das tarefas que estão prontas para teste. Tarefas (ou histórias) estarão "finalizadas" somente quando estiverem completamente testadas. 
  <br />
  Podemos auxiliar na priorização e definição de story points através de questionamentos: "qual valor será entregue nessa história?", "como o usuário final utilizará a funcionalidade de fato?", "o que poderia acontecer de pior?", "quais considerações de teste poderiam modificar a estimativa?", "será trabalhoso conseguir massa para os testes?", "terá alguma dependência de terceiros ou riscos severos?". 
  <br />
  Uma rápida análise de risco pode determinar a priorização e o foco dos testes da aplicação. Talvez seja uma história mais complexa ou que tenha foco na segurança, usabilidade, performance, etc..  
</p>
<br />

<strong>3) Escrever os testes em alto nível em primeiro lugar</strong>
<p>
  Quando as histórias tiverem sido divididas em tarefas menores, começamos a escrever os casos de teste em alto nível. Revê-los com clientes aumenta a transparência e a confiança e melhora a comunicação, mas também é necessário fazer o alinhamento de expectativas com os programadores, que podem utilizá-los para guiar o desenvolvimento. 
  <br />
  Conforme pequenos pedaços testáveis de código são produzidos, podemos começar a automatizar, mesmo sem ter a interface disponível. O primeiro e mais simples cenário deve ser o caminho feliz para garantir que a funcionalidade principal está entregando o valor esperado. Depois que o mínimo foi garantido, podemos adicionar mais casos de teste e utilizar edge cases.  
</p>
<br />

<strong>4) Testar incrementalmente</strong>
<p>
  Assim que testes automatizados já estiverem garantindo alguma qualidade da funcionalidade, é o momento de começar os testes exploratórios: tente cenários diferentes e observe se o comportamento está alinhado com o esperado. Se o resultado desses testes apresentar uma funcionalidade que não tinha sido coberta anteriormente, novas histórias de desenvolvimento podem ser criadas para próximas iterações. 
  <br />
  Assim que a interface estiver pronta já é indicado mostrá-la aos usuários para obter feedbacks rápidos (teste de aceitação) pois podemos descobrir algo que não estava claro anteriormente.  
  <br />
  Num cenário ideal, já há um conjunto de testes automatizados de regressão que está rodando numa pipeline integração contínua. Caso não seja sua realidade, esta infraestrutura deverá ser a prioridade do time.  
  <br />
  O objetivo dos testes de regressão é detectar mudanças inesperadas que afetam o sistema mas que não perceberíamos facilmente de forma manual. Caso tenha um conjunto rodando, poderá adicionar outros casos críticos para a funcionalidade conforme for evoluindo.   
  <br />
  Programadores deveriam rodar todos os testes unitários antes de mandar o código para a integração. Caso algum desses testes falhe, a prioridade é resolver os bugs. A integração contínua deve ser rápida e, por isso, os testes da pipeline não podem ser demorados. Testes mais longos, como os de integração e end to end , por exemplo, devem ser programados periodicamente e rodados separadamente. 
</p>
<br />

<strong>5) Resolver bugs assim que forem detectados</strong>
<p>
  Mostrar os bugs para os programadores sempre será mais eficiente do que reportá-lo em alguma ferramenta. Caso não haja ninguém disponível para resolver naquele exato momento, reportar é o mais indicado. 
  <br />
  Solucionar bugs são prioridades em relação a novas funcionalidades. Quando em produção acumulam débito técnico que precisará ser resolvido em um futuro próximo, já que a má qualidade geral do código fará a velocidade de entrega diminuir. A solução é uma política de "zero bugs" ou planejar iterações de tempos em tempos apenas para resolver os problemas pendentes e refatorar os códigos para sustentabilidade do projeto. 
</p>
<br />

<strong>6) Ter documentação simples e dinâmica</strong>
<p>
  Os próprios casos de testes de alto nível e os relatórios gerados pela automatização servem como documentação em um ambiente ágil. Exceções poderão ser tratadas de acordo com exigências específicas da gerência ou dos clientes. 
</p>
<br />


<h2>O que fazer no final da iteração e na entrega da funcionalidade?</h2>

<strong>1) Chegou o "end game"</strong>
<p>
  Se a funcionalidade estiver estável e as tarefas de desenvolvimento foram finalizadas, é o momento de nos preocupar com o ambiente de pré-produção e de produção, contactar os administradores das bases de dados e todos que estejam relacionados. 
  <br />
  Testes de integração dos sistemas, de carga e de estresse serão aplicados em ambiente de pré-produção, pois é o mais próximo do de produção. Também serão feitos os últimos testes exploratórios focando no sistema como um todo em cenários end to end.  
</p>
<br />

<strong>2) Recolher feedbacks imediatos dos usuários</strong>
<p>
  O teste de aceitação do usuário (UAT) é focado em verificar a usabilidade da funcionalidade (parte de negócios do produto), e ele deve começar assim que algumas tarefas são finalizadas.  
  <br />
  Caso esteja trabalhando em funcionalidades para o grande público, existem os testes Alpha e Beta. O Alpha é para obter feedback da funcionalidade como um todo e o Beta para reportar os problemas encontrados. 
</p>
<br />
 
<strong>3) Colher métricas</strong>
<p>
  A porcentagem de cobertura de código vai medir se os módulos programados estão sendo testados, mas não garantem que a funcionalidade foi desenvolvida seguindo a expectativa do cliente.  
  <br />
  Muitas funcionalidades precisam de treinamento customizado para os usuários e nós somos alguns dos profissionais mais indicados para ministrá-lo, já que entendemos as demandas do negócio e sabemos como a funcionalidade foi desenvolvida. 
</p>
<br />
 
<strong>4) Buscar promover entrega contínua</strong>
<p>
  Quando produzimos pequenos incrementos de software com qualidade com determinada frequência, podemos escolher quando lançá-los.  
  <br />
  Pequenas entregas possuem menor risco de um impacto negativo gigantesco, principalmente se esse processo for automatizado e rápido. 
</p>
 
<br /> <br /> <br />

>> Baseado em "Agile Testing", págs 327 a 517 

 