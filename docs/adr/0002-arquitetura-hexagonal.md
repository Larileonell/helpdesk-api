# ADR-002: Arquitetura hexagonal (Ports & Adapters)
Status: Aceito · Data: 25/11/2026

## Contexto
O helpdesk tem regras de negócio importantes (prazo de SLA por prioridade,
fluxo de status, permissões). No modelo em camadas tradicional, essas regras
ficam acopladas ao Spring e ao banco (entidades JPA, repositórios),
o que dificulta testar e mudar tecnologia.

## Decisão
Usar arquitetura hexagonal:
- domain: modelo e regras do negócio, sem dependência de Spring ou banco;
- application: casos de uso e portas (interfaces de entrada e saída);
- adapters: implementações de tecnologia (REST, JPA/PostgreSQL, agendador).
  As dependências sempre apontam para dentro: adapters → application → domain.

## Consequências
- Boas: regras testáveis sem banco e sem Spring; trocar tecnologia não afeta
  o núcleo; código organizado pelo negócio.
- Ruins: mais classes e interfaces; mapeamento entre o modelo de domínio
  e as entidades JPA; curva de aprendizado inicial.