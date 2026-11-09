# 02 · Estrutura do servidor e mudanças de direção

🇧🇷 Português · [🇺🇸 English](#english)

## Onde estamos (novembro/2026)

O servidor do setor está organizado. A lógica é a mesma em todas as áreas: **desenvolve na Engenharia, produz pelo PCP e fatura no Financeiro**, sempre por cliente > obra > Kit e Quadro, com numeração única de cliente.

```
1-ENGENHARIA
  0-PADRÃO DESENVOLVIMENTO   arquivos-raiz de orçamento e desenvolvimento (Kit | Quadro)
  1-CLIENTES                 cliente > obra > 0-KIT | 1-QUADRO, criados a partir de uma pasta-padrão
2-PCP                        gestão de Kit e de Quadro, ordens de produção por obra, geradores de OP únicos
4-FINANCEIRO                 cliente > obra > 0-KIT | 1-QUADRO (notas, boletos e medições)
5-GESTÃO DE PROCESSOS        plano e painel de andamento, reuniões e materiais de apoio
6-ESTOQUE                    controle de estoque e inventário de Quadros
```

O que já foi feito:

- Cópia dos clientes ativos de Quadros para a estrutura nova, com a origem conferida e intacta.
- Reorganização das obras da Engenharia no padrão cliente > obra > Kit e Quadro, com backup completo, teste a seco, conferência arquivo a arquivo e teste do gerador de OP do Kit depois da mudança.
- PCP e Financeiro organizados na mesma lógica.
- Planilha de estoque e inventário de Quadros, lendo o cadastro mestre de matéria-prima.
- Plano revisado e um painel de andamento com o status de cada entrega, num caminho fixo.

## Mudanças de direção e como foram absorvidas

Em poucos dias, o plano mudou de direção várias vezes. Cada virada ficou registrada com o motivo, a forma como a gestão absorveu a mudança e o aprendizado.

1. **Estrutura paralela → Quadros dentro da estrutura do Kit.** A primeira cópia criou raízes paralelas para não arriscar o Kit. A intenção era outra: Quadros entra como complemento da estrutura que já funciona. A mudança foi absorvida a partir de um exemplo real montado pelo próprio gestor. *Aprendizado: validar o modelo mental com um exemplo concreto antes de executar.*
2. **Migrar tudo → migrar só o que está vivo.** Em vez de centenas de orçamentos e OPs desde 2022, só o que teve atividade recente foi copiado. O histórico fica consultável onde está. *Aprendizado: migração boa é a que não para a operação.*
3. **Planilha de controle → ação mais simples possível.** No lugar de uma planilha de chegada de material, a cotação é renomeada quando o material chega. *Aprendizado: começar pela ação mínima que o processo absorve e só depois automatizar.*
4. **Estoque único → cadastro mestre.** O estoque de Quadros só lê o cadastro de matéria-prima, e item é inativado, nunca excluído. *Aprendizado: evitar dois lugares que editam o mesmo dado.*
5. **Organizar → entregar.** Na reunião com a diretoria, o plano foi aprovado sem entrar no detalhe, e a conversa foi para custo, margem e equipe. A diretoria delega por confiança e cobra por resultado. O foco passou de organizar para entregar: uma obra real como piloto, o custo do setor como número de referência e um reporte curto toda semana. *Aprendizado: ajustar a comunicação a quem decide. O detalhe vai para documento, e a reunião é para decisão.*
6. **Publicar tudo → dois registros.** O registro completo fica interno, e este case recebe só o que pode ser público, aos poucos. *Aprendizado: separar o registro do case desde o início.*

### Regras que ficaram

- Copiar, nunca alterar a origem durante a transição. Nada é apagado sem confirmação.
- Backup, teste a seco, execução e conferência em toda movimentação de servidor.
- Exemplo antes da escala: uma obra modelo antes de aplicar em todas.
- Toda decisão vira registro: ata, decisão numerada, status no plano e este repositório.
- Plano em um arquivo só, com revisões numeradas, e um painel de andamento no mesmo caminho fixo.

## Próximos passos

- Primeira ordem de produção de Quadros de uma obra piloto, feita pelo processo do Kit.
- Entrada das demandas de Quadros centralizada na gestão do setor.
- Custo do setor (ponto de equilíbrio) e uma planilha de custos fixos × faturamento, mês a mês, com o resultado do setor.
- Controle de orçamentos em um lugar só, com Kit e Quadro separados e o código da obra como número do orçamento.
- Compras de Quadros conduzidas pelo setor, com alçadas e pedido no ERP da empresa.
- Contagem inicial do estoque, e teste e fotos obrigatórios em toda ordem de produção.

---

<a id="english"></a>

## 🇺🇸 Where we are (November 2026)

The department's server is organized. The logic is the same in every area: **develop in Engineering, produce through Production Planning (PCP) and invoice in Finance**, always by client > job > Kit and Panel, with a single client numbering.

```
1-ENGENHARIA (Engineering)
  0-PADRÃO DESENVOLVIMENTO   root files for budgeting and development (Kit | Panel)
  1-CLIENTES                 client > job > 0-KIT | 1-QUADRO, created from a standard folder
2-PCP (Production Planning)  Kit and Panel management, production orders per job, shared order generators
4-FINANCEIRO (Finance)       client > job > 0-KIT | 1-QUADRO (invoices, payment slips, progress billing)
5-GESTÃO DE PROCESSOS        plan and progress dashboard, meetings and support material
6-ESTOQUE (Inventory)        Panels inventory control
```

Done so far:

- Active Panels clients copied into the new structure, with the source checked and left untouched.
- Engineering jobs reorganized into client > job > Kit and Panel, with a full backup, a dry run, a file-by-file check and a test of the Kits order generator afterwards.
- Production Planning and Finance organized with the same logic.
- Panels inventory workbook, reading from the master raw-material record.
- Revised plan and a progress dashboard showing the status of each deliverable, in a fixed location.

## Changes of direction and how they were absorbed

1. **Parallel structure → Panels inside the Kits structure.** The first copy created parallel roots to avoid any risk to Kits. The real intent was different: Panels joins the structure that already works, as a complement. The change was absorbed from a real example set up by the manager. *Lesson: validate the mental model with a concrete example before executing.*
2. **Migrate everything → migrate only what is alive.** Only recently active work was copied; history stays where it is, available for reference. *Lesson: a good migration is one that does not stop operations.*
3. **Tracking spreadsheet → the simplest possible action.** Instead of a material-arrival spreadsheet, the quote file is renamed when the material arrives. *Lesson: start with the smallest action the process can absorb, and automate later.*
4. **Single inventory → master record.** Panels inventory only reads the raw-material record, and items are deactivated, never deleted. *Lesson: avoid two places that edit the same data.*
5. **Organize → deliver.** The directors approved the plan without going into detail and moved the conversation to cost, margin and team. They delegate on trust and measure on results. The focus shifted from organizing to delivering: one real job as the pilot, the department's cost as the reference number, and a short weekly report. *Lesson: adapt communication to the decision-makers. Detail goes into documents; meetings are for decisions.*
6. **Publish everything → two records.** The full record stays internal, and this case receives only what can be public, step by step. *Lesson: separate the record from the case from day one.*

### Rules that stayed

- Copy, never change the source during the transition. Nothing is deleted without confirmation.
- Backup, dry run, execution and check on every server move.
- Example before scale: one model job before applying to all.
- Every decision becomes a record: minutes, numbered decision, plan status and this repository.
- One plan file with numbered revisions, and a progress dashboard in the same fixed location.

## Next steps

- First Panels production order for a pilot job, run through the Kits process.
- Panels requests centralized in the department's management.
- Department cost (break-even point) and a fixed costs × revenue workbook, month by month, with the department's result.
- A single budget register, with Kits and Panels kept separate and the job code used as the budget number.
- Panels purchasing led by the department, with approval limits and orders in the company ERP.
- Initial inventory count, and mandatory testing and photos for every production order.
