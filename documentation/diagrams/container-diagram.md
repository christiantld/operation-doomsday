# Diagrama de Container - GUTPriority

Este diagrama de container C4 mostra a arquitetura interna do sistema GUTPriority, incluindo seus principais componentes e suas interações.

```mermaid
C4Container
    title Diagrama de Container do Sistema GUTPriority

    Person_Ext(user, "Usuário", "Usuário do sistema (Individual/Gerente/Membro)")

    System_Boundary(gutPriority, "Sistema GUTPriority") {
        Container(webApp, "Aplicação Web", "Next.js, React, TypeScript", "Interface web responsiva para acesso ao sistema")
        
        Container(apiBackend, "API Backend", "NestJS, TypeScript", "API REST que gerencia toda a lógica de negócio, autenticação e persistência")
        
        Container(notificationService, "Serviço de Notificações", "NestJS", "Gerencia e envia notificações por email, push e in-app")
        Container(analyticsService, "Serviço de Analytics", "NestJS", "Coleta e processa dados de uso para gerar insights")
        Container(integrationService, "Serviço de Integrações", "NestJS", "Gerencia comunicação com sistemas externos")
        
        ContainerDb(db, "Banco de Dados Principal", "PostgreSQL", "Armazena todos os dados do sistema")
        ContainerDb(cache, "Cache", "Redis", "Cache de dados e sessões")
        ContainerDb(queue, "Fila de Mensagens", "Redis", "Gerencia operações assíncronas")
    }

    System_Ext(auth0, "Serviço de Autenticação", "Google/Microsoft OAuth")
    System_Ext(payment, "Sistema de Pagamentos", "Stripe/PayPal")
    System_Ext(emailService, "Serviço de Email", "AWS SES")
    System_Ext(externalApis, "Sistemas de Integração", "Jira/Trello/Asana")

    %% Relações com Frontend
    Rel_D(user, webApp, "Acessa", "HTTPS")
    Rel_D(webApp, apiBackend, "Faz requisições", "HTTPS/JSON")
    
    %% Relações com API Backend
    Rel_D(apiBackend, db, "Lê/Escreve", "SQL")
    Rel_R(apiBackend, cache, "Usa", "Redis")
    Rel_U(apiBackend, auth0, "Autentica", "OAuth2")
    
    %% Relações com Serviços
    Rel_R(notificationService, emailService, "Envia", "SMTP")
    Rel_D(notificationService, queue, "Publica/Consome", "Redis")
    
    Rel_L(analyticsService, db, "Analisa", "SQL")
    
    Rel_U(integrationService, externalApis, "Integra", "HTTPS/JSON")
    Rel_R(integrationService, queue, "Publica eventos", "Redis")

    UpdateRelLayout(3, 3)
```

## Descrição dos Containers

### Frontend

1. **Aplicação Web (Next.js)**
   - Interface do usuário responsiva
   - Server-side rendering para melhor performance
   - Componentes reutilizáveis com Shadcn/UI
   - Estado gerenciado com Zustand
   - Chamadas à API com React Query

### Backend

1. **API Backend (NestJS)**
   - Lógica de negócio principal
   - Autenticação e autorização
   - Gestão de usuários e workspaces
   - CRUD de tarefas e avaliações GUT
   - Controle de acesso (RBAC)

2. **Serviço de Notificações**
   - Envio de emails
   - Notificações push
   - Alertas in-app
   - Lembretes de tarefas

3. **Serviço de Analytics**
   - Coleta de dados de uso
   - Geração de insights
   - Métricas de produtividade
   - Relatórios personalizados

4. **Serviço de Integrações**
   - Integração com Jira
   - Integração com Trello
   - Integração com Asana
   - API pública para extensões

### Persistência

1. **Banco de Dados Principal (PostgreSQL)**
   - Dados estruturados do sistema
   - Transações ACID
   - Schemas separados por contexto
   - Backup e replicação

2. **Cache (Redis)**
   - Cache de dados frequentes
   - Sessões de usuário
   - Rate limiting
   - Dados temporários

3. **Fila de Mensagens (Redis)**
   - Comunicação assíncrona
   - Processamento em background
   - Eventos do sistema
   - Retry de operações 