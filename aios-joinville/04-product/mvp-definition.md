# Definição do MVP
**Data:** 2026-04-28 | **Fase:** 6 — Product

---

## Hipótese Central do MVP

> Um dentista com 1–3 cadeiras paga mensalmente por uma IA que atende 100% das ligações da clínica em PT-BR, agenda consultas e confirma presença — desde que o setup seja feito pela agência e o dentista não precise fazer nada.

**O MVP testa:** dentista paga? A qualidade da IA em PT-BR é boa o suficiente? O volume de ligações é compatível com a margem?

---

## Must-Have (o mínimo para testar a hipótese)

| Feature | Por Quê é Must-Have |
|---------|-------------------|
| Atender 100% das ligações no número da clínica | É o produto. Sem isso não há nada. |
| Responder perguntas comuns (horários, procedimentos, planos, endereço) | Paciente precisa de informação antes de agendar |
| Coletar dados para agendamento (nome, procedimento, preferência de horário) | Razão principal da ligação |
| Notificar o dentista/recepcionista sobre novo agendamento | Alguém precisa confirmar a consulta no sistema da clínica |
| Atender fora do horário comercial | É o diferencial principal — a dor número 1 do cliente |
| Transferir para humano quando necessário | Urgências, pacientes confusos, casos complexos |
| Configurado com informações específicas da clínica | Sem isso é uma IA genérica que envergonha o dentista |

---

## Fora do Escopo do MVP (v1.0)

| Feature | Por Que Fica de Fora |
|---------|---------------------|
| Integração direta com software de gestão (Clinicorp, etc.) | Complexidade técnica alta, cada clínica usa um sistema diferente |
| Confirmação/remarcação automática de consultas existentes | Requer acesso à agenda — complexidade de integração |
| Pagamento e cobrança pelo agente | Fora do escopo legal e técnico do MVP |
| Dashboard para o dentista ver métricas | Útil, não essencial para validar a hipótese |
| Agente de WhatsApp | Segundo serviço — não misturar no MVP |
| Múltiplos idiomas ou sotaques | PT-BR padrão basta para o beachhead |
| App mobile para o dentista | Complexidade desnecessária agora |

---

## Critérios de Sucesso do MVP

O MVP está validado quando:
1. Pelo menos 1 cliente pagou o setup fee + 2 meses de retainer sem pedir cancelamento
2. A IA atendeu pelo menos 50 ligações reais sem erros graves (dar informação errada, travar, não entender PT-BR)
3. O dentista fez ao menos 1 comentário positivo espontâneo sobre o resultado
4. O custo de plataforma ficou abaixo de 60% da receita do retainer daquele cliente

---

## Decisão de Arquitetura (Importante para o Setup)

**O problema do agendamento:**
A IA precisa saber quais horários estão disponíveis. Há 3 abordagens:

| Abordagem | Complexidade | Risco |
|-----------|-------------|-------|
| **Simples (MVP):** IA coleta nome, procedimento e preferência de horário → envia WhatsApp para dentista confirmar → dentista confirma com o paciente | Baixa | Depende do dentista confirmar rápido |
| **Média:** Integração com Google Calendar da clínica | Média | Dentista precisa usar Google Agenda |
| **Complexa:** Integração com Clinicorp/sistema da clínica | Alta | Cada cliente usa sistema diferente |

**Recomendação para MVP:** Abordagem Simples. A IA não confirma o horário na hora — ela coleta a intenção e dispara notificação para o dentista. É honesto com o paciente: "Vou verificar a disponibilidade e confirmar com você em breve." Resolve o problema de não perder a ligação sem exigir integração complexa.

Isso pode ser melhorado na v1.1 com integração de Google Calendar para clínicas que usam.
