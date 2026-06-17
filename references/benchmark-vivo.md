# Benchmark Vivo — Atualização de benchmarks via web search

Protocolo para buscar benchmarks **atualizados** da web antes de julgar uma conta,
em vez de usar só a tabela estática do `benchmarks-br.md`.

Use quando: o cliente **não tem meta definida** (CPL/ROAS alvo), ou quando o nicho
é incomum / não está coberto no `benchmarks-br.md`, ou numa auditoria mensal aprofundada.

Para o dia a dia (diagnóstico rápido), o `benchmarks-br.md` estático já basta — não
buscar na web em todo `/ads-ratos diagnostico`.

---

## Ordem de prioridade dos benchmarks (do mais forte pro mais fraco)

1. **Meta do cliente** (CPL/ROAS alvo definido no contas.yaml ou pelo gestor) → sempre vence
2. **Histórico da própria conta** (média dos últimos 90 dias) → segunda fonte mais confiável
3. **Benchmark vivo da web** (este protocolo) → quando não tem meta nem histórico suficiente
4. **`benchmarks-br.md` estático** (fallback) → se a busca não retornar nada útil

Sempre registrar no relatório **qual fonte foi usada**, com data.

---

## Como buscar (web search)

Rodar 1-3 buscas calibradas pelo nicho e plataforma do cliente. Queries que funcionam:

- `Google Ads benchmark Brasil [nicho] [ano atual] CPL CPC CTR`
- `custo por lead médio Google Ads [nicho] Brasil [ano atual]`
- `Meta Ads benchmark [nicho] CPM CPC Brasil [ano atual]`
- Para e-commerce: `ROAS médio Google Ads [nicho] Brasil [ano atual]`

**Calibragem geográfica:**
- Cliente BR (padrão) → valores em R$, priorizar fontes nacionais
- Se o cliente for de fora, ajustar moeda e fonte (ver tabela abaixo)

| País | Moeda | Fontes prioritárias |
|---|---|---|
| 🇧🇷 Brasil | R$ | RD Station, Rock Content, Conversion, Reportei, Safira Design, MLabs |
| 🇺🇸 EUA | US$ | WordStream/LocaliQ, HubSpot, Databox, Search Engine Land |
| 🇵🇹 Portugal | € | agências Google Partner PT, Think with Google PT |
| 🌍 Outro | local | `Google Ads benchmark [country] [industry] [year]` |

**Fontes globais sempre úteis como referência:** WordStream Google Ads Benchmarks
(anual, por setor), HubSpot Marketing Benchmarks, Think with Google, Databox.

---

## Regras ao usar benchmark vivo

1. **Citar fonte e data** no relatório. Ex: *"Benchmark: CPL R$30–80 para serviços locais
   (WordStream BR 2026 + Conversion, jun/2026)"*.
2. **Converter moeda com transparência** — se usar dado em US$, indicar a taxa e a data.
3. **Faixa, não número único** — benchmark é faixa (mín–máx), nunca um valor exato.
4. **Web vence o estático** — se a busca trouxe dado confiável e recente, ele tem
   prioridade sobre o `benchmarks-br.md`. Mas a meta do cliente sempre vence os dois.
5. **Fallback transparente** — se a busca falhar (sem rede, limite de sessão, nada
   relevante), avisar: *"Não encontrei benchmark atualizado pra [nicho], usando a
   tabela interna (benchmarks-br.md)"* e seguir com o estático.
6. **Nunca inventar número** — se não achou e não tem no estático, dizer que não tem
   referência confiável e julgar pelo histórico da própria conta.

---

## Benchmarks BR coletados (jun/2026) — Google Ads por setor

Snapshot da última atualização. Tendência geral 2025→2026: CPC subiu em ~86% dos
setores (~+5% a.a.), CPL subiu em ~13 de 23 setores. CTR médio cross-industry de
Search ficou em **3,5%–6,1%**. Revalidar via web search em auditorias.

| Setor (Google Search BR) | CPL típico | CPC típico |
|---|---|---|
| Jurídico / Advocacia | R$80–350 | R$12–25 |
| Saúde / Clínicas | R$15–80 | R$3–8 |
| Serviços profissionais | R$40–180 | — |
| Contabilidade / Financeiro | R$50–200 | R$3–10 |
| Tecnologia / SaaS B2B | R$60–280 | — |
| Indústria / Manufatura | R$30–150 | — |
| Educação | R$20–100 | — |
| Imóveis / Construtoras | R$30–120 | R$2–5 |

> Fontes: Safira Design, Conversion, WordStream 2025/2026. Valores de referência —
> o CPL real depende de criativo, landing page e histórico da conta. Para negócio
> local pequeno (raio 5–30km), o CPL costuma ficar abaixo da faixa por menor competição.
