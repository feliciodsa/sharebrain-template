# 🧠 ShareBrain

> **Cérebro compartilhado e protocolo de memória persistente para agentes de IA no terminal.**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Node.js](https://img.shields.io/badge/Node.js-%3E%3D18.0.0-green.svg)]()

 O **ShareBrain** resolve a amnésia de contexto em fluxos de desenvolvimento multi-agente. Alterne entre **Claude Code**, **OpenCode**, **Codex** ou scripts customizados sem perder o histórico de tarefas, decisões técnicas e arquivos ativos.

---

### ✨ Destaques

- 🔒 **100% Local & Seguro:** Sem servidores ativos, sockets ou portas expostas. Opera apenas via arquivos estáticos no repositório (`.ai-workspace/`).
- 🔄 **Handoff Perfeito:** O agente B assume a tarefa exatamente de onde o agente A parou.
- 📜 **Histórico Imutável:** Mantém log de ações (`history.jsonl`) e decisões arquiteturais (`decisions.md`).
- 🛡️ **Injeção Não-Destrutiva:** Preserva seus arquivos de regras existentes (`AGENTS.md`, `CLAUDE.md`, `.cursorrules`).
