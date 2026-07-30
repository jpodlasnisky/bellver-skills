# Bellver Contabilidade — regras da casa

> Este arquivo é lido **automaticamente** por qualquer agente que abrir este repositório —
> inclusive as **rotinas**, que rodam de madrugada sem ninguém por perto.
> Tudo que estiver escrito aqui vale para elas também. Tudo que **não** estiver escrito
> aqui, elas não sabem.

## Quem somos

A Bellver Contabilidade é um escritório contábil que atende pequenas e médias empresas.
Este repositório guarda os **procedimentos do escritório** em forma executável: as skills
que qualquer pessoa da equipe pode rodar, e as rotinas que rodam sozinhas.

## Os clientes deste repositório

Todos os dados aqui são **fictícios**, criados para treinamento. Ver `clientes/`.

| Pasta | Razão social | Regime | Responsável na Bellver |
|---|---|---|---|
| `padaria-do-ze` | Padaria do Zé Comércio de Alimentos ME | Simples Nacional — Anexo I | Marina |
| `mercado-luz-ltda` | Mercado Luz Ltda | Lucro Presumido | Marina |
| `oficina-bom-motor` | Oficina Bom Motor Serviços Automotivos Ltda | Simples Nacional — Anexo III | Rafael |

## Padrões de formatação

- **Data:** `dd/mm/aaaa`
- **Moeda:** `R$ 1.234,56` — sempre com `R$`, ponto de milhar e vírgula decimal
- **CNPJ:** sempre com máscara `00.000.000/0000-00`
- **Competência:** `mm/aaaa` (ex.: `07/2026`)
- **Nome de arquivo de relatório:** `aaaa-mm-<assunto>.md` (ex.: `2026-07-conferencia.md`)

## Tom de comunicação

- Direto e sem jargão desnecessário. O cliente não é contador.
- Nunca prometer prazo ou valor que não esteja confirmado no documento.
- Ao apontar um problema, dizer **o que fazer**, não só que existe um problema.

## ❗ NUNCA FAÇA

- **Nunca invente um número.** Valor que não puder ser lido com certeza vira `NÃO LEGÍVEL`.
- **Nunca envie nada para ninguém.** Rascunho e arquivo, sim. Envio, nunca — quem envia é humano.
- **Nunca coloque dado real de cliente neste repositório.** Ele é compartilhado e não protege nada.
- **Nunca apague ou reescreva** arquivo em `clientes/`. Este repositório só **lê** dados de cliente.
- **Nunca trate um total calculado como fechado.** Todo número gerado aqui é rascunho até um
  contador conferir.

## Regras de conferência que valem para todo cliente

Estas são as verificações que a Bellver faz em todo fechamento. Quem escrever uma skill de
conferência deve cobrir pelo menos estas:

1. **Lançamento duplicado** — mesmo documento, mesmo valor, mesma data.
2. **Valor negativo** — devolução e estorno não se lançam como despesa negativa.
3. **Retirada de sócio classificada como despesa operacional** — distribuição de lucro não é despesa.
4. **Imobilizado lançado como despesa** — compra de equipamento é ativo, não custo do mês.
5. **Receita de serviço misturada com venda de mercadoria** — muda a base de cálculo do tributo.
6. **Nota ilegível ou com campo faltando.**

> Se um cliente do Simples Nacional aparecer com receita de serviço e de mercadoria no mesmo
> mês, isso é **anexo diferente** e precisa de separação. Sinalize sempre.

## Como as rotinas devem se comportar

- Toda rotina **grava um relatório em `relatorios/`** e faz commit. Nunca deixa a saída só na tela.
- Todo relatório começa dizendo **quando rodou, o que leu e o que não conseguiu ler**.
- Se não houver nada a relatar, o relatório é gerado **mesmo assim**, dizendo "nenhum achado".
  Silêncio não é sinal de que está tudo certo — é sinal de que ninguém sabe.
- Toda rotina termina com a linha: `conferir antes de enviar ao cliente`.
