# Diagrama de Contexto - GUTPriority

Este diagrama de contexto C4 mostra a visão geral do sistema GUTPriority e suas interações com usuários e sistemas externos.

```mermaid
C4Context
    title Diagrama de Contexto do Sistema GUTPriority

    Person_Ext(individual, "Usuário Individual", "Profissional que utiliza o sistema para priorizar suas próprias tarefas")
    Person_Ext(teamManager, "Gerente de Equipe", "Líder que coordena a priorização de atividades em grupo")
    Person_Ext(teamMember, "Membro de Equipe", "Colaborador que participa de workspaces compartilhados")

    System(gutPriority, "Sistema GUTPriority", "Plataforma SaaS de priorização de atividades baseada na metodologia Matriz GUT")

    System_Ext(auth, "Serviço de Autenticação", "Google/Microsoft OAuth")
    System_Ext(payment, "Sistema de Pagamentos", "Stripe/PayPal")
    System_Ext(notification, "Serviço de Notificações", "Email/Push/SMS")
    System_Ext(integration, "Sistemas de Integração", "Jira/Trello/GitHub/Slack")

    Rel(individual, gutPriority, "Gerencia tarefas pessoais e avalia prioridades")
    Rel(teamManager, gutPriority, "Gerencia workspaces, equipes e visualiza dashboards")
    Rel(teamMember, gutPriority, "Participa de avaliações e colabora em tarefas")

    Rel(gutPriority, auth, "Autentica usuários")
    Rel(gutPriority, payment, "Processa pagamentos e assinaturas")
    Rel(gutPriority, notification, "Envia notificações")
    Rel(gutPriority, integration, "Sincroniza dados")
```

## Descrição dos Elementos

### Atores (Pessoas)

1. **Usuário Individual**
   - Profissionais que utilizam o sistema para priorização pessoal
   - Gerencia suas próprias tarefas e avaliações GUT
   - Visualiza relatórios individuais

2. **Gerente de Equipe**
   - Coordena workspaces e equipes
   - Define permissões e papéis
   - Analisa dashboards e métricas
   - Toma decisões baseadas em dados

3. **Membro de Equipe**
   - Participa de workspaces compartilhados
   - Contribui com avaliações GUT
   - Colabora em tarefas da equipe

### Sistema Principal

**GUTPriority**
- Plataforma SaaS de priorização
- Implementa a metodologia Matriz GUT
- Gerencia workspaces, tarefas e avaliações
- Fornece visualizações e relatórios
- Permite colaboração em tempo real

### Sistemas Externos

1. **Serviço de Autenticação**
   - Autenticação via Google/Microsoft
   - Gerenciamento de sessões
   - Single Sign-On (SSO)

2. **Sistema de Pagamentos**
   - Processamento de pagamentos
   - Gestão de assinaturas
   - Faturamento recorrente

3. **Serviço de Notificações**
   - Envio de emails
   - Notificações push
   - Alertas SMS

4. **Sistemas de Integração**
   - Integração com Jira
   - Integração com Trello
   - Integração com GitHub
   - Integração com Slack 