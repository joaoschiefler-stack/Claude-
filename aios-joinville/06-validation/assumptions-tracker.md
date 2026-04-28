# Tracker de Premissas
**Data:** 2026-04-28 | **Fase:** 8 — Validation

Cada premissa crítica do plano — o que está assumido, como testar, status atual.

---

| # | Premissa | Confiança Atual | Como Testar | Status |
|---|---------|----------------|-------------|--------|
| 1 | Dentistas respondem a cold DM sobre voice AI | Baixa | Enviar 50 DMs, medir resposta | ⬜ Não testado |
| 2 | Qualidade PT-BR da Retell/Vapi é boa o suficiente para pacientes reais | Baixa | Experimento 1 — demo + 20 ligações de teste | ⬜ Não testado |
| 3 | Dentista paga R$1.000/mês por esse serviço | Baixa | Experimento 4 — primeiro pagamento | ⬜ Não testado |
| 4 | Clínica pequena tem ≤ 1.200 min/mês de chamadas via IA | Média | Perguntar no onboarding; medir no 1º mês | ⬜ Não testado |
| 5 | Custo de plataforma fica abaixo de 60% do retainer | Média | Calcular após 1º mês real de uso | ⬜ Não testado |
| 6 | Cliente não cancela após mês 1 | Baixa | Experimento 5 — renovação | ⬜ Não testado |
| 7 | Você consegue fechar 1,5 clientes/mês com 2h/dia | Baixa | Medir taxa de conversão no mês 1 e 2 | ⬜ Não testado |
| 8 | Demo de 60s é suficiente para gerar interesse | Baixa | Medir % de quem pediu mais info após ver demo | ⬜ Não testado |
| 9 | Make.com (gratuito) é suficiente para notificações | Alta | Testar na configuração do demo | ⬜ Não testado |
| 10 | Número BR via Twilio funciona com Retell AI sem problemas | Média | Testar no Experimento 1 | ⬜ Não testado |

---

## Premissas Mais Críticas (Se Falharem, Pivote Necessário)

**#1 + #8 (DM + Demo):** Se dentistas não responderem e não se interessarem pelo demo, o canal de aquisição inteiro está errado. Pivote: tentar WhatsApp direto, cold call, ou mudar para clínicas estéticas.

**#2 (Qualidade PT-BR):** Se a voz soa ruim em testes, o produto não existe ainda. Não prospectar até resolver.

**#3 (Disposição para pagar R$1k):** Se o máximo que aceitam é R$400–500/mês, o modelo de negócio muda significativamente — precisaria de mais clientes para atingir R$10k.

**#6 (Retenção):** Se o 1º cliente cancela no mês 2, há um problema de produto ou expectativa. Entender o motivo antes de prospectar mais.

---

## Como Atualizar Este Tracker

Após cada experimento, volte aqui e mude o status para:
- ✅ Validado — premissa confirmada com evidência
- ❌ Invalidado — premissa errada, precisa de pivô
- 🔄 Parcial — evidência mista, continuar monitorando
