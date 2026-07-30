# Rotina — Conferência de fechamento mensal

> **Ficha da rotina.** Toda rotina da Bellver tem uma ficha aqui, versionada.
> A configuração vive na conta de quem criou; **o conhecimento vive neste arquivo.**
> Sem isto, quando a pessoa sai de férias ninguém sabe o que roda de madrugada, nem como desligar.

| Campo | Valor |
|---|---|
| **Nome da rotina** | `Bellver — conferência de fechamento` |
| **Dono** | Marina (criou e revisa) |
| **Suplente** | Rafael (sabe desligar) |
| **Quando roda** | Todo dia 5, às 07:00 de Brasília |
| **Cron (UTC)** | `0 10 5 * *` |
| **Modelo** | `claude-sonnet-5` |
| **Repositório** | `bellver-skills` |
| **Ferramentas liberadas** | `Read`, `Glob`, `Grep`, `Write`, `Bash` |
| **Conectores MCP** | nenhum |
| **Entrega** | commit de `relatorios/<aaaa-mm>-conferencia.md` |
| **Criada em** | 08/2026 |

## Por que ela existe

A conferência do fechamento era feita na correria do dia 10, junto com a entrega. Quando
aparecia uma duplicata ou um imobilizado lançado como despesa, já não havia tempo de falar
com o cliente. Rodando no dia 5, sobram cinco dias úteis para resolver.

## O prompt

> ⚠️ O agente da nuvem nasce **sem contexto nenhum**. Não sabe quem é a Bellver, não sabe o
> que é uma competência, não viu esta conversa. O prompt tem que se sustentar sozinho.

```
Você é o agente de conferência mensal da Bellver Contabilidade.

Leia o arquivo CLAUDE.md na raiz do repositório para conhecer as regras da casa
antes de qualquer coisa.

Execute o procedimento descrito em .claude/skills/conferencia-fechamento/SKILL.md,
seguindo todos os passos e todas as regras daquele arquivo.

Competência a conferir: o mês anterior ao mês atual.

Ao terminar:
1. Grave o relatório em relatorios/<aaaa-mm>-conferencia.md, no formato exato
   definido na skill.
2. Faça commit do relatório com a mensagem "conferência <mm/aaaa>".
3. Não altere nenhum outro arquivo do repositório.

Se você não conseguir ler algum cliente, isso NÃO é motivo para parar: registre a
falha como achado INFO daquele cliente e siga com os demais. Um relatório parcial
que diz o que faltou vale muito mais do que nenhum relatório.
```

## O que ela pode e não pode fazer

| Pode | Não pode |
|---|---|
| Ler tudo em `clientes/`, `normas/` e `.claude/` | Alterar qualquer arquivo em `clientes/` |
| Escrever em `relatorios/` | Escrever em qualquer outro lugar |
| Fazer commit do relatório | Enviar e-mail, mensagem ou qualquer coisa para fora |

A trava não é só a regra escrita na skill — é também a lista de **ferramentas liberadas**
na configuração da rotina. Ferramenta que não está na lista, o agente não tem. É a diferença
entre pedir para não fazer e não deixar fazer.

## Como conferir que rodou

1. Abrir o repositório e ver se existe `relatorios/<aaaa-mm>-conferencia.md` novo.
2. Não existe? Abrir https://claude.ai/code/routines e ver o histórico da execução.
3. Ler os achados `GRAVE` primeiro. São os que mexem em tributo.

## Como desligar

Em https://claude.ai/code/routines → abrir a rotina → desativar.
**Desligue antes de:** mexer na estrutura de pastas de `clientes/`, mudar o formato dos CSVs,
ou alterar a skill `conferencia-fechamento`. Religue depois de testar com uma execução manual.

## Histórico de mudanças

| Data | O que mudou | Quem |
|---|---|---|
| 08/2026 | Criada | Marina |
