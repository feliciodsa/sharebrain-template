# Instruções de Operação do Projeto (ShareBrain Protocol)

Este projeto utiliza o protocolo **ShareBrain** para persistência de contexto e handoff entre diferentes agentes de IA.

## 🚨 Regras Obrigatórias para os Agentes

### 1. Ao Iniciar a Sessão (Wake-up)
Antes de escrever código ou responder a qualquer solicitação, você DEVE:
1. Ler `.ai-workspace/state.json` para entender o objetivo atual e arquivos ativos.
2. Ler as últimas linhas de `.ai-workspace/history.jsonl` para absorver o histórico de ações recentes.
3. Consultar `.ai-workspace/decisions.md` para respeitar as decisões arquiteturais tomadas anteriormente.

### 2. Ao Concluir uma Tarefa (Checkpoint / Handoff)
Antes de finalizar seu turno ou entregar a solução:
1. Registre sua ação e os testes realizados no `.ai-workspace/history.jsonl` (formato JSON Lines).
2. Atualize o `.ai-workspace/state.json` com o status atual e as próximas tarefas pendentes.