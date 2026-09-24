# MATRIXPS4

Host web personalizado para acesso pelo navegador do PlayStation 4, com interface inspirada no tema Matrix e suporte a cache offline do navegador.

## Acesso

**Página direta:**  
https://MrAndersonRPC.github.io/MATRIXPS4/jb.html

## Recursos

- Interface personalizada MATRIXPS4.
- Tema visual Matrix em preto e verde.
- Logo própria `logo_raw.png`.
- Indicador visual de carregamento durante a execução da página.
- Cache offline por meio de `cache.appcache`.
- Acesso rápido pelo sistema de Favoritos do navegador do PS4.
- Arquivos organizados para publicação pelo GitHub Pages.
- Estrutura mantida localmente no próprio repositório, sem depender do endereço do projeto de origem.

## Uso pelo navegador do PS4

Na primeira utilização, acesse a página com conexão à internet e aguarde o carregamento dos arquivos do cache.

Depois, salve a página nos **Favoritos** do navegador do PS4 para facilitar os próximos acessos.

Quando o cache estiver corretamente armazenado no console, os arquivos disponíveis offline poderão ser carregados sem depender novamente do endereço original de terceiros.

> **Importante:** apagar cookies, dados de sites ou o cache do navegador do PS4 pode remover os arquivos armazenados para uso offline.

## Estrutura principal

```text
MATRIXPS4/
├── index.html
├── jb.html
├── jb.js
├── cache.html
├── cache.appcache
├── core.js
├── mem.js
├── int64.js
├── ps4_offsets.js
├── rpc_worker.js
├── logo_raw.png
├── goldhen.bin
├── hen.bin
├── ps4debug.bin
└── patches/
```


## Modo offline-first

Esta versão foi preparada para reduzir dependências de rede depois que o cache do navegador estiver instalado:

- a telemetria HTTP `POST /t` do script foi desativada;
- o manifesto inclui todos os patches `.bin` existentes neste repositório;
- `jb.js`, módulos JavaScript, workers, logo e payloads existentes são armazenados pelo AppCache;
- a regra `NETWORK: *` foi removida para que recursos ausentes não sejam buscados silenciosamente pela rede.

Na primeira carga ou quando o manifesto for atualizado, mantenha o PS4 online até o cache terminar. Depois disso, os recursos listados no manifesto podem ser atendidos pelo cache do navegador.

**Observação técnica:** o código original ainda possui uma seleção genérica de `payload.bin` para algumas tabelas de firmware, mas esse arquivo não existe neste repositório. Esta versão não altera a seleção de payload por firmware, pois trocar um payload sem validação em hardware pode afetar a estabilidade.

## Hospedagem

Este repositório foi preparado para publicação pelo **GitHub Pages** a partir da branch `main` e da pasta raiz `/`.

Endereço do projeto:

https://MrAndersonRPC.github.io/MATRIXPS4/

## Identidade

**MATRIXPS4**  
**MATRIX HOST**

Personalização do projeto: **MrAndersonRPC**
