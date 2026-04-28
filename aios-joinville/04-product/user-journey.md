# Jornada do Usuário
**Data:** 2026-04-28 | **Fase:** 6 — Product

---

Dois usuários distintos: o **dentista** (seu cliente) e o **paciente** (usuário final da IA). Ambos precisam ter boa experiência.

---

## Jornada do Dentista (Seu Cliente Direto)

### 1. Descoberta
- Recebe DM no Instagram ou WhatsApp
- Assiste vídeo demo de 60s
- Primeira emoção: curiosidade + ceticismo ("será que funciona mesmo?")
- **Risco de drop-off:** demo com qualidade ruim de voz ou script genérico

### 2. Consideração
- Pede mais informações / quanto custa
- Você apresenta o modelo (setup + mensalidade) com comparativo vs. recepcionista CLT
- Pode pedir para ligar para o número demo e testar ao vivo
- **Risco de drop-off:** preço sem ancoragem no custo da recepcionista; objeção "meu paciente não vai gostar de robô"

### 3. Decisão
- Fecha contrato (formal ou informal)
- Paga setup fee
- **Momento de alívio:** "alguém vai resolver isso por mim"
- **Risco:** pedido de garantia ("e se não funcionar?") — ter política clara

### 4. Onboarding
- Preenche formulário com informações da clínica (10–15 min de esforço do dentista)
- Você configura tudo (6–10h do seu lado)
- Dentista testa ligando para o número antes do go-live
- **Momento crítico:** se o dentista ligar e a IA soar estranha, confiança cai antes de lançar
- **Risco:** informações incompletas no formulário → IA dando respostas erradas

### 5. Go-Live
- Número ativo, IA atendendo chamadas reais
- **Aha moment:** dentista recebe a primeira notificação de WhatsApp — "Nova intenção de agendamento: paciente X quer fazer canal na quinta às 14h"
- Ele percebe que estava perdendo isso antes — sem qualquer esforço
- **Risco:** problema técnico nos primeiros dias destrói confiança antes de ser construída

### 6. Uso Recorrente
- Toda ligação fora do horário ou quando recepcionista está ocupada é atendida
- Dentista começa a não pensar mais nisso — simplesmente funciona
- Você faz check-ins mensais rápidos (WhatsApp: "tudo ok?")
- **Risco de churn:** IA cometer erro grave com paciente; custo subindo além do prometido; dentista achar que não vale

### 7. Expansão / Indicação
- Dentista comenta com colega de faculdade ou em grupo de WhatsApp
- Você pede depoimento em vídeo
- **Gate:** só peça depoimento depois de 30+ dias de funcionamento sem problemas graves

---

## Jornada do Paciente (Usuário Final)

### Ligação típica — paciente querendo agendar

```
Toca o telefone da clínica
↓
IA atende em 1–2 segundos
↓
"Clínica [Nome], boa tarde! Aqui é a [nome da IA]. Como posso ajudar?"
↓
Paciente: "Quero marcar uma consulta"
↓
IA: "Claro! Qual procedimento você precisa?" [coleta procedimento]
↓
IA: "Qual seu nome?" [coleta nome]
↓
IA: "Tem preferência de dia ou horário?" [coleta preferência]
↓
IA: "Perfeito. Vou verificar a disponibilidade com o Dr. [Nome] e confirmar com você em breve pelo WhatsApp ou telefone. Posso usar esse número para retornar?"
↓
Notificação automática para o dentista via WhatsApp
↓
Dentista confirma com o paciente
```

**Tempo médio da ligação:** 2–3 minutos
**Aha moment do paciente:** foi atendido imediatamente — não ficou escutando ocupado, não caiu na caixa postal

### Ligação atípica — urgência

```
Paciente: "Estou com dor muito forte"
↓
IA: "Entendo. Para emergências, vou te transferir agora para falar com alguém."
↓
[Transfere para o número do dentista ou recepcionista]
```

**Regra:** IA nunca tenta resolver urgência. Transfere imediatamente.

---

## Pontos de Risco na Experiência do Paciente

| Risco | Impacto | Mitigação |
|-------|---------|----------|
| Voz soa robótica demais | Paciente desliga, dentista envergonhado | Testar múltiplas vozes PT-BR antes de ativar; ElevenLabs tem opções melhores |
| IA não entende sotaque regional | Paciente frustrado, repete 3x | Testar com falantes nativos da cidade antes do go-live |
| IA dá informação errada (preço, plano) | Dentista perde credibilidade | Onboarding completo; revisão manual do script antes de ativar |
| IA não reconhece urgência | Paciente com dor não é atendido | Treinar keywords de urgência e fallback imediato para humano |
| IA fica em loop | Paciente desliga irritado | Configurar fallback: após 2 incompreensões seguidas, transfere para humano |
