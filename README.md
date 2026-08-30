# Revolt Desktop - chat.painelrp.app.br

Cliente desktop (Electron) configurado para conectar automaticamente no servidor
self-hosted **chat.painelrp.app.br**. Escolha uma das opcoes abaixo.

## Opcao 1 - So usar pelo navegador (mais simples)

Nao precisa instalar nada: acesse **https://chat.painelrp.app.br** no Chrome/Edge/Firefox.

## Opcao 2 - App portatil (recomendado pra quem quer app desktop)

1. Baixe `revolt-desktop-painelrp-portable.zip` na aba [Releases](../../releases).
2. Extraia o zip em qualquer pasta.
3. Rode `Revolt.exe`.

Nao precisa instalar - e uma copia portatil, ja configurada e com o bug de tela
preta corrigido.

## Opcao 3 - Ja tenho o Revolt Desktop instalado, so quero aplicar o patch

Se voce ja instalou o Revolt Desktop (fork) por conta propria e quer so
redirecionar/corrigir a instalacao existente:

1. Baixe `apply-patch.ps1` na aba [Releases](../../releases).
2. Clique com o botao direito no arquivo > **Executar com o PowerShell**
   (ou abra um terminal PowerShell na pasta e rode `.\apply-patch.ps1`).
3. O script fecha o app, faz backup do `app.asar` original, aplica a versao
   corrigida e reabre o app automaticamente.

## O que foi corrigido

- App apontava para `app.revolt.chat` (oficial) em vez do servidor self-hosted.
- Tela preta ao abrir: o frontend (Stoat) espera uma API `window.desktopConfig`
  que este fork nao expunha no preload - foi adicionado um shim de
  compatibilidade.
