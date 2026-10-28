# Registro de Decisões Arquiteturais (ADR)

Este documento registra as decisões técnicas, convenções de código e premissas de arquitetura do projeto. Agentes de IA **devem consultar este arquivo antes de propor grandes mudanças**.

---

## 📌 Convenções Gerais

- **Estilo de Código:** Manter padrões de código limpo (Clean Code) e princípios SOLID.
- **Persistência de Contexto:** Utilizar o protocolo **ShareBrain** via `.ai-workspace/` para registro de estado, histórico e decisões.

---

## 🏛️ Registros de Decisão (ADRs)

### ADR-001: Adoção do Protocolo ShareBrain para Persistência Local
- **Status:** Aceito
- **Data:** 2026-10-28
- **Contexto:** Necessidade de alternar entre diferentes ferramentas de CLI de IA (Claude Code, OpenCode, Cursor) sem perda de contexto e sem expor portas ou servidores externos.
- **Decisão:** Adotar uma estrutura baseada em arquivos estáticos locais dentro de `.ai-workspace/` com ponteiros na raiz (`ShareBrain.md`, `CLAUDE.md`, `AGENTS.md`).
- **Consequências:** Todo agente deve obrigatoriamente ler e atualizar o estado ao iniciar e encerrar suas sessões.