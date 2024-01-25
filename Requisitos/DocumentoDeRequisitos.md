# Documento de Requisitos - Nova Versão do Jogo [cards-game](https://github.com/CRFLuiz/cards-game)

## 1. Introdução
O documento de requisitos detalha os aspectos funcionais e não funcionais da nova versão do jogo [cards-game](https://github.com/CRFLuiz/cards-game), abrangendo melhorias na jogabilidade, integração de microservices, introdução de robôs com redes neurais e outros recursos.

## 2. Requisitos Funcionais

### 2.1. Interface do Usuário (UI) e Jogabilidade:
   - **RF1:** A interface do usuário deve ser redesenhada para proporcionar uma experiência mais intuitiva e esteticamente agradável.
      - **RF1.1:** Todos os monstros do jogo serão carregados dinamicamente, permitindo uma variedade maior de combinações em cada partida.

      - **RF1.2:** Na inicialização de uma partida, será realizado um sorteio aleatório para selecionar 5 monstros entre todos os monstros disponíveis.
   - **RF2:** As mecânicas de jogo devem ser aprimoradas para tornar as partidas mais dinâmicas.

Essas modificações proporcionam uma experiência mais dinâmica e variada para os jogadores, já que cada partida terá uma composição de monstros única, adicionando um elemento estratégico adicional ao jogo.

### 2.2. Sistema de Ataques:
   - **RF3:** O sistema de ataques deve ser modificado para introduzir variedade e dinamismo nas partidas.
      - **RF3.1:** Cada ataque terá atributos que podem incluir, mas não se limitar a: alteração de vida, resistências, energia, dano, magia, etc.
      
      - **RF3.2:** Os efeitos de um ataque podem adicionar ou remover valores dos atributos mencionados.
      
      - **RF3.3:** Cada efeito terá um target associado, indicando se o efeito será aplicado no inimigo ou no próprio atacante.

**Exemplo:**

- **Ataque Fogo Ardente:**
   - Atributos: Dano: 10, Magia: 5, Energia: -2
   - Efeitos: 
      - Alteração de Vida (Inimigo): -10
      - Alteração de Resistência Mágica (Inimigo): -3
      - Alteração de Energia (Atacante): +1

Essas modificações permitem uma personalização mais detalhada dos ataques, proporcionando uma variedade de estratégias e efeitos no jogo. Se necessário, podemos ajustar ou adicionar mais detalhes conforme o desenvolvimento do projeto avança.  

### 2.3. Sistema de Filas:
   - **RF4:** Implementar um sistema eficiente de filas para emparelhamento de jogadores.
      - **RF4.1:** Inicialmente, criar uma fila simples que guarde jogadores que desejam jogar.
      
      - **RF4.2:** Provisionar um robô para jogar contra cada jogador na fila.

      - **RF4.3:** Se o tempo de espera na fila for maior que 1 minuto, provisionar automaticamente um robô para jogar contra o jogador.

      - **RF4.4:** Implementar uma fila mais avançada no futuro, considerando pontuações dos jogadores para emparelhamento quando aprimoramentos no sistema estiverem concluídos.

Essa abordagem permite um início mais simples, com a possibilidade de adicionar funcionalidades mais avançadas posteriormente. A implementação da fila avançada e do algoritmo genético será realizada conforme planejado, após o desenvolvimento inicial do jogo estar concluído.  

### 2.4. Redes Neurais e Robôs:
   - **RF5:** Desenvolver redes neurais geradas por algoritmo genético, capazes de jogar contra jogadores e robôs aleatórios.
      - **RF5.1:** Não há restrições específicas nas ações que as redes neurais e robôs podem realizar. A evolução deve ser baseada na eficiência e desempenho durante as partidas.

      - **RF5.2:** Em cada geração, a melhor rede neural deve ter uma pontuação competitiva, garantindo uma evolução gradual e contínua.

      - **RF5.3:** O algoritmo genético deve ser capaz de gerar no mínimo 100 gerações de redes neurais, incluindo as 10 melhores da geração anterior.

Essas modificações enfatizam uma evolução constante e consistente das redes neurais ao longo das gerações, garantindo que a qualidade não decaia drasticamente em cada nova iteração do algoritmo genético. Este processo permitirá a criação de robôs desafiadores e estratégicos para jogar contra os jogadores humanos.

### 2.5. Autenticação e Registro:
   - **RF6:** Adicionar funcionalidades de registro de jogadores.
   - **RF7:** Implementar autenticação necessária para jogar, utilizando tokens para validar cada requisição.

### 2.6. Microservices:
   - **RF8:** Dividir o monolito em microservices, incluindo backend/frontend, registro/autenticação, interatividade do usuário, gerenciamento de partida e criação de robôs.

## 3. Requisitos Não Funcionais

### 3.1. Segurança:
   - **RNF1:** Reforçar a segurança, especialmente nas operações de registro, autenticação e gerenciamento de partidas.
      - **RNF1.1:** Todas as requisições para a API do jogo devem incluir um token de autenticação para garantir segurança e autorização adequadas.

      - **RNF1.2:** Os tokens de autenticação devem ter um tempo de expiração configurável para melhorar a segurança do sistema.

Essas adições asseguram que a API do jogo seja protegida por um mecanismo de autenticação baseado em tokens, proporcionando uma camada adicional de segurança. O tempo de expiração dos tokens ajuda a mitigar possíveis riscos associados a tokens que podem ser comprometidos. 

### 3.2. Eficiência:
   - **RNF2:** Garantir que a arquitetura de microservices permita escalabilidade e melhore o desempenho geral do sistema.

### 3.3. Comunicação Assíncrona:
   - **RNF3:** Utilizar RabbitMQ para facilitar a comunicação assíncrona entre os microservices.

### 3.4. Banco de Dados:
   - **RNF4:** Migração para PostgreSQL para melhorar a eficiência, escalabilidade e facilidade de gerenciamento.

### 3.5. Colaboração Open Source:
   - **RNF5:** Facilitar a colaboração externa ao manter o projeto como open source.

## 4. Casos de Uso

### 4.1. Caso de Uso 1 - Iniciar Partida

**Ator Principal:** Jogador

**Fluxo Principal:**
1. O jogador decide iniciar uma nova partida.
2. O sistema carrega todos os monstros disponíveis.
3. O sistema realiza um sorteio aleatório para selecionar 5 monstros para a partida.
4. Os monstros selecionados são apresentados ao jogador.
5. A partida é iniciada.

**Fluxo Alternativo:**
- Se o jogador cancelar a decisão de iniciar uma partida, o caso de uso é encerrado.

### 4.2. Caso de Uso 2 - Realizar Ataque

**Ator Principal:** Jogador

**Fluxo Principal:**
1. Durante sua vez, o jogador escolhe um dos monstros e uma das ações disponíveis.
2. O sistema processa o ataque, aplicando os efeitos especificados na ação.
3. O sistema atualiza o estado da partida.

**Fluxo Alternativo:**
- Se o jogador optar por não realizar um ataque, a vez passa para o próximo monstro.

### 4.3. Caso de Uso 3 - Gerar Redes Neurais com Algoritmo Genético

**Ator Principal:** Sistema

**Fluxo Principal:**
1. O sistema inicia o processo de geração de redes neurais utilizando o algoritmo genético.
2. As redes neurais são avaliadas com base no desempenho em partidas contra jogadores e robôs.
3. As melhores redes neurais são selecionadas para reprodução, formando a próxima geração.
4. O processo é repetido por pelo menos 100 gerações.

**Fluxo Alternativo:**
- Se o desempenho da melhor rede neural de uma geração não for competitivo, o sistema revisa parâmetros do algoritmo genético.

### 4.4. Caso de Uso 4 - Treinar Redes Neurais para Jogar Contra Jogadores

**Ator Principal:** Sistema

**Fluxo Principal:**
1. O sistema utiliza as redes neurais geradas pelo algoritmo genético para criar robôs.
2. Os robôs são treinados em partidas contra jogadores humanos.
3. O desempenho dos robôs é monitorado e utilizado para ajustar pesos e parâmetros das redes neurais.

**Fluxo Alternativo:**
- Se o desempenho dos robôs não mostrar melhoria ao longo do tempo, o sistema revisa parâmetros de treinamento.

### 4.5. Caso de Uso 5 - Participar da Fila

**Ator Principal:** Jogador

**Fluxo Principal:**
1. O jogador decide participar da fila para encontrar um adversário humano.
2. O sistema adiciona o jogador à fila.
3. Se o tempo de espera for inferior a 1 minuto, o sistema aguarda até encontrar um adversário humano.
4. Se o tempo de espera for superior a 1 minuto, o sistema provisiona automaticamente um robô como adversário.

**Fluxo Alternativo:**
- Se o jogador cancelar a participação na fila, o caso de uso é encerrado.

## 5. Critérios de Aceitação

### 5.1. Para o Caso de Uso 1 - Iniciar Partida:

- O sistema deve ser capaz de carregar e sortear monstros de forma eficiente.
- Os monstros selecionados devem ser apresentados de maneira clara ao jogador.
- A partida deve iniciar sem problemas após a seleção dos monstros.

### 5.2. Para o Caso de Uso 2 - Realizar Ataque:

- O sistema deve processar os ataques de forma precisa, aplicando corretamente os efeitos.
- As atualizações no estado da partida devem ser refletidas imediatamente após cada ataque.

### 5.3. Para o Caso de Uso 3 - Gerar Redes Neurais com Algoritmo Genético:

- O sistema deve ser capaz de gerar no mínimo 100 gerações de redes neurais.
- A melhor rede neural de cada geração deve ter uma pontuação competitiva ou maior em comparação com a melhor da geração anterior.
- O algoritmo genético deve ser capaz de evoluir estratégias de jogo ao longo das gerações.

### 5.4. Para o Caso de Uso 4 - Treinar Redes Neurais para Jogar Contra Jogadores:

- As redes neurais geradas pelo algoritmo genético devem ser efetivas na criação de robôs desafiadores.
- O treinamento dos robôs deve resultar em um aumento consistente na taxa de vitória contra jogadores humanos.
- O sistema deve ser capaz de ajustar dinamicamente os pesos e parâmetros das redes neurais durante o treinamento.

Esses casos de uso adicionais expandem as interações do sistema, incluindo processos cruciais como a geração de redes neurais e o treinamento de robôs, contribuindo para o alcance dos critérios de sucesso estabelecidos no Termo de Abertura do Projeto. Se precisar de mais ajustes ou adições, estou à disposição.

### 5.5. Para o Caso de Uso 5 - Participar da Fila:

- O jogador deve ser adicionado à fila com sucesso.
- O sistema deve aguardar adversários humanos por até 1 minuto antes de provisionar um robô.
- O robô provisionado deve ser um adversário desafiador.

Esses casos de uso e critérios de aceitação oferecem uma visão mais detalhada das interações e comportamentos esperados no sistema. Se houver necessidade de mais detalhes ou ajustes, estou à disposição para ajudar.

## 6. Considerações Finais

Este documento de requisitos fornece uma base sólida para o desenvolvimento da nova versão do jogo [cards-game](https://github.com/CRFLuiz/cards-game). Sua aprovação e revisão contínua são essenciais para garantir o alinhamento com os objetivos do projeto.

[CRFLuiz](https://github.com/CRFLuiz) - 25/01/2024