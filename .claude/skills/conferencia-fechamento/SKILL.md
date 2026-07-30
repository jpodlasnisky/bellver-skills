---
name: conferencia-fechamento
description: Confere os lançamentos de uma competência de todos os clientes da Bellver e grava um relatório de achados em relatorios/. Use quando pedirem "conferência do fechamento", "confere o mês", "o que tem de errado em julho" ou quando uma rotina agendada disparar o fechamento mensal.
---

## Tarefa

Conferir os lançamentos da competência informada, de **todos** os clientes em `clientes/`,
e gravar um relatório de achados em `relatorios/`.

> **Esta skill foi escrita para rodar sem ninguém por perto.** Ela nunca pergunta nada.
> Se faltar informação, ela assume o padrão descrito abaixo e **registra a suposição no
> relatório**.

## Entrada

- **Competência:** informada por quem chamou, no formato `aaaa-mm`.
  Se não foi informada, use o **mês anterior ao atual** e registre isso no relatório.
- **Clientes:** todas as pastas dentro de `clientes/`. Não receba lista por parâmetro —
  se entrar cliente novo no escritório, ele entra na conferência sozinho.

## Passos

1. Liste as pastas de `clientes/`.
2. Para cada cliente:
   a. Leia `clientes/<pasta>/ficha.md` — razão social, regime tributário, responsável na Bellver.
   b. Leia `clientes/<pasta>/lancamentos-<mes>-<ano>.csv` da competência.
      Se o arquivo não existir, registre `SEM DADOS` e **siga para o próximo cliente**.
   c. Some receitas e despesas, calcule o resultado.
   d. Rode as **6 verificações** da seção "Regras de conferência" do `CLAUDE.md`.
3. Grave o relatório em `relatorios/<aaaa-mm>-conferencia.md`.
4. Não altere nenhum arquivo dentro de `clientes/`.

## Formato da saída

Grave exatamente nesta estrutura:

```markdown
# Conferência de fechamento — <mm/aaaa>

**Rodou em:** <data e hora>
**Clientes lidos:** <n> · **Sem dados:** <n>
**Competência assumida por padrão?** <sim/não>

---

## <Razão social> · <regime tributário> · resp. <nome>

RECEITAS ....... R$ X
DESPESAS ....... R$ Y
RESULTADO ...... R$ Z

**Achados:**
- [GRAVE|ATENÇÃO|INFO] <descrição> — <documento> — <o que fazer>

(repetir por cliente)

---

## Resumo para o responsável

- <n> achados GRAVE, <n> ATENÇÃO
- Clientes que precisam de decisão humana: <lista>

conferir antes de enviar ao cliente
```

## Classificação dos achados

| Nível | Quando usar |
|---|---|
| `GRAVE` | altera o valor do tributo ou o resultado do mês (duplicata, imobilizado como despesa, receita no anexo errado) |
| `ATENÇÃO` | precisa de decisão humana, mas pode estar correto (prejuízo no mês, valor fora do padrão) |
| `INFO` | registro, sem ação imediata (nota ilegível já conhecida, cliente sem dados) |

## ❗ Regras

- **Nunca invente um número.** Valor ilegível vira `NÃO LEGÍVEL` e vira achado `INFO`.
- **Nunca altere arquivo em `clientes/`.** Esta skill só lê dados de cliente.
- **Nunca envie nada.** Ela grava um arquivo. Ponto.
- **Um cliente com problema não pode derrubar os outros.** Se a leitura de um cliente falhar,
  registre o erro como achado `INFO` daquele cliente e continue a conferência dos demais.
- **Se não houver nenhum achado, gere o relatório assim mesmo**, com "nenhum achado nesta
  competência". Relatório que não existe é indistinguível de rotina que não rodou.
- **Prejuízo no mês nunca é conclusão, é pergunta.** Antes de reportar prejuízo, verifique se
  há compra de equipamento lançada como despesa. Se houver, reporte as duas coisas juntas:
  o resultado apurado e o resultado que sairia se o imobilizado fosse reclassificado.
- Todo total termina com `(conferir antes de enviar ao cliente)`.
