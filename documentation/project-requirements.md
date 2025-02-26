# Requisitos Arquiteturais

Este é um documento vivo com os requisitos arquiteturais da aplicação web GUTPriority.

Para mais informações, consulte a [Especificação do Projeto](./project-spec.md).

## Objetivos de Negócio

| Stakeholder                      | Objetivo                                                                                | Contexto                                                                                                                |
| -------------------------------- | --------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------- |
| Desenvolvedor Principal          | Estabelecer uma base de código sustentável para crescimento futuro                      | A arquitetura deve permitir que o produto evolua de um MVP para uma solução completa sem grandes refatorações.         |
| Gerente de Equipes (Persona)     | Priorizar eficientemente as atividades da equipe e visualizar o progresso em tempo real | Os gerentes precisam de uma ferramenta que facilite a tomada de decisão baseada em dados objetivos.                    |
| Profissional Individual (Persona)| Organizar suas tarefas pessoais com base em critérios claros de priorização             | Profissionais buscam uma metodologia estruturada para gerenciar suas demandas e reduzir a sobrecarga cognitiva.        |

## Restrições

| Restrição                                                                | Contexto                                                                                                                |
| ------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------- |
| [Técnica] Deve ser implantado na infraestrutura AWS                      | A equipe tem experiência com AWS e já possui recursos configurados nesta plataforma.                                    |
| [Técnica] Deve ser responsivo e totalmente funcional em dispositivos móveis | Espera-se que grande parte dos usuários acesse a aplicação via smartphones, especialmente para consultas rápidas.    |
| [Negócio] Deve ser lançado em produção em 3 meses (MVP)                  | O prazo é crítico para validar o produto no mercado e iniciar o ciclo de feedback com usuários reais.                  |
| [Técnica] Deve ser desenvolvido por um único desenvolvedor inicialmente  | Os recursos iniciais são limitados, exigindo uma arquitetura que permita desenvolvimento eficiente por uma pessoa.      |

## Atributos de Qualidade

| Atributo de Qualidade | Cenário                                                                                                      | Prioridade |
| --------------------- | ------------------------------------------------------------------------------------------------------------ | ---------- |
| Performance           | Um usuário em um dispositivo móvel com conexão 4G pode carregar o aplicativo em 2 segundos ou menos.         | Alta       |
| Escalabilidade        | A arquitetura deve suportar o crescimento para 10.000 usuários sem degradação significativa de performance.  | Alta       |
| Manutenibilidade      | O código deve ser modularizado para permitir a expansão da equipe de desenvolvimento no futuro.              | Alta       |
| Segurança             | Dados sensíveis dos usuários devem ser protegidos em conformidade com a LGPD.                                | Média      |
| Disponibilidade       | O sistema deve manter um SLA de 99,9% de disponibilidade.                                                    | Média      |
| Extensibilidade       | Novas funcionalidades devem poder ser adicionadas sem modificar o código existente (princípio Open/Closed).  | Baixa      |

## Requisitos Funcionais Influentes

| Requisito Funcional                                                | Impacto na Arquitetura                                                                                |
| ------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------- |
| Avaliação colaborativa de tarefas                                  | Necessidade de sincronização em tempo real e resolução de conflitos entre múltiplos avaliadores.      |
| Cálculo automático de pontuação GUT                                | Lógica de negócio consistente entre frontend e backend para garantir resultados idênticos.            |
| Visualização em diferentes formatos (lista, kanban, matriz GUT)    | Arquitetura de UI flexível que permita múltiplas representações dos mesmos dados.                     |
| Integração com ferramentas externas (Jira, Trello, etc.)           | API extensível e sistema de plugins para suportar diferentes integrações.                             |
| Notificações em tempo real                                         | Infraestrutura de mensageria para entrega confiável de notificações.                                  |

## Outros Influenciadores

- Inicialmente, o desenvolvimento será realizado por um único desenvolvedor, mas espera-se expandir a equipe para 3-5 desenvolvedores no próximo ano.
- O desenvolvedor principal tem experiência com React, Next.js e NestJS, tornando esta stack a escolha natural para o projeto.
- A metodologia Matriz GUT é bem estabelecida, mas sua implementação digital requer adaptações para garantir uma experiência de usuário intuitiva.
- A expectativa é que o produto evolua rapidamente com base no feedback dos usuários iniciais, exigindo uma arquitetura flexível.
- O orçamento inicial é limitado, favorecendo soluções que otimizem custos de infraestrutura nos estágios iniciais.
