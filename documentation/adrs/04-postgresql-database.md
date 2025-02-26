# ADR 4: PostgreSQL como Banco de Dados Principal

## Status

Aceito

## Contexto

A escolha do banco de dados principal é crucial para o GUTPriority, considerando:

- Necessidade de armazenar dados estruturados (usuários, workspaces, tarefas, avaliações)
- Requisitos de integridade e consistência dos dados
- Suporte a transações para operações complexas
- Capacidade de escalar com o crescimento do sistema
- Necessidade de queries complexas para relatórios e dashboards
- Restrições de orçamento inicial

## Decisão

Decidimos utilizar PostgreSQL como banco de dados principal, com:
- Drizzle ORM para acesso aos dados
- Redis para caching
- AWS RDS para hospedagem
- Estrutura de schemas para separação de contextos

## Consequências

### Consequências Positivas

- **Confiabilidade:** PostgreSQL é conhecido por sua robustez e confiabilidade no armazenamento de dados.

- **Recursos Avançados:** Suporte nativo a JSON, arrays, full-text search e outros recursos necessários para o projeto.

- **Transações ACID:** Garantia de consistência em operações complexas, como avaliações colaborativas.

- **Escalabilidade:** Possibilidade de escalar verticalmente e horizontalmente conforme necessário.

- **Custo-Benefício:** Excelente performance e recursos sem custos de licenciamento.

### Consequências Negativas

- **Complexidade de Gestão:** Requer conhecimento específico para otimização e manutenção.

- **Custos de Hospedagem:** AWS RDS pode ser mais caro que alternativas NoSQL em alguns casos.

- **Esquema Rígido:** Alterações no schema podem ser mais trabalhosas comparadas a bancos NoSQL.

A escolha do PostgreSQL proporciona uma base sólida e confiável para os dados do GUTPriority, com flexibilidade para crescer e evoluir conforme as necessidades do sistema. 