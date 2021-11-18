#### Desenvolvimento de Plataforma BI para Monitoramento de Performance de Usinas Solares Fotovoltaicas

#### Aluno: Jun Fujise(https://github.com/jfujise94)
#### Orientador: [Felipe Borges](https://github.com/FelipeBorgesC)

---

Trabalho apresentado ao curso [BI MASTER](https://ica.puc-rio.ai/bi-master) como pré-requisito para conclusão de curso e obtenção de crédito na disciplina "Projetos de Sistemas Inteligentes de Apoio à Decisão".

- [Projeto.pdf](https://github.com/jfujise94/Trabalho-BI)

---

### Resumo

A diversidade de fornecedores de equipamentos fotovoltaicos torna o monitoramento das usinas solares uma tarefa trabalhosa e exaustiva, uma vez que os diferentes sistemas não são compatíveis um com os outros. O seguinte trabalho teve como objetivo criar um sistema de Business Intelligence capaz de realizar o monitoramento de diversas plantas solares fotovoltaicas em uma única plataforma. Para isso, um sistema de aquisição de dados foi criado utilizando um código Python, com os módulos selenium e BeautifulSoup4. O código acessa plataformas web para extrair os dados medidos pelos equipamentos fotovoltaicos e também atua como o ETL do processo. Em seguida, os dados foram armazenados em um banco de dados MySQL previamente configurado. Com os dados salvos e equalizados, um visualizador de dados foi criado utilizando o PowerBI para monitorar a geração das usinas solares, e, por fim, um sistema de alarmes foi criado, para enviar emails quando identifica algum problema nas usinas fotovoltaicas.

### Abstract
The diversity of suppliers of photovoltaic equipments made the monitoring of PV plants a hard and exhausting task, since the different systems are not comptible between each other. The present work aims to create a Business Intelligence system capable of monitoring several PV plants in a single platform. For that, a data acquisition system was created using a Python code with selenium and BeautifulSoup modules. The code accesses web apps to extract the data measured by the photovoltaic equipments, also, it is the ETL of the process. Then, the data are stored in a MySQL database, which was previously setup. With the stored and equalized data, a dashboard was created using PowerBI software to monitor the generation of the PV plants. Finally, an alarm system was created to send mails when it identifies any probles in the solar farms.


### 1. Introdução

A energia solar fotovoltaica é a tecnologia que converte a energia oriunda da radiação solar em energia elétrica a partir do efeito fotovoltaico. É caracterizada por ser uma energia de fonte limpa e renovável, por isso, está em foco nos dias atuais como uma das protagonistas na substituição das fontes fósseis de energia por alternativas menos impactantes para o meio ambiente. A popularidade da energia solar também deve-se ao fácil comissionamento de sistemas fotovoltaicos, inclusive no meio urbano. No Brasil, a energia solar proveniente de sistemas de geração distribuida é o modal que mais cresce atualmente.

Um sistema fotovoltaico residencial é composto principalmente pelos painéis fotovoltaicos, inversor, caixas de proteção, kit de fixação de painéis e sistema de aterramento. Os inversores geralmente possuem diversos sensores capazes de informar algumas informações importantes para o monitoramento da performance dos sistemas solares. Dados de voltagem, corrente, potência e energia gerada são algumas das variáveis que se costumam encontrar nestes monitoramentos.

A diversidade de equipamentos existente no mercado torna difícil um monitoramento eficiente de múltiplas plantas solares. Atualmente, os dados das usinas são obtidas através de plataformas web, sendo que cada fornecedor do equipamento tem a sua própria ferramenta. Assim, é necessário verificar diferentes plataformas para a avaliação da performance das plantas, o que pode consumir muito tempo e ser um trabalho exaustivo.

O seguinte trabalho tem como objetivo criar um protótipo de ferramenta de BI para integrar diferentes plataformas de monitoramento de sistemas solares fotovoltaicos. A ferramenta é composta por um sistema de aquisição de dados com web scrapers, banco de dados em nuvem, códigos Python para automação de processos e visualização de dados com o PowerBI.

### 2. Modelagem

A seguinte seção descreve com mais detalhes os diferentes módulos da ferramenta criada.

O sistema de aquisição de dados foi feito utilizando um código Python. Neste sistema, os pacotes selenium e BeatifulSoup4 foram utilizados para fazer a interface com as fontes de dados web e a interpretação do conteúdo. As plataformas acessadas neste trabalho foram dos fornecedores Solis (https://m.ginlong.com/login.html) e Hoymiles (https://m.hoymiles.com/platform/login). O código é rodado toda hora para a aquisição de dados de geração de energia dos diferentes sistemas fotovoltaicos cadastrados. A automação da rodada foi feita utilizando um arquivo bat e o agendador de tarefas nativo do Windows.

O banco de dados foi criado utilizando um serviço em nuvem de MySQL. A partir do MySQL Workbench, o design das tabelas foi feito, assim como o relacionamento entre elas. O esquema criado segue o Esquema Floco de Neve, sendo as tabelas dimensão a "channel_reg", "inverter_reg" e "pv_plant_reg", e a tabela fato "inverter". O código Python mencionado anteriormente é o ETL do processo e é responsável pelo armazenamento dos dados no banco criado.

A partir dos dados no banco, dois tipos de aplicativos foram conectados a ele: a ferramenta de visualização, feita no PowerBI, e ferramentas de análise de dados feitas em Python. O dashboard feito no PowerBI foi criado para realizar a visualização de dados de geração de energia de diferentes inversores ao longo dos dias. Já as ferramentas de análise de dados são duas. A primeira faz alguns cálculos com os dados obtidos e armazena os resultados no banco. A segunda verifica dados de alarmes das plataformas acessadas e se houver algum problema com algum sistema, ele automaticamente envia um email para um grupo de pessoas alertando o incidente.


### 3. Resultados

Após a definição da modelagem, todos os módulos da ferramenta de BI foram criados (aquisição, armazenamento, processamento e visualização). O sistema tornou-se operacional e está sendo utilizado para o monitoramento de sistemas solares reais, instalados no estado do RJ. Algumas imagens dos diferentes módulos podem ser encontradas no repositório.


### 4. Conclusões

A partir do conhecimento obtido durante o curso, foi possível aplicar as técnicas aprendidas no desenvolvimento de um sistema real de Business Intelligence para realizar o monitoramento de usinas solares, atingindo o objetivo proposto no trabalho. O sistema compreendeu toda a cadeia de BI, desde a aquisição de dados até a visualização.

Espera-se que este trabalho sirva como base para o aprofundamento do desenvolvimento do sistema aplicado. É sugerido a integração do sistema com mais plataformas web como fonte de dados e também que novas análises possam ser desenvolvidas, ajudando na identificação de problemas nos sistemas fotovoltaicos instalados e otimizando a geração de energia.

---

Matrícula: 192.110.215

Pontifícia Universidade Católica do Rio de Janeiro

Curso de Pós Graduação *Business Intelligence Master*
