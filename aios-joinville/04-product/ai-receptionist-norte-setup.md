# AI Receptionist — norte.ai (demo ao vivo + vendas automáticas)
**Objetivo:** Sofia atende ligações pra norte.ai, qualifica prospects e agenda a consultoria com João automaticamente.

**Tempo total de setup:** ~1h30min  
**Custo:** R$0 pra começar (planos gratuitos de tudo)

---

## Stack

| Ferramenta | Função | Custo |
|------------|--------|-------|
| Retell AI | Agente de voz | Gratuito (trial com minutos) |
| Cal.com | Calendário + agendamento | Gratuito |
| Twilio | Número BR (opcional) | ~R$5/mês |
| Make.com | Notificação WhatsApp (opcional) | Gratuito |

---

## PASSO 1 — Cal.com (10 min)

**O que é:** sistema de agendamento com API que o Retell consegue consultar.

1. Acessa **cal.com** → cria conta gratuita com seu email
2. Clica em **"+ New Event Type"**
3. Configura:
   - **Nome:** `Consultoria Diagnóstica Norte.ai`
   - **Duração:** `20 minutos`
   - **Descrição:** `Consultoria gratuita sobre IA aplicada ao seu negócio`
4. Em **Availability**, define seus horários livres:
   - Segunda a sexta: 12:45–13:30 e 20:00–22:00
   - Sábado: 10:00–12:00
5. **Salva** e copia o link do evento (ex: `cal.com/joaofontes/norte-ai`)

### Pegar a API Key do Cal.com
1. Cal.com → Settings → Developer → **API Keys**
2. Clica em **"+ New API Key"** → copia e salva em algum lugar seguro

---

## PASSO 2 — Retell AI: criar o agente norte.ai (20 min)

1. Entra no **dashboard do Retell** (retellai.com)
2. Clica em **"+ Create Agent"**
3. Configura:
   - **Agent Name:** `Sofia — norte.ai`
   - **Voice:** Hailey (PT-BR) — mesma que você usou antes
   - **Language:** Portuguese (Brazil)

### Prompt do agente (cola isso no campo "System Prompt"):

```
Você é Sofia, assistente virtual da norte.ai — agência de Joinville que implementa inteligência artificial em clínicas e consultórios.

SEU OBJETIVO: qualificar o prospect e agendar uma consultoria gratuita de 20 minutos com o João.

PERSONA:
- Português brasileiro, tom profissional e caloroso
- Fala 20% mais devagar que o normal
- Pausa 2-3 segundos após cada pergunta — não preenche o silêncio
- Se perguntarem se você é IA: "Sou um assistente virtual, sim. O João fala diretamente na consultoria."
- Nunca menciona que é IA proativamente

---

FLUXO DA CONVERSA:

[ABERTURA]
"Olá! Você ligou pra norte.ai. Meu nome é Sofia, como posso te ajudar?"

[QUALIFICAÇÃO — se não souber o motivo]
Pergunta em sequência, uma por vez:
1. "Você é dono de clínica ou consultório?"
2. "Qual o tipo de negócio?" (odontológica, estética, veterinária...)
3. "E em qual cidade você está?"
4. "Qual é o seu nome?"

[SE QUALIFICADO — dono de negócio, qualquer cidade]
"[Nome], o João oferece uma consultoria diagnóstica gratuita de 20 minutos — ele analisa como seu negócio funciona hoje e mostra onde IA pode economizar tempo ou aumentar receita. Zero compromisso. Você teria interesse em marcar?"

[SE SIM — agendar]
Use a ferramenta check_availability para verificar os próximos horários disponíveis.
Apresenta 2 opções: "Tenho [dia] às [hora] ou [dia] às [hora]. Qual fica melhor pra você?"
Confirma nome + negócio + cidade + horário escolhido.
Use a ferramenta book_appointment para confirmar o agendamento.
"Perfeito! Você vai receber uma confirmação por email. O João vai te esperar na call. Boa semana!"

[SE NÃO QUISER AGENDAR]
"Sem problema! Se mudar de ideia, pode nos ligar de volta ou acessar norte.ai. Boa semana!"

[SE PERGUNTAR "QUANTO CUSTA?"]
"A consultoria é totalmente gratuita. Se depois fizer sentido implementar algo, o João apresenta as opções nessa mesma call."

[SE PERGUNTAR "O QUE VOCÊS FAZEM EXATAMENTE?"]
"A norte.ai implementa inteligência artificial em negócios locais — principalmente recepcionistas virtuais de voz, automações de WhatsApp e agendamento inteligente. O melhor jeito de entender é na consultoria, que é gratuita. Posso marcar pra você?"

---

REGRAS:
- Nunca menciona preço além de "gratuito" pra consultoria
- Nunca promete resultado garantido
- Se a pessoa ligar com raiva ou confusão: "Entendo, me desculpe a confusão. Posso te ajudar a falar com o João diretamente — ele vai esclarecer tudo."
- Máximo de 3 tentativas pra convencer. Se insistir em não querer: encerra educadamente.
```

