# GUTPriority

GUTPriority é um SaaS de priorização de atividades baseado na metodologia Matriz GUT (Gravidade, Urgência, Tendência) que permite a indivíduos e equipes gerenciarem suas demandas de forma eficiente e estruturada.

## 🎯 Funcionalidades

- 📊 **Avaliação GUT**
  - Avalie tarefas usando critérios GUT (1-5)
  - Cálculo automático de prioridade (G×U×T)
  - Histórico de avaliações
  - Avaliações colaborativas em equipe

- 👥 **Workspaces e Equipes**
  - Múltiplos workspaces (pessoal/trabalho)
  - Convite de membros
  - Controle de permissões
  - Colaboração em tempo real

- ✅ **Gestão de Tarefas**
  - Criação e organização de tarefas
  - Atribuições e dependências
  - Anexos e comentários
  - Tags e categorização

- 📈 **Visualizações**
  - Lista priorizada
  - Kanban board
  - Matriz GUT
  - Dashboards personalizados

- 🔔 **Notificações**
  - Alertas de alta prioridade
  - Lembretes de prazos
  - Notificações de atribuição
  - Atualizações de tarefas

- 🔄 **Integrações**
  - Jira
  - Trello
  - Asana
  - API pública

## 🚀 Tecnologias

### Frontend
- Next.js
- TypeScript
- Tailwind CSS
- Shadcn/UI
- Zustand
- React Query

### Backend
- NestJS
- TypeScript
- Drizzle ORM
- PostgreSQL
- Redis

### DevOps
- Docker
- AWS (ECS, RDS, S3)
- GitHub Actions
- Terraform

## 📦 Estrutura do Projeto

```
apps/
  ├── web/           # Aplicação Next.js
  ├── api/           # API NestJS
  └── admin/         # Painel de administração
packages/
  ├── ui/            # Componentes compartilhados
  ├── config/        # Configurações compartilhadas
  ├── types/         # Tipos TypeScript
  ├── utils/         # Utilitários
  ├── auth/          # Lógica de autenticação
  └── env/           # Configurações de ambiente
```

## 🛠️ Desenvolvimento

### Pré-requisitos

- Node.js 18+
- Docker
- pnpm

### Instalação

1. Clone o repositório
```bash
git clone https://github.com/seu-usuario/gutpriority.git
cd gutpriority
```

2. Instale as dependências
```bash
pnpm install
```

3. Configure as variáveis de ambiente
```bash
cp .env.example .env
```

4. Inicie os serviços Docker
```bash
docker-compose up -d
```

5. Execute as migrações
```bash
pnpm db:migrate
```

6. Inicie o ambiente de desenvolvimento
```bash
pnpm dev
```

## 📝 Documentação

- [Especificação do Projeto](./documentation/project-spec.md)
- [Documento de Design](./documentation/design-doc.md)
- [Modelo de Domínio](./documentation/domain-model.md)
- [Requisitos do Projeto](./documentation/project-requirements.md)
- [ADRs](./documentation/adrs/)
- [Diagramas](./documentation/diagrams/)

## 🤝 Contribuição

1. Faça o fork do projeto
2. Crie uma branch para sua feature (`git checkout -b feature/AmazingFeature`)
3. Commit suas mudanças (`git commit -m 'feat: Add AmazingFeature'`)
4. Push para a branch (`git push origin feature/AmazingFeature`)
5. Abra um Pull Request

## 📄 Licença

Este projeto está sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.

## 📊 Roadmap

### Fase 1: MVP (Mês 1-3)
- [x] Configuração do monorepo
- [ ] Autenticação básica
- [ ] CRUD de tarefas
- [ ] Avaliação GUT
- [ ] Interface básica

### Fase 2: Colaboração (Mês 4-6)
- [ ] Workspaces e equipes
- [ ] Avaliação colaborativa
- [ ] Notificações
- [ ] Dashboards

### Fase 3: Expansão (Mês 7-12)
- [ ] Integrações
- [ ] Analytics
- [ ] API pública
- [ ] Monetização
