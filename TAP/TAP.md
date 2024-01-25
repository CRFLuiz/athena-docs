# Termo de Abertura de Projeto (TAP)

## 1. Introdução  
Este Termo de Abertura de Projeto (TAP) estabelece a base para a criação da nova versão do jogo [cards-game](https://github.com/CRFLuiz/cards-game), visando aprimorar a jogabilidade, introduzir novas mecânicas e adotar uma arquitetura de microservices.  

## 2. Objetivos do Projeto  
- **Divisão em Microservices:** 
    - O principal objetivo é dividir o monolito em microservices para uma arquitetura mais modular e escalável. Os microservices propostos são:
        - Frontend: Aplicação React dedicada à interface do usuário.
        - Backend de Registro e Autenticação: Gerenciamento de usuários, registros e validações.
        - Backend de Interatividade do Usuário: Responsável pela comunicação entre o frontend e o jogo.
        - Backend de Gerenciamento de Partida: Controle e lógica relacionados às partidas.
        - Backend de Criação de Robôs: Geração de robôs para jogar contra os usuários.
        - Infraestrutura de Filas (Possivelmente com RabbitMQ): Para gerenciar a comunicação assíncrona e filas necessárias.
- **Aplicação em React:** 
    - Desenvolver um frontend em React para proporcionar uma experiência de usuário mais dinâmica e responsiva.
- **Melhoria na Segurança:** 
    - Reforçar a segurança, especialmente nas operações relacionadas ao registro, autenticação e gerenciamento de partidas.
- **Eficiência nas Comunicações Assíncronas:**
    - Utilizar uma infraestrutura de filas (possivelmente RabbitMQ) para melhorar a eficiência nas comunicações assíncronas entre os serviços.
- **Escalabilidade e Desempenho:**
    - Garantir que a arquitetura de microservices permita escalabilidade e melhore o desempenho geral do sistema.

Esses objetivos específicos proporcionarão uma transição para uma arquitetura mais modular e eficiente, atendendo às necessidades de cada componente do jogo de forma independente.

## 3. Escopo do Projeto
- **Melhoria na UI e Jogabilidade:**
   - Redesenhar a interface do usuário para proporcionar uma experiência mais intuitiva e esteticamente agradável.
   - Aprimorar as mecânicas de jogabilidade para tornar as partidas mais dinâmicas e envolventes.

- **Alteração Dinâmica nos Ataques:**
   - Modificar o sistema de ataques para introduzir variedade e dinamismo nas partidas, proporcionando estratégias mais diversificadas.

- **Sistema de Filas de Jogadores:**
   - Implementar um sistema de filas para facilitar o emparelhamento de jogadores, melhorando a eficiência na formação de partidas.

- **Integração de Robôs com Algoritmo Genético:**
   - Desenvolver robôs com base nas melhores redes neurais geradas por um algoritmo genético.
   - Permitir que esses robôs joguem autonomamente, aprendendo e melhorando suas estratégias ao longo do tempo.

- **Sistema de Registro e Login:**
   - Adicionar funcionalidades de registro de jogadores.
   - Implementar autenticação necessária para jogar, utilizando tokens para validar cada requisição.
   - Garantir a segurança do sistema com práticas modernas de autenticação.

- **Migração para PostgreSQL:**
   - Transferir todos os dados do jogo de arquivos JSON para um banco de dados PostgreSQL para melhorar a eficiência, escalabilidade e facilidade de gerenciamento.

Essas melhorias no escopo visam aprimorar significativamente a experiência do jogador, proporcionando uma interface mais amigável, partidas mais dinâmicas e a introdução de elementos inovadores, como a presença de robôs aprendendo por meio de algoritmos genéticos.

## 4. Stakeholders / Recursos humanos
- **Desenvolvedor:**
   - [CRFLuiz](https://github.com/CRFLuiz) será responsável pela implementação e codificação de todos os aspectos do jogo, incluindo frontend e microservices.

- **Product Owner:**
   - Como o único participante no momento, [CRFLuiz](https://github.com/CRFLuiz) também será o Product Owner, definindo e priorizando os requisitos do jogo.

- **Project Manager:**
   - A função de Project Manager estará sob a responsabilidade de [CRFLuiz](https://github.com/CRFLuiz), envolvendo o planejamento, organização e monitoramento do progresso do projeto.

- **Tester:**
   - Como Tester, [CRFLuiz](https://github.com/CRFLuiz) será responsável pela execução de testes, identificação de bugs e garantia da qualidade do jogo.

- **Jogador:**
   - Além de todas as funções acima, [CRFLuiz](https://github.com/CRFLuiz) atuará como o principal jogador, testando a experiência do usuário e fornecendo feedback direto sobre a jogabilidade.

O modelo open source permite que outros interessados se envolvam no projeto, contribuindo com ideias, correções e melhorias. Esse formato colaborativo pode enriquecer o desenvolvimento e promover uma comunidade engajada ao redor do jogo.

## 5. Recursos técnicos
- **Linguagens e Tecnologias Frontend:**
   - JavaScript (Vanilla e React), HTML5 e CSS3 serão utilizados para o desenvolvimento do frontend.

- **Framework de Frontend:**
   - Bootstrap será empregado para facilitar o design responsivo e aprimorar a aparência geral do jogo.

- **Tecnologias de Backend:**
   - Express e Socket.io serão as principais tecnologias no backend, gerenciando a lógica de servidor e a comunicação em tempo real.
   - Prisma será a biblioteca utilizada como ORM para interação com o banco de dados PostgreSQL.

- **Comunicação Assíncrona:**
   - RabbitMQ será adotado para facilitar a comunicação assíncrona entre os diferentes microservices, proporcionando uma arquitetura escalável.

- **Banco de Dados:**
   - PostgreSQL será o banco de dados escolhido para armazenar todos os dados do jogo, substituindo os arquivos JSON.

Essa inclusão do Prisma como biblioteca para interação com o banco de dados fortalecerá a integração e a manipulação eficiente dos dados entre os microservices.

## 6. Orçamento preliminar
- Inicialmente
   - **Hospedagem e Infraestrutura:**
      - Considere opções de hospedagem econômicas para servidores e banco de dados, como serviços em nuvem com planos gratuitos ou de baixo custo.

   - **Licenças e Ferramentas de Desenvolvimento:**
      - Utilize ferramentas de desenvolvimento de código aberto sempre que possível para minimizar custos com licenças.

   - **Despesas Operacionais:**
      - Reserve parte do orçamento para despesas operacionais, como possíveis custos imprevistos ou atualizações de recursos.

- Futuramente

   - **Marketing e Promoção:**
      - Explore estratégias de marketing de baixo custo, como redes sociais, para promover o jogo e atrair jogadores.

   - **Monitoramento e Analytics:**
      - Considere ferramentas de monitoramento e analytics gratuitas ou de baixo custo para avaliar o desempenho do jogo e a interação dos usuários.

É importante otimizar o uso dos recursos disponíveis e explorar alternativas econômicas para garantir que o orçamento de até 100 reais por mês seja suficiente para o desenvolvimento e manutenção do jogo.

## 7. Prazo de Lançamento
Dado que não há um prazo definido para o lançamento, a flexibilidade de tempo proporciona a oportunidade de desenvolver o jogo com maior atenção aos detalhes, refinamento e testes extensivos. É importante, no entanto, manter um ritmo consistente e estabelecer marcos internos para garantir um progresso contínuo no desenvolvimento. O foco na qualidade do jogo pode beneficiar-se dessa abordagem sem pressa, permitindo a entrega de uma experiência aprimorada para os jogadores.

## 8. Critérios de Sucesso
- **Jogabilidade Básica contra Robô Aleatório (I):**
   - O jogador pode iniciar uma partida contra um robô que escolhe suas ações aleatoriamente.
   - O jogador joga até que as cartas acabem, e ao final, a pontuação é exibida.

- **Redes Neurais Jogando Contra Robô Aleatório (II):**
   - Diversas redes neurais são criadas e capazes de jogar contra o robô aleatório mencionado no Critério I, com desempenho comparável a um jogador humano.

- **Algoritmo Genético para Evolução das Redes Neurais (III):**
   - Um algoritmo genético é implementado, iniciando com 100 redes neurais.
   - O algoritmo gera uma nova geração de 100 redes neurais, incluindo as 10 melhores da geração anterior.
   - O processo é repetido para, no mínimo, 100 gerações.

- **Redes Neurais como Robôs contra Jogadores Humanos (IV):**
   - As redes neurais geradas pelo algoritmo genético têm a capacidade de se tornarem robôs que jogarão contra os jogadores humanos.
   - Esses robôs devem apresentar estratégias evoluídas e proporcionar uma experiência desafiadora para os jogadores.

Esses critérios abrangentes garantirão não apenas a jogabilidade básica e a interação com robôs aleatórios, mas também o desenvolvimento e evolução autônoma de redes neurais capazes de competir efetivamente contra jogadores humanos.

## 9. Riscos Adicionais
- **Sistema de Filas:**
   - **Descrição do Risco:** A falta de planejamento e arquitetura prévia para o sistema de filas pode resultar em dificuldades na implementação e eficiência na formação de partidas.
   - **Mitigação:** Realizar uma análise aprofundada dos requisitos para o sistema de filas, considerando a escalabilidade e eficiência, antes de sua implementação.

- **Comunicação entre Microservices:**
   - **Descrição do Risco:** Problemas na comunicação entre os microservices podem levar a falhas no fluxo de dados e na sincronização das operações.
   - **Mitigação:** Projetar uma arquitetura robusta de comunicação, possivelmente utilizando contratos bem definidos (APIs) e mecanismos de monitoramento.

- **Utilização Compartilhada do Banco de Dados com Prisma:**
   - **Descrição do Risco:** Desafios na configuração do Prisma para compartilhar um mesmo banco de dados entre diversas apps (microservices).
   - **Mitigação:** Realizar estudos específicos sobre a integração do Prisma para garantir a compatibilidade entre os microservices e o compartilhamento eficiente do banco de dados.

Essa identificação proativa de riscos permitirá que você tome medidas preventivas, reduzindo a probabilidade de problemas durante o desenvolvimento e implementação dos microservices.

## 10. Conclusão  
Este TAP estabelece as bases para o desenvolvimento da nova versão do jogo, incorporando melhorias significativas na jogabilidade, arquitetura técnica e integração de elementos inovadores, como robôs com redes neurais. A abordagem open source permite a colaboração e o crescimento da comunidade em torno do projeto

Este Termo de Abertura de Projeto serve como guia inicial para orientar o desenvolvimento da nova versão do jogo.