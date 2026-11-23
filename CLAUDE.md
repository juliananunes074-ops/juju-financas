# Juju Finanças — notas para o Claude

App pessoal de finanças da Juju, uma brasileira que mora na Argentina. Ela usa o app no iPhone, instalado na tela inicial ("Adicionar à Tela de Início") a partir do GitHub Pages, e ele abre em tela cheia.

- Endereço: https://juliananunes074-ops.github.io/juju-financas/
- Publicação: GitHub Pages, branch `main`, pasta raiz. Dar push na `main` já atualiza o app em 1–2 minutos.
- Tudo fica em um arquivo só: `index.html` (HTML, CSS e JS sem build). O ícone de florzinha e o manifest estão embutidos como data URI.
- Dados: Firebase Realtime Database do projeto `juju-financas`, com login por e-mail e senha. Cada usuária só lê e escreve em `users/<uid>`. A configuração do Firebase fica em `FIREBASE_CONFIG` dentro do `index.html` e não é segredo.
- Coleções em `users/<uid>`: `lancamentos` (Argentina, pesos ou reais, com `cotacao` de cada troca), `brasil` (contas do Brasil em reais, com `vencimento`) e `config/{limites,cotacoes,meta}`.

## Como falar com ela
- Sempre em português do Brasil, simples e carinhoso, um passo de cada vez. Ela não fala inglês e não é programadora.
- Quando precisar que ela faça algo no celular, peça um print e diga exatamente onde tocar.
- Visual: rosa, feminino, com florzinhas e carinhas (😄🙂😬😢). A abertura mostra o total gasto no mês. Ela pediu para não mostrar "quanto pode gastar por dia".

## Antes de publicar
- Testar o `index.html` localmente (por exemplo, Playwright com um Firebase falso) e conferir que o script não tem erro de sintaxe.
- Depois do push, avisar que ela pode precisar fechar e abrir o app para ver a versão nova.
