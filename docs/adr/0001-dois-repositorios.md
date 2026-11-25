# Helpdesk API

## Problema
A TI recebe pedidos de suporte por e-mail e WhatsApp, e chamados se perdem.

## Solução
API de chamados com perfis (cliente, atendente, admin), fluxo de status,
prazo de atendimento (SLA) por prioridade e alerta quando o prazo estoura.

## Stack
Java 21, Spring Boot 4, PostgreSQL, Docker, arquitetura hexagonal.

## Decisões
- [ADR-001: Dois repositórios](docs/adr/0001-dois-repositorios.md)
- [ADR-002: Arquitetura hexagonal](docs/adr/0002-arquitetura-hexagonal.md)