# HARDed AI

Arquitetura persistente:

HARDed Web -> GitHub Actions -> runner -> Llama 3.2 3B -> várias mensagens -> encerra.

O workflow fica com o modelo carregado e monitora `chat/queue.json`. A interface web coloca novas mensagens nessa fila. O runner processa e grava a resposta no mesmo arquivo.

Coloque o workflow em `.github/workflows/harded-persistent-chat.yml` (não na raiz).

O token usado no navegador precisa permitir:
- Actions: Read and write
- Contents: Read and write

O token não é armazenado no código; fica apenas na memória da página.
