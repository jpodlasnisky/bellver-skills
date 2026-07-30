# bellver-skills

**Os procedimentos do escritório, em forma executável.**

Este repositório é o lugar onde as skills da Bellver deixam de morar no computador de uma
pessoa e passam a ser do escritório: versionadas, iguais para todos, e disponíveis para as
**rotinas** que rodam sozinhas.

> ⚠️ **Todos os dados aqui são fictícios.** Este repositório nunca recebe dado real de
> cliente — nem CPF, nem CNPJ verdadeiro, nem valor de fechamento de verdade. Ele é
> compartilhado e não protege nada.

---

## Como ele está organizado

```
bellver-skills/
├── CLAUDE.md                    ← as regras da casa. Todo agente lê isto primeiro.
├── .claude/skills/              ← os procedimentos
│   ├── conferencia-fechamento/  ← exemplo completo, pronto para rodar sozinho
│   └── MODELO/                  ← modelo em branco: copie esta pasta
├── clientes/                    ← dados fictícios. SOMENTE LEITURA.
│   ├── padaria-do-ze/
│   ├── mercado-luz-ltda/
│   └── oficina-bom-motor/
├── normas/                      ← circulares e normas de referência
├── relatorios/                  ← onde as rotinas gravam o resultado
└── rotinas/                     ← uma ficha por rotina agendada
    ├── conferencia-fechamento.md
    └── MODELO.md
```

---

## As três regras deste repositório

1. **`clientes/` é só leitura.** Nada aqui altera dado de cliente.
2. **Toda skill tem `Regras`** — e a primeira linha é a proibição mais importante.
3. **Toda rotina tem uma ficha em `rotinas/`.** Automação que ninguém sabe que existe
   é um problema esperando acontecer.

---

## Passo a passo — colocar a sua skill aqui

### 1. Traga o repositório para a sua máquina

Pelo navegador, na página do repositório: **`Code` → `Download ZIP`**, e extraia.
Ou, se você usa Git: `git clone <url do repositório>`.

### 2. Copie a sua skill para cá

Pegue a pasta da skill que você escreveu na Sessão 3 — aquela em
`.claude/skills/<sua-skill>/` na sua pasta de teste — e copie para
`.claude/skills/` **deste** repositório.

**Renomeie com o seu primeiro nome na frente:**

```
.claude/skills/ana-conferencia-mensal/SKILL.md
.claude/skills/carlos-comunicado-das/SKILL.md
```

O prefixo evita que duas pessoas gravem por cima uma da outra hoje. Quando um procedimento
vira o padrão único do escritório, aí sim ele perde o prefixo.

### 3. Produtize

Abra o Claude Code nesta pasta e passe pelo **checklist de 6 pontos** que está no fim de
`.claude/skills/MODELO/SKILL.md`. Resumo:

| # | Pergunta | Por quê |
|---|---|---|
| 1 | Ela pergunta alguma coisa? | Rotina não tem ninguém para responder |
| 2 | Os caminhos existem fora do seu PC? | O agente roda em outra máquina |
| 3 | Ela grava arquivo? | Saída só na tela, às 6h, ninguém vê |
| 4 | Ela diz o que **não** conseguiu fazer? | Falha silenciosa é o pior defeito |
| 5 | Ela aguenta arquivo faltando? | O caso estranho sempre chega |
| 6 | Outra pessoa entende sem você? | É o teste final de produto |

### 4. Escreva a ficha da rotina

Copie `rotinas/MODELO.md` para `rotinas/<sua-skill>.md` e preencha.
O campo mais importante é o **prompt** — é ele que a rotina vai executar.

### 5. Suba

Pelo navegador: **`Add file` → `Upload files`**, arraste as pastas, escreva a mensagem do
commit e confirme. Ou, com Git: `git add . && git commit -m "skill da ana" && git push`.

---

## Onde os relatórios aparecem

Em `relatorios/`. Cada rotina grava com o nome `aaaa-mm-<assunto>.md`.
Se o arquivo do mês não apareceu, a rotina não rodou — confira o histórico em
https://claude.ai/code/routines

---

## Rotinas ativas

| Rotina | Quando roda | Dono | Ficha |
|---|---|---|---|
| Conferência de fechamento | dia 5, 07:00 | Marina | [`rotinas/conferencia-fechamento.md`](rotinas/conferencia-fechamento.md) |

<!-- Ao criar uma rotina, adicione uma linha aqui. -->
