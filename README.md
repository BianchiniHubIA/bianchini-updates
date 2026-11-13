# Bianchini Updates

Canal de atualização automática do **Bianchini Desk** (opção B: GitHub Releases público).

Este repositório contém **apenas binários de distribuição** (MSI e arquivos de assinatura).
Nenhum código-fonte mora aqui. O código do programa fica no repositório privado
`BianchiniHubIA/bianchini-desk`.

## Como o programa encontra a versão nova

1. O Bianchini Desk baixa `latest.json` deste repositório (branch `main`).
2. Se a versão apontada for maior que a instalada, o botão **Update** aparece.
3. Ao clicar, o programa baixa e verifica `bianchini-update.json` + `bianchini-update.json.sig`
   (assinatura ed25519) da release, confere o sha256 do MSI e instala sozinho.

## Como publicar uma versão nova

No PC do Victor, dentro do repositório `bianchini-desk`:

    python tools\publish_update.py --msi <caminho-do-msi> --version 1.5.6 --notes "O que mudou"

O script cria a release aqui, atualiza o `latest.json` e valida a assinatura.
A chave privada de assinatura fica somente em `C:\Users\Bianchini\.agents\bianchini-update-keys\signing.key`.
