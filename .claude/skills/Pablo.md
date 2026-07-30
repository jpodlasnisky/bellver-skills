---
name: organizacao-semanal
description: Monta o cronograma semanal do usuário e entrega uma planilha com as atividades priorizadas, respeitando o horário fixo de trabalho, 8h de sono, pausas e uma folga reservada para imprevistos. Use sempre que o usuário falar em organizar a semana, montar cronograma ou agenda, planejar/distribuir atividades, encaixar estudo e lazer na rotina, replanejar o que ficou pendente da semana passada, ou disser que "não está dando conta" das tarefas — mesmo que não peça uma planilha explicitamente. Não use para gerenciar a agenda de outras pessoas, nem para criar eventos em calendário ou enviar mensagens.
---

# Organização semanal

Transforma uma lista de atividades em uma semana realista: priorizada, encaixada nos horários que já existem e com espaço sobrando para a vida acontecer.

O erro mais comum ao montar cronogramas é otimismo aritmético — alocar mais horas do que a semana tem. Por isso o cálculo de capacidade vem **antes** da distribuição, nunca depois.

## Restrições fixas do usuário

Estas não se negociam. Nada é alocado por cima delas:

| Bloco | Quando |
|---|---|
| Sono | 8h por noite |
| Trabalho | Seg–Sex, 8h–12h e 14h–18h |
| Almoço | Seg–Sex, 12h–14h |
| Fim de semana | Sáb e Dom livres de trabalho |
| Sábado de manhã | Disponível para estudo ou gravação de vídeo (opcional, não obrigatório) |

## Passo 1 — Levantar as atividades

Se o usuário não listou as atividades, peça-as **em uma única mensagem**, não uma pergunta por vez. Para cada atividade, colete:

- **Nome**
- **Duração estimada** (em horas)
- **Categoria**: trabalho, estudo, lazer ou pessoal
- **Prazo**, se houver
- **Horário fixo?** (ex.: aula terça 19h) ou flexível

Se o usuário não souber a duração de algo, proponha uma estimativa e confirme. Não invente atividades que ele não mencionou.

## Passo 2 — Calcular a capacidade real da semana

Faça essa conta explicitamente e mostre o resultado ao usuário antes de montar a grade.

Por dia útil:

```
24h − 8h sono − 8h trabalho − 2h almoço = 6h
− rotinas fixas (deslocamento, refeições, higiene)  → perguntar; usar 1h30 se não informado
= tempo bruto disponível
− 20% de folga para imprevistos
= tempo alocável
```

Na prática isso costuma dar **3h30 a 4h por dia útil**. Fim de semana: até 4h no sábado de manhã e o restante livre por padrão — só ocupe o fim de semana se o usuário pedir.

Some as durações de todas as atividades. Se o total ultrapassar o alocável da semana, **não comprima os intervalos nem invada o sono**: informe o excedente em horas e ofereça três saídas — adiar para a semana seguinte, reduzir o escopo de alguma atividade, ou cortar as de menor prioridade. A decisão é do usuário.

## Passo 3 — Priorizar

Ordene nesta sequência:

1. **Âncoras** — compromissos com hora marcada. Entram primeiro e definem o formato da semana.
2. **Prazo curto + consequência alta** — o que quebra algo se atrasar.
3. **Importante sem prazo** — o que avança objetivos de médio prazo (estudo, projetos). Costuma ser o primeiro a ser sacrificado; proteja com bloco fixo.
4. **Opcional** — só entra se sobrar espaço alocável.

Empate: agrupe tarefas de menos de 30 minutos num único bloco em vez de espalhá-las pela semana.

## Passo 4 — Distribuir na grade

- Encaixe as âncoras, depois as prioridades em ordem.
- Blocos de 45 a 90 minutos, com 10 a 15 minutos de pausa entre eles. Nada de três horas seguidas sem intervalo.
- Tarefas que exigem concentração vão nos horários de maior energia do usuário; se ele não informou, pergunte se rende mais de manhã ou à noite.
- Deixe pelo menos **1 noite por semana inteiramente livre** e mantenha lazer como categoria alocada, não como sobra.
- A folga de 20% fica visível na planilha como espaço vazio — é onde os imprevistos caem sem derrubar o resto.

## Passo 5 — Gerar a planilha

Arquivo `.xlsx` com três abas:

**Aba `Semana`** — grade de horário × dia (Seg a Dom), blocos preenchidos e cor por categoria. Sono, trabalho e almoço aparecem sombreados como fixos.

**Aba `Atividades`** — uma linha por atividade:

| Prioridade | Atividade | Categoria | Duração | Prazo | Dia/horário alocado | Status |
|---|---|---|---|---|---|---|

**Aba `Resumo`** — horas por categoria, total alocado, capacidade da semana, folga restante em horas e em %.

Depois de salvar, apresente o arquivo ao usuário e resuma em 3–4 linhas: quanto foi alocado, quanto sobrou de folga, e o que ficou de fora (se algo ficou).

## Passo 6 — Replanejamento (semanas seguintes)

Quando o usuário voltar com pendências:

1. Pergunte o que **não** foi feito e por quê — falta de tempo, estimativa errada ou perda de interesse levam a ajustes diferentes.
2. Se foi estimativa errada, corrija a duração da atividade antes de reagendar. Repetir a mesma estimativa repete o atraso.
3. Reagende as pendências dentro do alocável da nova semana, **sem** somá-las por cima do que já estava planejado. Se não couber, aplique a regra do Passo 2.
4. Se a mesma atividade escorregar duas semanas seguidas, aponte isso ao usuário e pergunte diretamente: dividir em partes menores, marcar como âncora com hora fixa, ou tirar da lista. Uma tarefa arrastada por semanas geralmente não é prioridade real.

## Verificação antes de entregar

Confira, na ordem:

- [ ] 8h de sono preservadas todas as noites
- [ ] Nenhum bloco invadindo 8h–12h ou 14h–18h de segunda a sexta
- [ ] Folga ≥ 15% do tempo disponível ainda vazia
- [ ] Lazer presente na semana, não apenas trabalho e estudo
- [ ] Nenhuma atividade que o usuário não mencionou
- [ ] Total alocado ≤ capacidade calculada no Passo 2

Se algum item falhar, ajuste antes de mostrar o resultado.

## Limites

Esta skill apenas monta o plano e gera a planilha. Não cria eventos em calendário, não envia e-mails ou mensagens, e não compartilha o arquivo com ninguém.
