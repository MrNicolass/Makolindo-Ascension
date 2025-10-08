<p align="center">
    <img src="https://files.engaged.com.br/5db0810e95b4f900077e887e/account/5db0810e95b4f900077e887e/xMCS8NFKTMqwhefy8WLd_catolica-horizontal.png" width="400" alt="Logo Católica">
</p>

<h1 align="center">Makolindo Ascension</h1>

<p align="center">Uma aventura pela redenção e a honra!</p>
<table align="center">
    <tr>
        <td><strong>Nome do Estudante</strong></td>
        <td>Nicolas Gustavo Conte</td>
    </tr>
    <tr>
        <td><strong>Curso</strong></td>
        <td>Engenharia de Software</td>
    </tr>
    <tr>
        <td><strong>Data de Entrega</strong></td>
        <td>05/06/2026</td>
    </tr>
</table>

# Resumo

<!--
Breve descrição do conteúdo do documento, incluindo o propósito do projeto e os principais pontos de discussão.
-->

Neste documento, será descorrido o processo de desenvolvimento de um jogo ao estilo _roguelite_, que busca contar a história do personagem místico fictício chamado "Makolindo" e sua busca pela ascensão pós queda, ambientado em um mundo mágico médio. O projeto busca apresentar os aprendizados, desafios, erros e acertos envolvidos ao longo do processo, assim como uma visão do desenvolvimento de jogos dentro do mercado brasileiro e suas perspectivas para o futuro.

## 1. Introdução

<!--
- **Contexto**: Breve descrição do contexto que envolve o projeto.
- **Justificativa**: Explicação da relevância do projeto para o campo da engenharia de software.
- **Objetivos**: Descrição do objetivo principal do projeto e de quaisquer objetivos secundários.
-->

No cenário globalizado atual, os jogos digitais transcenderam o status de nicho, alcançando aproximadamente 3,6 bilhões de jogadores em todo o mundo e gerando um faturamento estimado de US$ 188,8 bilhões até setembro de 2025 (NEWZOO, 2025). Makolindo Ascension tem como seu ponto principal, apresentar que por meio do desenvolvimento de um jogo digital, mesmo em um mercado emergente como o brasileiro, é possível adquirir e unificar conhecimentos técnicos, profissionais e artísticos.

