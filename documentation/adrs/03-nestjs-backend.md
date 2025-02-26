# ADR 3: NestJS como Framework Backend

## Status

Aceito

## Contexto

Para o desenvolvimento do backend do GUTPriority, precisamos de um framework que:

- Permita desenvolvimento rápido e estruturado
- Ofereça boa integração com TypeScript
- Forneça estrutura para implementar Clean Architecture e DDD
- Suporte os requisitos de performance (resposta < 300ms para 95% das requisições)
- Facilite a implementação de autenticação, autorização e outros recursos de segurança
- Seja escalável para suportar o crescimento do sistema

## Decisão

Decidimos utilizar NestJS como framework backend, junto com:
- Drizzle ORM para acesso ao banco de dados
- Passport.js para autenticação
- Class-validator para validação
- Swagger para documentação da API

## Consequências

### Consequências Positivas

- **Arquitetura Organizada:** NestJS fornece uma estrutura modular que facilita a implementação de Clean Architecture e DDD.

- **TypeScript Nativo:** Integração perfeita com TypeScript, garantindo type safety e melhor DX.

- **Decorators Poderosos:** Simplifica a implementação de validação, autenticação e documentação.

- **Escalabilidade:** Suporte nativo a microsserviços facilita a evolução futura da arquitetura.

- **Segurança:** Recursos robustos para implementar autenticação, autorização e proteção contra vulnerabilidades comuns.

### Consequências Negativas

- **Overhead de Abstração:** As múltiplas camadas de abstração podem impactar levemente a performance.

- **Complexidade:** A arquitetura opinada do NestJS pode parecer complexa inicialmente.

- **Boilerplate:** Necessidade de escrever mais código devido à natureza estruturada do framework.

A escolha do NestJS alinha-se bem com os requisitos do projeto, oferecendo uma base sólida para construir uma API robusta e manutenível, mesmo que isso signifique um pouco mais de código inicial. 