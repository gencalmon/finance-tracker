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
Repositório próprio no GitHub: **https://github.com/gencalmon/finance-tracker**
App publicado (GitHub Pages): **https://gencalmon.github.io/finance-tracker/**

Publicar mudanças depois de editar:

```
cd ~/Documents/Financas
git add -A && git commit -m "descrição da mudança" && git push
```

Em 1–2 minutos o site atualiza. No celular, se o app já estiver instalado, abra 1–2 vezes online pra pegar a versão nova.

Pra instalar no iPhone: abra o link no Safari → botão Compartilhar → "Adicionar à Tela de Início".
