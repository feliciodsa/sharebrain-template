# ShareBrain: Protocolo de Memória Compartilhada para Agentes de IA

O **ShareBrain** é um padrão aberto, local e seguro de persistência de contexto multi-agente. Ele garante a continuidade de tarefas entre diferentes ferramentas no terminal (Claude Code, OpenCode, Cursor, etc.), eliminando a amnésia de contexto.

---

## 📂 Estrutura do Workspace (`.ai-workspace/`)

O cérebro compartilhado reside no diretório `.ai-workspace/` na raiz do repositório:

- `state.json`: Estado volátil atual (onde o projeto está agora).
- `history.jsonl`: Diário de bordo cronológico de ações (Append-only).
- `decisions.md`: Log de decisões arquiteturais e premissas técnicas.
- `checkpoints/`: Snapshots imutáveis de transições entre agentes.

---

## 🤖 Protocolo de Operação Obrigatório

Qualquer agente que iniciar uma sessão neste repositório **deve obrigatoriamente** seguir o ciclo de 3 etapas:

### 1. Inicialização (Wake-up)
Ao ser ativado, antes de propor ou alterar qualquer código:
1. Leia `.ai-workspace/state.json` para absorver o objetivo atual, tarefas pendentes e arquivos ativos.
2. Leia as últimas 5 a 10 linhas de `.ai-workspace/history.jsonl` para entender as ações executadas recentemente.
3. Consulte `.ai-workspace/decisions.md` para respeitar as premissas e decisões técnicas já tomadas.

### 2. Execução (Work)
Realize o trabalho solicitado mantendo o escopo alinhado com o estado ativo e sem desfazer padrões registrados em `decisions.md`.

### 3. Encerramento e Handoff (Checkpoint)
Ao concluir sua tarefa ou ao finalizar a sessão:
1. Registre uma nova linha no `.ai-workspace/history.jsonl` descrevendo o que foi feito e os testes executados.
2. Atualize o `.ai-workspace/state.json` ajustando o status, tarefas pendentes e os últimos arquivos modificados.