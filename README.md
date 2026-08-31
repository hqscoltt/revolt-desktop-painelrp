# Revolt Desktop - chat.painelrp.app.br

Cliente desktop (Electron) configurado para conectar automaticamente no servidor
self-hosted **chat.painelrp.app.br**. Escolha uma das opcoes abaixo.

## Opcao 1 - Instalador (recomendado)

1. Baixe `Revolt-Setup-1.0.0.exe` na aba [Releases](../../releases).
2. Rode o instalador e siga as etapas normalmente.
3. O Windows pode mostrar um aviso do SmartScreen (app sem certificado de
   assinatura de codigo) - clique em "Mais informacoes" > "Executar assim
   mesmo". Isso e esperado para apps distribuidos fora da loja/sem certificado
   pago, nao significa que o arquivo e malicioso.

O app ja vem com atualizacao automatica: quando sair uma versao nova, ele
baixa sozinho em segundo plano e avisa por notificacao para reiniciar e
aplicar.

## Opcao 2 - So usar pelo navegador

Nao precisa instalar nada: acesse **https://chat.painelrp.app.br** no Chrome/Edge/Firefox.

## Opcao 3 - App portatil (sem instalador)

1. Baixe `revolt-desktop-painelrp-portable.zip` na aba [Releases](../../releases).
2. Extraia o zip em qualquer pasta.
3. Rode `Revolt.exe`.

## Opcao 4 - Ja tenho o Revolt Desktop instalado, so quero aplicar o patch

Se voce ja instalou o Revolt Desktop (fork) por conta propria e quer so
redirecionar/corrigir a instalacao existente:

1. Baixe `apply-patch.ps1` na aba [Releases](../../releases).
2. Clique com o botao direito no arquivo > **Executar com o PowerShell**
   (ou abra um terminal PowerShell na pasta e rode `.\apply-patch.ps1`).
3. O script fecha o app, faz backup do `app.asar` original, aplica a versao
   corrigida e reabre o app automaticamente.

## O que foi corrigido

- App apontava para `app.revolt.chat` (oficial) em vez do servidor self-hosted.
- Tela preta ao abrir (`window.desktopConfig` ausente no preload).
- Tela de Settings nao abria (`window.native.versions` incompleto).
- Compartilhamento de tela nao funcionava (faltava o seletor de tela do
  Electron via `desktopCapturer`).
- Botoes de minimizar/maximizar nao respondiam (`native.maximise`/`minimise`
  ausentes).
- Clicar no icone da bandeja nao restaurava a janela.
- Atualizacao automatica em segundo plano com aviso para reiniciar.
