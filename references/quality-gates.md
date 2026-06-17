# Quality Gates — Regras de Decisão para Tráfego Pago

Regras rígidas que o Claude DEVE aplicar durante diagnóstico e auditoria.
São baseadas em boas práticas do mercado e evitam erros comuns de gestão.

---

## Hierarquia de decisão (ordem obrigatória)

Antes de otimizar qualquer coisa, seguir esta ordem:

```
1. Converte?       → A campanha está gerando conversões?
2. É lucrativo?    → O CPA/ROAS está dentro da meta?
3. É escalável?    → Tem margem pra crescer (impression share, orçamento)?
4. É eficiente?    → CTR, Quality Score, desperdício estão bons?
```

**NUNCA otimize eficiência (#4) antes de resolver lucratividade (#2).**

Exemplo: não adianta melhorar Quality Score de uma campanha que não converte.

---

## Regras de parar (Kill Rules)

| Regra | Condição | Ação |
|---|---|---|
| **3x Kill Rule** | CPA > 3x a meta do cliente | Pausar imediatamente |
| **Zero conversões** | Gasto > 2x CPA meta sem nenhuma conversão | Pausar e revisar |
| **Campanha travada** | 0 impressões por 24h+ com status ativo | Investigar (orçamento, bid, aprovação) |
| **Frequência tóxica** | Prospecção > 5.0 ou Retargeting > 12.0 | Pausar ou renovar criativo |
| **CTR morto** | CTR < 50% do benchmark do nicho por 7+ dias | Trocar criativo urgente |
| **Orçamento queimando** | > 80% do orçamento diário gasto antes das 15h | Revisar programação horária |

---

## Regras de escalar

| Regra | Condição | Ação |
|---|---|---|
| **Escalar gradual** | CPA dentro da meta por 7+ dias consecutivos | Aumentar orçamento em 20-30% |
| **Nunca dobrar** | Nunca aumentar orçamento > 30% de uma vez | Sair da learning phase destrói dados |
| **Learning phase** | Meta Ads: 50 conversões/semana por ad set | Não editar durante learning phase |
| **Duplicar vencedor** | Criativo com CTR > 2x média por 7+ dias | Duplicar em novo ad set com público similar |
| **Expandir público** | ROAS > 2x meta consistente por 14+ dias | Testar públicos mais amplos (Advantage+) |

---

## Regras de otimizar

### Meta Ads

| Situação | Diagnóstico | Ação recomendada |
|---|---|---|
| CPA alto + CTR bom | Landing page não converte | Revisar LP (velocidade, copy, formulário) |
| CPA alto + CTR baixo | Criativo não engaja | Trocar criativos, testar novos ângulos |
| CPA alto + frequência alta | Público saturado | Expandir público ou pausar e esperar |
| CPM alto + público pequeno | Audiência muito estreita | Ampliar targeting, testar Advantage+ |
| CPM alto + público grande | Competição ou sazonalidade | Verificar época do ano, ajustar expectativa |
| Muitos cliques, poucas conversões | Desconexão anúncio ↔ LP | Alinhar mensagem do anúncio com a LP |
| ROAS caindo gradualmente | Fadiga de criativo ou público | Renovar criativos, testar novos públicos |

### Google Ads

| Situação | Diagnóstico | Ação recomendada |
|---|---|---|
| QS < 5 + CTR baixo | Anúncio não relevante | Reescrever headlines com keyword principal |
| QS < 5 + LP ruim | Landing page lenta ou irrelevante | Otimizar velocidade e relevância da LP |
| Search terms irrelevantes | Faltam negativas | Adicionar negativas (exata ou frase) |
| CPA alto em Broad Match | Broad sem Smart Bidding | NUNCA usar Broad Match sem Smart Bidding |
| Muitas conversões em marca | Canibalização orgânico | Reduzir bid em marca, investir em genérica |

### Impression Share — diagnóstico por causa da perda

A perda de impressão se divide em duas causas. Olhar **qual** está alta muda a ação:

| Causa | O que significa | Ação |
|---|---|---|
| **Lost IS (budget)** | Anúncio deixou de aparecer por **orçamento insuficiente** | Aumentar orçamento; OU restringir match (phrase/exact) e negativar termos de baixa intenção pra reservar verba pro que converte |
| **Lost IS (rank)** | Anúncio deixou de aparecer por **Ad Rank baixo** (QS + bid fracos) | Melhorar Quality Score (relevância do anúncio + landing page), adicionar extensões (sobem Ad Rank sem subir bid), ou usar Target Impression Share / subir bid |

Regra: **só aumentar orçamento se a perda for por budget.** Se a perda for por rank,
jogar mais verba não resolve — o problema é qualidade/bid. Conferir no Auction Insights
em nível de campanha qual das duas domina antes de recomendar.

---

## Regras de orçamento

| Regra | Plataforma | Detalhe |
|---|---|---|
| **Mínimo Meta** | Meta Ads | Orçamento diário >= 5x CPA meta por ad set |
| **Mínimo Google** | Google Ads | Orçamento diário >= 10x CPC médio por campanha |
| **Split 70/20/10** | Ambas | 70% canais comprovados, 20% escalando, 10% testes |
| **Teto de teste** | Ambas | Não gastar mais que 2x CPA meta pra testar novo criativo/público |
| **Realocar, não aumentar** | Ambas | Primeiro realocar de campanhas ruins pra boas, depois pedir mais verba |

---

## Regras de bidding

### Meta Ads

| Situação | Estratégia recomendada |
|---|---|
| Início de campanha (< 50 conversões) | Lowest cost (sem cap) |
| Campanha madura (50+ conversões/semana) | Cost cap com meta de CPA |
| Retargeting | Lowest cost (volume menor, não precisa cap) |
| Advantage+ Shopping | Lowest cost (algoritmo otimiza sozinho) |

### Google Ads

| Situação | Estratégia recomendada |
|---|---|
| < 30 conversões/mês | Maximizar conversões (sem tCPA) — junta dados rápido |
| 30-50 conversões/mês | Maximizar conversões (pode testar tCPA no fim da faixa) |
| 50+ conversões/mês | tCPA (lead) ou tROAS (e-commerce com valor variável) |
| Marca | CPC manual ou Maximizar cliques (controlar custo) |

**Thresholds de volume (Smart Bidding 2026):**
- **tCPA** precisa de **>= 30 conversões nos últimos 30 dias** na campanha pra funcionar bem
- **tROAS** precisa de **>= 50 conversões nos últimos 30 dias** (precisa de variância de valor pra aprender)
- **Maximizar conversões** é o caminho pra novas campanhas saírem da learning e juntarem os 30-50 primeiros
- **Não editar alvo durante learning** — Google recomenda ~3 semanas de runway e ~60 conversões antes de mexer no tCPA/tROAS. Mudar alvo, orçamento >20%, ou criativo reseta o aprendizado.

**Erros que destroem performance:**
- tROAS em conta com pouca conversão → algoritmo sem dados, gasto trava
- Trocar de estratégia toda semana → nunca sai da learning
- tCPA muito agressivo (abaixo do CPA histórico) → volume despenca

### Performance Max (PMax)

| Regra | Detalhe |
|---|---|
| **Asset groups** | 3 a 7 por campanha, organizados por tema de produto/serviço (não por público) |
| **Search themes** | Até 50 por asset group; derivar das keywords que mais convertem no Search |
| **Negativas** | PMax não aceita negativa em nível de campanha direto — usar negativas em nível de conta (ou pedir ao rep do Google) |
| **Brand exclusion** | Adicionar a própria marca na lista de exclusão de marca da conta pra PMax não canibalizar busca de marca; adicionar concorrentes que não quer |
| **Asset ratings** | Asset com rating "Low" → substituir. Buscar maioria "Good"/"Best" |
| **Não duplicar** | Não duplicar asset group baseado em sinal de público — não funciona mais em 2026 |
| **Início** | Começar com 1-2 asset groups foco e escalar conforme dados |

---

## Health Score — como calcular

### Fórmula

```
Score = SUM(check_pass × peso_severidade × peso_categoria) / 
        SUM(total_checks × peso_severidade × peso_categoria) × 100
```

### Pesos de severidade

| Nível | Multiplicador |
|---|---|
| CRÍTICO | 5.0 |
| ALTO | 3.0 |
| MÉDIO | 1.5 |
| BAIXO | 0.5 |

### Status de check

| Status | Pontuação |
|---|---|
| PASS | 100% dos pontos |
| ATENÇÃO | 50% dos pontos |
| FAIL | 0 |

### Notas finais

| Faixa | Nota | Significado |
|---|---|---|
| 90-100 | A | Excelente — manter e escalar |
| 75-89 | B | Bom — otimizações pontuais |
| 60-74 | C | Atenção — problemas significativos |
| 40-59 | D | Ruim — ação urgente necessária |
| < 40 | F | Crítico — parar e reestruturar |

### Categorias de auditoria e pesos (Meta Ads)

| Categoria | Peso | Checks |
|---|---|---|
| Pixel/CAPI | 30% | EMQ, dedup, eventos configurados |
| Criativos | 30% | Fadiga, diversidade, formatos |
| Estrutura | 20% | CBO vs ABO, learning phase, consolidação |
| Público/Targeting | 20% | Frequência, exclusões, tamanho |

### Categorias de auditoria e pesos (Google Ads)

| Categoria | Peso | Checks |
|---|---|---|
| Conversion Tracking | 25% | Tag, Enhanced Conversions, Consent Mode |
| Desperdício | 20% | Search terms, negativas, Broad Match |
| Estrutura | 15% | Organização, RSAs, PMax |
| Keywords | 15% | QS, canibalizacão, impression share |
| Anúncios | 15% | RSA strength, extensões, copy |
| Configurações | 10% | Bidding, pacing, schedule, localização |

---

## Limites estatísticos mínimos

Não tomar decisões sem dados suficientes:

| Gasto mensal | Nível de decisão |
|---|---|
| < R$1.000 | Só mudanças grandes (pausar/ativar campanha) |
| R$1.000-5.000 | Mudanças por campanha |
| R$5.000-25.000 | Mudanças por ad set e criativo |
| > R$25.000 | Otimização granular (horário, device, placement) |

**Regra geral**: esperar pelo menos 100 cliques ou 1x CPA meta de gasto
antes de julgar um criativo ou público.
