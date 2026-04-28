# Modelo de Receita
**Data:** 2026-04-28 | **Fase:** 7 — Financial

---

## Estrutura de Preço Definida

| Componente | Valor | Frequência |
|-----------|-------|-----------|
| Setup fee | **R$2.000** | Único por cliente |
| Retainer mensal | **R$1.000** | Mensal recorrente |

**Racional do preço:**
- R$2.000 setup: cobre ~12–15h do seu tempo na primeira entrega + margem. Também filtra clientes não-sérios.
- R$1.000 retainer: âncora contra recepcionista CLT (R$3.400/mês). Número redondo, fácil de calcular ROI. Acima do ruído (Fiverr/SaaS barato), abaixo do premium enterprise.

**Para os primeiros 2 clientes (caso de estudo):**
- Setup: R$800–1.000 (desconto em troca de depoimento em vídeo)
- Retainer: R$700/mês
- Nunca de graça — mesmo desconto já é validação de pagamento.

---

## Custo de Plataforma por Cliente (Estimativa)

Clínica odontológica pequena (1–2 cadeiras):
- Chamadas via IA estimadas: 500–1.200 min/mês (inclui pós-horário + overflow)
- Custo Retell AI: ~R$0,60–0,80/min (plano agency dilui o custo por cliente)
- Custo telefonia BR (Twilio/Zenvia): ~R$50–80/mês
- **Total plataforma por cliente: R$350–1.040/mês**

⚠️ Com retainer de R$1.000 e plataforma em R$800+, margem fica apertada para clínicas de maior volume.

**Regra operacional:** antes de ativar qualquer cliente, perguntar volume médio de chamadas. Se estimativa ultrapassar 1.000 min/mês, retainer é R$1.200–1.500 — não R$1.000.

### Margem estimada por cliente (cenário base — 700 min/mês)

| Item | Valor/mês |
|------|----------|
| Retainer recebido | R$1.000 |
| Plataforma (~700 min × R$0,70) | -R$490 |
| Telefonia BR | -R$60 |
| Seu tempo manutenção (~3h × R$50) | -R$150 |
| **Margem líquida por cliente** | **≈ R$300/mês** |
| Setup fee amortizado (R$2.000 ÷ 12) | +R$167 |
| **Margem total equivalente mês 1–12** | **≈ R$467/mês/cliente** |

---

## Projeções de Receita — Meta R$10k MRR em Dezembro/2026

### Linha do tempo de clientes

| Mês | Atividade | Clientes Ativos | MRR Retainer | Setup Fees |
|-----|-----------|----------------|-------------|-----------|
| Mai/26 | Demo pronto, início prospecção | 0 | R$0 | R$0 |
| Jun/26 | 1º cliente (caso de estudo) | 1 | R$700 | R$800 |
| Jul/26 | 2º cliente | 2 | R$1.400 | R$800 |
| Ago/26 | 3º cliente (preço cheio) | 3 | R$2.400 | R$2.000 |
| Set/26 | 4º e 5º clientes | 5 | R$4.400 | R$4.000 |
| Out/26 | 6º e 7º clientes | 7 | R$6.400 | R$4.000 |
| Nov/26 | 8º e 9º clientes | 9 | R$8.400 | R$4.000 |
| Dez/26 | 10º cliente | 10 | **R$9.400** | R$2.000 |

**Receita total dez/26 (retainer + setup): R$11.400**
**MRR recorrente puro: R$9.400** — próximo da meta de R$10k.

*[Estimate] — assume 0% de churn, ritmo de 1,5 clientes/mês após os 2 primeiros.*

---

## Análise de Sensibilidade (+/- 30%)

| Variável | Base | -30% | +30% |
|----------|------|------|------|
| Clientes em dez/26 | 10 | 7 | 13 |
| MRR dez/26 | R$9.400 | R$6.580 | R$12.220 |
| Setup fees acumulados | R$18.600 | R$13.020 | R$24.180 |
| Churn mensal | 0% | 10% | 0% |

**Com 10% de churn** (1 a cada 10 clientes sai por mês): a meta de R$10k atrasa ~2 meses — alcançaria em fevereiro/2027 ao invés de dezembro/2026.

---

## Receita Acumulada (Caixa Real — Retainer + Setup)

| Período | Receita Acumulada |
|---------|-----------------|
| Jun–Ago/26 | R$5.700 |
| Jun–Out/26 | R$16.500 |
| Jun–Dez/26 | R$37.800 |

*Isso é receita bruta — antes de descontar plataforma e tempo.*
