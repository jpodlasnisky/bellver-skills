---
name: MODELO-copie-esta-pasta
description: NÃO USE. Este é o modelo em branco para produtizar a sua skill. Copie a pasta, renomeie e apague esta linha.
---

<!--
═══════════════════════════════════════════════════════════════════════════
  MODELO DE SKILL PRODUTIZADA — Sessão 4
═══════════════════════════════════════════════════════════════════════════

  COMO USAR:
  1. Copie esta pasta para  .claude/skills/<seu-nome>-<procedimento>/
     Ex.: .claude/skills/ana-conferencia-mensal/
     (o prefixo com o seu nome evita conflito com o colega do lado)
  2. Cole o conteúdo da SUA skill da Sessão 3 nas seções abaixo.
  3. Passe pelas 6 perguntas do checklist no fim do arquivo.
  4. Apague todos os comentários como este antes do commit.

  A DIFERENÇA ENTRE A SUA SKILL DA S3 E ESTA:
  a da S3 rodava com você do lado, na sua pasta, e podia perguntar.
  esta roda às 6h da manhã, num computador na nuvem, sem você.
  Tudo que você "ia explicar na hora" precisa estar escrito aqui.
═══════════════════════════════════════════════════════════════════════════
-->

## Tarefa

<!-- Uma frase. O que esta skill entrega, no fim. -->

## Entrada

<!--
  O QUE ELA PRECISA SABER PARA COMEÇAR — e o que fazer quando não souber.
  Regra dura: uma skill que roda sozinha NÃO PODE PERGUNTAR.
  Para cada informação, escreva o padrão:
    "Se a competência não for informada, use o mês anterior e registre isso no relatório."
-->

- **<informação>:** <de onde vem> · **se faltar:** <o que assumir>

## Passos

<!-- Numerados. Caminhos SEMPRE a partir da raiz do repositório, nunca "a pasta que eu abri". -->

1.
2.
3.

## Formato da saída

<!--
  Escreva o modelo do arquivo que ela grava, com os campos entre < >.
  Onde grava: relatorios/<aaaa-mm>-<assunto>.md
  Lembre: quem vai ler não estava lá quando rodou. O relatório precisa dizer
  QUANDO rodou, O QUE leu e O QUE NÃO CONSEGUIU ler.
-->

```markdown

```

## ❗ Regras

<!--
  A parte que carrega o SEU julgamento profissional. Nenhuma IA escreve isto por você.
  Coloque a proibição mais importante na PRIMEIRA linha.
  Toda skill deste repositório precisa ter, no mínimo:
-->

- **Nunca invente um número.**
- **Nunca envie nada para ninguém.** Grave arquivo, no máximo rascunho.
- **Nunca altere arquivo em `clientes/`.**
- **Se um item falhar, registre e continue** — não derrube o resto da execução.
- **Se não houver nada a relatar, gere o relatório assim mesmo.**
- <a sua regra de julgamento nº 1>
- <a sua regra de julgamento nº 2>

---

<!--
═══════════════════════════════════════════════════════════════════════════
  ✅ CHECKLIST DE PRODUTIZAÇÃO — passe pelas 6 antes do commit
═══════════════════════════════════════════════════════════════════════════

  [ ] 1. NÃO PERGUNTA NADA.  Procure por "pergunte", "se o usuário", "confirme com".
         Cada um desses vira um padrão declarado.

  [ ] 2. CAMINHOS ABSOLUTOS AO REPO.  Nada de "a pasta atual" ou "o arquivo que abri".
         Procure por caminhos que só existem no SEU computador (C:\Users\...).

  [ ] 3. GRAVA ARQUIVO.  Se ela só escreve na tela, ninguém vai ver o resultado
         de uma execução das 6h. Onde ela grava? Com que nome?

  [ ] 4. DIZ O QUE NÃO CONSEGUIU FAZER.  Falha silenciosa é o pior defeito de uma
         rotina. O relatório precisa listar o que ficou de fora.

  [ ] 5. AGUENTA O CASO ESTRANHO.  Arquivo faltando, pasta vazia, valor ilegível,
         cliente novo que apareceu. O que ela faz em cada um?

  [ ] 6. OUTRA PESSOA CONSEGUE LER.  Dê para o colega do lado ler sem você falar nada.
         Se ele tiver que perguntar alguma coisa, essa resposta vai no arquivo.
═══════════════════════════════════════════════════════════════════════════
-->
