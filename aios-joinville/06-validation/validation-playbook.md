# Playbook de Validação
**Data:** 2026-04-28 | **Fase:** 8 — Validation

Experimentos ordenados do mais barato/rápido para o mais caro. Execute nessa ordem.

---

## Experimento 1 — Demo em PT-BR funcionando
**O que testa:** A tecnologia entrega o prometido em português brasileiro?
**Como executar:**
1. Criar conta Retell AI (trial gratuito)
2. Configurar voice agent com script de clínica fictícia: horários, procedimentos comuns, coleta de agendamento
3. Adquirir número BR de teste via Twilio (trial ~R$30)
4. Ligar 20x para o número com diferentes sotaques, velocidades e tipos de pedido
5. Pedir para 3–5 pessoas de confiança ligarem e darem feedback honesto

**O que medir:** % de ligações em que a IA entendeu corretamente + agendou ou respondeu bem
**Critério de sucesso:** ≥ 80% das ligações sem erro grave
**Tempo:** 1–2 semanas | **Custo:** R$30–80
**Se falhar:** testar ElevenLabs para melhores vozes PT-BR; ajustar prompts; testar Vapi como alternativa

---

## Experimento 2 — Pitch de DM (Interesse de Mercado)
**O que testa:** Dentistas respondem a cold DM sobre esse serviço?
**Como executar:**
1. Criar lista de 50 dentistas no Instagram com telefone visível no perfil (prova de que recebem ligações)
2. Enviar DM personalizada: mencionar cidade/clínica deles, perguntar se pode mandar demo de 60s
3. Registrar: enviados / lidos / respondidos / interessados / pediram demo

**O que medir:** Taxa de resposta e taxa de interesse no demo
**Critério de sucesso:** ≥ 10% de resposta; ≥ 3 dentistas pedindo ver o demo
**Tempo:** 1 semana | **Custo:** R$0
**Se falhar:** testar mensagens alternativas; testar outro nicho (estética); revisar abordagem

---

## Experimento 3 — Demo ao Vivo (Disposição para Continuar Conversa)
**O que testa:** Depois de ver o demo, o dentista quer saber mais e discutir preço?
**Como executar:**
1. Enviar vídeo demo de 60s para os interessados do Experimento 2
2. Oferecer "posso configurar para a sua clínica como teste por 7 dias?"
3. Registrar quantos querem avançar para conversa de preço

**O que medir:** % de quem viu demo e quis continuar a conversa
**Critério de sucesso:** ≥ 1 dentista querendo discutir condições
**Tempo:** 1–2 semanas | **Custo:** R$0
**Se falhar:** o demo não está bom o suficiente — refinar qualidade da voz e script

---

## Experimento 4 — Primeiro Pagamento (Disposição para Pagar)
**O que testa:** Alguém paga pelo serviço antes de você ter histórico?
**Como executar:**
1. Oferecer setup com desconto (R$800) em troca de depoimento em vídeo após 30 dias
2. Cobrar R$700/mês de retainer pelo primeiro mês
3. Receber pagamento (via PIX para o familiar) antes de começar o setup

**O que medir:** Pagamento recebido sim/não
**Critério de sucesso:** 1 pagamento recebido
**Tempo:** semanas 3–6 | **Custo:** tempo de setup (~12h)
**Se falhar:** objeção de preço → testar R$500 setup / R$500/mês; objeção de confiança → oferecer garantia de 30 dias

---

## Experimento 5 — Entrega e Retenção (O Produto Funciona em Produção?)
**O que testa:** A IA funciona em produção com pacientes reais? O cliente renova?
**Como executar:**
1. Ativar o agente para o 1º cliente
2. Monitorar diariamente os primeiros 14 dias
3. Checar com o dentista na semana 2 e semana 4
4. No dia 25 do mês: perguntar se renova

**O que medir:** Renovação mês 2 sim/não; reclamações de pacientes sim/não; NPS informal do dentista
**Critério de sucesso:** Cliente renova sem negociação de preço
**Tempo:** 30–45 dias | **Custo:** custo de plataforma (~R$420)
**Se falhar:** identificar problema específico — voz ruim, IA errando, integração difícil — e corrigir antes de prospectar mais
