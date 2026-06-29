# Minhas Finanças

App web (PWA) simples para registrar **entradas** e **saídas**, organizar por **categoria** e acompanhar as **métricas** do mês.

É um projeto **separado** do app *Meu Painel* (que fica em `~/Documents/Tracker`). Compartilha apenas a mesma **conta de login** (Firebase) — mas os dados financeiros ficam guardados num lugar próprio na nuvem (`users/<uid>/financas`), sem se misturar com os do Painel.

## Arquivos
- `index.html` — o app inteiro (HTML + CSS + JS num arquivo só, sem build).
- `manifest.json` — configuração do PWA (nome, ícones, cor).
- `sw.js` — service worker (funciona offline; cache `financas-eliel-v1`).
- `icon-192.png` / `icon-512.png` — ícones do app.

## Abas
- **Resumo** — saldo do mês em destaque, entradas/saídas/saldo acumulado, orçamento e gráficos por categoria.
- **Lançar** — adicionar entrada/saída (valor, categoria, descrição, data) e ver a lista do mês.
- **Categorias** — criar/editar/ocultar categorias de receita e de gasto, com cores.
- **Relatório** — entradas x saídas dos últimos 6 meses, médias, taxa de poupança e gasto por categoria.

Setas ‹ › no topo trocam o mês.

## Dados
- Salvos no aparelho em `localStorage` (chave `financas-eliel-v1`).
- Sincronização opcional entre aparelhos pela mesma conta do Painel (botão "☁ Ativar sincronização").
- Backup/exportar e importar `.json` nas Configurações (engrenagem no canto inferior direito).

## Rodar local pra testar
Preview do Claude Code: servidor `financas` na porta 8788 (em `.claude/launch.json`).

## Publicar (GitHub Pages)
Este é um repositório git próprio. Para publicar:
1. Criar um repositório novo no GitHub (ex.: `financas`).
2. `git remote add origin <url-do-repo>` e `git push -u origin main`.
3. Em Settings → Pages, apontar para a branch `main`.
4. O app fica em `https://<seu-usuario>.github.io/financas/`.

Publicar mudanças depois: `git add -A && git commit -m "..." && git push`.
