# Modelo de Negócio
**Data:** 2026-04-28 | **Fase:** 4 — Strategy

---

## Modelo de Receita

### Estrutura de Preço

| Componente | Valor | Frequência | Racional |
|-----------|-------|-----------|---------|
| Setup fee | R$1.500–2.500 | Único por cliente | Cobre seu tempo de implementação (~8–15h) + margem; cria comprometimento do cliente |
| Retainer mensal | R$800–1.200 | Mensal recorrente | Cobre plataforma + número BR + seu tempo de manutenção + margem |

**Posicionamento de preço:** Abaixo do custo de uma recepcionista CLT (R$3.400/mês), acima do ruído de Fiverr. Fácil de justificar.

### Preço de Entrada (Primeiros 3 Clientes)
Para os primeiros clientes, considerar:
- Setup fee: R$0–800 (desconto para caso de estudo)
- Retainer: R$500–700/mês
- Em troca: depoimento em vídeo + permissão para usar como case study

**Não trabalhe de graça.** Mesmo R$300/mês já é validação de que alguém pagou pelo serviço.

---

## Unit Economics (Por Cliente)

### Receita
- Setup fee (amortizado em 12 meses): +R$150–200/mês equivalente
- Retainer mensal: R$800–1.200/mês
- **Receita total equivalente/mês: R$950–1.400**

### Custos Diretos (Por Cliente/Mês)
| Item | Custo Estimado |
|------|---------------|
| Plataforma Retell/Vapi (volume médio: ~1.500 min/mês clínica pequena) | R$975–2.850 |
| Número telefônico BR (Twilio/Zenvia) | R$30–80 |
| Seu tempo de manutenção (~3–5h/mês × R$X) | Depende do que você valoriza |
| **Total custos diretos** | **R$1.005–2.930** |

⚠️ **Atenção crítica:** O custo de plataforma pode consumir toda a margem se o volume de chamadas for alto.

**Antes de fechar preço com qualquer cliente, você precisa saber:**
1. Quantas ligações a clínica recebe por mês
2. Duração média de cada ligação
3. Calcular o custo de plataforma específico para aquela clínica

**Recomendação:** Incluir uma cláusula de volume no contrato (ex: até 2.000 min/mês no plano básico; acima disso, cobrança adicional por uso).

### Break-even
Com 3 clientes pagando R$900/mês de retainer: **R$2.700 MRR** — já cobre a maioria dos custos de plataforma de todos os clientes combinados se forem clínicas pequenas.

---

## Escalabilidade

| # Clientes | MRR (retainer) | Tempo dedicado/mês | Viabilidade |
|-----------|---------------|-------------------|------------|
| 1–3 | R$800–3.600 | 3–15h | Gerenciável com 2h/dia |
| 4–8 | R$3.200–9.600 | 12–40h | Limite real com escola + 2h/dia |
| 8+ | R$6.400+ | 24h+ | Precisa de processos ou sócio |

**Gargalo real:** Seu tempo é limitado a ~2h/dia. Com processos bons (onboarding padronizado, templates de configuração), você consegue manter 5–6 clientes sozinho.

---

## Dependências e Parcerias Chave

| Dependência | Risco | Mitigação |
|-------------|-------|-----------|
| Retell AI / Vapi (infraestrutura) | Mudança de preço ou saída do mercado | Manter capacidade de migrar entre plataformas |
| Fornecedor de número BR (Twilio/Zenvia) | Disponibilidade, preço | Testar 2 fornecedores, não depender de 1 |
| Familiar para recebimento (pagamentos) | Limitação legal da menoridade | Resolver assim que possível; PIX informal tem limite de confiança |
| ElevenLabs / voice provider (TTS PT-BR) | Qualidade da voz | Testar múltiplas vozes antes de apresentar ao cliente |

---

## Red Flags

- **[Red Flag]** Se uma clínica grande tiver 200+ ligações/dia, o custo de plataforma sozinho pode ultrapassar R$3.000/mês — e você cobrou R$1.200. Sempre calcule o volume antes.
- **[Yellow Flag]** Receber via familiar funciona no início, mas limita credibilidade e escala. Investigar MEI de familiar ou conta jurídica.
