# Priorização de Features
**Data:** 2026-04-28 | **Fase:** 6 — Product

---

## MoSCoW por Versão

### Must Have — v1.0 (MVP)

| Feature | Esforço | Dependências |
|---------|---------|--------------|
| Voice agent atendendo ligações (Retell AI / Vapi) | M | Conta na plataforma |
| Número de telefone BR (+55 DDD local) | P | Twilio ou Zenvia |
| Script base: horários, endereço, procedimentos, planos | P | Informações da clínica |
| Coleta de dados para agendamento (nome, procedimento, horário preferido) | M | Script configurado |
| Notificação ao dentista via WhatsApp sobre nova intenção de agendamento | P | Make/n8n ou webhook simples |
| Transferência para humano (keypress ou frase-chave) | P | Configuração na plataforma |
| Configuração personalizada com dados da clínica específica | M | Onboarding do cliente |
| Testes de qualidade PT-BR antes de ativar | P | — |

**Legenda:** P = Pequeno (< 2h), M = Médio (2–8h), G = Grande (> 8h)

**Tempo estimado de setup por cliente: 6–12h** (primeira vez), **3–5h** (a partir do 2º, com templates)

---

### Should Have — v1.1 (após 1º cliente validado)

| Feature | Esforço | Valor |
|---------|---------|-------|
| Integração com Google Calendar (leitura de disponibilidade) | G | Alto — elimina etapa manual de confirmação |
| Confirmação automática de consulta por WhatsApp após agendamento | M | Alto — reduz no-show |
| Lembrete automático 24h antes da consulta | M | Alto — reduz no-show |
| Relatório mensal de ligações atendidas para o cliente | M | Médio — prova de valor |
| Templates de onboarding (formulário + checklist) | P | Alto — reduz seu tempo de setup |

---

### Could Have — v1.2 (com 3+ clientes)

| Feature | Esforço | Valor |
|---------|---------|-------|
| Dashboard simples para o dentista ver métricas | G | Médio — "nice to have" |
| Integração com Clinicorp / outros sistemas | XG | Alto (mas complexo demais agora) |
| Agente de WhatsApp complementar | G | Alto — mas é produto diferente |
| Análise de ligações (o que os pacientes mais perguntam) | M | Médio |

---

### Won't Have (v1.0 e v1.1)

- Pagamento via agente
- App mobile
- Multi-idioma
- CRM próprio
- Transcrição e análise de sentimento

---

## Ordem de Build (Demo → 1º Cliente → Escala)

```
Semana 1:
  [1] Criar conta Retell AI (trial)
  [2] Configurar voice agent com clínica fictícia
  [3] Comprar número BR de teste (Twilio trial)
  [4] Testar qualidade PT-BR — ligar para o próprio número

Semana 2:
  [5] Gravar vídeo demo de 60s
  [6] Refinar script com base nos testes
  [7] Começar prospecção (já tem demo funcional)

Ao fechar 1º cliente:
  [8] Formulário de onboarding (coletar: procedimentos, preços, planos, horários, nome dos dentistas)
  [9] Configurar agente com dados reais da clínica
  [10] Configurar número real (Twilio/Zenvia — número local da cidade)
  [11] Configurar notificação WhatsApp para o dentista (Make.com — plano gratuito basta no início)
  [12] Teste com chamadas reais antes de ativar
  [13] Go-live + acompanhar primeiros 7 dias de perto
```

---

## Estimativa de Esforço Total (1º Cliente)

| Etapa | Horas |
|-------|-------|
| Demo inicial (clínica fictícia) | 4–6h |
| Onboarding e configuração (cliente real) | 6–10h |
| Testes e ajustes pré-go-live | 2–4h |
| Primeiros 7 dias de monitoramento | 2–3h |
| **Total** | **14–23h** |

A ~2h/dia: primeiro cliente entregue em **7–11 dias** após fechar o contrato.
