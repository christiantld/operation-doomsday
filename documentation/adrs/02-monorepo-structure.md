# ADR 2: Estrutura Monorepo com Turborepo

## Status

Aceito

## Contexto

Com o desenvolvimento do GUTPriority, precisamos definir a estrutura do projeto que permita:

- Compartilhamento eficiente de código entre frontend e backend
- Facilidade de manutenção para um único desenvolvedor inicialmente
- Capacidade de escalar conforme a equipe cresce
- Gerenciamento eficiente de dependências e builds
- Consistência de código e configurações entre diferentes partes do sistema

## Decisão

Decidimos utilizar uma estrutura de monorepo gerenciada com Turborepo, organizando o código em apps e packages compartilhados.

Estrutura básica:
```
apps/
  ├── web/           # Aplicação Next.js
  ├── api/           # API NestJS
  └── admin/         # Painel de administração
packages/
  ├── ui/            # Componentes compartilhados
  ├── config/        # Configurações compartilhadas
  ├── types/         # Tipos TypeScript compartilhados
  ├── utils/         # Utilitários compartilhados
  ├── auth/          # Lógica de autenticação compartilhada
  └── env/           # Configurações de ambiente
```

## Consequências

### Consequências Positivas

- **Compartilhamento de Código:** Facilita o compartilhamento de tipos, componentes e utilitários entre diferentes partes da aplicação.

- **Consistência:** Garante consistência de versões de dependências e configurações em todo o projeto.

- **DX Melhorada:** Turborepo oferece cache inteligente e builds otimizados, melhorando a experiência de desenvolvimento.

- **Manutenção Simplificada:** Um único repositório facilita a manutenção por um desenvolvedor individual.

- **Versionamento Unificado:** Facilita o controle de versão e a gestão de mudanças que afetam múltiplas partes do sistema.

### Consequências Negativas

- **Complexidade Inicial:** A configuração do monorepo e do Turborepo requer um esforço inicial maior.

- **Tamanho do Repositório:** O repositório crescerá mais rapidamente por conter todo o código do projeto.

- **CI/CD:** Pode requerer configurações mais complexas para CI/CD, especialmente para deploys parciais.

A estrutura de monorepo com Turborepo oferece benefícios significativos para o desenvolvimento inicial e futuro crescimento do GUTPriority, justificando a complexidade inicial adicional. 