A composição do mesmo, será feita por um conjunto de "sistemas base" integrados, baseados em jogos de sucesso do mesmo seguimento, como [*Hero Siege*](https://store.steampowered.com/app/269210/Hero_Siege/), [*Soul Knight*](https://play.google.com/store/apps/details?id=com.ChillyRoom.DungeonShooter&hl=pt_BR) e [*Undermine*](https://store.steampowered.com/agecheck/app/656350/). Haverão sistemas de geração de níveis randomizadsos, monetização _in-game_, combate (com inimigos e chefões), itens e poderes especiais, que serão destrinchados no decorrer deste documento.

O jogo será desenvolvido por meio da plataforma [GameMaker](https://gamemaker.io/pt-BR), com o estilo visual em [_pixel art_](https://en.wikipedia.org/wiki/Pixel_art) simples, voltado para computadores _desktop_ Windows e MacOS, com uma dificuldade ligeiramente mais elevada que seus pares. O intuito é fazer com que o jogador fique envolvido com a história, o fazendo simpatizar com Makolindo, suas dificuldades e empecilhos empostos por seus "inimigos" ao longo do trajeto.

Antes de seguir com a explanação do projeto, será introduzido os conceitos necessários para o entendimento do gênero do jogo, estilo artístico e as obras de referência.

### 1.1. Origem e significado do gênero _roguelite_

Para entendermos o significado de _roguelite_, primeiro veremos rapidamente o significado do termo _roguelike_, seu predecessor. O termo "_roguelite_" surgiu por voltade 1993 nos grupos de notícias da Usenet[[1]](#ref-1)[[2]](#ref-2)[[3]](#ref-3) (plataforma "pré web" de comunicação por texto, com fóruns e notícias), sendo citado pela primeira ver por Andrew Solovay, em uma discussão sobre a criação de um novo fórum específico para discussões sobre jogos como _Hack_, _Moria_ e _Rogue_; foi nesta discussão onde definiu-se que o subfórum se chamaria "rec.games.roguelike.*", pois entre todos os jogos, _Rogue_ era considerado o mais antigo entre eles.

![Exemplo de Roguelite](https://shared.fastly.steamstatic.com/store_item_assets/steam/apps/1443430/ss_8133cd666690fc773913cc0d1eb93b7e8bfc1ae3.1920x1080.jpg?t=1651574702)
<p align="center"><em>Figura 1. Imagem de uma das fases do game <a href="https://store.steampowered.com/app/1443430/Rogue/?l=portuguese">Rogue</a>.</em></p>

A grande maioria dos _roguelikes_ baseava-se em conceitos de jogos de interpretação de papéis (também conhecidos como RPG's - _Role-play gaming_) como _Dungeon & Dragons_, onde o jogador tem o controle sobre um personagem que pode ser personalizado, escolhendo uma classe, raça e gênero, assim como podendo também ajustar alguns pontos de atributos e habilidades. Porém com o passar dos anos, inúmeros jogos surgiram adotando a nomenclatura de _roguelike_, mas com características distintas aos seus predecessores.

Então em 2008, foi realizado em Berlim, a primeira conferência Internacional de Desenvolvimento de _Roguelike_, onde jogadores e desenvolvedores estabeleceram uma definição para _roguelikes_, conhecida como "Interpretação de Berlim". Essa interpretação definiu um conjunto de fatores de alto e baixo valor, baseando-se em cinco jogos _roguelike_ canônicos (_ADOM_, _Angband_, _Linley's Dungeon Crawl_, _NetHack_ e _Rogue_), para poder conseguir determinar "o quão _roguelike_ é um jogo". Os tópicos foram definidos como:

- Fatores principais (alto valor):
    - Geração aleatória – os mapas e itens mudam a cada jogo;
    - Morte permanente – morreu, começa tudo de novo;
    - Baseado em turnos – o jogo só anda quando o jogador age;
    - Movimento em grade – o mundo é dividido em blocos (tiles);
    - Sem modos separados – todas as ações (andar, lutar, usar item) seguem o mesmo fluxo;
    - Alta complexidade – muitas opções e estratégias possíveis;
    - Gerenciamento de recursos – o jogador precisa economizar itens, vida, comida etc;
    - Exploração e descoberta – o jogo incentiva explorar e aprender o que cada coisa faz;
- Fatores secundários (baixo valor):
    - Controlar apenas um personagem;
    - Inimigos seguem as mesmas regras do jogador;
    - Combate tático e desafiador;
    - Visual simples ou ASCII (como letras e símbolos);
    - Mapas tipo masmorra, com salas e corredores;
    - Números e estatísticas visíveis (vida, força, dano etc.).

Esses são considerados até hoje, os pontos base para a criação de um "_roguelike_ puro sangue", isso é claro, contendo algumas alterações com base na atualiade.

### 1.2. Origem e significado do gênero _roguelite_

### 1.3. Definição sobre o estilo artístico _pixel art_

## 2. Descrição do Projeto

* **Linha de Projeto**: Indique a categoria do projeto (Web Apps, Aplicações Mobile, Jogos Digitais, Projetos com IA ou Projetos IoT), conforme definido no regulamento.
* **Tema do Projeto**: Descreva de forma clara e objetiva o produto, serviço ou ferramenta a ser desenvolvido.
* **Propósito e Uso Prático**: Explique qual problema real será resolvido e como a solução será utilizada na prática.
* **Público-Alvo**: Defina o perfil dos usuários ou clientes potenciais que se beneficiarão da solução.
* **Problemas a Resolver**: Liste de forma objetiva os principais problemas ou necessidades que o projeto pretende atender.
* **Diferenciação/Ineditismo**: Destaque o que torna a proposta única em relação a soluções existentes, mesmo quando o tema é semelhante a outros projetos.
* **Limitações**: Especifique o que o projeto **não** abrangerá, evitando expectativas incorretas.
* **Normas e Legislações Aplicáveis**: Liste normas, leis e diretrizes relevantes ao contexto do projeto (ex.: LGPD, HIPAA, WCAG, ESRB/PEGI), indicando como serão observadas.
* **Métricas de Sucesso**: Apresente critérios iniciais para medir o desempenho e a efetividade do projeto (ex.: tempo de resposta, número de usuários atendidos, taxa de acerto do modelo de IA).

## 3. Especificação Técnica

Descrição detalhada da proposta, contemplando requisitos, arquitetura, tecnologias, segurança e aderência aos critérios obrigatórios da linha de projeto escolhida.

### 3.1. Requisitos de Software
- **Requisitos Funcionais (RF)**: Liste de forma clara as funcionalidades que o sistema deverá oferecer.
- **Requisitos Não-Funcionais (RNF)**: Inclua requisitos de desempenho, segurança, usabilidade, escalabilidade, disponibilidade, entre outros.
- **Representação dos Requisitos**: Inclua um Diagrama de Casos de Uso (UML) ou outra representação visual que facilite o entendimento.
- **Aderência aos Requisitos da Linha de Projeto**: Indique como cada requisito está alinhado aos itens “Obrigatório Atender” definidos para a linha de projeto (Web, Mobile, Jogos, IA ou IoT).

### 3.2. Considerações de Design
- **Visão Inicial da Arquitetura**: Apresente os principais componentes e suas interações.
- **Padrões de Arquitetura**: Informe padrões adotados (ex.: [MVC](https://en.wikipedia.org/wiki/Model–view–controller), [Microserviços](https://microservices.io/), [MVVM](https://en.wikipedia.org/wiki/Model–view–viewmodel), Arquitetura em Camadas).
- **Modelos C4**: Utilize os quatro níveis ([C4 Model](https://c4model.com/)) quando aplicável.
- **Mockups das Telas Principais**: Apresente protótipos visuais das telas mais relevantes, mostrando navegação, disposição de elementos e principais interações do usuário. Esses mockups podem ser feitos em ferramentas como Figma, Adobe XD ou similares, e devem refletir a identidade visual e usabilidade prevista para o produto.
- **Decisões e Alternativas Consideradas**: Justifique escolhas de design, documentando alternativas avaliadas.
- **Critérios de Escalabilidade, Resiliência e Segurança**: Descreva como a solução será projetada para suportar crescimento, lidar com falhas e manter segurança.

### 3.3. Stack Tecnológica
- **Linguagens de Programação**: Liste e justifique as escolhas.
- **Frameworks e Bibliotecas**: Detalhe e justifique a seleção.
- **Ferramentas de Desenvolvimento e Gestão**: Inclua IDEs, sistemas de versionamento, plataformas de integração contínua, monitoramento, entre outros.
- **Licenciamento**: Indique as licenças dos softwares e bibliotecas utilizados ([MIT](https://opensource.org/licenses/MIT), [GPL](https://www.gnu.org/licenses/gpl-3.0.html), [Apache](https://www.apache.org/licenses/), [Creative Commons](https://creativecommons.org/licenses/)).

### 3.4. Considerações de Segurança
- **Riscos Identificados**: Liste ameaças potenciais (ex.: injeção de código, vazamento de dados, falhas de autenticação).
- **Medidas de Mitigação**: Explique as ações planejadas para minimizar riscos (ex.: criptografia, controle de acesso, validação de entrada).
- **Normas e Boas Práticas Seguidas**: Cite padrões como [OWASP Top 10](https://owasp.org/www-project-top-ten/), [ISO/IEC 27001](https://www.iso.org/isoiec-27001-information-security.html), [LGPD](https://www.planalto.gov.br/ccivil_03/_ato2015-2018/2018/lei/L13709.htm) ou outros aplicáveis.
- **Responsabilidade Ética**: Para projetos de IA ou manipulação de dados sensíveis, descreva como serão tratados vieses, privacidade e uso responsável ([UNESCO – Ética em IA](https://unesdoc.unesco.org/ark:/48223/pf0000380455), [OECD AI Principles](https://oecd.ai/en/ai-principles)).

### 3.5. Conformidade e Normas Aplicáveis
- Relacione todas as legislações, regulamentações e normas técnicas aplicáveis ao projeto, descrevendo brevemente como serão atendidas.
- Exemplos:
  - [LGPD – Lei Geral de Proteção de Dados](https://www.planalto.gov.br/ccivil_03/_ato2015-2018/2018/lei/L13709.htm)
    - Coletar apenas dados necessários (nome, contato, dados do imóvel).
    - Evitar dados sensíveis desnecessários.
    - Solicitar consentimento explícito e exibir política de privacidade clara.
    - Permitir acesso, correção e exclusão de dados pelo usuário.
    -   ...
   
## 4. Próximos Passos

 - Descrição dos passos seguintes após a conclusão do documento, com uma visão geral do cronograma para Portfólio I e II.
 - Definição de Marcos: Estabelecer datas para entregas intermediárias e checkpoints.


## 5. Referências

1. <a id="ref-1">WIKIPÉDIA.</a> *Roguelike*. Wikipédia, a enciclopédia livre, 2025. Disponível em: [https://pt.wikipedia.org/wiki/Roguelike](https://pt.wikipedia.org/wiki/Roguelike). Acesso em: 07 out. 2025.
2. <a id="ref-2">ZAPATA,</a> Santiago. *On the Historical Origin of the “Roguelike” Term*. Slashie’s Gamedev Adventures, v. 1.2.1, 13 nov. 2017. Disponível em: [https://blog.slashie.net/on-the-historical-origin-of-the-roguelike-term/](https://blog.slashie.net/on-the-historical-origin-of-the-roguelike-term/). Acesso em: 07 out. 2025.
3. <a id="ref-3">GROUPS GOOGLE.</a> RFD: rec.games.dungeon.* hierarchy. Google Groups, 1993. Disponível em: [https://groups.google.com/g/news.groups/c/CdWOd-M6g-w/m/cgNn2b9uU2sJ](https://groups.google.com/g/news.groups/c/CdWOd-M6g-w/m/cgNn2b9uU2sJ). Acesso em: 07 out. 2025.

- OPEN GAME ART. [S. l.: s. n.], [s. d.]. Disponível em: [https://opengameart.org/](https://opengameart.org/). Acesso em: 15 set. 2025.
- BEEPBOX. [S. l.: s. n.], [s. d.]. Disponível em: [https://www.beepbox.co/](https://www.beepbox.co/). Acesso em: 15 set. 2025.
- ROGuelike vs. Roguelite: você sabe quais são as diferenças?. **TecMundo**, 28 maio 2022. Disponível em: [https://www.tecmundo.com.br/voxel/237827-roguelike-vs-roguelite-voce-sabe-diferencas.htm](https://www.tecmundo.com.br/voxel/237827-roguelike-vs-roguelite-voce-sabe-diferencas.htm). Acesso em: 15 set. 2025.
- BERLIN Interpretation. In: ROGUEBASIN. [S. l.], 2021. Disponível em: [https://www.roguebasin.com/index.php/Berlin_Interpretation](https://www.roguebasin.com/index.php/Berlin_Interpretation). Acesso em: 15 set. 2025.
- CAMPOS, Amanda Rodrigues. **Zombieland: Desenvolvimento de um jogo de gênero Roguelite** 2023. Trabalho de Conclusão de Curso (Graduação em Tecnologia em Jogos Digitais) - Faculdade de Tecnologia de Ameriacana (Fatec), São Paulo, 2023. Disponível em: [http://ric-cps.eastus2.cloudapp.azure.com/bitstream/123456789/15548/3/20232S_Amanda%20Campos_OD1833.pdf](http://ric-cps.eastus2.cloudapp.azure.com/bitstream/123456789/15548/3/20232S_Amanda%20Campos_OD1833.pdf). Acesso em: 15 set. 2025.
- MARTIN, Geoffrey. Roguelike vs. Roguelite: What's The Difference?. **TheGamer**, 23 ago. 2023. Disponível em: [https://www.thegamer.com/roguelike-vs-roguelite-what-the-difference/](https://www.thegamer.com/roguelike-vs-roguelite-what-the-difference/). Acesso em: 15 set. 2025.
- MAKOLINDO MONSTRO. **A Jornada de um DEPRESSIVO a um MONSTRO (INSPIRADOR)** - Motivação. [S. l.]: YouTube, 28 jan. 2023. Disponível em: [https://www.youtube.com/watch?v=PZUaRZJJNhg](https://www.youtube.com/watch?v=PZUaRZJJNhg). Acesso em: 15 set. 2025.
- MARCOS GAMEDEV. **PARE de usar a GODOT do JEITO ERRADO!**. [S. l.]: YouTube, 24 mar. 2024. Disponível em: [https://www.youtube.com/watch?v=xV6guE1Khuk](https://www.youtube.com/watch?v=xV6guE1Khuk). Acesso em: 15 set. 2025.
- MAKOLINDO MONSTRO. [S. l.]: YouTube, [s. d.]. Canal. Disponível em: [https://www.youtube.com/@MakolindoMonstro/videos](https://www.youtube.com/@MakolindoMonstro/videos). Acesso em: 15 set. 2025.
- GAME MAKER'S TOOLKIT. [S. l.]: YouTube, [s. d.]. Canal. Disponível em: [https://www.youtube.com/@GMTK/videos](https://www.youtube.com/@GMTK/videos). Acesso em: 15 set. 2025.
- MARCOS GAMEDEV. **Como foi criar o meu próprio Motor de Jogo?**. [S. l.]: YouTube, 21 out. 2023. Disponível em: [https://www.youtube.com/watch?v=opBd-Oa6wMk](https://www.youtube.com/watch?v=opBd-Oa6wMk). Acesso em: 15 set. 2025.
- MGYS - MAKE GAME YOURSELF. [S. l.: s. n.], [s. d.]. Planilha Google. Disponível em: [https://docs.google.com/spreadsheets/d/1Mqcqh9G20bH4nwyVIQn3OIXHdL8gzgyztdC6b8exiQM/edit?gid=88563757#gid=88563757](https://docs.google.com/spreadsheets/d/1Mqcqh9G20bH4nwyVIQn3OIXHdL8gzgyztdC6b8exiQM/edit?gid=88563757#gid=88563757). Acesso em: 15 set. 2025.
- NEWZOO. **Newzoo Global Games Market Report 2025**. [S. l.]: Newzoo, 2025. Disponível em: [https://newzoo.com/resources/trend-reports/newzoo-global-games-market-report-2025](https://newzoo.com/resources/trend-reports/newzoo-global-games-market-report-2025). Acesso em: 15 set. 2025.


## 6. Apêndices (Opcionais)

Informações complementares, dados de suporte ou discussões detalhadas fora do corpo principal.
## 7. Avaliações de Professores

Adicionar três páginas no final do RFC para que os Professores escolhidos possam fazer suas considerações e assinatura:
- Considerações Professor/a:
- Considerações Professor/a:
- Considerações Professor/a: