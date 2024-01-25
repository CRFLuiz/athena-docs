# Documento de Arquitetura

## 1. Introdução

O documento de arquitetura delineia a estrutura e o design do sistema para a nova versão do jogo [cards-game](https://github.com/CRFLuiz/cards-game). Ele fornece uma visão geral dos componentes principais, a interação entre eles e as tecnologias a serem utilizadas.

## 2. Visão Geral da Arquitetura

### 2.1. Arquitetura de Microservices

A arquitetura será baseada em microservices, dividindo o sistema em componentes independentes, cada um responsável por funções específicas.

### 2.2. Componentes Principais

- **Frontend (React):**
   - Interface do usuário para interação dos jogadores com o jogo.

- **Backend de Registro e Autenticação (Express, JWT):**
   - Gerenciamento de registros de jogadores e autenticação.

- **Backend de Jogo (Express, Socket.IO):**
   - Lógica principal do jogo e interação com jogadores.

- **Backend de Partida (Express):**
   - Gerenciamento das partidas em andamento.

- **Backend de Robôs (Express, Socket.IO, Synaptic):**
   - Geração e treinamento de robôs com redes neurais.

- **Banco de Dados (PostgreSQL):**
   - Armazenamento persistente para informações de jogadores, partidas e redes neurais.

- **RabbitMQ:**
   - Sistema de mensagens assíncronas para comunicação entre microservices.

### 2.3. Escalabilidade

Considerando que, inicialmente, o jogo terá um único jogador (o desenvolvedor), a arquitetura será projetada para acomodar escalabilidade conforme o número de jogadores aumenta no futuro. A adoção da arquitetura de microservices oferece flexibilidade para escalar componentes individualmente conforme necessário.

## 3. Fluxo de Dados

### 3.1. Fluxo de Jogo

1. O Frontend interage com o Backend de Registro e Autenticação para autenticar jogadores.
2. O Backend de Jogo gerencia a lógica do jogo e interage com o Backend de Partida para iniciar partidas.
3. O Backend de Robôs utiliza o algoritmo genético para gerar e treinar redes neurais.
4. A comunicação assíncrona via RabbitMQ facilita a troca de mensagens entre os microservices.

## 4. Detalhes sobre a Comunicação Assíncrona

O sistema adotará uma abordagem de comunicação assíncrona para otimizar a interação entre os microservices. A seguir estão os detalhes específicos:

- **Comunicação Frontend-Backend de Registro e Autenticação:**
  - Será realizada através de requisições HTTP para garantir a autenticação segura dos jogadores.

- **Comunicação Frontend-Backend de Jogo:**
  - Utilizará WebSocket para estabelecer uma conexão bidirecional eficiente, suportando interações em tempo real durante as partidas.

- **Comunicação Backend de Jogo-Backend de Partida:**
  - A comunicação será realizada através do RabbitMQ, utilizando uma única fila para transmitir mensagens relacionadas ao gerenciamento das partidas.

- **Comunicação Backend de Robôs-Backend de Jogo:**
  - Utilizará WebSocket para permitir a comunicação entre o backend de robôs e o backend de jogo, possibilitando a interação das redes neurais treinadas durante as partidas.

### Configuração Recomendada do RabbitMQ

Considerando a arquitetura proposta, uma configuração básica seria a utilização de uma única fila para a comunicação entre o Backend de Jogo e o Backend de Partida. No entanto, a configuração específica pode variar dependendo da complexidade do sistema, carga esperada e requisitos futuros.

## 5. Decisões Arquiteturais

### 5.1. Escolha do PostgreSQL

O PostgreSQL foi escolhido como banco de dados devido à sua confiabilidade, suporte a ACID e capacidade de escalabilidade.

### 5.2. Arquitetura de Microservices

A arquitetura de microservices foi escolhida para proporcionar flexibilidade, escalabilidade e manutenção independente de cada componente.

## 6. Considerações de Segurança

### 6.1. Autenticação com Tokens

A autenticação será realizada com tokens para garantir segurança nas interações entre o Frontend e os microservices.

### 6.2. Controle de Acesso

Cada microservice terá controles de acesso para garantir que apenas os serviços autorizados possam interagir.

## 7. Conclusão

O documento de arquitetura fornece uma estrutura sólida para o desenvolvimento da nova versão do jogo [cards-game](https://github.com/CRFLuiz/cards-game). A evolução contínua desta arquitetura será essencial para atender aos requisitos e objetivos do projeto.