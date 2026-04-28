# Análise de Risco
**Data:** 2026-04-28 | **Fase:** 8 — Validation

---

## Matriz de Risco (Probabilidade × Impacto)

| Risco | Prob | Impacto | Score | Prioridade |
|-------|------|---------|-------|-----------|
| Qualidade do PT-BR insuficiente — pacientes reclamam | Média | Alto | 🔴 Alto | #1 |
| Volume de chamadas alto demora margem | Média | Alto | 🔴 Alto | #2 |
| Dentista não renova após mês 1 | Média | Alto | 🔴 Alto | #3 |
| Cold DM sem resposta — não consegue 1º cliente | Alta | Médio | 🟠 Médio | #4 |
| Plataforma muda preço ou para de funcionar | Baixa | Alto | 🟠 Médio | #5 |
| Credibilidade — dentista pergunta idade e desiste | Média | Médio | 🟠 Médio | #6 |
| LGPD — cliente reclama de dados de pacientes | Baixa | Alto | 🟠 Médio | #7 |
| Escola + negócio — não consegue manter os dois | Média | Médio | 🟡 Baixo | #8 |
| Concorrente entra no mercado antes de você escalar | Baixa | Médio | 🟡 Baixo | #9 |

---

## Riscos de Alta Prioridade — Mitigação

### Risco #1: Qualidade do PT-BR
**Sinal de alerta precoce:** Durante testes, IA não entende palavras comuns como "canal", "clareamento", nome de planos de saúde
**Mitigação:**
- Testar com ElevenLabs PT-BR (Fernanda, Vitória — vozes nativas)
- Usar Retell AI que tem melhor infraestrutura inbound
- Criar lista de palavras comuns de odontologia e testar todas antes do go-live
- Fallback obrigatório após 2 incompreensões seguidas

### Risco #2: Volume alto destroys margem
**Sinal de alerta precoce:** Cliente menciona mais de 30 ligações/dia durante onboarding
**Mitigação:**
- Perguntar volume **antes** de fechar preço
- Fórmula: (ligações/dia × min média × 22 dias) × R$0,70 = custo plataforma
- Se > R$600/mês: retainer mínimo de R$1.400
- Incluir no contrato: "Plano inclui até 1.200 min/mês. Acima disso: R$0,80/min adicional"

### Risco #3: Churn no mês 1
**Sinal de alerta precoce:** Dentista para de responder WhatsApp na semana 2
**Mitigação:**
- Check-in ativo na semana 1 e semana 2 ("tudo ok? paciente reclamou de algo?")
- Corrigir qualquer problema em < 24h
- Coletar 1 métrica de impacto: "quantas ligações a IA atendeu que você teria perdido?"
- Mostrar esse número para o dentista antes da renovação

### Risco #4: Cold DM sem conversão
**Sinal de alerta precoce:** 100 DMs enviadas e < 5 respostas
**Mitigação:**
- Testar 3 versões diferentes de mensagem (A/B informal)
- Tentar horários diferentes (7h–9h antes de abrir a clínica; 19h–21h)
- Adicionar canal Google Maps (ligar para o número da clínica ao invés de DM)
- Testar clínicas estéticas como alternativa se dentistas não responderem

---

## Riscos de Médio Prazo

### Risco #6: Credibilidade / Idade
**Quando aparece:** Ligação de venda, reunião de onboarding
**Mitigação:** Demo resolve antes da pergunta surgir. Se perguntado: "Tenho 16 anos, mas o resultado está aqui — posso te mostrar os números da clínica X que já uso." Foco em evidência, não em justificativa.

### Risco #7: LGPD
**Mitigação:** Criar texto simples de "aviso de IA" que o dentista coloca no atendimento ("Você será atendido por nossa assistente virtual. Suas informações são protegidas conforme a LGPD."). Criar contrato básico de prestação de serviços com cláusula de processamento de dados. Não precisa ser advogado — modelo simples já reduz risco.