---

## PASSO 3 — Conectar Cal.com ao Retell (30 min)

O Retell permite adicionar **Custom Tools** (funções que o agente chama durante a ligação).

### Tool 1: Verificar disponibilidade

No Retell → seu agente → aba **"Tools"** → **"+ Add Tool"** → escolhe **"Custom API Tool"**

Configure:
- **Tool Name:** `check_availability`
- **Description:** `Verifica os próximos horários disponíveis na agenda do João`
- **Method:** `GET`
- **URL:** `https://api.cal.com/v1/availability`
- **Headers:**
  ```
  Authorization: Bearer SUA_API_KEY_DO_CALCOM
  Content-Type: application/json
  ```
- **Parameters:**
  ```json
  {
    "dateFrom": "hoje",
    "dateTo": "daqui 7 dias",
    "eventTypeId": "ID_DO_SEU_EVENTO"
  }
  ```

> Para pegar o `eventTypeId`: Cal.com → seu evento → URL da página, tem o ID lá.

---

### Tool 2: Confirmar agendamento

**"+ Add Tool"** → **"Custom API Tool"**

- **Tool Name:** `book_appointment`
- **Description:** `Confirma o agendamento da consultoria no calendário`
- **Method:** `POST`
- **URL:** `https://api.cal.com/v1/bookings`
- **Headers:**
  ```
  Authorization: Bearer SUA_API_KEY_DO_CALCOM
  Content-Type: application/json
  ```
- **Body (parameters que o agente preenche):**
  ```json
  {
    "eventTypeId": "ID_DO_SEU_EVENTO",
    "start": "{{horario_escolhido}}",
    "name": "{{nome_do_prospect}}",
    "email": "{{email_do_prospect}}",
    "notes": "Negócio: {{tipo_negocio}} | Cidade: {{cidade}}"
  }
  ```

> **Observação:** email é opcional se você não tiver. Pode remover esse campo e depois coletar na call.

---

## PASSO 4 — Número de telefone (10 min)

### Opção A: Número US gratuito (pra demo agora)
- Retell → **Phone Numbers** → **"+ Get Phone Number"**
- Ele te dá um número americano grátis (ex: +1 555-123-4567)
- Usa esse como "número de demonstração" nas prospecções
- Custo: R$0

### Opção B: Número brasileiro (quando tiver primeiro cliente)
1. Cria conta no **Twilio** (twilio.com)
2. Compra número com DDD de Joinville (~R$5/mês)
3. Retell → Phone Numbers → **"+ Import Twilio Number"**
4. Conecta com as credenciais do Twilio

---

## PASSO 5 — Testar (10 min)

1. Liga pro número da Sofia
2. Simula ser um dentista de Joinville
3. Verifica se ela:
   - [ ] Qualifica corretamente
   - [ ] Consulta o calendário
   - [ ] Oferece 2 horários
   - [ ] Confirma o agendamento
4. Abre o Cal.com e verifica se o evento apareceu

---

## Como usar nas prospecções

### No DM/WhatsApp:
> "Se quiser ver como funciona antes da consultoria, pode ligar pro [número] — é a Sofia, nossa recepcionista de IA. Ela já agenda a call direto com você."

### No cold call:
> "Posso te mandar o número da nossa recepcionista virtual pra você testar agora mesmo — é a mesma tecnologia que implementamos em clínicas. São 2 minutos."

---

## Opcional: Notificação no WhatsApp quando alguém agendar

1. Cal.com → Settings → **Webhooks** → **"+ New Webhook"**
2. URL: Make.com webhook (cria um cenário no Make)
3. Make.com envia mensagem no seu WhatsApp pessoal:
   > "🔔 Nova consultoria marcada! [Nome] — [Negócio] — [Cidade] — [Horário]"

---

## Resumo dos custos

| Item | Custo |
|------|-------|
| Retell AI (trial) | R$0 |
| Cal.com | R$0 |
| Número US (demo) | R$0 |
| Número BR (Twilio) | ~R$5/mês |
| Make.com (notificação) | R$0 |
| **Total pra começar** | **R$0** |
