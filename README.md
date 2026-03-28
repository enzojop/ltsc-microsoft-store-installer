# Add Microsoft Store no Windows 10 LTSC

Script para adicionar a Microsoft Store no Windows 10 Enterprise LTSC 2019, versão que normalmente não inclui esse componente por padrao.

## Sobre

O Windows 10 Enterprise LTSC e focado em estabilidade para ambientes corporativos, com menos apps nativos. Por isso, a Microsoft Store vem removida.

Este projeto restaura a Store e suas dependencias, permitindo:

- Instalar aplicativos UWP
- Usar recursos que dependem da Microsoft Store
- Instalar jogos e apps com compras integradas

## Compatibilidade

- Windows 10 Enterprise LTSC 2019
- Permissoes de administrador obrigatorias

## Download

Baixe o pacote oficial utilizado no processo:

- [Download do pacote](https://forums.mydigitallife.net/threads/add-store-to-windows-10-enterprise-ltsc-LTSC.70741/page-30#post-1468779)

## Instalacao

1. Baixe e extraia os arquivos do projeto.
2. Localize o arquivo `Add-Store.cmd`.
3. Execute o arquivo como Administrador.
4. Aguarde a instalacao dos pacotes.
5. Reinicie o computador, se solicitado.

## Personalizacao (opcional)

Antes de executar o script, voce pode remover componentes opcionais apagando os arquivos `.appxbundle` correspondentes:

- App Installer
- Purchase App
- Xbox Identity

Se voce pretende instalar jogos ou aplicativos com compras internas, mantenha esses componentes.

## Solucao de problemas

### 1. Reiniciar o sistema

Se a Microsoft Store nao abrir apos a instalacao, reinicie o computador.

### 2. Reinstalar registro da Store via PowerShell

Abra o Prompt de Comando como administrador e execute:

```powershell
PowerShell -ExecutionPolicy Unrestricted -Command "& {$manifest = (Get-AppxPackage Microsoft.WindowsStore).InstallLocation + '\AppxManifest.xml' ; Add-AppxPackage -DisableDevelopmentMode -Register $manifest}"
```

Depois, reinicie o sistema novamente.

### 3. Limpar cache da Store

1. Pressione `Win + R`.
2. Digite `WSReset.exe`.
3. Pressione `Enter`.

## O que o script faz

- Instalacao manual de pacotes `.appx` e `.appxbundle`
- Registro da Microsoft Store no sistema
- Inclusao das dependencias necessarias

## Avisos importantes

- Requer privilegios de administrador
- Pode nao funcionar em versoes diferentes do LTSC 2019
- Recomenda-se criar um ponto de restauracao antes de executar

## Creditos

- Script original: abbodi1406
- Fonte: [MyDigitalLife Forum](https://forums.mydigitallife.net/threads/add-store-to-windows-10-enterprise-ltsc-LTSC.70741/page-30#post-1468779)
