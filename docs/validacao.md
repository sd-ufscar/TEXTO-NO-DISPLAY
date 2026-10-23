# Validação e preservação — TEXTO-NO-DISPLAY

Verificações estáticas realizadas em **23 de outubro de 2026**. A publicação preserva a organização interna da pasta local, a lógica, os parâmetros e as conexões dos circuitos.

## Integridade dos arquivos locais

| Conferência | Resultado |
|---|---|
| Arquivos locais inventariados | 337 |
| Arquivos da pasta original versionados | 63 |
| Intermediários e estado local ignorados | 274 |
| Dependências espelhadas na raiz | 0 |
| Resumos de compilação originais preservados | 3 |
| Alterações de bytes nas fontes locais ou nas cópias | Nenhuma |
| ROM conferida | 64 endereços, 8 bits, todos preenchidos |
| Referências verificadas a partir do QSF ativo | 24 |

O [inventário completo](inventario-local.csv) registra cada caminho, tamanho, SHA-256 e decisão de versionamento. As cópias publicadas devem conservar os hashes correspondentes. O conjunto mantém a subpasta original `Texto_Display/Lab_04/`. As capturas PNG são registros originais; seus valores diferem da ROM atual e não comprovam sua simulação.

## Conteúdo preexistente no repositório

Base anterior: `525c35b0add21f3e75ae4450ed3fc97a8a66e9a0`. As movimentações foram realizadas com `git mv`. O conteúdo de cada arquivo foi preservado:

| Caminho anterior | Destino | SHA-256 |
|---|---|---|
| `README.md` | [comprimido/README-original.md](../comprimido/README-original.md) | `5722879e5c11f1125b39ebf60baf8f3a4dd54c0f9bc9baac297a39e79a9633be` |
| `TEXTO_DISPLAY.zip` | [comprimido/TEXTO_DISPLAY.zip](../comprimido/TEXTO_DISPLAY.zip) | `e4d7e37f7b9d87e1ed284a307cb602ff58fa81756d05d567f1f3988558977661` |
| `result.zip` | [comprimido/result.zip](../comprimido/result.zip) | `93b9bc9f2557e4a6d9d587dac2c9dfc49a4f30b6e00e57555f2d5b6c787040ac` |

Nenhum arquivo preexistente foi descartado, recompactado ou substituído. Uma referência local de backup conserva o commit anterior; o histórico remoto não é reescrito.

## Dependências e configuração

A revisão é `texto_display`, o topo é `texto_display` e o dispositivo é `5CSXFC6D6F31C6`. Foram conferidos os arquivos de IP relacionados pelo QSF, seus arquivos gerados, símbolos e inicialização da ROM. As referências ativas ficam contidas no repositório; o modelo geral `Arquivo_Pinos_DE10_2V5.qsf` não é importado pela revisão ativa.

O QPF conserva `QUARTUS_VERSION = "25.1"`, enquanto o QSF registra a última utilização em 23.1 e os IPs declaram 23.1. Essa diferença de metadados foi preservada; a abertura no Quartus 23.1 não foi verificada.

Os arquivos `.v` preservados pertencem aos componentes gerados pelo ambiente gráfico do Quartus. A implementação do experimento permanece em BDF; não foi adicionada uma reimplementação HDL.

O atributo `linguist-generated` identifica esses arquivos de IP nos metadados do GitHub. Eles continuam presentes para reprodução do projeto; a marcação apenas os caracteriza como gerados para as estatísticas e comparações da plataforma.

## Exclusões do versionamento

| Grupo | Justificativa |
|---|---|
| `db/`, `incremental_db/`, `greybox_tmp/` | Bancos, bloqueios e intermediários regenerados pelo Quartus |
| `output_files/` | Relatórios, netlists e arquivos de programação regeneráveis; três resumos históricos preservados em `docs/relatorios-originais/` |
| `*.bak` | Cópias de edição que não integram a revisão ativa |
| `*.qws` | Estado local da interface Quartus |
| `simulation/questa/*.vo` e `*.sft` | Netlist de simulação e arquivos de apoio gerados; não são estímulos originais ou configurações de IP |

Não foram ignorados globalmente `.v`, `.qpf`, `.qsf`, `.bdf`, `.bsf`, `.qip`, `.mif`, `.hex`, `.cmp` ou `.inc`. A cópia local integral permanece preservada; as exclusões tratam do conteúdo enviado ao GitHub.

## Relatórios e limites da validação

Os resumos originais de [síntese](relatorios-originais/texto_display.map.summary), [Fitter](relatorios-originais/texto_display.fit.summary) e [temporização](relatorios-originais/texto_display.sta.summary) registram a compilação de **22 de outubro de 2026**. O Fitter consta como concluído, mas o Timing Analyzer apresenta folgas negativas. Esses registros não certificam fechamento temporal nem uma compilação executada durante a publicação.

O Quartus Prime não foi encontrado no PATH ou nos diretórios usuais do ambiente. Não foram realizados abertura dos projetos no Quartus, nova síntese, simulação, gravação ou ensaio físico. O funcionamento descrito no [README](../README.md) é fundamentado nos esquemáticos, nos parâmetros dos IPs, no MIF e nos registros originais, com os cálculos teóricos identificados.

Foram conferidos os links relativos, os hashes de preservação e os tamanhos dos arquivos preparados para commit. A inspeção automática do conteúdo novo não detectou padrões usuais de tokens, chaves privadas ou caminhos pessoais. Os arquivos preexistentes em `comprimido/` mantêm o conteúdo que já estava publicado.
